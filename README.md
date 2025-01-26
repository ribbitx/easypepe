# EasyPepe API System

EasyPepe is a robust, open-source API system built exclusively for the Pepecoin blockchain. It simplifies blockchain development by providing developers with seamless integration capabilities. This document serves as the complete guide to installing, configuring, and using EasyPepe.

---

## Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [System Requirements](#system-requirements)
4. [Installation](#installation)
5. [Configuration](#configuration)
6. [Usage](#usage)
7. [API Endpoints](#api-endpoints)
8. [Advanced Configuration](#advanced-configuration)
9. [Troubleshooting](#troubleshooting)
10. [Contributing](#contributing)
11. [License](#license)

---

## Overview

EasyPepe provides a set of APIs for interacting with the Pepecoin blockchain. It uses RPC information provided by users to communicate with the blockchain network. The system is lightweight, efficient, and built for both beginner and advanced developers.

- **Default Port:** 4555
- **Customizable:** Port and RPC details are user-configurable.
- **Local Hosting:** The core system must be hosted locally to ensure security and reliability.

---

## Features

| Feature                  | Description                                                |
|--------------------------|------------------------------------------------------------|
| Easy Installation        | Simple setup with automatic dependency management.         |
| Secure                  | Supports encrypted communication for RPC interactions.      |
| Flexible Configuration  | Allows custom port and RPC setup.                           |
| Comprehensive API        | Offers endpoints for transactions, blocks, accounts, etc.  |
| Local Hosting            | Ensures data security by running the core locally.         |
| Open Source             | Completely transparent and community-driven.                |

---

## System Requirements

| Component                | Minimum Requirement                                       |
|--------------------------|-----------------------------------------------------------|
| Operating System         | Linux, Windows, or macOS                                  |
| Python Version           | 3.8 or higher                                             |
| Pepecoin Node            | Fully synchronized Pepecoin node with RPC enabled         |
| Memory                   | 4 GB RAM or higher                                        |
| Storage                  | 20 GB free disk space                                     |

---

## Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/pepecoin/easypepe-api.git
   cd easypepe-api
   ```

2. **Create a Virtual Environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate   # For Linux/Mac
   venv\Scripts\activate     # For Windows
   ```

3. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Setup Script**

   The setup script collects RPC details and creates a configuration file.

   ```bash
   python setup.py
   ```

   During setup, you will be prompted to enter:
   - RPC URL
   - RPC Username
   - RPC Password
   - Preferred API Port (default is 4555)

5. **Start the API**

   ```bash
   python main.py
   ```

---

## Configuration

EasyPepe generates a `config.json` file during setup. Below is an example of the configuration file:

```json
{
  "rpc": {
    "url": "http://127.0.0.1:8332",
    "username": "user",
    "password": "password"
  },
  "port": 4555
}
```

### Modifying Configuration

You can manually edit the `config.json` file to update RPC details or change the API port.

---

## Usage

Once the API is running, it can be accessed at:

```
http://localhost:4555
```

### Example API Call

To retrieve blockchain information:

```bash
curl -X GET http://localhost:4555/api/blockchain/info
```

Expected Response:

```json
{
  "chain": "main",
  "blocks": 700000,
  "difficulty": 1234567.890
}
```

---

## API Endpoints

| Endpoint                 | Method   | Description                                    |
|--------------------------|----------|------------------------------------------------|
| `/api/blockchain/info`   | GET      | Retrieves blockchain information.             |
| `/api/transactions/send` | POST     | Broadcasts a new transaction.                 |
| `/api/account/balance`   | GET      | Retrieves the balance of a specific address.  |
| `/api/block/{hash}`      | GET      | Retrieves details of a specific block.        |

For a full list of endpoints, refer to the [API Documentation](docs/api.md).

---

## Advanced Configuration

### Environment Variables

You can override `config.json` settings using environment variables:

| Variable                 | Description                                    |
|--------------------------|------------------------------------------------|
| `EASYPEPE_RPC_URL`       | RPC URL for the Pepecoin node.                |
| `EASYPEPE_RPC_USER`      | Username for RPC authentication.              |
| `EASYPEPE_RPC_PASS`      | Password for RPC authentication.              |
| `EASYPEPE_PORT`          | Port number for the API.                      |

### Example

```bash
export EASYPEPE_RPC_URL=http://127.0.0.1:8332
export EASYPEPE_RPC_USER=user
export EASYPEPE_RPC_PASS=password
export EASYPEPE_PORT=8080
python main.py
```

---

## Troubleshooting

| Issue                    | Possible Solution                                |
|--------------------------|-------------------------------------------------|
| API not starting         | Ensure `config.json` has valid RPC credentials. |
| Connection refused       | Verify the Pepecoin node is running and RPC is enabled. |
| Port conflict            | Change the port in `config.json` or use `EASYPEPE_PORT`. |

---

## Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Submit a pull request.

For more details, refer to [CONTRIBUTING.md](CONTRIBUTING.md).

---

## License

EasyPepe is licensed under the [MIT License](LICENSE).

---

Start building on the Pepecoin blockchain today with EasyPepe! 🚀

