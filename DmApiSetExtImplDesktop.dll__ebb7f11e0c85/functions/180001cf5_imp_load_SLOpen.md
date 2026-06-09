# __imp_load_SLOpen

- ea: `0x180001cf5`
- end: `0x180001d01`
- name: `__imp_load_SLOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c76`

## import_xrefs

- `sppc!SLOpen` at `0x180001cf5`

## pseudocode

```c
__int64 load_SLOpen()
{
  return _tailMerge_sppc_dll();
}

```

## disassembly

```asm
0x180001cf5  lea     rax, __imp_SLOpen
0x180001cfc  jmp     __tailMerge_sppc_dll
```
