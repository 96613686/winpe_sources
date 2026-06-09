# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateLinkedItem

- ea: `0x156c0`
- end: `0x15708`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateLinkedItem`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x23c50`

## string_xrefs

- `0x156eb`: `CreateLinkedItem`

## pseudocode

```c

```

## disassembly

```asm
0x156c0  newobj   instance void <>c__DisplayClass117_0::.ctor()
0x156c5  stloc.0
0x156c6  ldloc.0
0x156c7  ldarg.0
0x156c8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass117_0::<>4__this
0x156cd  ldloc.0
0x156ce  ldarg.1
0x156cf  stfld    string <>c__DisplayClass117_0::itemPath
0x156d4  ldloc.0
0x156d5  ldarg.2
0x156d6  stfld    string <>c__DisplayClass117_0::parent
0x156db  ldloc.0
0x156dc  ldarg.3
0x156dd  stfld    string <>c__DisplayClass117_0::link
0x156e2  ldloc.0
0x156e3  ldarg.s  4
0x156e5  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[] <>c__DisplayClass117_0::properties
0x156ea  ldarg.0
0x156eb  ldstr    aCreatelinkedit// "CreateLinkedItem"
0x156f0  ldloc.0
0x156f1  ldftn    instance int32 <>c__DisplayClass117_0::<CreateLinkedItem>b__0()
0x156f7  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x156fc  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x15701  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x15706  pop
0x15707  ret
```
