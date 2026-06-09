# __imp_load_CoTaskMemAlloc

- ea: `0x1800025d7`
- end: `0x1800025e3`
- name: `__imp_load_CoTaskMemAlloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002558`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800025d7`

## pseudocode

```c
__int64 load_CoTaskMemAlloc()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x1800025d7  lea     rax, __imp_CoTaskMemAlloc
0x1800025de  jmp     __tailMerge_ole32_dll
```
