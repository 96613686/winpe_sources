# System.Deployment.Application.ComponentStore::ActivateApplication

- ea: `0xe780`
- end: `0xe8e9`
- name: `System.Deployment.Application.ComponentStore::ActivateApplication`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1f860`

## callees

- `0xd600`
- `0xe780`
- `0xeaa0`
- `0xeac0`
- `0x14700`
- `0x17cd0`
- `0x17d40`
- `0x1a310`
- `0x23020`
- `0x23500`
- `0x23fe0`
- `0x23ff0`
- `0x24b90`
- `0x2a540`

## string_xrefs

- `0xe7bb`: `ComponentStore.ActivateApplication(appId=[`

## pseudocode

```c

```

## disassembly

```asm
0xe780  ldarg.0
0xe781  ldarg.1
0xe782  call     instance valuetype HostType System.Deployment.Application.ComponentStore::GetHostTypeFromMetadata(class System.Deployment.Application.DefinitionAppId defAppId)
0xe787  stloc.0
0xe788  ldc.i4.0
0xe789  stloc.1
0xe78a  call     valuetype HostType System.Deployment.Application.PolicyKeys::ClrHostType()
0xe78f  stloc.2
0xe790  ldloc.2
0xe791  ldc.i4.1
0xe792  bne.un.s loc_E798
0xe794  ldc.i4.1
0xe795  stloc.0
0xe796  br.s     loc_E79E
0xe798  ldloc.2
0xe799  ldc.i4.2
0xe79a  bne.un.s loc_E79E
0xe79c  ldc.i4.2
0xe79d  stloc.0
0xe79e  ldarg.1
0xe79f  callvirt instance string [mscorlib]System.Object::ToString()
0xe7a4  stloc.3
0xe7a5  ldarg.0
0xe7a6  ldarg.1
0xe7a7  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionAppId::get_DeploymentIdentity()
0xe7ac  call     instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.ComponentStore::GetAssemblyManifest(class System.Deployment.Application.DefinitionIdentity asmId)
0xe7b1  stloc.s  4
0xe7b3  ldc.i4.7
0xe7b4  newarr   [mscorlib]System.String
0xe7b9  dup
0xe7ba  ldc.i4.0
0xe7bb  ldstr    aComponentstore// "ComponentStore.ActivateApplication(appI"...
0xe7c0  stelem.ref
0xe7c1  dup
0xe7c2  ldc.i4.1
0xe7c3  ldloc.3
0xe7c4  stelem.ref
0xe7c5  dup
0xe7c6  ldc.i4.2
0xe7c7  ldstr    aActivationpara// "] ,activationParameter="
0xe7cc  stelem.ref
0xe7cd  dup
0xe7ce  ldc.i4.3
0xe7cf  ldarg.2
0xe7d0  stelem.ref
0xe7d1  dup
0xe7d2  ldc.i4.4
0xe7d3  ldstr    aUseactivationp// ",useActivationParameter="
0xe7d8  stelem.ref
0xe7d9  dup
0xe7da  ldc.i4.5
0xe7db  ldarga.s 3
0xe7dd  call     instance string [mscorlib]System.Boolean::ToString()
0xe7e2  stelem.ref
0xe7e3  dup
0xe7e4  ldc.i4.6
0xe7e5  ldstr    aCalled// ") called."
0xe7ea  stelem.ref
0xe7eb  call     string [mscorlib]System.String::Concat(string[])
0xe7f0  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0xe7f5  ldstr    aHosttype// "HostType="
0xe7fa  ldloc.0
0xe7fb  stloc.s  7
0xe7fd  ldloca.s 7
0xe7ff  call     instance string [mscorlib]System.UInt32::ToString()
0xe804  call     string [mscorlib]System.String::Concat(string, string)
0xe809  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xe80e  ldc.i4.0
0xe80f  stloc.s  5
0xe811  ldnull
0xe812  stloc.s  6
0xe814  ldarg.2
0xe815  brfalse.s loc_E842
0xe817  ldloc.s  4
0xe819  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xe81e  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_TrustURLParameters()
0xe823  ldarg.3
0xe824  or
0xe825  brfalse.s loc_E838
0xe827  ldc.i4.1
0xe828  stloc.s  5
0xe82a  ldc.i4.1
0xe82b  newarr   [mscorlib]System.String
0xe830  dup
0xe831  ldc.i4.0
0xe832  ldarg.2
0xe833  stelem.ref
0xe834  stloc.s  6
0xe836  br.s     loc_E842
0xe838  ldstr    aActivationPara// "Activation parameters are not passed."
0xe83d  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xe842  ldloc.0
0xe843  stloc.1
0xe844  ldloc.s  4
0xe846  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xe84b  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0xe850  brtrue.s loc_E85A
0xe852  ldloc.1
0xe853  ldc.i4   0x80000100
0xe858  or
0xe859  stloc.1
0xe85a  nop
0xe85b  ldstr    aActivatingAppl// "Activating application via CorLaunchApp"...
0xe860  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xe865  ldloc.1
0xe866  ldloc.3
0xe867  ldc.i4.0
0xe868  ldnull
0xe869  ldloc.s  5
0xe86b  ldloc.s  6
0xe86d  newobj   instance void PROCESS_INFORMATION::.ctor()
0xe872  call     void System.Deployment.Application.NativeMethods::CorLaunchApplication(unsigned int32 hostType, string applicationFullName, int32 manifestPathsCount, string[] manifestPaths, int32 activationDataCount, string[] activationData, class PROCESS_INFORMATION processInformation)
0xe877  leave.s  loc_E8E8
0xe879  stloc.s  8
0xe87b  ldloc.s  8
0xe87d  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0xe882  ldc.i4   0xFFFF
0xe887  and
0xe888  stloc.s  9
0xe88a  ldloc.s  9
0xe88c  ldc.i4   0x36B0
0xe891  blt.s    loc_E8AF
0xe893  ldloc.s  9
0xe895  ldc.i4   0x3A97
0xe89a  bgt.s    loc_E8AF
0xe89c  ldc.i4.1
0xe89d  ldstr    aExActivationfa// "Ex_ActivationFailureDueToSxSError"
0xe8a2  call     string System.Deployment.Application.Resources::GetString(string s)
0xe8a7  ldloc.s  8
0xe8a9  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0xe8ae  throw
0xe8af  ldloc.s  8
0xe8b1  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0xe8b6  ldc.i4   0x80070070
0xe8bb  bne.un.s loc_E8D1
0xe8bd  ldc.i4.s 0xA
0xe8bf  ldstr    aExStoreoperati// "Ex_StoreOperationFailed"
0xe8c4  call     string System.Deployment.Application.Resources::GetString(string s)
0xe8c9  ldloc.s  8
0xe8cb  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0xe8d0  throw
0xe8d1  rethrow
0xe8d3  stloc.s  0xA
0xe8d5  ldc.i4.1
0xe8d6  ldstr    aExGenericactiv// "Ex_GenericActivationFailure"
0xe8db  call     string System.Deployment.Application.Resources::GetString(string s)
0xe8e0  ldloc.s  0xA
0xe8e2  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0xe8e7  throw
0xe8e8  ret
```
