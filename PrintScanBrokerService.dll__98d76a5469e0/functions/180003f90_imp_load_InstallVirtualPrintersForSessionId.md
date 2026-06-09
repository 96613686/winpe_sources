# __imp_load_InstallVirtualPrintersForSessionId

- ea: `0x180003f90`
- end: `0x180003f9c`
- name: `__imp_load_InstallVirtualPrintersForSessionId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003eff`

## import_xrefs

- `IppCommon!InstallVirtualPrintersForSessionId` at `0x180003f90`

## pseudocode

```c
__int64 load_InstallVirtualPrintersForSessionId()
{
  return _tailMerge_ippcommon_dll();
}

```

## disassembly

```asm
0x180003f90  lea     rax, __imp_InstallVirtualPrintersForSessionId
0x180003f97  jmp     __tailMerge_ippcommon_dll
```
