# __imp_load_SafeArrayCreateVector

- ea: `0x180008b10`
- end: `0x180008b1c`
- name: `__imp_load_SafeArrayCreateVector`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008940`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180008b10`

## pseudocode

```c
__int64 load_SafeArrayCreateVector()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x180008b10  lea     rax, __imp_SafeArrayCreateVector
0x180008b17  jmp     __tailMerge_oleaut32_dll
```
