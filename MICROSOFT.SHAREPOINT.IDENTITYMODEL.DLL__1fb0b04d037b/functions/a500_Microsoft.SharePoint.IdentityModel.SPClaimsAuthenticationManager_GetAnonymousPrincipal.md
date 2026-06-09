# Microsoft.SharePoint.IdentityModel.SPClaimsAuthenticationManager::GetAnonymousPrincipal

- ea: `0xa500`
- end: `0xa637`
- name: `Microsoft.SharePoint.IdentityModel.SPClaimsAuthenticationManager::GetAnonymousPrincipal`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xa400`

## callees

- `0xa500`

## string_xrefs

- `0xa53a`: `SPClaimsAuthenticationManager failed to preserve original thread token: Exception '{0}'.`
- `0xa573`: `SPClaimsAuthenticationManager failed to impersonate anonymous user: Exception '{0}'.`
- `0xa5b9`: `SPClaimsAuthenticationManager failed to revert to original WindowsIdentity: Exception '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0xa500  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xa505  stloc.0
0xa506  call     native int [Microsoft.SharePoint]Microsoft.SharePoint.Win32.SPKernel32::GetCurrentThread()
0xa50b  ldc.i4.4
0xa50c  ldc.i4.1
0xa50d  ldloca.s 0
0xa50f  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Win32.SPAdvApi32/UnsafeNativeMethods::OpenThreadToken(native int, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Win32.SPAdvApi32/TokenAccessRights, bool, native int&)
0xa514  brtrue.s loc_A52B
0xa516  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0xa51b  stloc.1
0xa51c  ldc.i4   0x3F0
0xa521  ldloc.1
0xa522  beq.s    loc_A52B
0xa524  ldloc.1
0xa525  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0xa52a  throw
0xa52b  leave.s  loc_A555
0xa52d  stloc.2
0xa52e  ldc.i4   0x666C3665
0xa533  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xa538  ldc.i4.s 0x32
0xa53a  ldstr    aSpclaimsauthen_0// "SPClaimsAuthenticationManager failed to"...
0xa53f  ldc.i4.1
0xa540  newarr   [mscorlib]System.Object
0xa545  stloc.s  7
0xa547  ldloc.s  7
0xa549  ldc.i4.0
0xa54a  ldloc.2
0xa54b  stelem.ref
0xa54c  ldloc.s  7
0xa54e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xa553  rethrow
0xa555  ldnull
0xa556  stloc.3
0xa557  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Win32.SPAdvApi32::ImpersonateAnonymousToken()
0xa55c  pop
0xa55d  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0xa562  stloc.3
0xa563  leave.s  loc_A58F
0xa565  stloc.s  4
0xa567  ldc.i4   0x666C3666
0xa56c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xa571  ldc.i4.s 0x32
0xa573  ldstr    aSpclaimsauthen_1// "SPClaimsAuthenticationManager failed to"...
0xa578  ldc.i4.1
0xa579  newarr   [mscorlib]System.Object
0xa57e  stloc.s  8
0xa580  ldloc.s  8
0xa582  ldc.i4.0
0xa583  ldloc.s  4
0xa585  stelem.ref
0xa586  ldloc.s  8
0xa588  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xa58d  rethrow
0xa58f  leave.s  loc_A5D6
0xa591  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xa596  ldloc.0
0xa597  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Win32.SPAdvApi32/UnsafeNativeMethods::SetThreadToken(native int, native int)
0xa59c  brtrue.s loc_A5A9
0xa59e  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0xa5a3  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0xa5a8  throw
0xa5a9  leave.s  loc_A5D5
0xa5ab  stloc.s  5
0xa5ad  ldc.i4   0x666C3667
0xa5b2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xa5b7  ldc.i4.s 0x32
0xa5b9  ldstr    aSpclaimsauthen_2// "SPClaimsAuthenticationManager failed to"...
0xa5be  ldc.i4.1
0xa5bf  newarr   [mscorlib]System.Object
0xa5c4  stloc.s  9
0xa5c6  ldloc.s  9
0xa5c8  ldc.i4.0
0xa5c9  ldloc.s  5
0xa5cb  stelem.ref
0xa5cc  ldloc.s  9
0xa5ce  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xa5d3  rethrow
0xa5d5  endfinally
0xa5d6  ldloc.3
0xa5d7  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.WindowsClaimsPrincipal::.ctor(class [mscorlib]System.Security.Principal.WindowsIdentity)
0xa5dc  stloc.s  6
0xa5de  ldloc.s  6
0xa5e0  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xa5e5  castclass [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity
0xa5ea  ldarg.0
0xa5eb  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0xa5f0  ldc.i4.0
0xa5f1  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0xa5f6  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0xa5fb  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::set_Actor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity)
0xa600  ldloc.s  6
0xa602  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xa607  castclass [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity
0xa60c  ldarg.0
0xa60d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0xa612  ldc.i4.0
0xa613  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0xa618  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_BootstrapToken()
0xa61d  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::set_BootstrapToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0xa622  ldloc.s  6
0xa624  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xa629  castclass [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity
0xa62e  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0xa633  pop
0xa634  ldloc.s  6
0xa636  ret
```
