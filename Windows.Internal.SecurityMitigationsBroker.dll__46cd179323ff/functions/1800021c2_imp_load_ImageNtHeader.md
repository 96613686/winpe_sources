# __imp_load_ImageNtHeader

- ea: `0x1800021c2`
- end: `0x1800021ce`
- name: `__imp_load_ImageNtHeader`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000210d`

## import_xrefs

- `imagehlp!ImageNtHeader` at `0x1800021c2`

## pseudocode

```c
__int64 load_ImageNtHeader()
{
  return _tailMerge_imagehlp_dll();
}

```

## disassembly

```asm
0x1800021c2  lea     rax, __imp_ImageNtHeader
0x1800021c9  jmp     __tailMerge_imagehlp_dll
```
