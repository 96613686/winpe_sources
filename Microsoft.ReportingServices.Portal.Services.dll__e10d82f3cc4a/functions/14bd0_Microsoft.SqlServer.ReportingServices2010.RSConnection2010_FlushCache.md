# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::FlushCache

- ea: `0x14bd0`
- end: `0x14c02`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::FlushCache`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x231e0`

## string_xrefs

- `0x14be5`: `FlushCache`

## pseudocode

```c

```

## disassembly

```asm
0x14bd0  newobj   instance void <>c__DisplayClass74_0::.ctor()
0x14bd5  stloc.0
0x14bd6  ldloc.0
0x14bd7  ldarg.0
0x14bd8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass74_0::<>4__this
0x14bdd  ldloc.0
0x14bde  ldarg.1
0x14bdf  stfld    string <>c__DisplayClass74_0::itemPath
0x14be4  ldarg.0
0x14be5  ldstr    aFlushcache// "FlushCache"
0x14bea  ldloc.0
0x14beb  ldftn    instance int32 <>c__DisplayClass74_0::<FlushCache>b__0()
0x14bf1  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x14bf6  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14bfb  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x14c00  pop
0x14c01  ret
```
