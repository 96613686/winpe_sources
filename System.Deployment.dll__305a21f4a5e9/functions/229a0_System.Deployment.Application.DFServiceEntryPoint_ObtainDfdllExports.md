# System.Deployment.Application.DFServiceEntryPoint::ObtainDfdllExports

- ea: `0x229a0`
- end: `0x22a1c`
- name: `System.Deployment.Application.DFServiceEntryPoint::ObtainDfdllExports`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x22a20`

## callees

- `0x1a270`
- `0x22970`
- `0x229a0`

## string_xrefs

- `0x229a5`: `dfdll.dll`
- `0x229da`: `RegisterDeploymentServiceCom`
- `0x229fd`: `UnregisterDeploymentServiceCom`

## pseudocode

```c

```

## disassembly

```asm
0x229a0  call     string [mscorlib]System.Runtime.InteropServices.RuntimeEnvironment::GetRuntimeDirectory()
0x229a5  ldstr    aDfdllDll// "dfdll.dll"
0x229aa  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x229af  call     native int System.Deployment.Application.NativeMethods::LoadLibrary(string lpModuleName)
0x229b4  stsfld   native int System.Deployment.Application.DFServiceEntryPoint::DfdllHandle
0x229b9  ldsfld   native int System.Deployment.Application.DFServiceEntryPoint::DfdllHandle
0x229be  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x229c3  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x229c8  brfalse.s loc_229D5
0x229ca  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x229cf  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x229d4  throw
0x229d5  ldsfld   native int System.Deployment.Application.DFServiceEntryPoint::DfdllHandle
0x229da  ldstr    aRegisterdeploy// "RegisterDeploymentServiceCom"
0x229df  ldtoken  RegisterDeploymentServiceComDelegate
0x229e4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x229e9  call     object System.Deployment.Application.DFServiceEntryPoint::GetMethodDelegate(native int handle, string methodName, class [mscorlib]System.Type methodDelegateType)
0x229ee  castclass RegisterDeploymentServiceComDelegate
0x229f3  stsfld   class RegisterDeploymentServiceComDelegate System.Deployment.Application.DFServiceEntryPoint::RegisterDeploymentServiceCom
0x229f8  ldsfld   native int System.Deployment.Application.DFServiceEntryPoint::DfdllHandle
0x229fd  ldstr    aUnregisterdepl// "UnregisterDeploymentServiceCom"
0x22a02  ldtoken  UnregisterDeploymentServiceComDelegate
0x22a07  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22a0c  call     object System.Deployment.Application.DFServiceEntryPoint::GetMethodDelegate(native int handle, string methodName, class [mscorlib]System.Type methodDelegateType)
0x22a11  castclass UnregisterDeploymentServiceComDelegate
0x22a16  stsfld   class UnregisterDeploymentServiceComDelegate System.Deployment.Application.DFServiceEntryPoint::UnregisterDeploymentServiceCom
0x22a1b  ret
```
