# __imp_load_WinHttpOpenRequest

- ea: `0x180002495`
- end: `0x1800024a1`
- name: `__imp_load_WinHttpOpenRequest`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800022a1`

## import_xrefs

- `WINHTTP!WinHttpOpenRequest` at `0x180002495`

## pseudocode

```c
__int64 load_WinHttpOpenRequest()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180002495  lea     rax, __imp_WinHttpOpenRequest
0x18000249c  jmp     __tailMerge_winhttp_dll
```
