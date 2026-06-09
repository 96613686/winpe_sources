# System.Deployment.Application.DeploymentManager::WaitForAssertApplicationRequirements

- ea: `0x12100`
- end: `0x1218d`
- name: `System.Deployment.Application.DeploymentManager::WaitForAssertApplicationRequirements`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x11d60`

## callees

- `0x12100`
- `0x146b0`
- `0x17d30`
- `0x23020`

## string_xrefs

- `0x12145`: `Ex_CannotCommitNoTrustDecision`
- `0x12158`: `Ex_CannotCommitTrustFailed`
- `0x1216c`: `Ex_CannotCommitPlatformRequirementsFailed`

## pseudocode

```c

```

## disassembly

```asm
0x12100  ldarg.0
0x12101  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x12106  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.CommitApplicationParams::appType
0x1210b  ldc.i4.3
0x1210c  bne.un.s loc_1210F
0x1210e  ret
0x1210f  ldarg.0
0x12110  ldfld    valuetype CallerType System.Deployment.Application.DeploymentManager::_callerType
0x12115  ldc.i4.1
0x12116  bne.un.s loc_12119
0x12118  ret
0x12119  ldarg.0
0x1211a  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x1211f  ldstr    aWaitforasserta// "WaitForAssertApplicationRequirements() "...
0x12124  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x12129  ldarg.0
0x1212a  ldfld    class [mscorlib]System.Threading.ManualResetEvent[] System.Deployment.Application.DeploymentManager::_assertApplicationReqEvents
0x1212f  stloc.1
0x12130  ldloc.1
0x12131  ldsfld   valuetype [mscorlib]System.TimeSpan System.Deployment.Application.Constants::AssertApplicationRequirementsTimeout
0x12136  ldc.i4.0
0x12137  call     int32 [mscorlib]System.Threading.WaitHandle::WaitAny(class [mscorlib]System.Threading.WaitHandle[], valuetype [mscorlib]System.TimeSpan, bool)
0x1213c  stloc.0
0x1213d  ldloc.0
0x1213e  ldc.i4   0x102
0x12143  bne.un.s loc_12155
0x12145  ldstr    aExCannotcommit// "Ex_CannotCommitNoTrustDecision"
0x1214a  call     string System.Deployment.Application.Resources::GetString(string s)
0x1214f  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(string message)
0x12154  throw
0x12155  ldloc.0
0x12156  brtrue.s loc_12168
0x12158  ldstr    aExCannotcommit_0// "Ex_CannotCommitTrustFailed"
0x1215d  call     string System.Deployment.Application.Resources::GetString(string s)
0x12162  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(string message)
0x12167  throw
0x12168  ldloc.0
0x12169  ldc.i4.1
0x1216a  bne.un.s loc_1217C
0x1216c  ldstr    aExCannotcommit_1// "Ex_CannotCommitPlatformRequirementsFail"...
0x12171  call     string System.Deployment.Application.Resources::GetString(string s)
0x12176  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(string message)
0x1217b  throw
0x1217c  ldarg.0
0x1217d  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x12182  ldstr    aWaitforasserta_0// "WaitForAssertApplicationRequirements() "...
0x12187  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x1218c  ret
```
