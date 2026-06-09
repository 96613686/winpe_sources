# System.Deployment.Application.NativeMethods::GetAssemblyCacheInterface

- ea: `0x1a420`
- end: `0x1a509`
- name: `System.Deployment.Application.NativeMethods::GetAssemblyCacheInterface`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1ba20`

## callees

- `0x1a410`
- `0x1a420`
- `0x2a5f0`
- `0x2a650`
- `0x2a8e0`
- `0x2a920`
- `0x2aa80`

## string_xrefs

- `0x1a4cc`: `CreateAssemblyCache`

## pseudocode

```c

```

## disassembly

```asm
0x1a420  ldnull
0x1a421  stloc.0
0x1a422  ldarg.2
0x1a423  ldnull
0x1a424  stind.ref
0x1a425  ldsflda  valuetype [mscorlib]System.Guid System.Deployment.Application.NativeMethods::_metaHostPolicyClsIdGuid
0x1a42a  ldsflda  valuetype [mscorlib]System.Guid System.Deployment.Application.NativeMethods::_metaHostPolicyGuid
0x1a42f  ldloca.s 0
0x1a431  call     void System.Deployment.Application.NativeMethods::GetClrMetaHostPolicy([hasfieldmarshal] valuetype [mscorlib]System.Guid&, valuetype [mscorlib]System.Guid& clsid, class IClrMetaHostPolicy& iid)
0x1a436  ldloc.0
0x1a437  brtrue.s loc_1A43B
0x1a439  ldnull
0x1a43a  ret
0x1a43b  ldstr    aV// "v"
0x1a440  ldstr    aV6553565535655// "v65535.65535.65535"
0x1a445  call     instance int32 [mscorlib]System.String::get_Length()
0x1a44a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string, int32)
0x1a44f  stloc.1
0x1a450  ldloc.1
0x1a451  ldarg.0
0x1a452  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a457  pop
0x1a458  ldloc.1
0x1a459  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Capacity()
0x1a45e  stloc.2
0x1a45f  ldc.i4.0
0x1a460  stloc.3
0x1a461  ldc.i4.0
0x1a462  stloc.s  4
0x1a464  ldloc.0
0x1a465  ldc.i4.8
0x1a466  ldnull
0x1a467  ldnull
0x1a468  ldloc.1
0x1a469  ldloca.s 2
0x1a46b  ldnull
0x1a46c  ldloca.s 3
0x1a46e  ldloca.s 4
0x1a470  ldsfld   valuetype [mscorlib]System.Guid System.Deployment.Application.NativeMethods::_clrRuntimeInfoGuid
0x1a475  callvirt instance object IClrMetaHostPolicy::GetRequestedRuntime([hasfieldmarshal] valuetype MetaHostPolicyFlags, [in] string policyFlags, [in] [hasfieldmarshal] class [mscorlib]System.Runtime.InteropServices.ComTypes.IStream binaryPath, [in] [hasfieldmarshal] class [mscorlib]System.Text.StringBuilder configStream, [in] [out] [hasfieldmarshal] int32& version, [in] [out] [hasfieldmarshal] class [mscorlib]System.Text.StringBuilder versionLength, [out] [hasfieldmarshal] int32& imageVersion, [in] [out] [hasfieldmarshal] int32& imageVersionLength, [out] [hasfieldmarshal] valuetype [mscorlib]System.Guid pdwConfigFlags)
0x1a47a  castclass IClrRuntimeInfo
0x1a47f  stloc.s  5
0x1a481  ldloc.s  5
0x1a483  brtrue.s loc_1A487
0x1a485  ldnull
0x1a486  ret
0x1a487  ldloc.s  5
0x1a489  ldstr    aCoinitializeee// "CoInitializeEE"
0x1a48e  callvirt instance native int IClrRuntimeInfo::GetProcAddress([in] [hasfieldmarshal] string procName)
0x1a493  stloc.s  6
0x1a495  ldloc.s  6
0x1a497  ldtoken  CoInitializeEEDelegate
0x1a49c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a4a1  call     class [mscorlib]System.Delegate [mscorlib]System.Runtime.InteropServices.Marshal::GetDelegateForFunctionPointer(native int, class [mscorlib]System.Type)
0x1a4a6  castclass CoInitializeEEDelegate
0x1a4ab  stloc.s  7
0x1a4ad  ldloc.s  7
0x1a4af  ldc.i4.0
0x1a4b0  callvirt instance int32 CoInitializeEEDelegate::Invoke(unsigned int32 fFlags)
0x1a4b5  stloc.s  8
0x1a4b7  ldloc.s  8
0x1a4b9  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x1a4be  ldarg.1
0x1a4bf  brfalse.s loc_1A4CA
0x1a4c1  ldarg.2
0x1a4c2  ldloc.s  5
0x1a4c4  newobj   instance void CCorRuntimeHost::.ctor(class IClrRuntimeInfo RuntimeInfo)
0x1a4c9  stind.ref
0x1a4ca  ldloc.s  5
0x1a4cc  ldstr    aCreateassembly// "CreateAssemblyCache"
0x1a4d1  callvirt instance native int IClrRuntimeInfo::GetProcAddress([in] [hasfieldmarshal] string procName)
0x1a4d6  stloc.s  9
0x1a4d8  ldloc.s  9
0x1a4da  ldtoken  CreateAssemblyCacheDelegate
0x1a4df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a4e4  call     class [mscorlib]System.Delegate [mscorlib]System.Runtime.InteropServices.Marshal::GetDelegateForFunctionPointer(native int, class [mscorlib]System.Type)
0x1a4e9  castclass CreateAssemblyCacheDelegate
0x1a4ee  stloc.s  0xA
0x1a4f0  ldnull
0x1a4f1  stloc.s  0xB
0x1a4f3  ldloc.s  0xA
0x1a4f5  ldloca.s 0xB
0x1a4f7  ldc.i4.0
0x1a4f8  callvirt instance int32 CreateAssemblyCacheDelegate::Invoke([out] [hasfieldmarshal] class IAssemblyCache& ppAsmCache, unsigned int32 reserved)
0x1a4fd  stloc.s  8
0x1a4ff  ldloc.s  8
0x1a501  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x1a506  ldloc.s  0xB
0x1a508  ret
```
