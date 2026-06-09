# Microsoft.BIServer.Configuration.LSA.LocalSecurityAuthority::AddPrivilegeToAccount

- ea: `0x5ee0`
- end: `0x5fc8`
- name: `Microsoft.BIServer.Configuration.LSA.LocalSecurityAuthority::AddPrivilegeToAccount`
- size: `232`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x5e90`
- `0x5ea0`
- `0x5eb0`
- `0x5ec0`
- `0x5ee0`

## pseudocode

```c

```

## disassembly

```asm
0x5ee0  ldsfld   int32 [mscorlib]System.Security.Principal.SecurityIdentifier::MaxBinaryLength
0x5ee5  newarr   [mscorlib]System.Byte
0x5eea  stloc.0
0x5eeb  ldarg.0
0x5eec  ldloc.0
0x5eed  ldc.i4.0
0x5eee  callvirt instance void [mscorlib]System.Security.Principal.SecurityIdentifier::GetBinaryForm(unsigned int8[], int32)
0x5ef3  ldc.i4   0x810
0x5ef8  stloc.1
0x5ef9  ldloca.s 6
0x5efb  initobj  LSA_OBJECT_ATTRIBUTES
0x5f01  ldloca.s 6
0x5f03  ldc.i4.0
0x5f04  stfld    int32 LSA_OBJECT_ATTRIBUTES::Length
0x5f09  ldloca.s 6
0x5f0b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5f10  stfld    native int LSA_OBJECT_ATTRIBUTES::RootDirectory
0x5f15  ldloca.s 6
0x5f17  ldc.i4.0
0x5f18  stfld    unsigned int32 LSA_OBJECT_ATTRIBUTES::Attributes
0x5f1d  ldloca.s 6
0x5f1f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5f24  stfld    native int LSA_OBJECT_ATTRIBUTES::SecurityDescriptor
0x5f29  ldloca.s 6
0x5f2b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5f30  stfld    native int LSA_OBJECT_ATTRIBUTES::SecurityQualityOfService
0x5f35  ldloc.s  6
0x5f37  stloc.3
0x5f38  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5f3d  ldloca.s 3
0x5f3f  ldloc.1
0x5f40  ldloca.s 2
0x5f42  call     unsigned int32 Microsoft.BIServer.Configuration.LSA.LocalSecurityAuthorityNative::LsaOpenPolicy(native int systemName, valuetype LSA_OBJECT_ATTRIBUTES& objectAttributes, unsigned int32 desiredAccess, [out] native int& policyHandle)
0x5f47  call     unsigned int32 Microsoft.BIServer.Configuration.LSA.LocalSecurityAuthorityNative::LsaNtStatusToWinError(unsigned int32 status)
0x5f4c  stloc.s  4
0x5f4e  ldloc.s  4
0x5f50  brfalse.s loc_5F5A
0x5f52  ldloc.s  4
0x5f54  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x5f59  throw
0x5f5a  ldc.i4.1
0x5f5b  newarr   LSA_UNICODE_STRING
0x5f60  stloc.s  5
0x5f62  ldloc.s  5
0x5f64  ldc.i4.0
0x5f65  ldloca.s 7
0x5f67  initobj  LSA_UNICODE_STRING
0x5f6d  ldloca.s 7
0x5f6f  ldarg.1
0x5f70  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToHGlobalUni(string)
0x5f75  stfld    native int LSA_UNICODE_STRING::Buffer
0x5f7a  ldloca.s 7
0x5f7c  ldarg.1
0x5f7d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5f82  ldc.i4.2
0x5f83  mul
0x5f84  conv.u2
0x5f85  stfld    unsigned int16 LSA_UNICODE_STRING::Length
0x5f8a  ldloca.s 7
0x5f8c  ldarg.1
0x5f8d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5f92  ldc.i4.1
0x5f93  add
0x5f94  ldc.i4.2
0x5f95  mul
0x5f96  conv.u2
0x5f97  stfld    unsigned int16 LSA_UNICODE_STRING::MaximumLength
0x5f9c  ldloc.s  7
0x5f9e  stelem   LSA_UNICODE_STRING
0x5fa3  ldloc.2
0x5fa4  ldloc.0
0x5fa5  ldloc.s  5
0x5fa7  ldc.i4.1
0x5fa8  call     unsigned int32 Microsoft.BIServer.Configuration.LSA.LocalSecurityAuthorityNative::LsaAddAccountRights(native int policyHandle, [hasfieldmarshal] unsigned int8[] sid, valuetype LSA_UNICODE_STRING[] userRights, unsigned int32 countOfRights)
0x5fad  call     unsigned int32 Microsoft.BIServer.Configuration.LSA.LocalSecurityAuthorityNative::LsaNtStatusToWinError(unsigned int32 status)
0x5fb2  stloc.s  4
0x5fb4  ldloc.s  4
0x5fb6  brfalse.s loc_5FC0
0x5fb8  ldloc.s  4
0x5fba  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x5fbf  throw
0x5fc0  ldloc.2
0x5fc1  call     int64 Microsoft.BIServer.Configuration.LSA.LocalSecurityAuthorityNative::LsaClose(native int objectHandle)
0x5fc6  pop
0x5fc7  ret
```
