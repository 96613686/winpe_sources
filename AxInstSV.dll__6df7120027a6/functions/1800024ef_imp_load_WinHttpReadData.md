# __imp_load_WinHttpReadData

- ea: `0x1800024ef`
- end: `0x1800024fb`
- name: `__imp_load_WinHttpReadData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800022a1`

## import_xrefs

- `WINHTTP!WinHttpReadData` at `0x1800024ef`

## pseudocode

```c
__int64 load_WinHttpReadData()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x1800024ef  lea     rax, __imp_WinHttpReadData
0x1800024f6  jmp     __tailMerge_winhttp_dll
```
