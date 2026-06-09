# __imp_load_InternetOpenUrlW

- ea: `0x180002dbf`
- end: `0x180002dcb`
- name: `__imp_load_InternetOpenUrlW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002d1c`

## import_xrefs

- `WININET!InternetOpenUrlW` at `0x180002dbf`

## pseudocode

```c
__int64 load_InternetOpenUrlW()
{
  return _tailMerge_wininet_dll();
}

```

## disassembly

```asm
0x180002dbf  lea     rax, __imp_InternetOpenUrlW
0x180002dc6  jmp     __tailMerge_wininet_dll
```
