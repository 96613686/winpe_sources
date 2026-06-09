# __imp_load_InternetOpenA

- ea: `0x180002d9b`
- end: `0x180002da7`
- name: `__imp_load_InternetOpenA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002d1c`

## import_xrefs

- `WININET!InternetOpenA` at `0x180002d9b`

## pseudocode

```c
__int64 load_InternetOpenA()
{
  return _tailMerge_wininet_dll();
}

```

## disassembly

```asm
0x180002d9b  lea     rax, __imp_InternetOpenA
0x180002da2  jmp     __tailMerge_wininet_dll
```
