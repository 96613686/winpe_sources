# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::MoveItem

- ea: `0x13f80`
- end: `0x13fb9`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::MoveItem`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x226c0`

## string_xrefs

- `0x13f9c`: `MoveItem`

## pseudocode

```c

```

## disassembly

```asm
0x13f80  newobj   instance void <>c__DisplayClass29_0::.ctor()
0x13f85  stloc.0
0x13f86  ldloc.0
0x13f87  ldarg.0
0x13f88  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass29_0::<>4__this
0x13f8d  ldloc.0
0x13f8e  ldarg.1
0x13f8f  stfld    string <>c__DisplayClass29_0::itemPath
0x13f94  ldloc.0
0x13f95  ldarg.2
0x13f96  stfld    string <>c__DisplayClass29_0::target
0x13f9b  ldarg.0
0x13f9c  ldstr    aMoveitem// "MoveItem"
0x13fa1  ldloc.0
0x13fa2  ldftn    instance int32 <>c__DisplayClass29_0::<MoveItem>b__0()
0x13fa8  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x13fad  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x13fb2  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x13fb7  pop
0x13fb8  ret
```
