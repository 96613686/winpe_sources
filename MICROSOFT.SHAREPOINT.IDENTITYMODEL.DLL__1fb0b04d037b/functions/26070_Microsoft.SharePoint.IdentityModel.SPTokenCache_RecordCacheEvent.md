# Microsoft.SharePoint.IdentityModel.SPTokenCache::RecordCacheEvent

- ea: `0x26070`
- end: `0x260e5`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::RecordCacheEvent`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x26300`
- `0x26690`

## callees

- `0x26070`

## string_xrefs

- `0x26087`: `SPTokenCache: No SPRequestUsageMonitoredScope available.`
- `0x260a8`: `SPTokenCache: No SPClaimsCounter available on SPRequestUsageMonitoredScope.`
- `0x260c2`: `SPTokenCache: Event recorded. Value: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x26070  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope::get_Local()
0x26075  stloc.0
0x26076  ldnull
0x26077  stloc.1
0x26078  ldloc.0
0x26079  brtrue.s loc_26092
0x2607b  ldc.i4   0x20F88E
0x26080  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x26085  ldc.i4.s 0x64
0x26087  ldstr    aSptokencacheNo// "SPTokenCache: No SPRequestUsageMonitore"...
0x2608c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x26091  ret
0x26092  ldloc.0
0x26093  callvirt T0x2B00001F
0x26098  dup
0x26099  stloc.1
0x2609a  brtrue.s loc_260B3
0x2609c  ldc.i4   0x20F88F
0x260a1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x260a6  ldc.i4.s 0xA
0x260a8  ldstr    aSptokencacheNo_0// "SPTokenCache: No SPClaimsCounter availa"...
0x260ad  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x260b2  ret
0x260b3  ldc.i4   0x261242
0x260b8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x260bd  ldc.i4   0xC8
0x260c2  ldstr    aSptokencacheEv// "SPTokenCache: Event recorded. Value: '{"...
0x260c7  ldc.i4.1
0x260c8  newarr   [mscorlib]System.Object
0x260cd  stloc.2
0x260ce  ldloc.2
0x260cf  ldc.i4.0
0x260d0  ldarg.0
0x260d1  box      [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPClaimsAuthenticationTimeCategory
0x260d6  stelem.ref
0x260d7  ldloc.2
0x260d8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x260dd  ldloc.1
0x260de  ldarg.0
0x260df  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPClaimsCounter::set_ClaimsAuthenticationTimeType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPClaimsAuthenticationTimeCategory)
0x260e4  ret
```
