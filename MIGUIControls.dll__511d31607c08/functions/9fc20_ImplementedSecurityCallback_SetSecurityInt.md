# ImplementedSecurityCallback::SetSecurityInt

- ea: `0x9fc20`
- end: `0x9fdba`
- name: `ImplementedSecurityCallback::SetSecurityInt`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x9fb00`

## callees

- `0x12200`
- `0x12210`
- `0x12220`
- `0x12230`
- `0x12250`
- `0x12260`
- `0x12270`
- `0x12280`
- `0x13510`
- `0x9fc20`

## string_xrefs

- `0x9fc82`: `Error after NativeMethods.GetSecurityDescriptorDacl`
- `0x9fcac`: `Error after NativeMethods.SetSecurityDescriptorDacl`
- `0x9fd04`: `Error after NativeMethods.SetSecurityDescriptorDacl`
- `0x9fd59`: `Error after NativeMethods.SetSecurityDescriptorDacl`
- `0x9fdad`: `Error after NativeMethods.SetSecurityDescriptorDacl`
- `0x9fcd8`: `Error after NativeMethods.GetSecurityDescriptorSacl`
- `0x9fd2e`: `Error after NativeMethods.GetSecurityDescriptorSacl`
- `0x9fd83`: `Error after NativeMethods.GetSecurityDescriptorSacl`

## pseudocode

```c

