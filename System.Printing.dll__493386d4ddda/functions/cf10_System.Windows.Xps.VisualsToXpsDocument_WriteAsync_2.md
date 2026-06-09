# System.Windows.Xps.VisualsToXpsDocument::WriteAsync_2

- ea: `0xcf10`
- end: `0xcf22`
- name: `System.Windows.Xps.VisualsToXpsDocument::WriteAsync_2`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0xced0`

## callees

- `0xd330`
- `0xd680`

## pseudocode

```c

```

## disassembly

```asm
0xcf10  ldarg.0
0xcf11  call     instance void System.Windows.Xps.VisualsToXpsDocument::VerifyAccess()
0xcf16  ldarg.0
0xcf17  ldc.i4.1
0xcf18  ldnull
0xcf19  ldc.i4.0
0xcf1a  ldarg.1
0xcf1b  call     instance bool System.Windows.Xps.VisualsToXpsDocument::WriteVisual([hasfieldmarshal] bool value, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket asyncMode, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, class [PresentationCore]System.Windows.Media.Visual printTicketLevel)
0xcf20  pop
0xcf21  ret
```
