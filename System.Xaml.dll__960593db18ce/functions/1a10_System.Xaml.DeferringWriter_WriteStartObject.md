# System.Xaml.DeferringWriter::WriteStartObject

- ea: `0x1a10`
- end: `0x1a1e`
- name: `System.Xaml.DeferringWriter::WriteStartObject`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1a20`

## string_xrefs

- `0x1a13`: `WriteStartObject`

## pseudocode

```c

```

## disassembly

```asm
0x1a10  ldarg.0
0x1a11  ldarg.1
0x1a12  ldc.i4.0
0x1a13  ldstr    aWritestartobje// "WriteStartObject"
0x1a18  call     instance void System.Xaml.DeferringWriter::WriteObject(class System.Xaml.XamlType xamlType, bool fromMember, string methodName)
0x1a1d  ret
```
