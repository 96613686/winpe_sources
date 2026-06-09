# Microsoft.ReportingServices.Diagnostics.RangedParameter`1::Validate

- ea: `0x2880`
- end: `0x2917`
- name: `Microsoft.ReportingServices.Diagnostics.RangedParameter`1::Validate`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1220`
- `0x1230`
- `0x2880`

## pseudocode

```c

```

## disassembly

```asm
0x2880  ldloca.s 0
0x2882  initobj  var<u1>
0x2888  ldarg.0
0x2889  ldarg.1
0x288a  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<var<u1>>::Parse(!!T0)
0x288f  stloc.0
0x2890  ldloca.s 0
0x2892  ldarg.0
0x2893  call     instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<var<u1>>::get_MinValue()
0x2898  constrained. var<u1>
0x289e  callvirt instance int32 class [mscorlib]System.IComparable`1<var<u1>>::CompareTo(var<u1>)
0x28a3  ldc.i4.0
0x28a4  blt.s    loc_28BC
0x28a6  ldloca.s 0
0x28a8  ldarg.0
0x28a9  call     instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<var<u1>>::get_MaxValue()
0x28ae  constrained. var<u1>
0x28b4  callvirt instance int32 class [mscorlib]System.IComparable`1<var<u1>>::CompareTo(var<u1>)
0x28b9  ldc.i4.0
0x28ba  ble.s    loc_290D
0x28bc  ldarg.0
0x28bd  call     instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ApplicationParameter::get_Tracer()
0x28c2  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x28c7  brfalse.s loc_2908
0x28c9  ldarg.0
0x28ca  call     instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ApplicationParameter::get_Tracer()
0x28cf  ldstr    aValue0OfParame// "Value '{0}' of parameter {1} is out of "...
0x28d4  ldc.i4.4
0x28d5  newarr   [mscorlib]System.Object
0x28da  dup
0x28db  ldc.i4.0
0x28dc  ldarg.1
0x28dd  stelem.ref
0x28de  dup
0x28df  ldc.i4.1
0x28e0  ldarg.0
0x28e1  call     instance string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::get_ConfigValue()
0x28e6  stelem.ref
0x28e7  dup
0x28e8  ldc.i4.2
0x28e9  ldarg.0
0x28ea  call     instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<var<u1>>::get_MinValue()
0x28ef  box      var<u1>
0x28f4  stelem.ref
0x28f5  dup
0x28f6  ldc.i4.3
0x28f7  ldarg.0
0x28f8  call     instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<var<u1>>::get_MaxValue()
0x28fd  box      var<u1>
0x2902  stelem.ref
0x2903  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x2908  ldarg.2
0x2909  ldnull
0x290a  stind.ref
0x290b  ldc.i4.0
0x290c  ret
0x290d  ldarg.2
0x290e  ldloc.0
0x290f  box      var<u1>
0x2914  stind.ref
0x2915  ldc.i4.1
0x2916  ret
```
