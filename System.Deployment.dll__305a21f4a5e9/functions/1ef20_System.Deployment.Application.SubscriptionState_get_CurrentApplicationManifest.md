# System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest

- ea: `0x1ef20`
- end: `0x1ef32`
- name: `System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest`
- size: `18`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0xae50`
- `0xb170`
- `0xb2f0`
- `0x11860`
- `0x15660`
- `0x1ded0`
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
0x1ef20  ldarg.0
0x1ef21  call     instance void System.Deployment.Application.SubscriptionState::Validate()
0x1ef26  ldarg.0
0x1ef27  ldfld    class System.Deployment.Application.SubscriptionStateInternal System.Deployment.Application.SubscriptionState::state
0x1ef2c  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionStateInternal::CurrentApplicationManifest
0x1ef31  ret
```
