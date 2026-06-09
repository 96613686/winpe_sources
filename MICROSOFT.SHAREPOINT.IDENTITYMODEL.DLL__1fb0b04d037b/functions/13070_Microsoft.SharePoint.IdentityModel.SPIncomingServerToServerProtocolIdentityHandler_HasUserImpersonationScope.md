# Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::HasUserImpersonationScope

- ea: `0x13070`
- end: `0x130c0`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::HasUserImpersonationScope`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140a0`

## callees

- `0x13070`

## string_xrefs

- `0x130b2`: `user_impersonation`
- `0x13073`: `claimsIdentity`
- `0x130a0`: `SPIncomingServerToServerProtocolIdentityHandler identity doesn't have scope claim`

## pseudocode

```c

```

## disassembly

```asm
0x13070  ldarg.0
0x13071  brtrue.s loc_1307E
0x13073  ldstr    aClaimsidentity// "claimsIdentity"
0x13078  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1307d  throw
0x1307e  ldarg.0
0x1307f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x13084  ldstr    aScp// "scp"
0x13089  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1308e  stloc.0
0x1308f  ldc.i4.0
0x13090  stloc.1
0x13091  ldloc.0
0x13092  brtrue.s loc_130AC
0x13094  ldc.i4   0x5DD15A
0x13099  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1309e  ldc.i4.s 0x64
0x130a0  ldstr    aSpincomingserv// "SPIncomingServerToServerProtocolIdentit"...
0x130a5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x130aa  br.s     loc_130BE
0x130ac  ldloc.0
0x130ad  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x130b2  ldstr    aUserImpersonat// "user_impersonation"
0x130b7  ldc.i4.5
0x130b8  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x130bd  stloc.1
0x130be  ldloc.1
0x130bf  ret
```
