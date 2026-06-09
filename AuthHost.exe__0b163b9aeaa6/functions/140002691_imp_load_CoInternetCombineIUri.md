# __imp_load_CoInternetCombineIUri

- ea: `0x140002691`
- end: `0x14000269d`
- name: `__imp_load_CoInternetCombineIUri`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400025b8`

## import_xrefs

- `urlmon!CoInternetCombineIUri` at `0x140002691`

## pseudocode

```c
__int64 load_CoInternetCombineIUri()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x140002691  lea     rax, __imp_CoInternetCombineIUri
0x140002698  jmp     __tailMerge_urlmon_dll
```
