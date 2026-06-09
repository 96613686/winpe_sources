# __imp_load_WinHttpOpen

- ea: `0x180002471`
- end: `0x18000247d`
- name: `__imp_load_WinHttpOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800022a1`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x180002471`

## pseudocode

```c
__int64 load_WinHttpOpen()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180002471  lea     rax, __imp_WinHttpOpen
0x180002478  jmp     __tailMerge_winhttp_dll
```
