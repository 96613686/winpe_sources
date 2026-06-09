# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::RemoveAllModelItemPolicies

- ea: `0x15680`
- end: `0x156b2`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::RemoveAllModelItemPolicies`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x23c10`

## string_xrefs

- `0x15695`: `RemoveAllModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x15680  newobj   instance void <>c__DisplayClass116_0::.ctor()
0x15685  stloc.0
0x15686  ldloc.0
0x15687  ldarg.0
0x15688  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass116_0::<>4__this
0x1568d  ldloc.0
0x1568e  ldarg.1
0x1568f  stfld    string <>c__DisplayClass116_0::model
0x15694  ldarg.0
0x15695  ldstr    aRemoveallmodel// "RemoveAllModelItemPolicies"
0x1569a  ldloc.0
0x1569b  ldftn    instance int32 <>c__DisplayClass116_0::<RemoveAllModelItemPolicies>b__0()
0x156a1  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x156a6  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x156ab  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x156b0  pop
0x156b1  ret
```
