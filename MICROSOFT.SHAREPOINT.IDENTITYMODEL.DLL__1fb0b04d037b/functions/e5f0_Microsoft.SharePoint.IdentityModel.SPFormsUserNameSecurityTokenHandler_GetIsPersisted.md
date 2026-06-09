# Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetIsPersisted

- ea: `0xe5f0`
- end: `0xe7f7`
- name: `Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetIsPersisted`
- size: `519`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x20a60`
- `0x218b0`

## callees

- `0xd240`
- `0xe5f0`
- `0xe800`
- `0x2c520`
- `0x2c570`

## string_xrefs

- `0xe5ff`: `token`
- `0xe619`: `token.Id`

## pseudocode

```c

```

## disassembly

```asm
0xe5f0  ldc.i4   0x1299201
0xe5f5  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xe5fa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe5ff  ldstr    aToken// "token"
0xe604  ldarg.0
0xe605  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0xe60a  ldc.i4   0x1299202
0xe60f  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xe614  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe619  ldstr    aTokenId// "token.Id"
0xe61e  ldarg.0
0xe61f  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe624  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnEmpty(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, string value)
0xe629  ldc.i4.0
0xe62a  stloc.0
0xe62b  ldc.i4.m1
0xe62c  stloc.1
0xe62d  ldc.i4.m1
0xe62e  stloc.2
0xe62f  ldc.i4.m1
0xe630  ldarg.0
0xe631  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe636  ldc.i4.s 0x3A
0xe638  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0xe63d  dup
0xe63e  stloc.1
0xe63f  bne.un.s loc_E65E
0xe641  ldc.i4.0
0xe642  stloc.0
0xe643  ldc.i4   0xDB416
0xe648  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe64d  ldc.i4.s 0xA
0xe64f  ldstr    aNoPersistedFla// "No persisted flag because we could not "...
0xe654  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe659  br       loc_E7F5
0xe65e  ldloc.1
0xe65f  ldarg.0
0xe660  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe665  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe66a  ldc.i4.1
0xe66b  sub
0xe66c  bne.un.s loc_E68B
0xe66e  ldc.i4.0
0xe66f  stloc.0
0xe670  ldc.i4   0xDB417
0xe675  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe67a  ldc.i4.s 0xA
0xe67c  ldstr    aNoPersistedFla_0// "No persisted flag because first separat"...
0xe681  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe686  br       loc_E7F5
0xe68b  ldc.i4.m1
0xe68c  ldarg.0
0xe68d  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe692  ldc.i4.s 0x3A
0xe694  ldloc.1
0xe695  ldc.i4.1
0xe696  add
0xe697  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0xe69c  dup
0xe69d  stloc.2
0xe69e  bne.un.s loc_E6BD
0xe6a0  ldc.i4.0
0xe6a1  stloc.0
0xe6a2  ldc.i4   0xDB418
0xe6a7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe6ac  ldc.i4.s 0xA
0xe6ae  ldstr    aNoPersistedFla_1// "No persisted flag because we could not "...
0xe6b3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe6b8  br       loc_E7F5
0xe6bd  ldloc.2
0xe6be  ldarg.0
0xe6bf  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe6c4  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe6c9  ldc.i4.1
0xe6ca  sub
0xe6cb  bne.un.s loc_E6EA
0xe6cd  ldc.i4.0
0xe6ce  stloc.0
0xe6cf  ldc.i4   0xDB419
0xe6d4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe6d9  ldc.i4.s 0xA
0xe6db  ldstr    aNoPersistedFla_2// "No persisted flag because second separa"...
0xe6e0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe6e5  br       loc_E7F5
0xe6ea  ldc.i4.0
0xe6eb  stloc.3
0xe6ec  ldc.i4   0x2EA
0xe6f1  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0xe6f6  stloc.s  4
0xe6f8  ldloc.s  4
0xe6fa  brfalse.s loc_E76F
0xe6fc  ldarg.0
0xe6fd  call     valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption> Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetOptionFromTokenId(class [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken token)
0xe702  stloc.s  5
0xe704  ldloca.s 5
0xe706  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption>::get_HasValue()
0xe70b  brtrue.s loc_E727
0xe70d  ldc.i4   0x1192317
0xe712  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe717  ldc.i4.s 0xA
0xe719  ldstr    aCouldNotObtain// "Could not obtain forms authentication o"...
0xe71e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe723  ldc.i4.0
0xe724  stloc.3
0xe725  br.s     loc_E76F
0xe727  ldloca.s 5
0xe729  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption>::get_Value()
0xe72e  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption
0xe733  ldc.i4.1
0xe734  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption
0xe739  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0xe73e  stloc.0
0xe73f  ldc.i4   0x1192318
0xe744  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe749  ldc.i4   0xC8
0xe74e  ldstr    aPersistedFlagI// "Persisted flag is '{0}'."
0xe753  ldc.i4.1
0xe754  newarr   [mscorlib]System.Object
0xe759  stloc.s  7
0xe75b  ldloc.s  7
0xe75d  ldc.i4.0
0xe75e  ldloca.s 0
0xe760  call     instance string [mscorlib]System.Boolean::ToString()
0xe765  stelem.ref
0xe766  ldloc.s  7
0xe768  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xe76d  ldc.i4.1
0xe76e  stloc.3
0xe76f  ldloc.3
0xe770  brtrue   loc_E7F5
0xe775  ldarg.0
0xe776  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe77b  ldloc.2
0xe77c  ldc.i4.1
0xe77d  add
0xe77e  callvirt instance string [mscorlib]System.String::Substring(int32)
0xe783  stloc.s  6
0xe785  ldloc.s  6
0xe787  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe78c  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0xe791  stloc.0
0xe792  ldc.i4   0xDB41A
0xe797  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe79c  ldc.i4   0xC8
0xe7a1  ldstr    aPersistedFlagI// "Persisted flag is '{0}'."
0xe7a6  ldc.i4.1
0xe7a7  newarr   [mscorlib]System.Object
0xe7ac  stloc.s  8
0xe7ae  ldloc.s  8
0xe7b0  ldc.i4.0
0xe7b1  ldloc.0
0xe7b2  brtrue.s loc_E7BB
0xe7b4  ldsfld   string [mscorlib]System.Boolean::FalseString
0xe7b9  br.s     loc_E7C0
0xe7bb  ldsfld   string [mscorlib]System.Boolean::TrueString
0xe7c0  stelem.ref
0xe7c1  ldloc.s  8
0xe7c3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xe7c8  leave.s  loc_E7F5
0xe7ca  pop
0xe7cb  ldc.i4.0
0xe7cc  stloc.0
0xe7cd  ldc.i4   0xDB41B
0xe7d2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe7d7  ldc.i4.s 0xA
0xe7d9  ldstr    aNoPersistedFla_3// "No persisted flag because we could not "...
0xe7de  ldc.i4.1
0xe7df  newarr   [mscorlib]System.Object
0xe7e4  stloc.s  9
0xe7e6  ldloc.s  9
0xe7e8  ldc.i4.0
0xe7e9  ldloc.s  6
0xe7eb  stelem.ref
0xe7ec  ldloc.s  9
0xe7ee  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xe7f3  leave.s  loc_E7F5
0xe7f5  ldloc.0
0xe7f6  ret
```
