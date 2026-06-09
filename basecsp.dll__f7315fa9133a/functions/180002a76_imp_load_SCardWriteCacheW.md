# __imp_load_SCardWriteCacheW

- ea: `0x180002a76`
- end: `0x180002a82`
- name: `__imp_load_SCardWriteCacheW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002955`

## import_xrefs

- `WinSCard!SCardWriteCacheW` at `0x180002a76`

## pseudocode

```c
__int64 load_SCardWriteCacheW()
{
  return _tailMerge_winscard_dll();
}

```

## disassembly

```asm
0x180002a76  lea     rax, __imp_SCardWriteCacheW
0x180002a7d  jmp     __tailMerge_winscard_dll
```
