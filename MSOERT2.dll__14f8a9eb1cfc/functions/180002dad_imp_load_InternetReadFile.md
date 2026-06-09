# __imp_load_InternetReadFile

- ea: `0x180002dad`
- end: `0x180002db9`
- name: `__imp_load_InternetReadFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180002d1c`

## import_xrefs

- `WININET!InternetReadFile` at `0x180002dad`

## pseudocode

```c
__int64 load_InternetReadFile()
{
  return _tailMerge_wininet_dll();
}

```

## disassembly

```asm
0x180002dad  lea     rax, __imp_InternetReadFile
0x180002db4  jmp     __tailMerge_wininet_dll
```
