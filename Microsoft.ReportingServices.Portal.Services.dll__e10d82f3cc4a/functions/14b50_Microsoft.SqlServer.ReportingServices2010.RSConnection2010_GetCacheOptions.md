# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetCacheOptions

- ea: `0x14b50`
- end: `0x14b90`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetCacheOptions`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x23160`

## string_xrefs

- `0x14b6c`: `GetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x14b50  newobj   instance void <>c__DisplayClass72_0::.ctor()
0x14b55  stloc.0
0x14b56  ldloc.0
0x14b57  ldarg.0
0x14b58  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass72_0::<>4__this
0x14b5d  ldloc.0
0x14b5e  ldarg.1
0x14b5f  stfld    string <>c__DisplayClass72_0::itemPath
0x14b64  ldloc.0
0x14b65  ldnull
0x14b66  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExpirationDefinition <>c__DisplayClass72_0::outCacheExpiration
0x14b6b  ldarg.0
0x14b6c  ldstr    aGetcacheoption// "GetCacheOptions"
0x14b71  ldloc.0
0x14b72  ldftn    instance bool <>c__DisplayClass72_0::<GetCacheOptions>b__0()
0x14b78  newobj   instance void class SoapMethod<bool>::.ctor(object, native int)
0x14b7d  newobj   instance void class SoapMethodWrapper`1<bool>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14b82  callvirt instance var<u1> class SoapMethodWrapper`1<bool>::ExecuteMethod()
0x14b87  ldarg.2
0x14b88  ldloc.0
0x14b89  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExpirationDefinition <>c__DisplayClass72_0::outCacheExpiration
0x14b8e  stind.ref
0x14b8f  ret
```
