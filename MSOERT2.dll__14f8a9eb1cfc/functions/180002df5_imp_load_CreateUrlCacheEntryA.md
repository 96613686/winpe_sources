# __imp_load_CreateUrlCacheEntryA

- ea: `0x180002df5`
- end: `0x180002e01`
- name: `__imp_load_CreateUrlCacheEntryA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002d1c`

## import_xrefs

- `WININET!CreateUrlCacheEntryA` at `0x180002df5`

## pseudocode

```c
__int64 load_CreateUrlCacheEntryA()
{
  return _tailMerge_wininet_dll();
}

```

## disassembly

```asm
0x180002df5  lea     rax, __imp_CreateUrlCacheEntryA
0x180002dfc  jmp     __tailMerge_wininet_dll
```
