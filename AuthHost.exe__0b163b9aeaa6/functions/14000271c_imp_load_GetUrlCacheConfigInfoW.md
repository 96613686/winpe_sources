# __imp_load_GetUrlCacheConfigInfoW

- ea: `0x14000271c`
- end: `0x140002728`
- name: `__imp_load_GetUrlCacheConfigInfoW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000269d`

## import_xrefs

- `WININET!GetUrlCacheConfigInfoW` at `0x14000271c`

## pseudocode

```c
__int64 load_GetUrlCacheConfigInfoW()
{
  return _tailMerge_wininet_dll();
}

```

## disassembly

```asm
0x14000271c  lea     rax, __imp_GetUrlCacheConfigInfoW
0x140002723  jmp     __tailMerge_wininet_dll
```
