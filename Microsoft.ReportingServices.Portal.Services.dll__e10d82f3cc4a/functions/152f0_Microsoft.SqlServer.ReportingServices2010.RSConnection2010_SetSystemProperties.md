# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetSystemProperties

- ea: `0x152f0`
- end: `0x15322`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetSystemProperties`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x238c0`

## string_xrefs

- `0x15305`: `SetSystemProperties`

## pseudocode

```c

```

## disassembly

```asm
0x152f0  newobj   instance void <>c__DisplayClass102_0::.ctor()
0x152f5  stloc.0
0x152f6  ldloc.0
0x152f7  ldarg.0
0x152f8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass102_0::<>4__this
0x152fd  ldloc.0
0x152fe  ldarg.1
0x152ff  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[] <>c__DisplayClass102_0::properties
0x15304  ldarg.0
0x15305  ldstr    aSetsystemprope// "SetSystemProperties"
0x1530a  ldloc.0
0x1530b  ldftn    instance int32 <>c__DisplayClass102_0::<SetSystemProperties>b__0()
0x15311  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x15316  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x1531b  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x15320  pop
0x15321  ret
```
