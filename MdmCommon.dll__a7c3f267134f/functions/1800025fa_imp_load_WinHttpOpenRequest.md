# __imp_load_WinHttpOpenRequest

- ea: `0x1800025fa`
- end: `0x180002606`
- name: `__imp_load_WinHttpOpenRequest`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002533`

## import_xrefs

- `WINHTTP!WinHttpOpenRequest` at `0x1800025fa`

## pseudocode

```c
__int64 load_WinHttpOpenRequest()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x1800025fa  lea     rax, __imp_WinHttpOpenRequest
0x180002601  jmp     __tailMerge_winhttp_dll
```
