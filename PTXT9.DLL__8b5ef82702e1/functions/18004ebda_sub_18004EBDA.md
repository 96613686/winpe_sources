# sub_18004EBDA

- ea: `0x18004ebda`
- end: `0x18004ebe6`
- name: `sub_18004EBDA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001dcca`

## import_xrefs

- `GDI32!DeleteDC` at `0x18004ebda`

## pseudocode

```c
__int64 sub_18004EBDA()
{
  return sub_18001DCCA();
}

```

## disassembly

```asm
0x18004ebda  lea     rax, DeleteDC
0x18004ebe1  jmp     sub_18001DCCA
```
