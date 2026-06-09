# __imp_load_WinHttpReadData

- ea: `0x180001d5f`
- end: `0x180001d6b`
- name: `__imp_load_WinHttpReadData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c86`

## import_xrefs

- `WINHTTP!WinHttpReadData` at `0x180001d5f`

## pseudocode

```c
__int64 load_WinHttpReadData()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180001d5f  lea     rax, __imp_WinHttpReadData
0x180001d66  jmp     __tailMerge_winhttp_dll
```
