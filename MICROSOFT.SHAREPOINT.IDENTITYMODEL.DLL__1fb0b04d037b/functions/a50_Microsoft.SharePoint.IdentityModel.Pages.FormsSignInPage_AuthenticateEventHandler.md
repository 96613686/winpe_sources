# Microsoft.SharePoint.IdentityModel.Pages.FormsSignInPage::AuthenticateEventHandler

- ea: `0xa50`
- end: `0xbcb`
- name: `Microsoft.SharePoint.IdentityModel.Pages.FormsSignInPage::AuthenticateEventHandler`
- size: `379`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x70`
- `0x150`
- `0x2c0`
- `0x850`
- `0xa20`
- `0xa50`
- `0xcc0`
- `0xcd0`

## string_xrefs

- `0xa98`: `Attempting to sign-in user '{0}'.`
- `0xabb`: `FormsSignInPage.AuthenticateEventHandler: Retrieve security token and establish session.`
- `0xae4`: `Failed to get token for user '{0}' from Security Token Service Sign-In attempt terminated.`

## pseudocode

```c

```

## disassembly

```asm
0xa50  ldarg.1
0xa51  brtrue.s loc_A5E
0xa53  ldstr    aSender// "sender"
0xa58  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa5d  throw
0xa5e  ldarg.2
0xa5f  brtrue.s loc_A6C
0xa61  ldstr    aFormauthentica// "formAuthenticateEventArgs"
0xa66  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa6b  throw
0xa6c  ldc.i4.0
0xa6d  stloc.0
0xa6e  ldarg.1
0xa6f  isinst   [System.Web]System.Web.UI.WebControls.Login
0xa74  stloc.1
0xa75  ldnull
0xa76  stloc.2
0xa77  ldloc.1
0xa78  brtrue.s loc_A86
0xa7a  ldnull
0xa7b  ldstr    aSender// "sender"
0xa80  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xa85  throw
0xa86  ldc.i4   0x15D5C4
0xa8b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xa90  ldc.i4.s 0x64
0xa92  ldarg.0
0xa93  callvirt instance string Microsoft.SharePoint.IdentityModel.Pages.IdentityModelSignInPageBase::get_LogPrefix()
0xa98  ldstr    aAttemptingToSi// "Attempting to sign-in user '{0}'."
0xa9d  call     string [mscorlib]System.String::Concat(string, string)
0xaa2  ldc.i4.1
0xaa3  newarr   [mscorlib]System.Object
0xaa8  stloc.s  5
0xaaa  ldloc.s  5
0xaac  ldc.i4.0
0xaad  ldloc.1
0xaae  callvirt instance string [System.Web]System.Web.UI.WebControls.Login::get_UserName()
0xab3  stelem.ref
0xab4  ldloc.s  5
0xab6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xabb  ldstr    aFormssigninpag// "FormsSignInPage.AuthenticateEventHandle"...
0xac0  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0xac5  stloc.s  6
0xac7  ldarg.0
0xac8  ldloc.1
0xac9  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.Pages.FormsSignInPage::GetSecurityToken(class [System.Web]System.Web.UI.WebControls.Login formsSignInControl)
0xace  dup
0xacf  stloc.2
0xad0  brtrue.s loc_B0E
0xad2  ldc.i4   0x15D5C5
0xad7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xadc  ldc.i4.s 0x64
0xade  ldarg.0
0xadf  callvirt instance string Microsoft.SharePoint.IdentityModel.Pages.IdentityModelSignInPageBase::get_LogPrefix()
0xae4  ldstr    aFailedToGetTok// "Failed to get token for user '{0}' from"...
0xae9  call     string [mscorlib]System.String::Concat(string, string)
0xaee  ldc.i4.1
0xaef  newarr   [mscorlib]System.Object
0xaf4  stloc.s  7
0xaf6  ldloc.s  7
0xaf8  ldc.i4.0
0xaf9  ldloc.1
0xafa  callvirt instance string [System.Web]System.Web.UI.WebControls.Login::get_UserName()
0xaff  stelem.ref
0xb00  ldloc.s  7
0xb02  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xb07  ldc.i4.0
0xb08  stloc.0
0xb09  br       loc_B98
0xb0e  ldarg.0
0xb0f  ldloc.1
0xb10  callvirt instance valuetype Microsoft.SharePoint.IdentityModel.SPSessionTokenWriteType Microsoft.SharePoint.IdentityModel.Pages.FormsSignInPage::GetSessionTokenWriteType(class [System.Web]System.Web.UI.WebControls.Login formsSignInControl)
0xb15  stloc.3
0xb16  ldarg.0
0xb17  ldloc.2
0xb18  ldloc.3
0xb19  callvirt instance void Microsoft.SharePoint.IdentityModel.Pages.IdentityModelSignInPageBase::EstablishSessionWithToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken securityToken, valuetype Microsoft.SharePoint.IdentityModel.SPSessionTokenWriteType sessionCookie)
0xb1e  ldc.i4   0x15D5C6
0xb23  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb28  ldc.i4.s 0x64
0xb2a  ldarg.0
0xb2b  callvirt instance string Microsoft.SharePoint.IdentityModel.Pages.IdentityModelSignInPageBase::get_LogPrefix()
0xb30  ldstr    aSuccesfullySig// "Succesfully signed-in user '{0}'."
0xb35  call     string [mscorlib]System.String::Concat(string, string)
0xb3a  ldc.i4.1
0xb3b  newarr   [mscorlib]System.Object
0xb40  stloc.s  8
0xb42  ldloc.s  8
0xb44  ldc.i4.0
0xb45  ldloc.1
0xb46  callvirt instance string [System.Web]System.Web.UI.WebControls.Login::get_UserName()
0xb4b  stelem.ref
0xb4c  ldloc.s  8
0xb4e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xb53  ldc.i4.1
0xb54  stloc.0
0xb55  leave.s  loc_B98
0xb57  stloc.s  4
0xb59  ldc.i4   0x15D5C7
0xb5e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb63  ldc.i4.s 0xA
0xb65  ldarg.0
0xb66  callvirt instance string Microsoft.SharePoint.IdentityModel.Pages.IdentityModelSignInPageBase::get_LogPrefix()
0xb6b  ldstr    aFailedToSignIn// "Failed to sign-in user '{0}'. Exception"...
0xb70  call     string [mscorlib]System.String::Concat(string, string)
0xb75  ldc.i4.2
0xb76  newarr   [mscorlib]System.Object
0xb7b  stloc.s  9
0xb7d  ldloc.s  9
0xb7f  ldc.i4.0
0xb80  ldloc.1
0xb81  callvirt instance string [System.Web]System.Web.UI.WebControls.Login::get_UserName()
0xb86  stelem.ref
0xb87  ldloc.s  9
0xb89  ldc.i4.1
0xb8a  ldloc.s  4
0xb8c  stelem.ref
0xb8d  ldloc.s  9
0xb8f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xb94  ldc.i4.0
0xb95  stloc.0
0xb96  leave.s  loc_B98
0xb98  leave.s  loc_BAC
0xb9a  ldloc.0
0xb9b  brfalse.s loc_BA5
0xb9d  ldarg.0
0xb9e  callvirt instance void Microsoft.SharePoint.IdentityModel.Pages.FormsSignInPage::LogSignInSuccess()
0xba3  br.s     loc_BAB
0xba5  ldarg.0
0xba6  callvirt instance void Microsoft.SharePoint.IdentityModel.Pages.FormsSignInPage::LogSignInFailure()
0xbab  endfinally
0xbac  leave.s  loc_BBA
0xbae  ldloc.s  6
0xbb0  brfalse.s loc_BB9
0xbb2  ldloc.s  6
0xbb4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbb9  endfinally
0xbba  ldarg.2
0xbbb  ldloc.0
0xbbc  callvirt instance void [System.Web]System.Web.UI.WebControls.AuthenticateEventArgs::set_Authenticated(bool)
0xbc1  ldloc.0
0xbc2  brfalse.s loc_BCA
0xbc4  ldarg.0
0xbc5  callvirt instance void Microsoft.SharePoint.IdentityModel.Pages.IdentityModelSignInPageBase::RedirectToSuccessUrl()
0xbca  ret
```
