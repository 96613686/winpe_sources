# __imp_load_CreateUri

- ea: `0x14000266d`
- end: `0x140002679`
- name: `__imp_load_CreateUri`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400025b8`

## import_xrefs

- `urlmon!CreateUri` at `0x14000266d`

## pseudocode

```c
__int64 load_CreateUri()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x14000266d  lea     rax, __imp_CreateUri
0x140002674  jmp     __tailMerge_urlmon_dll
```
