# Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::CreateBackGroundSession

- ea: `0x38540`
- end: `0x38669`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::CreateBackGroundSession`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x381a0`

## callees

- `0x12110`
- `0x12840`
- `0x1cd50`
- `0x1ce20`
- `0x37920`
- `0x37940`
- `0x37960`
- `0x38540`
- `0x4d100`
- `0x4d410`

## string_xrefs

- `0x38541`: `CreateBackGroundSession`
- `0x3865d`: `CreateBackGroundSession`

## pseudocode

```c

```

## disassembly

```asm
0x38540  ldarg.0
0x38541  ldstr    aCreatebackgrou// "CreateBackGroundSession"
0x38546  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x3854b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x38550  stloc.0
0x38551  ldloca.s 1
0x38553  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventLogin
0x38559  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3855e  stloc.2
0x3855f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x38564  pop
0x38565  ldarg.0
0x38566  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::remoteComputer
0x3856b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x38570  brtrue.s loc_385CF
0x38572  ldloca.s 1
0x38574  ldarg.0
0x38575  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::remoteComputer
0x3857a  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToCoTaskMemUni(string)
0x3857f  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventLogin::Server
0x38584  ldarg.0
0x38585  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_UserName()
0x3858a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3858f  brtrue.s loc_385CF
0x38591  ldloca.s 1
0x38593  ldarg.0
0x38594  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_UserDomain()
0x38599  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToCoTaskMemUni(string)
0x3859e  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventLogin::Domain
0x385a3  ldloca.s 1
0x385a5  ldarg.0
0x385a6  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_UserName()
0x385ab  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToCoTaskMemUni(string)
0x385b0  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventLogin::User
0x385b5  ldarg.0
0x385b6  call     instance class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_EncryptedPassword()
0x385bb  brfalse.s loc_385CF
0x385bd  ldloca.s 1
0x385bf  ldarg.0
0x385c0  call     instance class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_EncryptedPassword()
0x385c5  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::SecureStringToCoTaskMemUnicode(class [mscorlib]System.Security.SecureString)
0x385ca  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventLogin::Password
0x385cf  ldloc.1
0x385d0  box      Microsoft.Windows.ManagementUI.CombinedControls.EventLogin
0x385d5  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x385da  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x385df  stloc.2
0x385e0  ldloc.1
0x385e1  box      Microsoft.Windows.ManagementUI.CombinedControls.EventLogin
0x385e6  ldloc.2
0x385e7  ldc.i4.1
0x385e8  call     void [mscorlib]System.Runtime.InteropServices.Marshal::StructureToPtr(object, native int, bool)
0x385ed  ldc.i4.1
0x385ee  ldloc.2
0x385ef  ldc.i4.0
0x385f0  ldc.i4.0
0x385f1  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::OpenSession([hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventLoginClass loginclass, native int login, int32 timeout, int32 flags)
0x385f6  stloc.0
0x385f7  ldloc.0
0x385f8  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x385fd  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x38602  brfalse.s loc_3860C
0x38604  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x38609  pop
0x3860a  leave.s  loc_38668
0x3860c  ldarg.0
0x3860d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::backGroundSession
0x38612  ldloc.0
0x38613  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::InitHandle(native int crimsonHandle)
0x38618  leave.s  loc_38668
0x3861a  ldloca.s 1
0x3861c  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventLogin::Dispose()
0x38621  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x38626  ldloc.2
0x38627  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x3862c  brfalse.s loc_3865B
0x3862e  ldloc.2
0x3862f  ldloc.1
0x38630  box      Microsoft.Windows.ManagementUI.CombinedControls.EventLogin
0x38635  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x3863a  call     void Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::SecureZeroMemory(native int handle, unsigned int32 length)
0x3863f  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x38644  pop
0x38645  ldloc.2
0x38646  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventLogin
0x3864b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x38650  call     void [mscorlib]System.Runtime.InteropServices.Marshal::DestroyStructure(native int, class [mscorlib]System.Type)
0x38655  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3865a  pop
0x3865b  endfinally
0x3865c  ldarg.0
0x3865d  ldstr    aCreatebackgrou// "CreateBackGroundSession"
0x38662  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x38667  endfinally
0x38668  ret
```
