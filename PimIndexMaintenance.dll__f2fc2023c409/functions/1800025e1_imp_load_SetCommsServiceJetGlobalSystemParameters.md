# __imp_load_SetCommsServiceJetGlobalSystemParameters

- ea: `0x1800025e1`
- end: `0x1800025ed`
- name: `__imp_load_SetCommsServiceJetGlobalSystemParameters`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800024f6`

## import_xrefs

- `UserDataPlatformHelperUtil!SetCommsServiceJetGlobalSystemParameters` at `0x1800025e1`

## pseudocode

```c
__int64 load_SetCommsServiceJetGlobalSystemParameters()
{
  return _tailMerge_userdataplatformhelperutil_dll();
}

```

## disassembly

```asm
0x1800025e1  lea     rax, __imp_SetCommsServiceJetGlobalSystemParameters
0x1800025e8  jmp     __tailMerge_userdataplatformhelperutil_dll
```
