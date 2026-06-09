# __imp_load_CreateUri

- ea: `0x180002683`
- end: `0x18000268f`
- name: `__imp_load_CreateUri`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002604`

## import_xrefs

- `urlmon!CreateUri` at `0x180002683`

## pseudocode

```c
__int64 load_CreateUri()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x180002683  lea     rax, __imp_CreateUri
0x18000268a  jmp     __tailMerge_urlmon_dll
```
