# ImplementedSecurityCallback::SetSecurity

- ea: `0x9fb00`
- end: `0x9fba9`
- name: `ImplementedSecurityCallback::SetSecurity`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x10c60`
- `0x121e0`
- `0x133f0`
- `0x13510`
- `0x4d0f0`
- `0x9fb00`
- `0x9fc20`

## string_xrefs

- `0x9fb3b`: `Error in ConvertStringSecurityDescriptorToSecurityDescriptor`
- `0x9fb6e`: `Error after ConvertStringSecurityDescriptorToSecurityDescriptor in LocalFree`
- `0x9fb8a`: `SetSecurity Error`

## pseudocode

```c

```

## disassembly

```asm
0x9fb00  ldsfld   string [mscorlib]System.String::Empty
0x9fb05  stloc.0
0x9fb06  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9fb0b  stloc.1
0x9fb0c  ldc.i4.0
0x9fb0d  stloc.2
0x9fb0e  ldc.i4.0
0x9fb0f  stloc.3
0x9fb10  ldarg.0
0x9fb11  ldarg.1
0x9fb12  ldarg.2
0x9fb13  call     instance void ImplementedSecurityCallback::SetSecurityInt(valuetype Microsoft.Windows.ManagementUI.CombinedControls.SECURITY_INFORMATION securityInformation, native int securityDescriptior)
0x9fb18  ldc.i4.s 0xF
0x9fb1a  stloc.s  4
0x9fb1c  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fb21  ldarg.0
0x9fb22  ldfld    native int ImplementedSecurityCallback::currentSecurityDescriptior
0x9fb27  ldc.i4.1
0x9fb28  ldloc.s  4
0x9fb2a  ldloca.s 1
0x9fb2c  ldloca.s 2
0x9fb2e  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::ConvertSecurityDescriptorToStringSecurityDescriptor(native int SecurityDescriptor, unsigned int32 RequestedStringSDRevision, unsigned int32 SecurityInformation, [out] native int& StringSecurityDescriptor, [out] unsigned int32& StringSecurityDescriptorLen)
0x9fb33  bne.un.s loc_9FB4F
0x9fb35  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x9fb3a  stloc.3
0x9fb3b  ldstr    aErrorInConvert// "Error in ConvertStringSecurityDescripto"...
0x9fb40  ldloc.3
0x9fb41  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x9fb46  ldsfld   unsigned int32 ImplementedSecurityCallback::E_FAIL
0x9fb4b  stloc.s  5
0x9fb4d  leave.s  loc_9FBA6
0x9fb4f  ldloc.1
0x9fb50  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0x9fb55  stloc.0
0x9fb56  ldloc.1
0x9fb57  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::LocalFree(native int ptr)
0x9fb5c  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9fb61  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x9fb66  brfalse.s loc_9FB79
0x9fb68  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x9fb6d  stloc.3
0x9fb6e  ldstr    aErrorAfterConv// "Error after ConvertStringSecurityDescri"...
0x9fb73  ldloc.3
0x9fb74  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x9fb79  ldarg.0
0x9fb7a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ISecurityInfoInternal ImplementedSecurityCallback::securityInfo
0x9fb7f  ldarg.1
0x9fb80  ldloc.0
0x9fb81  callvirt instance unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.ISecurityInfoInternal::SetSecurity(valuetype Microsoft.Windows.ManagementUI.CombinedControls.SECURITY_INFORMATION SecurityInformation, string SddlString)
0x9fb86  stloc.s  5
0x9fb88  leave.s  loc_9FBA6
0x9fb8a  ldstr    aSetsecurityErr// "SetSecurity Error"
0x9fb8f  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x9fb94  callvirt instance string [mscorlib]System.Object::ToString()
0x9fb99  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x9fb9e  leave.s  loc_9FBA0
0x9fba0  ldsfld   unsigned int32 ImplementedSecurityCallback::E_FAIL
0x9fba5  ret
0x9fba6  ldloc.s  5
0x9fba8  ret
```
