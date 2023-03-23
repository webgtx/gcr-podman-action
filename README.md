<div align=center>

# Featureful google container registry action 🏗
Build and Push your images securly with lightweight podman
  
</div>

## Github Action Inputs

| Variable                         | Description                                                                   |
|----------------------------------|-------------------------------------------------------------------------------|
| `access_token`                   | ***Required*** Service Account JSON Key (base64 encoded) or oauth Access Token|
| `auth_type`                      | Authetication Type `oauth2` or `jsonkey`, default "jsonkey"                   |
| `project_id`                     | ***Required*** Project Name                                                   |
| `host`                           |  Registry host name, default: "gcr.io"                                        |
| `image_id`                       | ***Required*** Image name with tag                                            |

## Example usage
```yml
- uses: webgtx/gcr-podman-action@v2.0
  with:
    project_id: init64
    image_id: webgtx-blog:latest
    access_token: ${{ secrets.GOOGLE_JSON_KEY }}
```

## Why podman
Podman allows for non-root privileges for containers.Rootless containers are considered safer than containers with root privileges.
In Docker, daemons have root privileges, making them the preferred gateway for attackers. Containers in Podman do not have root access by default,
adding a natural barrier between root and rootless levels, improving security. Still, Podman can run both root and rootless containers.
