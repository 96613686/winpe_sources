# __imp_load_CreatePermanentSecurityManagerHelper

- ea: `0x140002649`
- end: `0x140002655`
- name: `__imp_load_CreatePermanentSecurityManagerHelper`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400025b8`

## import_xrefs

- `urlmon!__imp_CreatePermanentSecurityManagerHelper` at `0x140002649`

## pseudocode

```c
__int64 load_CreatePermanentSecurityManagerHelper()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x140002649  lea     rax, __imp_CreatePermanentSecurityManagerHelper
0x140002650  jmp     __tailMerge_urlmon_dll
```
