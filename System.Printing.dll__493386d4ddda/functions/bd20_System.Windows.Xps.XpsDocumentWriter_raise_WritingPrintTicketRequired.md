# System.Windows.Xps.XpsDocumentWriter::raise_WritingPrintTicketRequired

- ea: `0xbd20`
- end: `0xbd29`
- name: `System.Windows.Xps.XpsDocumentWriter::raise_WritingPrintTicketRequired`
- size: `9`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0xbf70`
- `0xc650`

## callees

- `0xbe30`

## pseudocode

```c

```

## disassembly

```asm
0xbd20  ldarg.0
0xbd21  ldarg.1
0xbd22  ldarg.2
0xbd23  call     instance void System.Windows.Xps.XpsDocumentWriter::raise__WritingPrintTicketRequired(object sender, class [PresentationFramework]System.Windows.Documents.Serialization.WritingPrintTicketRequiredEventArgs e)
0xbd28  ret
```
