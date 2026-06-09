# Microsoft.ReportingServices.Portal.Services.DataService::CheckRequiredDataSetParameters

- ea: `0x9800`
- end: `0x9892`
- name: `Microsoft.ReportingServices.Portal.Services.DataService::CheckRequiredDataSetParameters`
- size: `146`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x91c0`
- `0x92e0`
- `0x93c0`
- `0x9450`

## callees

- `0x9800`
- `0x20470`

## pseudocode

```c

```

## disassembly

```asm
0x9800  newobj   instance void <>c__DisplayClass24_0::.ctor()
0x9805  stloc.0
0x9806  ldarg.0
0x9807  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameterInfo> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema::get_Parameters()
0x980c  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameterInfo, bool> <>c::<>9__24_0
0x9811  dup
0x9812  brtrue.s loc_982B
0x9814  pop
0x9815  ldsfld   class <>c <>c::<>9
0x981a  ldftn    instance bool <>c::<CheckRequiredDataSetParameters>b__24_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameterInfo x)
0x9820  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameterInfo, bool>::.ctor(object, native int)
0x9825  dup
0x9826  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameterInfo, bool> <>c::<>9__24_0
0x982b  call     T0x2B000090
0x9830  stloc.1
0x9831  ldloc.1
0x9832  call     T0x2B00008B
0x9837  brtrue.s loc_983A
0x9839  ret
0x983a  ldloc.0
0x983b  ldarg.1
0x983c  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter, bool> <>c::<>9__24_1
0x9841  dup
0x9842  brtrue.s loc_985B
0x9844  pop
0x9845  ldsfld   class <>c <>c::<>9
0x984a  ldftn    instance bool <>c::<CheckRequiredDataSetParameters>b__24_1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter x)
0x9850  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter, bool>::.ctor(object, native int)
0x9855  dup
0x9856  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter, bool> <>c::<>9__24_1
0x985b  call     T0x2B000091
0x9860  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> <>c__DisplayClass24_0::overriden
0x9865  ldloc.1
0x9866  ldloc.0
0x9867  ldftn    instance bool <>c__DisplayClass24_0::<CheckRequiredDataSetParameters>b__2(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameterInfo m)
0x986d  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameterInfo, bool>::.ctor(object, native int)
0x9872  call     T0x2B000090
0x9877  stloc.2
0x9878  ldloc.2
0x9879  call     T0x2B00008B
0x987e  brfalse.s loc_9891
0x9880  ldloc.2
0x9881  call     T0x2B000092
0x9886  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameterInfo::get_Name()
0x988b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.DataSetParameterValueNotSetException::.ctor(string)
0x9890  throw
0x9891  ret
```
