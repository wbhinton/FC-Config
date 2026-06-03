# Flight Controller Configurations

A repository to track and version control changes to flight controller configurations for iNav and Betaflight. By saving configurator CLI outputs here, we can leverage git version control to review diffs and track changes over time.

## Directory Structure

```text
├── betaflight/          # Betaflight configurations
│   ├── diffs/           # CLI `diff all` configurations per model (regular tracking)
│   └── dumps/           # Full CLI `dump` backups and binary configurations
├── inav/                # iNav configurations
│   ├── diffs/           # CLI `diff all` configurations per model (regular tracking)
│   └── dumps/           # Full CLI `dump` backups and binary configurations
└── README.md            # Repository documentation
```

## How to Track Configurations

To maintain clean history and easily trace changes, follow these guidelines:

### 1. Diffs (Recommended for Version Control)
CLI Diffs only contain settings that deviate from the defaults, making them readable and clean for tracking history.

*   Connect your quad/model to the Configurator (Betaflight or iNav).
*   Go to the **CLI** tab.
*   Type `diff all` and press Enter.
*   Click **Save to File** (or copy the text) and save it in the corresponding `diffs/` folder as `<model_name>.txt`.
*   Commit the change: `git commit -am "Update configuration for <model_name>"`

### 2. Full Dumps (Backups)
Full Dumps contain all settings, including hardware defaults. These are useful for restoration or troubleshooting, but less friendly for git history.

*   Connect to the CLI tab.
*   Type `dump` and press Enter.
*   Click **Save to File** and save it in the corresponding `dumps/` folder as `<model_name>_backup.txt`.
