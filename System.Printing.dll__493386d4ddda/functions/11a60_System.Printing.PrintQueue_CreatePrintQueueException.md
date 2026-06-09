# System.Printing.PrintQueue::CreatePrintQueueException

- ea: `0x11a60`
- end: `0x11a6e`
- name: `System.Printing.PrintQueue::CreatePrintQueueException`
- size: `14`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0xd960`
- `0xd9f0`
- `0xe420`
- `0xe450`
- `0xe5b0`
- `0xf710`
- `0x102b0`
- `0x11240`
- `0x11470`

## callees

- `0xe640`

## pseudocode

```c

```

## disassembly

```asm
0x11a60  ldarg.1
0x11a61  ldarg.2
0x11a62  ldarg.0
0x11a63  callvirt instance string System.Printing.PrintQueue::get_Name()
0x11a68  newobj   instance void [ReachFramework]System.Printing.PrintQueueException::.ctor(int32, string, string)
0x11a6d  ret
```
