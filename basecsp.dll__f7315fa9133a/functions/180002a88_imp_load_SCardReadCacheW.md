# __imp_load_SCardReadCacheW

- ea: `0x180002a88`
- end: `0x180002a94`
- name: `__imp_load_SCardReadCacheW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002955`

## import_xrefs

- `WinSCard!SCardReadCacheW` at `0x180002a88`

## pseudocode

```c
__int64 load_SCardReadCacheW()
{
  return _tailMerge_winscard_dll();
}

```

## disassembly

```asm
0x180002a88  lea     rax, __imp_SCardReadCacheW
0x180002a8f  jmp     __tailMerge_winscard_dll
```
