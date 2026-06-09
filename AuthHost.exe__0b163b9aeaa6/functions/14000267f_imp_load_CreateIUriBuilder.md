# __imp_load_CreateIUriBuilder

- ea: `0x14000267f`
- end: `0x14000268b`
- name: `__imp_load_CreateIUriBuilder`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400025b8`

## import_xrefs

- `urlmon!CreateIUriBuilder` at `0x14000267f`

## pseudocode

```c
__int64 load_CreateIUriBuilder()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x14000267f  lea     rax, __imp_CreateIUriBuilder
0x140002686  jmp     __tailMerge_urlmon_dll
```
