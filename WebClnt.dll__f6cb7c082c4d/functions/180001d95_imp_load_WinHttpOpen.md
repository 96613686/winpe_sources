# __imp_load_WinHttpOpen

- ea: `0x180001d95`
- end: `0x180001da1`
- name: `__imp_load_WinHttpOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c86`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x180001d95`

## pseudocode

```c
__int64 load_WinHttpOpen()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180001d95  lea     rax, __imp_WinHttpOpen
0x180001d9c  jmp     __tailMerge_winhttp_dll
```
