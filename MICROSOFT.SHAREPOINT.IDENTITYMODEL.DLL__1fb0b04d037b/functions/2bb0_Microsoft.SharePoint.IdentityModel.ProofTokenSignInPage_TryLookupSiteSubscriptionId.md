# Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::TryLookupSiteSubscriptionId

- ea: `0x2bb0`
- end: `0x2cc8`
- name: `Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::TryLookupSiteSubscriptionId`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x29a0`

## callees

- `0x2bb0`
- `0x2c630`

## string_xrefs

- `0x2bcc`: `redirectUri`
- `0x2c5b`: `ProofTokenSignIn: Successfully looked up site: '{0}'.`
- `0x2c83`: `No site at redireciton Uri. Value: '{0}'.`
- `0x2cab`: `Exception looking up site data at redireciton Uri. Value: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x2bb0  ldc.i4.0
0x2bb1  stloc.0
0x2bb2  ldarg.1
0x2bb3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2bb8  stobj    [mscorlib]System.Guid
0x2bbd  ldc.i4   0x1E495854
0x2bc2  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x2bc7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2bcc  ldstr    aRedirecturi_0// "redirectUri"
0x2bd1  ldarg.0
0x2bd2  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnRelative(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, class [System]System.Uri value)
0x2bd7  ldarg.0
0x2bd8  stloc.1
0x2bd9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2bde  stloc.2
0x2bdf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2be4  stloc.3
0x2be5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2bea  stloc.s  4
0x2bec  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2bf1  stloc.s  5
0x2bf3  ldc.i4.0
0x2bf4  stloc.s  8
0x2bf6  ldc.i4.0
0x2bf7  stloc.s  9
0x2bf9  ldc.i4.0
0x2bfa  stloc.s  0xA
0x2bfc  ldnull
0x2bfd  stloc.s  0xB
0x2bff  ldnull
0x2c00  stloc.s  0xC
0x2c02  ldnull
0x2c03  stloc.s  0xD
0x2c05  ldnull
0x2c06  stloc.s  0xE
0x2c08  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x2c0d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x2c12  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_WebApplication()
0x2c17  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Farm()
0x2c1c  stloc.s  0x10
0x2c1e  ldloc.s  0x10
0x2c20  ldc.i4.0
0x2c21  ldc.i4.0
0x2c22  ldloca.s 1
0x2c24  ldloca.s 8
0x2c26  ldloca.s 2
0x2c28  ldloca.s 3
0x2c2a  ldloca.s 4
0x2c2c  ldloca.s 5
0x2c2e  ldloca.s 6
0x2c30  ldloca.s 7
0x2c32  ldloca.s 9
0x2c34  ldloca.s 0xA
0x2c36  ldloca.s 0xB
0x2c38  ldloca.s 0xC
0x2c3a  ldloca.s 0xD
0x2c3c  ldloca.s 0xE
0x2c3e  ldloca.s 0xF
0x2c40  call     void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::LookupSiteInfo(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm, bool, bool, class [System]System.Uri&, bool&, valuetype [mscorlib]System.Guid&, valuetype [mscorlib]System.Guid&, valuetype [mscorlib]System.Guid&, valuetype [mscorlib]System.Guid&, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone&, string&, bool&, bool&, string&, string&, string&, string&, class [System]System.Uri&)
0x2c45  ldarg.1
0x2c46  ldloc.s  5
0x2c48  stobj    [mscorlib]System.Guid
0x2c4d  ldc.i4.1
0x2c4e  stloc.0
0x2c4f  ldc.i4   0x1E495853
0x2c54  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2c59  ldc.i4.s 0x32
0x2c5b  ldstr    aProoftokensign_40// "ProofTokenSignIn: Successfully looked u"...
0x2c60  ldc.i4.1
0x2c61  newarr   [mscorlib]System.Object
0x2c66  stloc.s  0x11
0x2c68  ldloc.s  0x11
0x2c6a  ldc.i4.0
0x2c6b  ldarg.0
0x2c6c  stelem.ref
0x2c6d  ldloc.s  0x11
0x2c6f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2c74  leave.s  loc_2CC6
0x2c76  pop
0x2c77  ldc.i4   0x1E495852
0x2c7c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2c81  ldc.i4.s 0x14
0x2c83  ldstr    aNoSiteAtRedire// "No site at redireciton Uri. Value: '{0}"...
0x2c88  ldc.i4.1
0x2c89  newarr   [mscorlib]System.Object
0x2c8e  stloc.s  0x12
0x2c90  ldloc.s  0x12
0x2c92  ldc.i4.0
0x2c93  ldarg.0
0x2c94  stelem.ref
0x2c95  ldloc.s  0x12
0x2c97  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2c9c  leave.s  loc_2CC6
0x2c9e  pop
0x2c9f  ldc.i4   0x1E495851
0x2ca4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2ca9  ldc.i4.s 0x14
0x2cab  ldstr    aExceptionLooki// "Exception looking up site data at redir"...
0x2cb0  ldc.i4.1
0x2cb1  newarr   [mscorlib]System.Object
0x2cb6  stloc.s  0x13
0x2cb8  ldloc.s  0x13
0x2cba  ldc.i4.0
0x2cbb  ldarg.0
0x2cbc  stelem.ref
0x2cbd  ldloc.s  0x13
0x2cbf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2cc4  leave.s  loc_2CC6
0x2cc6  ldloc.0
0x2cc7  ret
```
