# Microsoft.SharePoint.IdentityModel.SPWindowsClaimsAuthenticationHttpModule::GetWindowsIdentityFromContext

- ea: `0x273f0`
- end: `0x27592`
- name: `Microsoft.SharePoint.IdentityModel.SPWindowsClaimsAuthenticationHttpModule::GetWindowsIdentityFromContext`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x26910`

## callees

- `0x273f0`

## string_xrefs

- `0x27479`: `Can't instantiate WindowsIdentity for user <name>'{0}'</name> and authentication type '{1}'. ClaimsIdentity IsAuthenticated '{2}'`
- `0x274e2`: `Successfully instantiate WindowsIdentity for user <name>'{0}'</name> and authentication type '{1}'.`
- `0x27512`: `Can't instantiate WindowsIdentity for user <name>'{0}'</name> and authentication type '{1}'.`
- `0x27572`: `Can't instantiate WindowsIdentity for user <name>'{0}'</name> and authentication type '{1}'.`
- `0x27540`: `Can't instantiate WindowsIdentity for user <name>'{0}'</name> and authentication type '{1}'. Http worker request '{2}'`

## pseudocode

```c

```

## disassembly

```asm
0x273f0  ldarg.1
0x273f1  brfalse.s loc_273FB
0x273f3  ldarg.1
0x273f4  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x273f9  brtrue.s loc_273FD
0x273fb  ldnull
0x273fc  ret
0x273fd  ldnull
0x273fe  stloc.0
0x273ff  ldarg.1
0x27400  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x27405  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_ServerVariables()
0x2740a  ldstr    aLogonUser// "LOGON_USER"
0x2740f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x27414  stloc.1
0x27415  ldarg.1
0x27416  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2741b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_ServerVariables()
0x27420  ldstr    aAuthType// "AUTH_TYPE"
0x27425  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2742a  stloc.2
0x2742b  ldloc.1
0x2742c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x27431  brtrue   loc_27566
0x27436  ldloc.2
0x27437  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2743c  brtrue   loc_27566
0x27441  ldloc.2
0x27442  ldstr    aFederation_0// "Federation"
0x27447  ldc.i4.5
0x27448  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2744d  brtrue   loc_27566
0x27452  call     class [mscorlib]System.Security.Principal.IPrincipal [mscorlib]System.Threading.Thread::get_CurrentPrincipal()
0x27457  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x2745c  isinst   [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity
0x27461  stloc.3
0x27462  ldloc.3
0x27463  brfalse.s loc_274AB
0x27465  ldloc.3
0x27466  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0x2746b  brfalse.s loc_274AB
0x2746d  ldc.i4   0x2098315
0x27472  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x27477  ldc.i4.s 0x64
0x27479  ldstr    aCanTInstantiat// "Can't instantiate WindowsIdentity for u"...
0x2747e  ldc.i4.3
0x2747f  newarr   [mscorlib]System.Object
0x27484  stloc.s  5
0x27486  ldloc.s  5
0x27488  ldc.i4.0
0x27489  ldloc.1
0x2748a  stelem.ref
0x2748b  ldloc.s  5
0x2748d  ldc.i4.1
0x2748e  ldloc.2
0x2748f  stelem.ref
0x27490  ldloc.s  5
0x27492  ldc.i4.2
0x27493  ldloc.3
0x27494  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0x27499  box      [mscorlib]System.Boolean
0x2749e  stelem.ref
0x2749f  ldloc.s  5
0x274a1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x274a6  br       loc_27590
0x274ab  ldarg.1
0x274ac  ldtoken  [System.Web]System.Web.HttpWorkerRequest
0x274b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x274b6  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x274bb  isinst   [System.Web]System.Web.HttpWorkerRequest
0x274c0  stloc.s  4
0x274c2  ldloc.s  4
0x274c4  brfalse.s loc_27534
0x274c6  ldloc.s  4
0x274c8  callvirt instance native int [System.Web]System.Web.HttpWorkerRequest::GetUserToken()
0x274cd  ldloc.2
0x274ce  ldc.i4.0
0x274cf  ldc.i4.1
0x274d0  newobj   instance void [mscorlib]System.Security.Principal.WindowsIdentity::.ctor(native int, string, valuetype [mscorlib]System.Security.Principal.WindowsAccountType, bool)
0x274d5  stloc.0
0x274d6  ldc.i4   0x2098316
0x274db  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x274e0  ldc.i4.s 0x64
0x274e2  ldstr    aSuccessfullyIn// "Successfully instantiate WindowsIdentit"...
0x274e7  ldc.i4.2
0x274e8  newarr   [mscorlib]System.Object
0x274ed  stloc.s  6
0x274ef  ldloc.s  6
0x274f1  ldc.i4.0
0x274f2  ldloc.1
0x274f3  stelem.ref
0x274f4  ldloc.s  6
0x274f6  ldc.i4.1
0x274f7  ldloc.2
0x274f8  stelem.ref
0x274f9  ldloc.s  6
0x274fb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x27500  leave    loc_27590
0x27505  pop
0x27506  ldc.i4   0x67346939
0x2750b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x27510  ldc.i4.s 0x32
0x27512  ldstr    aCanTInstantiat_0// "Can't instantiate WindowsIdentity for u"...
0x27517  ldc.i4.2
0x27518  newarr   [mscorlib]System.Object
0x2751d  stloc.s  7
0x2751f  ldloc.s  7
0x27521  ldc.i4.0
0x27522  ldloc.1
0x27523  stelem.ref
0x27524  ldloc.s  7
0x27526  ldc.i4.1
0x27527  ldloc.2
0x27528  stelem.ref
0x27529  ldloc.s  7
0x2752b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x27530  ldnull
0x27531  stloc.0
0x27532  leave.s  loc_27590
0x27534  ldc.i4   0x2098317
0x27539  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2753e  ldc.i4.s 0x64
0x27540  ldstr    aCanTInstantiat_1// "Can't instantiate WindowsIdentity for u"...
0x27545  ldc.i4.3
0x27546  newarr   [mscorlib]System.Object
0x2754b  stloc.s  8
0x2754d  ldloc.s  8
0x2754f  ldc.i4.0
0x27550  ldloc.1
0x27551  stelem.ref
0x27552  ldloc.s  8
0x27554  ldc.i4.1
0x27555  ldloc.2
0x27556  stelem.ref
0x27557  ldloc.s  8
0x27559  ldc.i4.2
0x2755a  ldloc.s  4
0x2755c  stelem.ref
0x2755d  ldloc.s  8
0x2755f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x27564  br.s     loc_27590
0x27566  ldc.i4   0x2098318
0x2756b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x27570  ldc.i4.s 0x64
0x27572  ldstr    aCanTInstantiat_0// "Can't instantiate WindowsIdentity for u"...
0x27577  ldc.i4.2
0x27578  newarr   [mscorlib]System.Object
0x2757d  stloc.s  9
0x2757f  ldloc.s  9
0x27581  ldc.i4.0
0x27582  ldloc.1
0x27583  stelem.ref
0x27584  ldloc.s  9
0x27586  ldc.i4.1
0x27587  ldloc.2
0x27588  stelem.ref
0x27589  ldloc.s  9
0x2758b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x27590  ldloc.0
0x27591  ret
```
