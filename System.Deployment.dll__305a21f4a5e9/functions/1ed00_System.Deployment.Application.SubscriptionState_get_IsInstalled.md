# System.Deployment.Application.SubscriptionState::get_IsInstalled

- ea: `0x1ed00`
- end: `0x1ed12`
- name: `System.Deployment.Application.SubscriptionState::get_IsInstalled`
- size: `18`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0xb170`
- `0xb2f0`
- `0xba90`
- `0xc300`
- `0xd750`
- `0xe080`
- `0xf610`
- `0xf930`
- `0xfc00`
- `0x11090`
- `0x11860`
- `0x11b00`
- `0x15660`
- `0x1f1c0`
- `0x1f800`
- `0x1fad0`
- `0x1faf0`
- `0x1fbb0`
- `0x287b0`
- `0x28930`

## callees

- `0x1f030`

## pseudocode

```c

```

## disassembly

```asm
0x1ed00  ldarg.0
0x1ed01  call     instance void System.Deployment.Application.SubscriptionState::Validate()
0x1ed06  ldarg.0
0x1ed07  ldfld    class System.Deployment.Application.SubscriptionStateInternal System.Deployment.Application.SubscriptionState::state
0x1ed0c  ldfld    bool System.Deployment.Application.SubscriptionStateInternal::IsInstalled
0x1ed11  ret
```
