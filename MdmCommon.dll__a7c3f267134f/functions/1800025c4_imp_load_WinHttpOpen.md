# __imp_load_WinHttpOpen

- ea: `0x1800025c4`
- end: `0x1800025d0`
- name: `__imp_load_WinHttpOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002533`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x1800025c4`

## pseudocode

```c
__int64 load_WinHttpOpen()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x1800025c4  lea     rax, __imp_WinHttpOpen
0x1800025cb  jmp     __tailMerge_winhttp_dll
```
