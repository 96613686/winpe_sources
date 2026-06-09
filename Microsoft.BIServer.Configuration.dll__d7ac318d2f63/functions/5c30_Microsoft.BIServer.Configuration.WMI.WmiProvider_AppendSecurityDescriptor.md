# Microsoft.BIServer.Configuration.WMI.WmiProvider::AppendSecurityDescriptor

- ea: `0x5c30`
- end: `0x5ddd`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::AppendSecurityDescriptor`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x5170`

## callees

- `0x4ad0`
- `0x4ae0`
- `0x4af0`
- `0x4b00`
- `0x4b10`
- `0x4b20`
- `0x4fa0`
- `0x5c30`

## pseudocode

```c

```

## disassembly

```asm
0x5c30  ldc.i4.0
0x5c31  stloc.0
0x5c32  ldc.i4.0
0x5c33  stloc.1
0x5c34  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5c39  stloc.2
0x5c3a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5c3f  stloc.3
0x5c40  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5c45  stloc.s  4
0x5c47  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5c4c  stloc.s  5
0x5c4e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5c53  stloc.s  6
0x5c55  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5c5a  stloc.s  7
0x5c5c  ldnull
0x5c5d  stloc.s  8
0x5c5f  ldc.i4.0
0x5c60  stloc.s  9
0x5c62  ldnull
0x5c63  stloc.s  0xA
0x5c65  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5c6a  stloc.s  0xB
0x5c6c  ldc.i4.0
0x5c6d  stloc.s  0xC
0x5c6f  ldc.i4.0
0x5c70  stloc.s  0xD
0x5c72  ldarg.2
0x5c73  ldc.i4.0
0x5c74  ldarg.2
0x5c75  ldstr    asc_B040// "("
0x5c7a  ldc.i4.5
0x5c7b  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x5c80  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x5c85  stloc.s  0xA
0x5c87  ldarg.1
0x5c88  ldstr    asc_B040// "("
0x5c8d  ldc.i4.5
0x5c8e  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x5c93  stloc.s  9
0x5c95  ldarg.1
0x5c96  ldc.i4.0
0x5c97  ldloc.s  9
0x5c99  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x5c9e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5ca3  brfalse.s loc_5CB9
0x5ca5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5caa  ldstr    a01// "{0}{1}"
0x5caf  ldloc.s  0xA
0x5cb1  ldarg.1
0x5cb2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x5cb7  starg.s  1
0x5cb9  ldarg.0
0x5cba  ldarg.2
0x5cbb  ldloca.s 3
0x5cbd  call     instance valuetype Microsoft.BIServer.Configuration.WMI.SecurityDescriptorControlFlags Microsoft.BIServer.Configuration.WMI.WmiProvider::GetFlagsFromDescriptor(string descriptor, native int& sdCur)
0x5cc2  pop
0x5cc3  ldloc.3
0x5cc4  ldloca.s 0xC
0x5cc6  ldloca.s 6
0x5cc8  ldloca.s 0xD
0x5cca  call     bool Microsoft.BIServer.Configuration.WMI.NativeMethods::GetSecurityDescriptorDacl(native int pSecurityDescriptor, [out] bool& daclPresent, [out] native int& pDacl, [out] bool& daclDefaulted)
0x5ccf  brfalse.s loc_5CD5
0x5cd1  ldloc.s  0xC
0x5cd3  brtrue.s loc_5CE0
0x5cd5  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x5cda  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x5cdf  throw
0x5ce0  ldarg.0
0x5ce1  ldarg.1
0x5ce2  ldloca.s 2
0x5ce4  call     instance valuetype Microsoft.BIServer.Configuration.WMI.SecurityDescriptorControlFlags Microsoft.BIServer.Configuration.WMI.WmiProvider::GetFlagsFromDescriptor(string descriptor, native int& sdCur)
0x5ce9  pop
0x5cea  ldloc.2
0x5ceb  ldloca.s 0xC
0x5ced  ldloca.s 5
0x5cef  ldloca.s 0xD
0x5cf1  call     bool Microsoft.BIServer.Configuration.WMI.NativeMethods::GetSecurityDescriptorDacl(native int pSecurityDescriptor, [out] bool& daclPresent, [out] native int& pDacl, [out] bool& daclDefaulted)
0x5cf6  brfalse.s loc_5CFC
0x5cf8  ldloc.s  0xC
0x5cfa  brtrue.s loc_5D07
0x5cfc  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x5d01  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x5d06  throw
0x5d07  nop
0x5d08  ldloc.s  5
0x5d0a  ldloca.s 1
0x5d0c  ldloca.s 0xB
0x5d0e  call     unsigned int32 Microsoft.BIServer.Configuration.WMI.NativeMethods::GetExplicitEntriesFromAcl(native int pacl, [out] unsigned int32& nACE, [out] native int& ppEA)
0x5d13  pop
0x5d14  ldloc.1
0x5d15  ldc.i4.0
0x5d16  ble.un   loc_5DBF
0x5d1b  ldloc.1
0x5d1c  ldloc.s  0xB
0x5d1e  ldloc.s  6
0x5d20  ldloca.s 7
0x5d22  call     unsigned int32 Microsoft.BIServer.Configuration.WMI.NativeMethods::SetEntriesInAcl(unsigned int32 cCountOfExplicitEntries, native int pListOfExplicitEntries, native int OldAcl, [out] native int& NewAcl)
0x5d27  stloc.0
0x5d28  ldloc.0
0x5d29  brfalse.s loc_5D32
0x5d2b  ldloc.0
0x5d2c  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x5d31  throw
0x5d32  ldloc.3
0x5d33  ldtoken  SECURITY_DESCRIPTOR
0x5d38  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5d3d  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x5d42  unbox.any SECURITY_DESCRIPTOR
0x5d47  dup
0x5d48  call     T0x2B000031
0x5d4d  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x5d52  stloc.s  4
0x5d54  ldloc.s  4
0x5d56  ldc.i4.1
0x5d57  call     T0x2B000032
0x5d5c  ldloc.s  4
0x5d5e  ldc.i4.1
0x5d5f  call     bool Microsoft.BIServer.Configuration.WMI.NativeMethods::InitializeSecurityDescriptor(native int pSecurityDescriptor, unsigned int32 dwRevision)
0x5d64  brtrue.s loc_5D71
0x5d66  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x5d6b  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x5d70  throw
0x5d71  ldloc.s  4
0x5d73  ldc.i4.1
0x5d74  ldloc.s  7
0x5d76  ldc.i4.0
0x5d77  call     bool Microsoft.BIServer.Configuration.WMI.NativeMethods::SetSecurityDescriptorDacl(native int pSD, bool daclPresent, native int dacl, bool daclDefaulted)
0x5d7c  brtrue.s loc_5D89
0x5d7e  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x5d83  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x5d88  throw
0x5d89  ldloc.s  4
0x5d8b  call     string Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertSDtoStringSD(native int pSD)
0x5d90  stloc.s  8
0x5d92  ldloc.s  8
0x5d94  ldstr    asc_B040// "("
0x5d99  ldc.i4.5
0x5d9a  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x5d9f  stloc.s  9
0x5da1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5da6  ldstr    a01// "{0}{1}"
0x5dab  ldloc.s  0xA
0x5dad  ldloc.s  8
0x5daf  ldloc.s  9
0x5db1  callvirt instance string [mscorlib]System.String::Substring(int32)
0x5db6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x5dbb  stloc.s  8
0x5dbd  leave.s  loc_5DDA
0x5dbf  ldarg.2
0x5dc0  stloc.s  8
0x5dc2  leave.s  loc_5DDA
0x5dc4  ldloc.s  0xB
0x5dc6  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x5dcb  ldloc.s  7
0x5dcd  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x5dd2  ldloc.s  4
0x5dd4  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x5dd9  endfinally
0x5dda  ldloc.s  8
0x5ddc  ret
```
