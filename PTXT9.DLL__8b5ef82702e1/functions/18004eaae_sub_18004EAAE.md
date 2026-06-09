# sub_18004EAAE

- ea: `0x18004eaae`
- end: `0x18004eaba`
- name: `sub_18004EAAE`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001dcca`

## import_xrefs

- `GDI32!FlattenPath` at `0x18004eaae`

## pseudocode

```c
__int64 sub_18004EAAE()
{
  return sub_18001DCCA();
}

```

## disassembly

```asm
0x18004eaae  lea     rax, FlattenPath
0x18004eab5  jmp     sub_18001DCCA
```
