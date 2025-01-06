# batesste-firefly-iii

A repository for the setup and running of my personal
[Firefly-iii][ref-firefly] personal account tracking.

# Install

We use the Docker method to install and we include the [firefly-ii
data importer][ref-importer]. We also include import configs in JSON
format in the [import configs folder](./import-configs). We can use
these for the relevant bank account imports.
```
docker compose \
  -f batesste-firefly-iii.dc.yml \
  up
```
Note that the first time you do this two volumes will be created. Also
note this will register these containers to auto-start on reboot. This
is handy.

# Credentials

The first time I set this up I created an account. I do not see any
easy way to automate this. Also two docker volumes were created.

# Backups

I use [this container][ref-backup] to back these up the volumes
associated with this service on a regular daily basis to a bucket on
my [AWS S3][ref-aws-s3] account. See the [configuration
file](./.backup.env) file for configuration.

# Importing

For now I do manual imports for my CIBC and RBC accounts. I do not see
an easy way to directly access those accounts.

[ref-firefly]: https://docs.firefly-iii.org/
[ref-importer]: https://docs.firefly-iii.org/how-to/data-importer/installation/docker/
[ref-backup]: https://github.com/offen/docker-volume-backup
[ref-aws-s3]: https://aws.amazon.com/s3/