```

## disassembly

```asm
0x9fc20  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9fc25  stloc.0
0x9fc26  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fc2b  stloc.1
0x9fc2c  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fc31  stloc.2
0x9fc32  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9fc37  stloc.3
0x9fc38  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fc3d  stloc.s  4
0x9fc3f  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fc44  stloc.s  5
0x9fc46  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9fc4b  stloc.s  6
0x9fc4d  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fc52  stloc.s  7
0x9fc54  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9fc59  stloc.s  8
0x9fc5b  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fc60  stloc.s  9
0x9fc62  ldarg.1
0x9fc63  ldc.i4.4
0x9fc64  and
0x9fc65  ldc.i4.0
0x9fc66  ble.un.s loc_9FCB8
0x9fc68  ldarg.2
0x9fc69  ldloca.s 1
0x9fc6b  ldloca.s 0
0x9fc6d  ldloca.s 2
0x9fc6f  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::GetSecurityDescriptorDacl(native int pSecurityDescriptor, [out] int32& lpbDaclPresent, [out] native int& pDacl, [out] int32& lpbDaclDefaulted)
0x9fc74  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fc79  bne.un.s loc_9FC90
0x9fc7b  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x9fc80  stloc.s  0xA
0x9fc82  ldstr    aErrorAfterNati// "Error after NativeMethods.GetSecurityDe"...
0x9fc87  ldloc.s  0xA
0x9fc89  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x9fc8e  br.s     loc_9FCB8
0x9fc90  ldarg.0
0x9fc91  ldfld    native int ImplementedSecurityCallback::currentSecurityDescriptior
0x9fc96  ldloc.1
0x9fc97  ldloc.0
0x9fc98  ldloc.2
0x9fc99  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::SetSecurityDescriptorDacl(native int pSecurityDescriptor, int32 bDaclPresent, native int pDacl, int32 bDaclDefaulted)
0x9fc9e  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fca3  bne.un.s loc_9FCB8
0x9fca5  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x9fcaa  stloc.s  0xA
0x9fcac  ldstr    aErrorAfterNati_0// "Error after NativeMethods.SetSecurityDe"...
0x9fcb1  ldloc.s  0xA
0x9fcb3  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x9fcb8  ldarg.1
0x9fcb9  ldc.i4.8
0x9fcba  and
0x9fcbb  ldc.i4.0
0x9fcbc  ble.un.s loc_9FD10
0x9fcbe  ldarg.2
0x9fcbf  ldloca.s 4
0x9fcc1  ldloca.s 3
0x9fcc3  ldloca.s 5
0x9fcc5  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::GetSecurityDescriptorSacl(native int pSecurityDescriptor, [out] int32& lpbSaclPresent, [out] native int& pSacl, [out] int32& lpbSaclDefaulted)
0x9fcca  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fccf  bne.un.s loc_9FCE6
0x9fcd1  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x9fcd6  stloc.s  0xA
0x9fcd8  ldstr    aErrorAfterNati_1// "Error after NativeMethods.GetSecurityDe"...
0x9fcdd  ldloc.s  0xA
0x9fcdf  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x9fce4  br.s     loc_9FD10
0x9fce6  ldarg.0
0x9fce7  ldfld    native int ImplementedSecurityCallback::currentSecurityDescriptior
0x9fcec  ldloc.s  4
0x9fcee  ldloc.3
0x9fcef  ldloc.s  5
0x9fcf1  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::SetSecurityDescriptorSacl(native int pSecurityDescriptor, int32 bSaclPresent, native int pSacl, int32 bSaclDefaulted)
0x9fcf6  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fcfb  bne.un.s loc_9FD10
0x9fcfd  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x9fd02  stloc.s  0xA
0x9fd04  ldstr    aErrorAfterNati_0// "Error after NativeMethods.SetSecurityDe"...
0x9fd09  ldloc.s  0xA
0x9fd0b  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x9fd10  ldarg.1
0x9fd11  ldc.i4.1
0x9fd12  and
0x9fd13  ldc.i4.0
0x9fd14  ble.un.s loc_9FD65
0x9fd16  ldarg.2
0x9fd17  ldloca.s 6
0x9fd19  ldloca.s 7
0x9fd1b  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::GetSecurityDescriptorOwner(native int pSecurityDescriptor, [out] native int& pOwner, [out] int32& lpbOwnerDefaulted)
0x9fd20  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fd25  bne.un.s loc_9FD3C
0x9fd27  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x9fd2c  stloc.s  0xA
0x9fd2e  ldstr    aErrorAfterNati_1// "Error after NativeMethods.GetSecurityDe"...
0x9fd33  ldloc.s  0xA
0x9fd35  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x9fd3a  br.s     loc_9FD65
0x9fd3c  ldarg.0
0x9fd3d  ldfld    native int ImplementedSecurityCallback::currentSecurityDescriptior
0x9fd42  ldloc.s  6
0x9fd44  ldloc.s  7
0x9fd46  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::SetSecurityDescriptorOwner(native int pSecurityDescriptor, native int pOwner, int32 bOwnerDefaulted)
0x9fd4b  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fd50  bne.un.s loc_9FD65
0x9fd52  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x9fd57  stloc.s  0xA
0x9fd59  ldstr    aErrorAfterNati_0// "Error after NativeMethods.SetSecurityDe"...
0x9fd5e  ldloc.s  0xA
0x9fd60  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x9fd65  ldarg.1
0x9fd66  ldc.i4.2
0x9fd67  and
0x9fd68  ldc.i4.0
0x9fd69  ble.un.s loc_9FDB9
0x9fd6b  ldarg.2
0x9fd6c  ldloca.s 8
0x9fd6e  ldloca.s 9
0x9fd70  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::GetSecurityDescriptorGroup(native int pSecurityDescriptor, [out] native int& pGroup, [out] int32& lpbGroupDefaulted)
0x9fd75  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fd7a  bne.un.s loc_9FD90
0x9fd7c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x9fd81  stloc.s  0xA
0x9fd83  ldstr    aErrorAfterNati_1// "Error after NativeMethods.GetSecurityDe"...
0x9fd88  ldloc.s  0xA
0x9fd8a  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x9fd8f  ret
0x9fd90  ldarg.0
0x9fd91  ldfld    native int ImplementedSecurityCallback::currentSecurityDescriptior
0x9fd96  ldloc.s  8
0x9fd98  ldloc.s  9
0x9fd9a  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::SetSecurityDescriptorGroup(native int pSecurityDescriptor, native int pGroup, int32 bGroupDefaulted)
0x9fd9f  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::BOOL_FALSE
0x9fda4  bne.un.s loc_9FDB9
0x9fda6  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x9fdab  stloc.s  0xA
0x9fdad  ldstr    aErrorAfterNati_0// "Error after NativeMethods.SetSecurityDe"...
0x9fdb2  ldloc.s  0xA
0x9fdb4  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x9fdb9  ret
```
