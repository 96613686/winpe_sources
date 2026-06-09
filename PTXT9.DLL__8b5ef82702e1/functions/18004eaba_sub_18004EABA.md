# sub_18004EABA

- ea: `0x18004eaba`
- end: `0x18004eac6`
- name: `sub_18004EABA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001dcca`

## import_xrefs

- `GDI32!GetPath` at `0x18004eaba`

## pseudocode

```c
__int64 sub_18004EABA()
{
  return sub_18001DCCA();
}

```

## disassembly

```asm
0x18004eaba  lea     rax, GetPath
0x18004eac1  jmp     sub_18001DCCA
```
