# Microsoft.BIServer.Configuration.WMI.WmiProvider::GetSecurityDescriptior

- ea: `0x5280`
- end: `0x534f`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::GetSecurityDescriptior`
- size: `207`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4fd0`
- `0x5170`

## callees

- `0x4a80`
- `0x4e90`
- `0x5280`

## string_xrefs

- `0x52a9`: `:__SystemSecurity`
- `0x52d6`: `sddl must be provided when overwriting security descriptors`
- `0x5280`: `Attempting to get security descriptor for namespace path {0}`
- `0x5300`: `Returning security descriptor {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5280  ldstr    aAttemptingToGe// "Attempting to get security descriptor f"...
0x5285  ldc.i4.1
0x5286  newarr   [mscorlib]System.Object
0x528b  dup
0x528c  ldc.i4.0
0x528d  ldarg.1
0x528e  stelem.ref
0x528f  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Trace(string, object[])
0x5294  ldsfld   string [mscorlib]System.String::Empty
0x5299  stloc.0
0x529a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x529f  stloc.1
0x52a0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x52a5  stloc.2
0x52a6  ldc.i4.0
0x52a7  stloc.3
0x52a8  ldarg.1
0x52a9  ldstr    aSystemsecurity// ":__SystemSecurity"
0x52ae  call     string [mscorlib]System.String::Concat(string, string)
0x52b3  newobj   instance void [System.Management]System.Management.ManagementClass::.ctor(string)
0x52b8  ldstr    aGetsd// "GetSD"
0x52bd  ldnull
0x52be  ldnull
0x52bf  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObject::InvokeMethod(string, class [System.Management]System.Management.ManagementBaseObject, class [System.Management]System.Management.InvokeMethodOptions)
0x52c4  dup
0x52c5  ldstr    aReturnvalue// "ReturnValue"
0x52ca  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x52cf  unbox.any [mscorlib]System.UInt32
0x52d4  brfalse.s loc_52E1
0x52d6  ldstr    aSddlMustBeProv// "sddl must be provided when overwriting "...
0x52db  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message)
0x52e0  throw
0x52e1  ldstr    aSd// "SD"
0x52e6  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x52eb  castclass unsigned int8[]
0x52f0  ldloca.s 1
0x52f2  ldloca.s 3
0x52f4  call     void Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertSDtoStringSD(unsigned int8[] securityDescriptor, [out] native int& stringSecurityDescriptorPtr, [out] int32& stringSecurityDescriptorSize)
0x52f9  ldloc.1
0x52fa  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0x52ff  stloc.0
0x5300  ldstr    aReturningSecur// "Returning security descriptor {0}"
0x5305  ldc.i4.1
0x5306  newarr   [mscorlib]System.Object
0x530b  dup
0x530c  ldc.i4.0
0x530d  ldloc.0
0x530e  stelem.ref
0x530f  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Trace(string, object[])
0x5314  ldloc.0
0x5315  stloc.s  4
0x5317  leave.s  loc_534C
0x5319  ldloc.2
0x531a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x531f  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x5324  brfalse.s loc_5332
0x5326  ldloc.2
0x5327  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x532c  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5331  stloc.2
0x5332  ldloc.1
0x5333  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5338  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x533d  brfalse.s loc_534B
0x533f  ldloc.1
0x5340  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x5345  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x534a  stloc.1
0x534b  endfinally
0x534c  ldloc.s  4
0x534e  ret
```
