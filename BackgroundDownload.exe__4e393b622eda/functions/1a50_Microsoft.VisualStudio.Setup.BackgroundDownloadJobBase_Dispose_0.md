# Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::Dispose_0

- ea: `0x1a50`
- end: `0x1a60`
- name: `Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::Dispose_0`
- size: `16`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd70`
- `0x1a40`
- `0x2ac0`

## callees

- `0x19d0`
- `0x19e0`
- `0x1a50`

## pseudocode

```c

```

## disassembly

```asm
0x1a50  ldarg.0
0x1a51  call     instance bool Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_IsDisposed()
0x1a56  brtrue.s loc_1A5F
0x1a58  ldarg.0
0x1a59  ldc.i4.1
0x1a5a  call     instance void Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::set_IsDisposed(bool value)
0x1a5f  ret
```
