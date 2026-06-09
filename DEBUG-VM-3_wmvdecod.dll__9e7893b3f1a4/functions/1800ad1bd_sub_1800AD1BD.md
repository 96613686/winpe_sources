# sub_1800AD1BD

- ea: `0x1800ad1bd`
- end: `0x1800ad1c9`
- name: `sub_1800AD1BD`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800ad13e`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!GetSystemPaletteEntries` at `0x1800ad1bd`

## pseudocode

```c
__int64 sub_1800AD1BD()
{
  return sub_1800AD13E();
}

```

## disassembly

```asm
0x1800ad1bd  lea     rax, GetSystemPaletteEntries
0x1800ad1c4  jmp     sub_1800AD13E
```
