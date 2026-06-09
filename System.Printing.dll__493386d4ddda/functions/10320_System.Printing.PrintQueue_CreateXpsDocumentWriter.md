# System.Printing.PrintQueue::CreateXpsDocumentWriter

- ea: `0x10320`
- end: `0x10349`
- name: `System.Printing.PrintQueue::CreateXpsDocumentWriter`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10380`

## callees

- `0x10320`
- `0x118d0`
- `0x119c0`

## pseudocode

```c

```

## disassembly

```asm
0x10320  ldnull
0x10321  stloc.s  4
0x10323  ldnull
0x10324  stloc.3
0x10325  ldnull
0x10326  stloc.2
0x10327  ldloca.s 4
0x10329  ldloca.s 3
0x1032b  ldloca.s 2
0x1032d  ldloca.s 1
0x1032f  ldloca.s 0
0x10331  ldarg.2
0x10332  ldarg.3
0x10333  ldarg.0
0x10334  call     bool System.Printing.PrintQueue::ShowPrintDialogEnablePageRange([hasfieldmarshal] class System.Windows.Xps.XpsDocumentWriter& value, class [ReachFramework]System.Printing.PrintTicket& xpsDocumentWriter, class System.Printing.PrintQueue& partialTrustPrintTicket, float64& partialTrustPrintQueue, float64& width, valuetype [PresentationFramework]System.Windows.Controls.PageRangeSelection& height, valuetype [PresentationFramework]System.Windows.Controls.PageRange& pageRangeSelection, string pageRange)
0x10339  brfalse.s loc_10346
0x1033b  ldarg.1
0x1033c  ldloc.3
0x1033d  ldloc.2
0x1033e  ldloc.1
0x1033f  ldloc.0
0x10340  call     class System.Printing.PrintDocumentImageableArea System.Printing.PrintQueue::CalculateImagableArea(class [ReachFramework]System.Printing.PrintTicket partialTrustPrintTicket, class System.Printing.PrintQueue partialTrustPrintQueue, float64 height, float64 width)
0x10345  stind.ref
0x10346  ldloc.s  4
0x10348  ret
```
