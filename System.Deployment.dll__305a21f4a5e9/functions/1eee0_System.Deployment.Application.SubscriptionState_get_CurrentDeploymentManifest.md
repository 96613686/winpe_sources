# System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest

- ea: `0x1eee0`
- end: `0x1eef2`
- name: `System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest`
- size: `18`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0xb4c0`
- `0xc5b0`
- `0xe080`
- `0x11860`
- `0x12a70`
- `0x139e0`
- `0x1dba0`
- `0x1e580`
- `0x1efa0`
- `0x1efe0`
- `0x1f550`
- `0x1f5f0`
- `0x1f680`

## callees

- `0x1f030`

## pseudocode

```c

```

## disassembly

```asm
0x1eee0  ldarg.0
0x1eee1  call     instance void System.Deployment.Application.SubscriptionState::Validate()
0x1eee6  ldarg.0
0x1eee7  ldfld    class System.Deployment.Application.SubscriptionStateInternal System.Deployment.Application.SubscriptionState::state
0x1eeec  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionStateInternal::CurrentDeploymentManifest
0x1eef1  ret
```
