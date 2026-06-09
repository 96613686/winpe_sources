# Microsoft.BIServer.Configuration.WMI.WmiProvider::SetSecurityDescriptor_0

- ea: `0x5170`
- end: `0x5280`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::SetSecurityDescriptor_0`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x4a70`
- `0x4e90`
- `0x4fa0`
- `0x4fd0`
- `0x5170`
- `0x5280`
- `0x5c30`

## string_xrefs

- `0x5170`: `Attempting to set security descriptor {0}, namespace path {1}`
- `0x5192`: `sddl must be provided when overwriting security descriptors`
- `0x51a8`: `SDDL is NULL/empty and overwriteSecurityDescriptor is false, so nothing to do, return.`
- `0x523c`: `Failed to turn off the DACL inheritance on namespace: '{0}'`
- `0x5256`: `Security on WMI namespace '{0}' before appending: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x5170  ldstr    aAttemptingToSe// "Attempting to set security descriptor {"...
0x5175  ldc.i4.2
0x5176  newarr   [mscorlib]System.Object
0x517b  dup
0x517c  ldc.i4.0
0x517d  ldarg.2
0x517e  stelem.ref
0x517f  dup
0x5180  ldc.i4.1
0x5181  ldarg.1
0x5182  stelem.ref
0x5183  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Trace(string, object[])
0x5188  ldarg.2
0x5189  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x518e  ldarg.3
0x518f  and
0x5190  brfalse.s loc_519D
0x5192  ldstr    aSddlMustBeProv// "sddl must be provided when overwriting "...
0x5197  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message)
0x519c  throw
0x519d  ldarg.2
0x519e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x51a3  brfalse.s loc_51B8
0x51a5  ldarg.3
0x51a6  brtrue.s loc_51B8
0x51a8  ldstr    aSddlIsNullEmpt// "SDDL is NULL/empty and overwriteSecurit"...
0x51ad  call     T0x2B000015
0x51b2  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x51b7  ret
0x51b8  ldstr    aSettingWmiName// "Setting WMI Namespace '{0}' with SDDL {"...
0x51bd  ldc.i4.3
0x51be  newarr   [mscorlib]System.Object
0x51c3  dup
0x51c4  ldc.i4.0
0x51c5  ldarg.1
0x51c6  stelem.ref
0x51c7  dup
0x51c8  ldc.i4.1
0x51c9  ldarg.3
0x51ca  brtrue.s loc_51D3
0x51cc  ldsfld   string [mscorlib]System.String::Empty
0x51d1  br.s     loc_51D8
0x51d3  ldstr    aOverwritting// "(overwritting)"
0x51d8  stelem.ref
0x51d9  dup
0x51da  ldc.i4.2
0x51db  ldarg.2
0x51dc  stelem.ref
0x51dd  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x51e2  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x51e7  stloc.0
0x51e8  ldsfld   string [mscorlib]System.String::Empty
0x51ed  stloc.1
0x51ee  ldarg.0
0x51ef  ldarg.1
0x51f0  call     instance string Microsoft.BIServer.Configuration.WMI.WmiProvider::GetSecurityDescriptior(string namespacePath)
0x51f5  stloc.1
0x51f6  ldarg.3
0x51f7  brfalse.s loc_5256
0x51f9  ldarg.0
0x51fa  ldloc.1
0x51fb  ldloca.s 0
0x51fd  call     instance valuetype Microsoft.BIServer.Configuration.WMI.SecurityDescriptorControlFlags Microsoft.BIServer.Configuration.WMI.WmiProvider::GetFlagsFromDescriptor(string descriptor, native int& sdCur)
0x5202  stloc.2
0x5203  ldc.i4   0x1000
0x5208  ldloc.2
0x5209  ldc.i4   0x1000
0x520e  and
0x520f  bne.un.s loc_5227
0x5211  ldstr    aNoNeedToProtec// "No need to protect the WMI Namespace: '"...
0x5216  ldc.i4.1
0x5217  newarr   [mscorlib]System.Object
0x521c  dup
0x521d  ldc.i4.0
0x521e  ldarg.1
0x521f  stelem.ref
0x5220  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x5225  br.s     loc_5252
0x5227  nop
0x5228  ldloc.0
0x5229  ldc.i4   0x1000
0x522e  ldc.i4   0x1000
0x5233  call     bool Microsoft.BIServer.Configuration.WMI.NativeMethods::SetSecurityDescriptorControl(native int pSecurityDescriptor, valuetype Microsoft.BIServer.Configuration.WMI.SecurityDescriptorControlFlags ControlBitsOfInterest, valuetype Microsoft.BIServer.Configuration.WMI.SecurityDescriptorControlFlags ControlBitsToSet)
0x5238  pop
0x5239  leave.s  loc_5252
0x523b  stloc.3
0x523c  ldstr    aFailedToTurnOf// "Failed to turn off the DACL inheritance"...
0x5241  ldc.i4.1
0x5242  newarr   [mscorlib]System.Object
0x5247  dup
0x5248  ldc.i4.0
0x5249  ldarg.1
0x524a  stelem.ref
0x524b  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x5250  ldloc.3
0x5251  throw
0x5252  ldarg.2
0x5253  stloc.1
0x5254  br.s     loc_5277
0x5256  ldstr    aSecurityOnWmiN// "Security on WMI namespace '{0}' before "...
0x525b  ldc.i4.2
0x525c  newarr   [mscorlib]System.Object
0x5261  dup
0x5262  ldc.i4.0
0x5263  ldarg.1
0x5264  stelem.ref
0x5265  dup
0x5266  ldc.i4.1
0x5267  ldloc.1
0x5268  stelem.ref
0x5269  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x526e  ldarg.0
0x526f  ldarg.2
0x5270  ldloc.1
0x5271  call     instance string Microsoft.BIServer.Configuration.WMI.WmiProvider::AppendSecurityDescriptor(string newSDDL, string oldSDDL)
0x5276  stloc.1
0x5277  ldarg.0
0x5278  ldarg.1
0x5279  ldloc.1
0x527a  call     instance void Microsoft.BIServer.Configuration.WMI.WmiProvider::SetSecurityDescriptor(string namespacePath, string securityDescriptor)
0x527f  ret
```
