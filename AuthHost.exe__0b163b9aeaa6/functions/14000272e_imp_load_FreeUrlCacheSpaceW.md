# __imp_load_FreeUrlCacheSpaceW

- ea: `0x14000272e`
- end: `0x14000273a`
- name: `__imp_load_FreeUrlCacheSpaceW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000269d`

## import_xrefs

- `WININET!FreeUrlCacheSpaceW` at `0x14000272e`

## pseudocode

```c
__int64 load_FreeUrlCacheSpaceW()
{
  return _tailMerge_wininet_dll();
}

```

## disassembly

```asm
0x14000272e  lea     rax, __imp_FreeUrlCacheSpaceW
0x140002735  jmp     __tailMerge_wininet_dll
```
