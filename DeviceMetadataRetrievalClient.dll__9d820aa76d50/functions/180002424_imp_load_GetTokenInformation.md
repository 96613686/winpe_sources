# __imp_load_GetTokenInformation

- ea: `0x180002424`
- end: `0x180002430`
- name: `__imp_load_GetTokenInformation`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x180002424`

## pseudocode

```c
__int64 load_GetTokenInformation()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002424  lea     rax, __imp_GetTokenInformation
0x18000242b  jmp     __tailMerge_advapi32_dll
```
