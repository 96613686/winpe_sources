# Microsoft.VisualStudio.Setup.Cache.Instance::EnsureErrorStateInitialized

- ea: `0x1afb0`
- end: `0x1afc4`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::EnsureErrorStateInitialized`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1ad20`
- `0x1ad60`
- `0x1ae40`

## callees

- `0x19360`
- `0x1aa60`
- `0x1aa70`
- `0x1afb0`

## pseudocode

```c

```

## disassembly

```asm
0x1afb0  ldarg.0
0x1afb1  call     instance class Microsoft.VisualStudio.Setup.Cache.ErrorState Microsoft.VisualStudio.Setup.Cache.Instance::get_Errors()
0x1afb6  brtrue.s loc_1AFC3
0x1afb8  ldarg.0
0x1afb9  newobj   instance void Microsoft.VisualStudio.Setup.Cache.ErrorState::.ctor()
0x1afbe  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_Errors(class Microsoft.VisualStudio.Setup.Cache.ErrorState value)
0x1afc3  ret
```
