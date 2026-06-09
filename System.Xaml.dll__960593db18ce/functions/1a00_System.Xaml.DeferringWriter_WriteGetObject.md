# System.Xaml.DeferringWriter::WriteGetObject

- ea: `0x1a00`
- end: `0x1a0e`
- name: `System.Xaml.DeferringWriter::WriteGetObject`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1a20`

## string_xrefs

- `0x1a03`: `WriteGetObject`

## pseudocode

```c

```

## disassembly

```asm
0x1a00  ldarg.0
0x1a01  ldnull
0x1a02  ldc.i4.1
0x1a03  ldstr    aWritegetobject// "WriteGetObject"
0x1a08  call     instance void System.Xaml.DeferringWriter::WriteObject(class System.Xaml.XamlType xamlType, bool fromMember, string methodName)
0x1a0d  ret
```
