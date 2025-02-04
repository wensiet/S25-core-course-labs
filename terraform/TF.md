# Terraform

## Docker infrastructure

Command `terraform state list` gives:

```bash
➜  docker_tf git:(lab-4) ✗ terraform state list
docker_container.py_app
```

Command `terraform state show docker_container.py_app` gives:

```bash
➜  docker_tf git:(lab-4) ✗ terraform state show docker_container.py_app
# docker_container.py_app:
resource "docker_container" "py_app" {
    attach                                      = false
    command                                     = [
        "/opt/app/venv/bin/python",
        "/opt/app/main.py",
    ]
    container_read_refresh_timeout_milliseconds = 15000
    cpu_shares                                  = 0
    entrypoint                                  = []
    env                                         = []
    hostname                                    = "5e87033a92b5"
    id                                          = "5e87033a92b5b85549db8683e044ce74e13ce414b7073c6bcdbc9d5cab16a004"
    image                                       = "sha256:be88791ba7c3d1234118ec7956e7de3fa57968f6088f81ce841fedb04fe081c0"
    init                                        = false
    ipc_mode                                    = "private"
    log_driver                                  = "json-file"
    logs                                        = false
    max_retry_count                             = 0
    memory                                      = 0
    memory_swap                                 = 0
    must_run                                    = true
    name                                        = "py_app"
    network_data                                = [
        {
            gateway                   = "172.17.0.1"
            global_ipv6_address       = ""
            global_ipv6_prefix_length = 0
            ip_address                = "172.17.0.2"
            ip_prefix_length          = 16
            ipv6_gateway              = ""
            mac_address               = "02:42:ac:11:00:02"
            network_name              = "bridge"
        },
    ]
    network_mode                                = "bridge"
    privileged                                  = false
    publish_all_ports                           = false
    read_only                                   = false
    remove_volumes                              = true
    restart                                     = "no"
    rm                                          = false
    runtime                                     = "runc"
    security_opts                               = []
    shm_size                                    = 64
    start                                       = true
    stdin_open                                  = false
    stop_timeout                                = 0
    tty                                         = false
    user                                        = "pydev"
    wait                                        = false
    wait_timeout                                = 60
    working_dir                                 = "/opt/app"

    ports {
        external = 8000
        internal = 8000
        ip       = "0.0.0.0"
        protocol = "tcp"
    }
}
```

Command `terraform output` gives:

```bash
➜  docker_tf git:(lab-4) ✗ terraform output
py_app_container_id = "5e87033a92b5b85549db8683e044ce74e13ce414b7073c6bcdbc9d5cab16a004"
```

