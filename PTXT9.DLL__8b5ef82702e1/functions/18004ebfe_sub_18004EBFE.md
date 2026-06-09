# sub_18004EBFE

- ea: `0x18004ebfe`
- end: `0x18004ec0a`
- name: `sub_18004EBFE`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001dcca`

## import_xrefs

- `GDI32!RemoveFontResourceW` at `0x18004ebfe`

## pseudocode

```c
__int64 sub_18004EBFE()
{
  return sub_18001DCCA();
}

```

## disassembly

```asm
0x18004ebfe  lea     rax, RemoveFontResourceW
0x18004ec05  jmp     sub_18001DCCA
```
