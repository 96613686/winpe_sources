# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetCacheOptions

- ea: `0x14b90`
- end: `0x14bd0`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetCacheOptions`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x21760`

## callees

- `0x231a0`

## string_xrefs

- `0x14bb3`: `SetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x14b90  newobj   instance void <>c__DisplayClass73_0::.ctor()
0x14b95  stloc.0
0x14b96  ldloc.0
0x14b97  ldarg.0
0x14b98  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass73_0::<>4__this
0x14b9d  ldloc.0
0x14b9e  ldarg.1
0x14b9f  stfld    string <>c__DisplayClass73_0::itemPath
0x14ba4  ldloc.0
0x14ba5  ldarg.2
0x14ba6  stfld    bool <>c__DisplayClass73_0::cacheItem
0x14bab  ldloc.0
0x14bac  ldarg.3
0x14bad  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExpirationDefinition <>c__DisplayClass73_0::cacheExpiration
0x14bb2  ldarg.0
0x14bb3  ldstr    aSetcacheoption// "SetCacheOptions"
0x14bb8  ldloc.0
0x14bb9  ldftn    instance int32 <>c__DisplayClass73_0::<SetCacheOptions>b__0()
0x14bbf  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x14bc4  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14bc9  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x14bce  pop
0x14bcf  ret
```
