# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetItemLink

- ea: `0x144f0`
- end: `0x14529`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetItemLink`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x22bd0`

## string_xrefs

- `0x1450c`: `SetItemLink`

## pseudocode

```c

```

## disassembly

```asm
0x144f0  newobj   instance void <>c__DisplayClass52_0::.ctor()
0x144f5  stloc.0
0x144f6  ldloc.0
0x144f7  ldarg.0
0x144f8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass52_0::<>4__this
0x144fd  ldloc.0
0x144fe  ldarg.1
0x144ff  stfld    string <>c__DisplayClass52_0::itemPath
0x14504  ldloc.0
0x14505  ldarg.2
0x14506  stfld    string <>c__DisplayClass52_0::link
0x1450b  ldarg.0
0x1450c  ldstr    aSetitemlink// "SetItemLink"
0x14511  ldloc.0
0x14512  ldftn    instance int32 <>c__DisplayClass52_0::<SetItemLink>b__0()
0x14518  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x1451d  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14522  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x14527  pop
0x14528  ret
```
