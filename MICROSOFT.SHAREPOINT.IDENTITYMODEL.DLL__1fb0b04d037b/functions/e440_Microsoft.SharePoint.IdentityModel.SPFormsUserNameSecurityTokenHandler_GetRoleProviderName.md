# Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetRoleProviderName

- ea: `0xe440`
- end: `0xe5c4`
- name: `Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetRoleProviderName`
- size: `388`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xd2c0`
- `0xe5e0`

## callees

- `0xd240`
- `0xe440`
- `0x2c520`
- `0x2c570`

## string_xrefs

- `0xe44f`: `token`
- `0xe483`: `token.Id`

## pseudocode

```c

```

## disassembly

```asm
0xe440  ldc.i4   0x12991E2
0xe445  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xe44a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe44f  ldstr    aToken// "token"
0xe454  ldarg.0
0xe455  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0xe45a  ldc.i4   0x12991E3
0xe45f  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xe464  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe469  ldstr    aLogprefix// "logPrefix"
0xe46e  ldarg.1
0xe46f  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0xe474  ldc.i4   0x1299200
0xe479  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xe47e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe483  ldstr    aTokenId// "token.Id"
0xe488  ldarg.0
0xe489  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe48e  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnEmpty(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, string value)
0xe493  ldnull
0xe494  stloc.0
0xe495  ldc.i4.m1
0xe496  stloc.1
0xe497  ldc.i4.m1
0xe498  stloc.2
0xe499  ldc.i4.m1
0xe49a  stloc.3
0xe49b  ldc.i4.m1
0xe49c  ldarg.0
0xe49d  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe4a2  ldc.i4.s 0x3A
0xe4a4  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0xe4a9  dup
0xe4aa  stloc.1
0xe4ab  bne.un.s loc_E4D0
0xe4ad  ldnull
0xe4ae  stloc.0
0xe4af  ldc.i4   0xDB411
0xe4b4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe4b9  ldc.i4.s 0xA
0xe4bb  ldarg.1
0xe4bc  ldstr    aNotUsingARoleP// "Not using a role provider because we co"...
0xe4c1  call     string [mscorlib]System.String::Concat(string, string)
0xe4c6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe4cb  br       loc_E5C2
0xe4d0  ldloc.1
0xe4d1  ldarg.0
0xe4d2  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe4d7  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe4dc  ldc.i4.1
0xe4dd  sub
0xe4de  bne.un.s loc_E503
0xe4e0  ldnull
0xe4e1  stloc.0
0xe4e2  ldc.i4   0xDB412
0xe4e7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe4ec  ldc.i4.s 0xA
0xe4ee  ldarg.1
0xe4ef  ldstr    aNotUsingARoleP_0// "Not using a role provider because first"...
0xe4f4  call     string [mscorlib]System.String::Concat(string, string)
0xe4f9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe4fe  br       loc_E5C2
0xe503  ldc.i4.m1
0xe504  ldarg.0
0xe505  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe50a  ldc.i4.s 0x3A
0xe50c  ldloc.1
0xe50d  ldc.i4.1
0xe50e  add
0xe50f  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0xe514  dup
0xe515  stloc.2
0xe516  bne.un.s loc_E557
0xe518  ldarg.0
0xe519  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe51e  ldloc.1
0xe51f  ldc.i4.1
0xe520  add
0xe521  callvirt instance string [mscorlib]System.String::Substring(int32)
0xe526  stloc.0
0xe527  ldc.i4   0xDB413
0xe52c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe531  ldc.i4   0xC8
0xe536  ldarg.1
0xe537  ldstr    aUsingRoleProvi// "Using role provider. Name: '{0}'."
0xe53c  call     string [mscorlib]System.String::Concat(string, string)
0xe541  ldc.i4.1
0xe542  newarr   [mscorlib]System.Object
0xe547  stloc.s  4
0xe549  ldloc.s  4
0xe54b  ldc.i4.0
0xe54c  ldloc.0
0xe54d  stelem.ref
0xe54e  ldloc.s  4
0xe550  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xe555  br.s     loc_E5C2
0xe557  ldc.i4.0
0xe558  ldloc.2
0xe559  ldloc.1
0xe55a  sub
0xe55b  ldc.i4.1
0xe55c  sub
0xe55d  dup
0xe55e  stloc.3
0xe55f  bge.s    loc_E5A1
0xe561  ldarg.0
0xe562  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe567  ldloc.1
0xe568  ldc.i4.1
0xe569  add
0xe56a  ldloc.3
0xe56b  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xe570  stloc.0
0xe571  ldc.i4   0xDB414
0xe576  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe57b  ldc.i4   0xC8
0xe580  ldarg.1
0xe581  ldstr    aUsingRoleProvi_0// "Using role provider.  Name: '{0}'."
0xe586  call     string [mscorlib]System.String::Concat(string, string)
0xe58b  ldc.i4.1
0xe58c  newarr   [mscorlib]System.Object
0xe591  stloc.s  5
0xe593  ldloc.s  5
0xe595  ldc.i4.0
0xe596  ldloc.0
0xe597  stelem.ref
0xe598  ldloc.s  5
0xe59a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xe59f  br.s     loc_E5C2
0xe5a1  ldnull
0xe5a2  stloc.0
0xe5a3  ldc.i4   0xDB415
0xe5a8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe5ad  ldc.i4   0xC8
0xe5b2  ldarg.1
0xe5b3  ldstr    aNotUsingARoleP_1// "Not using a role provider."
0xe5b8  call     string [mscorlib]System.String::Concat(string, string)
0xe5bd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe5c2  ldloc.0
0xe5c3  ret
```
