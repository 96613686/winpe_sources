# System.Windows.Xps.VisualsToXpsDocument::WriteAsync_1

- ea: `0xcef0`
- end: `0xcf02`
- name: `System.Windows.Xps.VisualsToXpsDocument::WriteAsync_1`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0xceb0`

## callees

- `0xd330`
- `0xd680`

## pseudocode

```c

```

## disassembly

```asm
0xcef0  ldarg.0
0xcef1  call     instance void System.Windows.Xps.VisualsToXpsDocument::VerifyAccess()
0xcef6  ldarg.0
0xcef7  ldc.i4.1
0xcef8  ldarg.2
0xcef9  ldc.i4.3
0xcefa  ldarg.1
0xcefb  call     instance bool System.Windows.Xps.VisualsToXpsDocument::WriteVisual([hasfieldmarshal] bool value, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket asyncMode, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, class [PresentationCore]System.Windows.Media.Visual printTicketLevel)
0xcf00  pop
0xcf01  ret
```
