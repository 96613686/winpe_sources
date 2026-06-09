# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateRole

- ea: `0x14100`
- end: `0x14140`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateRole`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x22840`

## string_xrefs

- `0x14123`: `CreateRole`

## pseudocode

```c

```

## disassembly

```asm
0x14100  newobj   instance void <>c__DisplayClass35_0::.ctor()
0x14105  stloc.0
0x14106  ldloc.0
0x14107  ldarg.0
0x14108  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass35_0::<>4__this
0x1410d  ldloc.0
0x1410e  ldarg.1
0x1410f  stfld    string <>c__DisplayClass35_0::name
0x14114  ldloc.0
0x14115  ldarg.2
0x14116  stfld    string <>c__DisplayClass35_0::description
0x1411b  ldloc.0
0x1411c  ldarg.3
0x1411d  stfld    string[] <>c__DisplayClass35_0::taskIds
0x14122  ldarg.0
0x14123  ldstr    aCreaterole// "CreateRole"
0x14128  ldloc.0
0x14129  ldftn    instance int32 <>c__DisplayClass35_0::<CreateRole>b__0()
0x1412f  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x14134  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14139  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x1413e  pop
0x1413f  ret
```
