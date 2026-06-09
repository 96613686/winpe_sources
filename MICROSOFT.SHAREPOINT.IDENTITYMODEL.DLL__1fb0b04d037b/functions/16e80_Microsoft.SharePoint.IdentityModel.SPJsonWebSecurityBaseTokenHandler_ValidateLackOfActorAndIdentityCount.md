# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateLackOfActorAndIdentityCount

- ea: `0x16e80`
- end: `0x16fa5`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateLackOfActorAndIdentityCount`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x16a10`

## callees

- `0x169b0`
- `0x169c0`
- `0x16e80`
- `0x2c520`

## string_xrefs

- `0x16e8f`: `token`
- `0x16ea9`: `tokenIdentities`
- `0x16ec9`: `Json token has inccorect number of identities. Count: '{0}', Mode: '{1}'.`
- `0x16f12`: `Json token's identity to validate is null. Mode: '{0}'.`
- `0x16f52`: `Json token's identity has an actor which is unsupported. Mode: '{0}'.`
- `0x16f84`: `Json token has a single identity without actors. Mode: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x16e80  ldc.i4   0x1186052
0x16e85  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x16e8a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16e8f  ldstr    aToken// "token"
0x16e94  ldarg.1
0x16e95  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x16e9a  ldc.i4   0x1186053
0x16e9f  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x16ea4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16ea9  ldstr    aTokenidentitie// "tokenIdentities"
0x16eae  ldarg.2
0x16eaf  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x16eb4  ldc.i4.1
0x16eb5  ldarg.2
0x16eb6  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x16ebb  beq.s    loc_16EFD
0x16ebd  ldc.i4   0x1186054
0x16ec2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16ec7  ldc.i4.s 0xA
0x16ec9  ldstr    aJsonTokenHasIn// "Json token has inccorect number of iden"...
0x16ece  ldc.i4.2
0x16ecf  newarr   [mscorlib]System.Object
0x16ed4  stloc.0
0x16ed5  ldloc.0
0x16ed6  ldc.i4.0
0x16ed7  ldarg.2
0x16ed8  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x16edd  box      [mscorlib]System.Int32
0x16ee2  stelem.ref
0x16ee3  ldloc.0
0x16ee4  ldc.i4.1
0x16ee5  ldarg.0
0x16ee6  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Mode()
0x16eeb  box      Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode
0x16ef0  stelem.ref
0x16ef1  ldloc.0
0x16ef2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16ef7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x16efc  throw
0x16efd  ldarg.2
0x16efe  ldc.i4.0
0x16eff  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x16f04  brtrue.s loc_16F38
0x16f06  ldc.i4   0x1186055
0x16f0b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16f10  ldc.i4.s 0xA
0x16f12  ldstr    aJsonTokenSIden_2// "Json token's identity to validate is nu"...
0x16f17  ldc.i4.1
0x16f18  newarr   [mscorlib]System.Object
0x16f1d  stloc.1
0x16f1e  ldloc.1
0x16f1f  ldc.i4.0
0x16f20  ldarg.0
0x16f21  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Mode()
0x16f26  box      Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode
0x16f2b  stelem.ref
0x16f2c  ldloc.1
0x16f2d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16f32  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x16f37  throw
0x16f38  ldarg.2
0x16f39  ldc.i4.0
0x16f3a  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x16f3f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x16f44  brfalse.s loc_16F78
0x16f46  ldc.i4   0x1186056
0x16f4b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16f50  ldc.i4.s 0xA
0x16f52  ldstr    aJsonTokenSIden_3// "Json token's identity has an actor whic"...
0x16f57  ldc.i4.1
0x16f58  newarr   [mscorlib]System.Object
0x16f5d  stloc.2
0x16f5e  ldloc.2
0x16f5f  ldc.i4.0
0x16f60  ldarg.0
0x16f61  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Mode()
0x16f66  box      Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode
0x16f6b  stelem.ref
0x16f6c  ldloc.2
0x16f6d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16f72  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x16f77  throw
0x16f78  ldc.i4   0x1186057
0x16f7d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16f82  ldc.i4.s 0x64
0x16f84  ldstr    aJsonTokenHasAS// "Json token has a single identity withou"...
0x16f89  ldc.i4.1
0x16f8a  newarr   [mscorlib]System.Object
0x16f8f  stloc.3
0x16f90  ldloc.3
0x16f91  ldc.i4.0
0x16f92  ldarg.0
0x16f93  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Mode()
0x16f98  box      Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode
0x16f9d  stelem.ref
0x16f9e  ldloc.3
0x16f9f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16fa4  ret
```
