# __imp_load_CreateUri

- ea: `0x1800094cb`
- end: `0x1800094d7`
- name: `__imp_load_CreateUri`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000944c`

## import_xrefs

- `urlmon!CreateUri` at `0x1800094cb`

## pseudocode

```c
__int64 load_CreateUri()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x1800094cb  lea     rax, __imp_CreateUri
0x1800094d2  jmp     __tailMerge_urlmon_dll
```
