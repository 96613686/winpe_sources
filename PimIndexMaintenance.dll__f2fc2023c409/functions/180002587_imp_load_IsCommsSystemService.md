# __imp_load_IsCommsSystemService

- ea: `0x180002587`
- end: `0x180002593`
- name: `__imp_load_IsCommsSystemService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800024f6`

## import_xrefs

- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x180002587`

## pseudocode

```c
__int64 load_IsCommsSystemService()
{
  return _tailMerge_userdataplatformhelperutil_dll();
}

```

## disassembly

```asm
0x180002587  lea     rax, __imp_IsCommsSystemService
0x18000258e  jmp     __tailMerge_userdataplatformhelperutil_dll
```
