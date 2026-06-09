# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::DeleteItem

- ea: `0x13f40`
- end: `0x13f72`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::DeleteItem`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x20e10`

## callees

- `0x22680`

## string_xrefs

- `0x13f55`: `DeleteItem`

## pseudocode

```c

```

## disassembly

```asm
0x13f40  newobj   instance void <>c__DisplayClass28_0::.ctor()
0x13f45  stloc.0
0x13f46  ldloc.0
0x13f47  ldarg.0
0x13f48  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass28_0::<>4__this
0x13f4d  ldloc.0
0x13f4e  ldarg.1
0x13f4f  stfld    string <>c__DisplayClass28_0::itemPath
0x13f54  ldarg.0
0x13f55  ldstr    aDeleteitem// "DeleteItem"
0x13f5a  ldloc.0
0x13f5b  ldftn    instance int32 <>c__DisplayClass28_0::<DeleteItem>b__0()
0x13f61  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x13f66  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x13f6b  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x13f70  pop
0x13f71  ret
```
