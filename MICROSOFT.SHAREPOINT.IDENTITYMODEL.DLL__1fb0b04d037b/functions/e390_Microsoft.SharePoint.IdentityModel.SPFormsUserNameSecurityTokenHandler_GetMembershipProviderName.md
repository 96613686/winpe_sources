# Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetMembershipProviderName

- ea: `0xe390`
- end: `0xe439`
- name: `Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetMembershipProviderName`
- size: `169`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xd270`
- `0xe5d0`

## callees

- `0xd240`
- `0xe390`
- `0x2c520`
- `0x2c570`

## string_xrefs

- `0xe39f`: `token`
- `0xe3d3`: `token.Id`

## pseudocode

```c

```

## disassembly

```asm
0xe390  ldc.i4   0x12991DF
0xe395  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xe39a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe39f  ldstr    aToken// "token"
0xe3a4  ldarg.0
0xe3a5  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0xe3aa  ldc.i4   0x12991E0
0xe3af  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xe3b4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe3b9  ldstr    aLogprefix// "logPrefix"
0xe3be  ldarg.1
0xe3bf  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0xe3c4  ldc.i4   0x12991E1
0xe3c9  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xe3ce  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe3d3  ldstr    aTokenId// "token.Id"
0xe3d8  ldarg.0
0xe3d9  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe3de  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnEmpty(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, string value)
0xe3e3  ldarg.0
0xe3e4  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe3e9  ldc.i4.s 0x3A
0xe3eb  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0xe3f0  stloc.1
0xe3f1  ldc.i4.m1
0xe3f2  ldloc.1
0xe3f3  bne.un.s loc_E3FE
0xe3f5  ldarg.0
0xe3f6  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe3fb  stloc.0
0xe3fc  br.s     loc_E40C
0xe3fe  ldarg.0
0xe3ff  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe404  ldc.i4.0
0xe405  ldloc.1
0xe406  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xe40b  stloc.0
0xe40c  ldc.i4   0xDB410
0xe411  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe416  ldc.i4   0xC8
0xe41b  ldarg.1
0xe41c  ldstr    aUsingMembershi// "Using membership provider. Name: '{0}'."
0xe421  call     string [mscorlib]System.String::Concat(string, string)
0xe426  ldc.i4.1
0xe427  newarr   [mscorlib]System.Object
0xe42c  stloc.2
0xe42d  ldloc.2
0xe42e  ldc.i4.0
0xe42f  ldloc.0
0xe430  stelem.ref
0xe431  ldloc.2
0xe432  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xe437  ldloc.0
0xe438  ret
```
