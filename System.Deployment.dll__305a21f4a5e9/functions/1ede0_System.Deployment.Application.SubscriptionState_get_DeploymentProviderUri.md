# System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri

- ea: `0x1ede0`
- end: `0x1edf2`
- name: `System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri`
- size: `18`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb4c0`
- `0xb6d0`
- `0xc590`
- `0xcbe0`
- `0xe080`
- `0xf610`
- `0xfc00`
- `0x11090`
- `0x113b0`
- `0x1d970`
- `0x1dba0`
- `0x1ded0`
- `0x1e580`
- `0x1f8f0`
- `0x1f9c0`

## callees

- `0x1f030`

## pseudocode

```c

```

## disassembly

```asm
0x1ede0  ldarg.0
0x1ede1  call     instance void System.Deployment.Application.SubscriptionState::Validate()
0x1ede6  ldarg.0
0x1ede7  ldfld    class System.Deployment.Application.SubscriptionStateInternal System.Deployment.Application.SubscriptionState::state
0x1edec  ldfld    class [System]System.Uri System.Deployment.Application.SubscriptionStateInternal::DeploymentProviderUri
0x1edf1  ret
```
