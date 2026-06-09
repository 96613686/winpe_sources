# System.Printing.PrintQueueStream::CreatePrintingCanceledException

- ea: `0x19380`
- end: `0x19388`
- name: `System.Printing.PrintQueueStream::CreatePrintingCanceledException`
- size: `8`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18dc0`
- `0x18e30`
- `0x18e90`
- `0x19140`

## pseudocode

```c

```

## disassembly

```asm
0x19380  ldarg.0
0x19381  ldarg.1
0x19382  newobj   instance void [ReachFramework]System.Printing.PrintingCanceledException::.ctor(int32, string)
0x19387  ret
```
