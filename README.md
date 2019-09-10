# Mozilla/sops Circle CI Orb #

[Mozilla/Sops](https://github.com/mozilla/sops) | Orb Based on [vranystepan/sops](https://circleci.com/orbs/registry/orb/vranystepan/sops).

Orb Registry: [https://circleci.com/orbs/registry/orb/theskimm/sops](https://circleci.com/orbs/registry/orb/theskimm/sops)

## Publish ##

Initial Release

```bash
circleci orb publish sops.yaml theskimm/sops@#.#.#
```

Incremental Updates

```bash
circleci orb publish increment <path> <namespace>/<orb> <segment> [flags]
```

## Orb Quick Start Guide ##

1. Use CircleCI version 2.1 at the top of your .circleci/config.yml file.

```yaml
version: 2.1
```
If you do not already have Pipelines enabled, you'll need to go to Project Settings -> Advanced Settings and turn it on.

2. Add the orbs stanza below your version, invoking the orb:

```yaml
orbs:
  sops: theskimm/sops@0.0.1
```

3. Use sops elements in your existing workflows and jobs.

```yaml
      - sops:
          input_file_path: .env.test.circle
          output_file_path: .env.test
```

4. Opt-in to use of third-party orbs on your organization’s Security settings page.

[Read more in the docs here.](https://circleci.com/docs/2.0/using-orbs/)

## Jobs ##

### Commands ###

`aws_decrypt`

| PARAMETER             | DESCRIPTION | REQUIRED | DEFAULT                                                                  | TYPE         |
|-----------------------|-------------|----------|--------------------------------------------------------------------------|--------------|
| `aws_access_key_id`     | -           | -        | `AWS_ACCESS_KEY_ID`                                                        | `env_var_name` |
| `aws_secret_access_key` | -           | -        | `AWS_SECRET_ACCESS_KEY`                                                    | `env_var_name` |
| `input_file_path`       | -           | ✅        | -                                                                        | `string`       |
| `output_file_path`      | -           | ✅        | -                                                                        | `string`       |
| `output_type`      | --output-type $type           | ✅        | -                                                                        | `string`       |
| `sops_release_url`      | -           | -        | [https://github.com/mozilla/sops/releases/download/3.3.1/sops-3.3.1.linux](https://github.com/mozilla/sops/releases/download/3.3.1/sops-3.3.1.linux) | `string`       |
