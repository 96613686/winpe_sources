# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::DeleteRole

- ea: `0x14140`
- end: `0x14172`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::DeleteRole`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x22880`

## string_xrefs

- `0x14155`: `DeleteRole`

## pseudocode

```c

```

## disassembly

```asm
0x14140  newobj   instance void <>c__DisplayClass36_0::.ctor()
0x14145  stloc.0
0x14146  ldloc.0
0x14147  ldarg.0
0x14148  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass36_0::<>4__this
0x1414d  ldloc.0
0x1414e  ldarg.1
0x1414f  stfld    string <>c__DisplayClass36_0::name
0x14154  ldarg.0
0x14155  ldstr    aDeleterole// "DeleteRole"
0x1415a  ldloc.0
0x1415b  ldftn    instance int32 <>c__DisplayClass36_0::<DeleteRole>b__0()
0x14161  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x14166  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x1416b  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x14170  pop
0x14171  ret
```
