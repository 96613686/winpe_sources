# Microsoft.BIServer.Configuration.WMI.WmiProvider::SetSecurityDescriptor

- ea: `0x4fd0`
- end: `0x5163`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::SetSecurityDescriptor`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x5170`

## callees

- `0x4a30`
- `0x4a70`
- `0x4e90`
- `0x4fa0`
- `0x4fd0`
- `0x5280`

## string_xrefs

- `0x4fd0`: `Attempting to set security descriptor {0}, namespace path {1}`
- `0x504f`: `Failed on SetSecurityDescriptorControl API with Error {0}`
- `0x50ca`: `:__SystemSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x4fd0  ldstr    aAttemptingToSe// "Attempting to set security descriptor {"...
0x4fd5  ldc.i4.2
0x4fd6  newarr   [mscorlib]System.Object
0x4fdb  dup
0x4fdc  ldc.i4.0
0x4fdd  ldarg.2
0x4fde  stelem.ref
0x4fdf  dup
0x4fe0  ldc.i4.1
0x4fe1  ldarg.1
0x4fe2  stelem.ref
0x4fe3  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Trace(string, object[])
0x4fe8  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4fed  stloc.0
0x4fee  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4ff3  stloc.1
0x4ff4  ldc.i4.0
0x4ff5  stloc.2
0x4ff6  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4ffb  stloc.3
0x4ffc  ldsfld   string [mscorlib]System.String::Empty
0x5001  stloc.s  4
0x5003  ldarg.0
0x5004  ldarg.1
0x5005  call     instance string Microsoft.BIServer.Configuration.WMI.WmiProvider::GetSecurityDescriptior(string namespacePath)
0x500a  stloc.s  4
0x500c  ldarg.0
0x500d  ldloc.s  4
0x500f  ldloca.s 3
0x5011  call     instance valuetype Microsoft.BIServer.Configuration.WMI.SecurityDescriptorControlFlags Microsoft.BIServer.Configuration.WMI.WmiProvider::GetFlagsFromDescriptor(string descriptor, native int& sdCur)
0x5016  stloc.s  5
0x5018  ldc.i4   0x1000
0x501d  ldloc.s  5
0x501f  ldc.i4   0x1000
0x5024  and
0x5025  bne.un.s loc_503D
0x5027  ldstr    aNoNeedToProtec// "No need to protect the WMI Namespace: '"...
0x502c  ldc.i4.1
0x502d  newarr   [mscorlib]System.Object
0x5032  dup
0x5033  ldc.i4.0
0x5034  ldarg.1
0x5035  stelem.ref
0x5036  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x503b  br.s     loc_5069
0x503d  ldloc.3
0x503e  ldc.i4   0x1000
0x5043  ldc.i4   0x1000
0x5048  call     bool Microsoft.BIServer.Configuration.WMI.NativeMethods::SetSecurityDescriptorControl(native int pSecurityDescriptor, valuetype Microsoft.BIServer.Configuration.WMI.SecurityDescriptorControlFlags ControlBitsOfInterest, valuetype Microsoft.BIServer.Configuration.WMI.SecurityDescriptorControlFlags ControlBitsToSet)
0x504d  brtrue.s loc_5069
0x504f  ldstr    aFailedOnSetsec// "Failed on SetSecurityDescriptorControl "...
0x5054  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x5059  box      [mscorlib]System.Int32
0x505e  call     string [mscorlib]System.String::Format(string, object)
0x5063  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message)
0x5068  throw
0x5069  ldarg.2
0x506a  ldc.i4.0
0x506b  ldarg.2
0x506c  ldstr    asc_B040// "("
0x5071  ldc.i4.5
0x5072  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x5077  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x507c  stloc.s  6
0x507e  ldloc.s  6
0x5080  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5085  brfalse.s loc_50AD
0x5087  ldloc.s  4
0x5089  ldc.i4.0
0x508a  ldloc.s  4
0x508c  ldstr    asc_B040// "("
0x5091  ldc.i4.5
0x5092  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x5097  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x509c  stloc.s  6
0x509e  ldstr    a01// "{0}{1}"
0x50a3  ldloc.s  6
0x50a5  ldarg.2
0x50a6  call     string [mscorlib]System.String::Format(string, object, object)
0x50ab  starg.s  2
0x50ad  ldarg.2
0x50ae  ldloca.s 1
0x50b0  ldloca.s 2
0x50b2  call     void Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertStringSDtoSD(string stringSecurityDescriptor, [out] native int& securityDescriptorPtr, [out] int32& securityDescriptorSize)
0x50b7  ldloc.2
0x50b8  newarr   [mscorlib]System.Byte
0x50bd  stloc.s  7
0x50bf  ldloc.1
0x50c0  ldloc.s  7
0x50c2  ldc.i4.0
0x50c3  ldloc.2
0x50c4  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x50c9  ldarg.1
0x50ca  ldstr    aSystemsecurity// ":__SystemSecurity"
0x50cf  call     string [mscorlib]System.String::Concat(string, string)
0x50d4  newobj   instance void [System.Management]System.Management.ManagementClass::.ctor(string)
0x50d9  dup
0x50da  ldstr    aSetsd// "SetSD"
0x50df  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObject::GetMethodParameters(string)
0x50e4  stloc.s  8
0x50e6  ldloc.s  8
0x50e8  ldstr    aSd// "SD"
0x50ed  ldloc.s  7
0x50ef  callvirt instance void [System.Management]System.Management.ManagementBaseObject::set_Item(string, object)
0x50f4  ldstr    aSetsd// "SetSD"
0x50f9  ldloc.s  8
0x50fb  ldnull
0x50fc  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObject::InvokeMethod(string, class [System.Management]System.Management.ManagementBaseObject, class [System.Management]System.Management.InvokeMethodOptions)
0x5101  stloc.s  9
0x5103  ldloc.s  9
0x5105  ldstr    aReturnvalue// "ReturnValue"
0x510a  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x510f  unbox.any [mscorlib]System.UInt32
0x5114  brfalse.s loc_512D
0x5116  ldloc.s  9
0x5118  ldstr    aReturnvalue// "ReturnValue"
0x511d  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x5122  callvirt instance string [mscorlib]System.Object::ToString()
0x5127  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message)
0x512c  throw
0x512d  leave.s  loc_5162
0x512f  ldloc.1
0x5130  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5135  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x513a  brfalse.s loc_5148
0x513c  ldloc.1
0x513d  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x5142  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5147  stloc.1
0x5148  ldloc.0
0x5149  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x514e  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x5153  brfalse.s loc_5161
0x5155  ldloc.0
0x5156  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x515b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5160  stloc.0
0x5161  endfinally
0x5162  ret
```
