# System.Printing.IndexedProperties.PrintThreadPriorityProperty::set_Value

- ea: `0x154f0`
- end: `0x15556`
- name: `System.Printing.IndexedProperties.PrintThreadPriorityProperty::set_Value`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x15450`
- `0x154b0`

## callees

- `0x13ff0`
- `0x14580`
- `0x145c0`
- `0x145d0`
- `0x145f0`
- `0x154f0`
- `0x15560`

## pseudocode

```c

```

## disassembly

```asm
0x154f0  ldarg.1
0x154f1  castclass [mscorlib]System.Threading.ThreadPriority
0x154f6  stloc.0
0x154f7  ldloc.0
0x154f8  brfalse.s loc_15555
0x154fa  ldarg.0
0x154fb  ldfld    valuetype [mscorlib]System.Threading.ThreadPriority System.Printing.IndexedProperties.PrintThreadPriorityProperty::value
0x15500  ldloc.0
0x15501  unbox    [mscorlib]System.Threading.ThreadPriority
0x15506  ldind.i4
0x15507  beq.s    loc_15555
0x15509  ldarg.0
0x1550a  ldloc.0
0x1550b  unbox    [mscorlib]System.Threading.ThreadPriority
0x15510  ldind.i4
0x15511  stfld    valuetype [mscorlib]System.Threading.ThreadPriority System.Printing.IndexedProperties.PrintThreadPriorityProperty::value
0x15516  ldarg.0
0x15517  call     instance class ThreadPriorityValueChanged System.Printing.IndexedProperties.PrintThreadPriorityProperty::get_ChangeHandler()
0x1551c  brfalse.s loc_1552F
0x1551e  ldarg.0
0x1551f  call     instance class ThreadPriorityValueChanged System.Printing.IndexedProperties.PrintThreadPriorityProperty::get_ChangeHandler()
0x15524  ldarg.0
0x15525  ldfld    valuetype [mscorlib]System.Threading.ThreadPriority System.Printing.IndexedProperties.PrintThreadPriorityProperty::value
0x1552a  callvirt instance void ThreadPriorityValueChanged::Invoke(valuetype [mscorlib]System.Threading.ThreadPriority newValue)
0x1552f  ldarg.0
0x15530  call     instance bool System.Printing.IndexedProperties.PrintProperty::get_IsInternallyInitialized()
0x15535  brfalse.s loc_1554E
0x15537  ldarg.0
0x15538  ldc.i4.0
0x15539  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsInternallyInitialized([hasfieldmarshal] bool A_0)
0x1553e  ldarg.0
0x1553f  ldc.i4.1
0x15540  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsInitialized([hasfieldmarshal] bool setInitialized)
0x15545  ldarg.0
0x15546  ldc.i4.0
0x15547  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsDirty([hasfieldmarshal] bool setDirty)
0x1554c  br.s     loc_15555
0x1554e  ldarg.0
0x1554f  ldc.i4.1
0x15550  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsDirty([hasfieldmarshal] bool setDirty)
0x15555  ret
```
