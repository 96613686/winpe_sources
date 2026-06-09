# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::InheritParentSecurity

- ea: `0x14410`
- end: `0x14442`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::InheritParentSecurity`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x22b10`

## string_xrefs

- `0x14425`: `InheritParentSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x14410  newobj   instance void <>c__DisplayClass48_0::.ctor()
0x14415  stloc.0
0x14416  ldloc.0
0x14417  ldarg.0
0x14418  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass48_0::<>4__this
0x1441d  ldloc.0
0x1441e  ldarg.1
0x1441f  stfld    string <>c__DisplayClass48_0::itemPath
0x14424  ldarg.0
0x14425  ldstr    aInheritparents// "InheritParentSecurity"
0x1442a  ldloc.0
0x1442b  ldftn    instance int32 <>c__DisplayClass48_0::<InheritParentSecurity>b__0()
0x14431  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x14436  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x1443b  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x14440  pop
0x14441  ret
```
