# System.Printing.IndexedProperties.PrintThreadPriorityProperty::InternalDispose

- ea: `0x155f0`
- end: `0x15628`
- name: `System.Printing.IndexedProperties.PrintThreadPriorityProperty::InternalDispose`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14620`
- `0x14650`
- `0x14660`
- `0x155f0`

## pseudocode

```c

```

## disassembly

```asm
0x155f0  ldarg.0
0x155f1  call     instance bool System.Printing.IndexedProperties.PrintProperty::get_IsDisposed()
0x155f6  brtrue.s loc_15627
0x155f8  ldarg.0
0x155f9  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x155fe  ldarg.0
0x155ff  call     instance bool System.Printing.IndexedProperties.PrintProperty::get_IsDisposed()
0x15604  brtrue.s loc_15610
0x15606  ldarg.1
0x15607  brfalse.s loc_15610
0x15609  ldarg.0
0x1560a  ldnull
0x1560b  stfld    class ThreadPriorityValueChanged System.Printing.IndexedProperties.PrintThreadPriorityProperty::changeHandler
0x15610  ldarg.0
0x15611  ldarg.1
0x15612  call     instance void System.Printing.IndexedProperties.PrintProperty::InternalDispose([hasfieldmarshal] bool disposing)
0x15617  leave.s  loc_15627
0x15619  ldarg.0
0x1561a  ldc.i4.1
0x1561b  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsDisposed([hasfieldmarshal] bool disposing)
0x15620  ldarg.0
0x15621  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x15626  endfinally
0x15627  ret
```
