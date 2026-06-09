# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetItemLink

- ea: `0x144b0`
- end: `0x144e1`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetItemLink`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x22b90`

## string_xrefs

- `0x144c5`: `GetItemLink`

## pseudocode

```c

```

## disassembly

```asm
0x144b0  newobj   instance void <>c__DisplayClass51_0::.ctor()
0x144b5  stloc.0
0x144b6  ldloc.0
0x144b7  ldarg.0
0x144b8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass51_0::<>4__this
0x144bd  ldloc.0
0x144be  ldarg.1
0x144bf  stfld    string <>c__DisplayClass51_0::itemPath
0x144c4  ldarg.0
0x144c5  ldstr    aGetitemlink// "GetItemLink"
0x144ca  ldloc.0
0x144cb  ldftn    instance string <>c__DisplayClass51_0::<GetItemLink>b__0()
0x144d1  newobj   instance void class SoapMethod<string>::.ctor(object, native int)
0x144d6  newobj   instance void class SoapMethodWrapper`1<string>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x144db  callvirt instance var<u1> class SoapMethodWrapper`1<string>::ExecuteMethod()
0x144e0  ret
```
