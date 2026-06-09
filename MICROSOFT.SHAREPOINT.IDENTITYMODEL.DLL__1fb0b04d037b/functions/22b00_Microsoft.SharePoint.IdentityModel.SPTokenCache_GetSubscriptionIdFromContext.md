# Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSubscriptionIdFromContext

- ea: `0x22b00`
- end: `0x22c34`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSubscriptionIdFromContext`
- size: `308`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4500`
- `0x59f0`
- `0x22c40`
- `0x25f80`
- `0x26e80`

## callees

- `0x22b00`

## string_xrefs

- `0x22b1c`: `Token Cache: The context is null. Stack: '{0}'.`
- `0x22b81`: `Token Cache: Got site subscription. Value: '{0}', SPSite: '{1}', Context: '{2}'.`
- `0x22bbf`: `Token Cache: No site subscription. SPSite: '{0}', Context: '{1}'.`
- `0x22c11`: `Token Cache: Could not find SPSite. Context: '{0}', Stack: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x22b00  ldarg.0
0x22b01  brtrue.s loc_22B40
0x22b03  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22b08  ldc.i4.s 0xA
0x22b0a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x22b0f  stloc.0
0x22b10  ldc.i4   0x20F885
0x22b15  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22b1a  ldc.i4.s 0xA
0x22b1c  ldstr    aTokenCacheTheC// "Token Cache: The context is null. Stack"...
0x22b21  ldc.i4.1
0x22b22  newarr   [mscorlib]System.Object
0x22b27  stloc.s  5
0x22b29  ldloc.s  5
0x22b2b  ldc.i4.0
0x22b2c  ldloc.0
0x22b2d  stelem.ref
0x22b2e  ldloc.s  5
0x22b30  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22b35  ldstr    aContext_0// "context"
0x22b3a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x22b3f  throw
0x22b40  ldnull
0x22b41  stloc.1
0x22b42  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x22b47  ldarg.0
0x22b48  newobj   instance void [System]System.Uri::.ctor(string)
0x22b4d  ldc.i4.1
0x22b4e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserToken [Microsoft.SharePoint]Microsoft.SharePoint.SPUserToken::get_SystemAccount()
0x22b53  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm, class [System]System.Uri, bool, class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserToken)
0x22b58  stloc.2
0x22b59  ldloc.2
0x22b5a  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x22b5f  brfalse.s loc_22BB0
0x22b61  ldloc.2
0x22b62  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x22b67  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionIdentifier [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription::get_Id()
0x22b6c  callvirt instance string [mscorlib]System.Object::ToString()
0x22b71  stloc.1
0x22b72  ldc.i4   0x15D660
0x22b77  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22b7c  ldc.i4   0xC8
0x22b81  ldstr    aTokenCacheGotS// "Token Cache: Got site subscription. Val"...
0x22b86  ldc.i4.3
0x22b87  newarr   [mscorlib]System.Object
0x22b8c  stloc.s  6
0x22b8e  ldloc.s  6
0x22b90  ldc.i4.0
0x22b91  ldloc.1
0x22b92  stelem.ref
0x22b93  ldloc.s  6
0x22b95  ldc.i4.1
0x22b96  ldloc.2
0x22b97  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x22b9c  box      [mscorlib]System.Guid
0x22ba1  stelem.ref
0x22ba2  ldloc.s  6
0x22ba4  ldc.i4.2
0x22ba5  ldarg.0
0x22ba6  stelem.ref
0x22ba7  ldloc.s  6
0x22ba9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22bae  br.s     loc_22BE7
0x22bb0  ldc.i4   0x20F886
0x22bb5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22bba  ldc.i4   0xC8
0x22bbf  ldstr    aTokenCacheNoSi// "Token Cache: No site subscription. SPSi"...
0x22bc4  ldc.i4.2
0x22bc5  newarr   [mscorlib]System.Object
0x22bca  stloc.s  7
0x22bcc  ldloc.s  7
0x22bce  ldc.i4.0
0x22bcf  ldloc.2
0x22bd0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x22bd5  box      [mscorlib]System.Guid
0x22bda  stelem.ref
0x22bdb  ldloc.s  7
0x22bdd  ldc.i4.1
0x22bde  ldarg.0
0x22bdf  stelem.ref
0x22be0  ldloc.s  7
0x22be2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22be7  leave.s  loc_22BF3
0x22be9  ldloc.2
0x22bea  brfalse.s loc_22BF2
0x22bec  ldloc.2
0x22bed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22bf2  endfinally
0x22bf3  leave.s  loc_22C32
0x22bf5  stloc.3
0x22bf6  ldloc.3
0x22bf7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22bfc  ldc.i4.s 0xA
0x22bfe  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::ExceptionTraceString(class [mscorlib]System.Exception, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x22c03  stloc.s  4
0x22c05  ldc.i4   0x20F887
0x22c0a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22c0f  ldc.i4.s 0x32
0x22c11  ldstr    aTokenCacheCoul// "Token Cache: Could not find SPSite. Con"...
0x22c16  ldc.i4.2
0x22c17  newarr   [mscorlib]System.Object
0x22c1c  stloc.s  8
0x22c1e  ldloc.s  8
0x22c20  ldc.i4.0
0x22c21  ldarg.0
0x22c22  stelem.ref
0x22c23  ldloc.s  8
0x22c25  ldc.i4.1
0x22c26  ldloc.s  4
0x22c28  stelem.ref
0x22c29  ldloc.s  8
0x22c2b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22c30  leave.s  loc_22C32
0x22c32  ldloc.1
0x22c33  ret
```
