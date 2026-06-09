# __imp_load_SCardGetReaderIconW

- ea: `0x180002af4`
- end: `0x180002b00`
- name: `__imp_load_SCardGetReaderIconW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002955`

## import_xrefs

- `WinSCard!SCardGetReaderIconW` at `0x180002af4`

## pseudocode

```c
__int64 load_SCardGetReaderIconW()
{
  return _tailMerge_winscard_dll();
}

```

## disassembly

```asm
0x180002af4  lea     rax, __imp_SCardGetReaderIconW
0x180002afb  jmp     __tailMerge_winscard_dll
```
