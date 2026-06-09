# __imp_load_RunServicesInProc

- ea: `0x1800025bd`
- end: `0x1800025c9`
- name: `__imp_load_RunServicesInProc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800024f6`

## import_xrefs

- `UserDataPlatformHelperUtil!RunServicesInProc` at `0x1800025bd`

## pseudocode

```c
__int64 load_RunServicesInProc()
{
  return _tailMerge_userdataplatformhelperutil_dll();
}

```

## disassembly

```asm
0x1800025bd  lea     rax, __imp_RunServicesInProc
0x1800025c4  jmp     __tailMerge_userdataplatformhelperutil_dll
```
