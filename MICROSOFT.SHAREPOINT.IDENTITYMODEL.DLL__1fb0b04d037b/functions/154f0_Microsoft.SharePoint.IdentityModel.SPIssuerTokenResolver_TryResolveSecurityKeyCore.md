# Microsoft.SharePoint.IdentityModel.SPIssuerTokenResolver::TryResolveSecurityKeyCore

- ea: `0x154f0`
- end: `0x1560d`
- name: `Microsoft.SharePoint.IdentityModel.SPIssuerTokenResolver::TryResolveSecurityKeyCore`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x154f0`
- `0x2c520`

## string_xrefs

- `0x1557e`: `Token validation succeeded but is null.`
- `0x1559c`: `Token validation succeeded but security keys are null.`
- `0x155c0`: `The key identifier clause resolved token does not have a single key. Count: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x154f0  ldc.i4.0
0x154f1  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x154f6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x154fb  ldstr    aKeyidentifierc// "keyIdentifierClause"
0x15500  ldarg.1
0x15501  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x15506  ldc.i4.0
0x15507  stloc.0
0x15508  ldnull
0x15509  stloc.1
0x1550a  ldarg.2
0x1550b  ldnull
0x1550c  stind.ref
0x1550d  ldarg.1
0x1550e  isinst   [System.IdentityModel]System.IdentityModel.Tokens.EncryptedKeyIdentifierClause
0x15513  brfalse.s loc_1552E
0x15515  ldc.i4.0
0x15516  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x1551b  ldc.i4.s 0xA
0x1551d  ldstr    aTheKeyIdentifi// "The key identifier clause is an encrypt"...
0x15522  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15527  ldc.i4.0
0x15528  stloc.0
0x15529  br       loc_1560B
0x1552e  ldarg.0
0x1552f  ldarg.1
0x15530  ldloca.s 1
0x15532  call     instance bool [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver::TryResolveToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyIdentifierClause, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken&)
0x15537  brtrue.s loc_15573
0x15539  ldarg.1
0x1553a  callvirt instance bool [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyIdentifierClause::get_CanCreateKey()
0x1553f  brfalse.s loc_1555A
0x15541  ldc.i4.0
0x15542  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x15547  ldc.i4.s 0xA
0x15549  ldstr    aTheKeyIdentifi_0// "The key identifier clause is embeded ke"...
0x1554e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15553  ldc.i4.0
0x15554  stloc.0
0x15555  br       loc_1560B
0x1555a  ldc.i4.0
0x1555b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x15560  ldc.i4.s 0xA
0x15562  ldstr    aTheKeyIdentifi_1// "The key identifier clause could not be "...
0x15567  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1556c  ldc.i4.0
0x1556d  stloc.0
0x1556e  br       loc_1560B
0x15573  ldloc.1
0x15574  brtrue.s loc_1558C
0x15576  ldc.i4.0
0x15577  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x1557c  ldc.i4.s 0xA
0x1557e  ldstr    aTokenValidatio// "Token validation succeeded but is null."
0x15583  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15588  ldc.i4.0
0x15589  stloc.0
0x1558a  br.s     loc_1560B
0x1558c  ldloc.1
0x1558d  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey> [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_SecurityKeys()
0x15592  brtrue.s loc_155AA
0x15594  ldc.i4.0
0x15595  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x1559a  ldc.i4.s 0xA
0x1559c  ldstr    aTokenValidatio_0// "Token validation succeeded but security"...
0x155a1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x155a6  ldc.i4.0
0x155a7  stloc.0
0x155a8  br.s     loc_1560B
0x155aa  ldloc.1
0x155ab  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey> [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_SecurityKeys()
0x155b0  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey>::get_Count()
0x155b5  ldc.i4.1
0x155b6  beq.s    loc_155E9
0x155b8  ldc.i4.0
0x155b9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x155be  ldc.i4.s 0xA
0x155c0  ldstr    aTheKeyIdentifi_2// "The key identifier clause resolved toke"...
0x155c5  ldc.i4.1
0x155c6  newarr   [mscorlib]System.Object
0x155cb  stloc.2
0x155cc  ldloc.2
0x155cd  ldc.i4.0
0x155ce  ldloc.1
0x155cf  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey> [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_SecurityKeys()
0x155d4  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey>::get_Count()
0x155d9  box      [mscorlib]System.Int32
0x155de  stelem.ref
0x155df  ldloc.2
0x155e0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x155e5  ldc.i4.0
0x155e6  stloc.0
0x155e7  br.s     loc_1560B
0x155e9  ldc.i4.0
0x155ea  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x155ef  ldc.i4.s 0x64
0x155f1  ldstr    aTheKeyIdentifi_3// "The key identifier clause resulve succe"...
0x155f6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x155fb  ldarg.2
0x155fc  ldloc.1
0x155fd  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey> [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_SecurityKeys()
0x15602  ldc.i4.0
0x15603  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey>::get_Item(!!T0)
0x15608  stind.ref
0x15609  ldc.i4.1
0x1560a  stloc.0
0x1560b  ldloc.0
0x1560c  ret
```
