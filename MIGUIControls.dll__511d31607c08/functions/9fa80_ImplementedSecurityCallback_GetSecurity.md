# ImplementedSecurityCallback::GetSecurity

- ea: `0x9fa80`
- end: `0x9faf9`
- name: `ImplementedSecurityCallback::GetSecurity`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x10c50`
- `0x121f0`
- `0x133f0`
- `0x13510`
- `0x9f9c0`
- `0x9fa80`

## string_xrefs

- `0x9fab8`: `Error in ConvertStringSecurityDescriptorToSecurityDescriptor`
- `0x9fadb`: `GetSecurity Error`

## pseudocode

```c

```

## disassembly

```asm
0x9fa80  ldarg.2
0x9fa81  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9fa86  stind.i
0x9fa87  ldarg.0
0x9fa88  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ISecurityInfoInternal ImplementedSecurityCallback::securityInfo
0x9fa8d  ldarg.1
0x9fa8e  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ISecurityInfoInternal::GetSecurity(valuetype Microsoft.Windows.ManagementUI.CombinedControls.SECURITY_INFORMATION RequestedInformation)
0x9fa93  stloc.0
0x9fa94  ldc.i4.0
0x9fa95  stloc.1
0x9fa96  ldarg.0
0x9fa97  call     instance void ImplementedSecurityCallback::CleanObject()
0x9fa9c  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9faa1  ldloc.0
0x9faa2  ldc.i4.1
0x9faa3  ldarg.0
0x9faa4  ldflda   native int ImplementedSecurityCallback::currentSecurityDescriptior
0x9faa9  ldloca.s 1
0x9faab  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::ConvertStringSecurityDescriptorToSecurityDescriptor(string StringSecurityDescriptor, unsigned int32 StringSDRevision, [out] native int& SecurityDescriptor, [out] unsigned int32& SecurityDescriptorSize)
0x9fab0  bne.un.s loc_9FACB
0x9fab2  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x9fab7  stloc.2
0x9fab8  ldstr    aErrorInConvert// "Error in ConvertStringSecurityDescripto"...
0x9fabd  ldloc.2
0x9fabe  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x9fac3  ldsfld   unsigned int32 ImplementedSecurityCallback::E_FAIL
0x9fac8  stloc.3
0x9fac9  leave.s  loc_9FAF7
0x9facb  ldarg.2
0x9facc  ldarg.0
0x9facd  ldfld    native int ImplementedSecurityCallback::currentSecurityDescriptior
0x9fad2  stind.i
0x9fad3  ldsfld   unsigned int32 ImplementedSecurityCallback::S_OK
0x9fad8  stloc.3
0x9fad9  leave.s  loc_9FAF7
0x9fadb  ldstr    aGetsecurityErr// "GetSecurity Error"
0x9fae0  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x9fae5  callvirt instance string [mscorlib]System.Object::ToString()
0x9faea  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x9faef  ldsfld   unsigned int32 ImplementedSecurityCallback::E_FAIL
0x9faf4  stloc.3
0x9faf5  leave.s  loc_9FAF7
0x9faf7  ldloc.3
0x9faf8  ret
```
