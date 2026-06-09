# System.Printing.PrintQueue::CreateXpsDocumentWriter_0

- ea: `0x10350`
- end: `0x10377`
- name: `System.Printing.PrintQueue::CreateXpsDocumentWriter_0`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10390`

## callees

- `0x10350`
- `0x118b0`
- `0x119c0`

## pseudocode

```c

```

## disassembly

```asm
0x10350  ldnull
0x10351  stloc.s  4
0x10353  ldnull
0x10354  stloc.3
0x10355  ldnull
0x10356  stloc.2
0x10357  ldloca.s 4
0x10359  ldloca.s 3
0x1035b  ldloca.s 2
0x1035d  ldloca.s 1
0x1035f  ldloca.s 0
0x10361  ldarg.0
0x10362  call     bool System.Printing.PrintQueue::ShowPrintDialog([hasfieldmarshal] class System.Windows.Xps.XpsDocumentWriter& value, class [ReachFramework]System.Printing.PrintTicket& xpsDocumentWriter, class System.Printing.PrintQueue& partialTrustPrintTicket, float64& partialTrustPrintQueue, float64& width, string height)
0x10367  brfalse.s loc_10374
0x10369  ldarg.1
0x1036a  ldloc.3
0x1036b  ldloc.2
0x1036c  ldloc.1
0x1036d  ldloc.0
0x1036e  call     class System.Printing.PrintDocumentImageableArea System.Printing.PrintQueue::CalculateImagableArea(class [ReachFramework]System.Printing.PrintTicket partialTrustPrintTicket, class System.Printing.PrintQueue partialTrustPrintQueue, float64 height, float64 width)
0x10373  stind.ref
0x10374  ldloc.s  4
0x10376  ret
```
