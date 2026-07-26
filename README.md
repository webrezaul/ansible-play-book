# 🚀 Ansible Playbook for Stratos DC App Server 2

A playbook and inventory configuration to automate the creation of an empty file on **App Server 2** in the **Stratos DC** infrastructure using **Ansible**.

---

## 📦 Stack / Tech Used

| Technology   | Version  | Purpose                                      |
|--------------|----------|----------------------------------------------|
| Ansible      | `v2.9+`  | Configuration management and task automation |
| YAML         | `1.2`    | Playbook serialization format                |
| SSH          | `OpenSSH`| Secure communication channel to App Server 2 |

---

## 📁 Project Structure

```
.
├── inventory            # Ansible inventory file with Stratos DC hosts
├── playbook.yml         # Playbook to create the file on App Server 2
└── README.md            # This documentation file
```

---

## ✅ Prerequisites

Before you run the playbook, make sure you have the following ready:

- **Ansible** installed on the control node.
- SSH connectivity from the control node to the Stratos DC hosts.
- Valid user credentials (`steve` for `stapp02`).

---

## 🚀 Quick Start

### 1. Clone or Copy the Files
Ensure `inventory` and `playbook.yml` are placed in your working directory (e.g., `/home/thor/ansible`).

### 2. Verify the Host Connection
You can test the connectivity to App Server 2 using Ansible's ping module:

```bash
ansible stratos -i inventory -m ping
```

### 3. Run the Playbook
Run the playbook without any extra arguments beyond the inventory definition:

```bash
ansible-playbook -i inventory playbook.yml
```

---

## 🔧 Configuration

### Stratos DC App Server Credentials

| Hostname | Host Alias     | Username | Password   | Description   |
|----------|----------------|----------|------------|---------------|
| `stapp02`| `stapp02`      | `steve`  | `Am3ric@`  | App Server 2  |

#### Inventory File Format (`/home/thor/ansible/inventory`):
```ini
[stratos]
stapp02 ansible_host=stapp02 ansible_user=steve ansible_ssh_pass=Am3ric@ ansible_connection=ssh ansible_ssh_common_args='-o StrictHostKeyChecking=no'
```

---

## 📋 Available Commands

| Command                                     | Description                                                    |
|---------------------------------------------|----------------------------------------------------------------|
| `ansible-playbook -i inventory playbook.yml`| Executes the playbook to touch `/tmp/file.txt` on App Server 2 |
| `ansible-inventory -i inventory --list`     | Lists all parsed hosts and host variables                      |
| `ansible -i inventory stratos -m ping`      | Pings App Server 2 listed in the inventory                     |

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m "Add amazing feature"`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📝 Changelog

| Version | Date       | Changes                                            |
|---------|------------|----------------------------------------------------|
| `1.0.0` | 2026-07-26 | Initial playbook and inventory file configuration  |

---

## 📄 License

MIT

---

## 👤 Author

**Rezaul Karim**
- GitHub: [@webrezaul](https://github.com/webrezaul)
- Website: [mdrezaulkarim.com](https://mdrezaulkarim.com)
