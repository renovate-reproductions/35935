# Reproduction of: https://github.com/renovatebot/renovate/discussions/35935


## Current behavior

Running renovate causing yarn artifact issues:

```
DEBUG: Executing command (repository=gregory-hive/renovate-minimal-reproduction-35935, branch=renovate/apollo-server-4.x)
       "command": "yarn install --ignore-engines --ignore-platform --network-timeout 100000 --ignore-scripts"
DEBUG: rawExec err (repository=gregory-hive/renovate-minimal-reproduction-35935, branch=renovate/apollo-server-4.x)
       "err": {
         "cmd": "/bin/sh -c yarn install --ignore-engines --ignore-platform --network-timeout 100000 --ignore-scripts",
         "stderr": "",
         "stdout": "Unknown Syntax Error: Unsupported option name (\"--ignore-platform\").\n\n$ yarn install [--json] [--immutable] [--immutable-cache] [--refresh-lockfile] [--check-cache] [--check-resolutions] [--inline-builds] [--mode #0]\n",
         "options": {
           "cwd": "/tmp/renovate/repos/github/gregory-hive/renovate-minimal-reproduction-35935",
           "encoding": "utf-8",
           "env": {
             "NPM_CONFIG_CACHE": "/tmp/renovate/cache/others/npm",
             "npm_config_store": "/tmp/renovate/cache/others/pnpm",
             "CI": "true",
             "YARN_CACHE_FOLDER": "/tmp/renovate/cache/others/yarn",
             "HOME": "/root",
             "PATH": "/home/ubuntu/.local/bin:/home/ubuntu/bin:/home/ubuntu/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
             "LC_ALL": "C.UTF-8",
             "LANG": "C.UTF-8"
           },
           "maxBuffer": 10485760,
           "timeout": 900000
         },
         "exitCode": 1,
         "name": "ExecError",
         "message": "Command failed: yarn install --ignore-engines --ignore-platform --network-timeout 100000 --ignore-scripts\n",
         "stack": "ExecError: Command failed: yarn install --ignore-engines --ignore-platform --network-timeout 100000 --ignore-scripts\n\n    at ChildProcess.<anonymous> (/usr/local/renovate/lib/util/exec/common.ts:120:11)\n    at ChildProcess.emit (node:events:530:35)\n    at ChildProcess.emit (node:domain:489:12)\n    at Process.ChildProcess._handle.onexit (node:internal/child_process:293:12)"
       },
       "durationMs": 2295
DEBUG: lock file error (repository=gregory-hive/renovate-minimal-reproduction-35935, branch=renovate/apollo-server-4.x)
       "err": {
         "cmd": "/bin/sh -c yarn install --ignore-engines --ignore-platform --network-timeout 100000 --ignore-scripts",
         "stderr": "",
         "stdout": "Unknown Syntax Error: Unsupported option name (\"--ignore-platform\").\n\n$ yarn install [--json] [--immutable] [--immutable-cache] [--refresh-lockfile] [--check-cache] [--check-resolutions] [--inline-builds] [--mode #0]\n",
         "options": {
           "cwd": "/tmp/renovate/repos/github/gregory-hive/renovate-minimal-reproduction-35935",
           "encoding": "utf-8",
           "env": {
             "NPM_CONFIG_CACHE": "/tmp/renovate/cache/others/npm",
             "npm_config_store": "/tmp/renovate/cache/others/pnpm",
             "CI": "true",
             "YARN_CACHE_FOLDER": "/tmp/renovate/cache/others/yarn",
             "HOME": "/root",
             "PATH": "/home/ubuntu/.local/bin:/home/ubuntu/bin:/home/ubuntu/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
             "LC_ALL": "C.UTF-8",
             "LANG": "C.UTF-8"
           },
           "maxBuffer": 10485760,
           "timeout": 900000
         },
         "exitCode": 1,
         "name": "ExecError",
         "message": "Command failed: yarn install --ignore-engines --ignore-platform --network-timeout 100000 --ignore-scripts\n",
         "stack": "ExecError: Command failed: yarn install --ignore-engines --ignore-platform --network-timeout 100000 --ignore-scripts\n\n    at ChildProcess.<anonymous> (/usr/local/renovate/lib/util/exec/common.ts:120:11)\n    at ChildProcess.emit (node:events:530:35)\n    at ChildProcess.emit (node:domain:489:12)\n    at Process.ChildProcess._handle.onexit (node:internal/child_process:293:12)"
       },
       "type": "yarn"
```



## Expected behavior

Renovate creates PRs for yarn dependencies. 

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/35935
