# Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::AddIncomingValidFromTimeClaim

- ea: `0xe060`
- end: `0xe16b`
- name: `Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::AddIncomingValidFromTimeClaim`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xe1c0`

## callees

- `0xd240`
- `0xe060`
- `0x2c520`

## string_xrefs

- `0xe089`: `AddIncomingValidFromTimeClaim: This is a sign in request. Not adding this claim because we will get a new value from the token.`
- `0xe0bc`: `AddIncomingValidFromTimeClaim: No or invalid valid-from time on the incoming cookie. Not adding this claim.`
- `0xe0d3`: `AddIncomingValidFromTimeClaim: Incoming cookie has an authentication valid-from time. Adding claim. Time (UTC): '{0}'.`
- `0xe14a`: `AddIncomingValidFromTimeClaim: Exception encountered while adding claim. Ex: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0xe060  ldc.i4   0x12991DB
0xe065  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xe06a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe06f  ldstr    aClaims// "claims"
0xe074  ldarg.3
0xe075  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0xe07a  ldarg.1
0xe07b  brtrue.s loc_E094
0xe07d  ldc.i4   0x5D488A
0xe082  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe087  ldc.i4.s 0x32
0xe089  ldstr    aAddincomingval// "AddIncomingValidFromTimeClaim: This is "...
0xe08e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe093  ret
0xe094  ldarga.s 2
0xe096  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xe09b  brfalse.s loc_E0B0
0xe09d  ldarga.s 2
0xe09f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0xe0a4  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xe0a9  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xe0ae  brfalse.s loc_E0C7
0xe0b0  ldc.i4   0x5D488B
0xe0b5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe0ba  ldc.i4.s 0x32
0xe0bc  ldstr    aAddincomingval_0// "AddIncomingValidFromTimeClaim: No or in"...
0xe0c1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe0c6  ret
0xe0c7  ldc.i4   0x5D488C
0xe0cc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe0d1  ldc.i4.s 0x32
0xe0d3  ldstr    aAddincomingval_1// "AddIncomingValidFromTimeClaim: Incoming"...
0xe0d8  ldc.i4.1
0xe0d9  newarr   [mscorlib]System.Object
0xe0de  stloc.2
0xe0df  ldloc.2
0xe0e0  ldc.i4.0
0xe0e1  ldarga.s 2
0xe0e3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0xe0e8  stloc.3
0xe0e9  ldloca.s 3
0xe0eb  constrained. [mscorlib]System.DateTime
0xe0f1  callvirt instance string [mscorlib]System.Object::ToString()
0xe0f6  stelem.ref
0xe0f7  ldloc.2
0xe0f8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xe0fd  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_CookieAuthenticationValidFromUtc()
0xe102  ldarga.s 2
0xe104  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0xe109  stloc.s  4
0xe10b  ldloca.s 4
0xe10d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0xe112  stloc.s  5
0xe114  ldloca.s 5
0xe116  call     instance int64 [mscorlib]System.DateTime::ToFileTimeUtc()
0xe11b  stloc.s  6
0xe11d  ldloca.s 6
0xe11f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe124  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0xe129  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimValueTypes::get_Integer()
0xe12e  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string)
0xe133  stloc.0
0xe134  ldarg.3
0xe135  ldloc.0
0xe136  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim>::Add(var<u1>)
0xe13b  leave.s  loc_E16A
0xe13d  stloc.1
0xe13e  ldc.i4   0x1207890
0xe143  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe148  ldc.i4.s 0x32
0xe14a  ldstr    aAddincomingval_2// "AddIncomingValidFromTimeClaim: Exceptio"...
0xe14f  ldc.i4.1
0xe150  newarr   [mscorlib]System.Object
0xe155  stloc.s  7
0xe157  ldloc.s  7
0xe159  ldc.i4.0
0xe15a  ldloc.1
0xe15b  callvirt instance string [mscorlib]System.Object::ToString()
0xe160  stelem.ref
0xe161  ldloc.s  7
0xe163  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xe168  leave.s  loc_E16A
0xe16a  ret
```
