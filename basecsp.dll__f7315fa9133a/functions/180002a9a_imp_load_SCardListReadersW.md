# __imp_load_SCardListReadersW

- ea: `0x180002a9a`
- end: `0x180002aa6`
- name: `__imp_load_SCardListReadersW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002955`

## import_xrefs

- `WinSCard!SCardListReadersW` at `0x180002a9a`

## pseudocode

```c
__int64 load_SCardListReadersW()
{
  return _tailMerge_winscard_dll();
}

```

## disassembly

```asm
0x180002a9a  lea     rax, __imp_SCardListReadersW
0x180002aa1  jmp     __tailMerge_winscard_dll
```
