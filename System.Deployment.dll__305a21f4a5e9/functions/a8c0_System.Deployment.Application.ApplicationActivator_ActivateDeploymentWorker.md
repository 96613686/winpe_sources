# System.Deployment.Application.ApplicationActivator::ActivateDeploymentWorker

- ea: `0xa8c0`
- end: `0xabd0`
- name: `System.Deployment.Application.ApplicationActivator::ActivateDeploymentWorker`
- size: `784`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callees

- `0x40`
- `0xa410`
- `0xa780`
- `0xa8c0`
- `0xad70`
- `0xc080`
- `0xc100`
- `0x146f0`
- `0x14740`
- `0x147b0`
- `0x16c90`
- `0x17640`
- `0x17660`
- `0x17790`
- `0x17c80`
- `0x17cf0`
- `0x17d40`
- `0x17d50`
- `0x218f0`
- `0x21b30`
- `0x21bb0`
- `0x21bc0`
- `0x21e00`
- `0x22b20`
- `0x23020`
- `0x23410`
- `0x23440`

## string_xrefs

- `0xa9b9`: `Ex_NotSupportedUriScheme`
- `0xa9f4`: `ActivateManifestSucceeded`
- `0xaa16`: `ActivateManifestException`
- `0xaa60`: `ActivateManifestException`
- `0xaa82`: `ActivateManifestException`
- `0xaaa4`: `ActivateManifestException`
- `0xab4e`: `ActivateManifestException`

## pseudocode

```c

```

## disassembly

```asm
0xa8c0  ldnull
0xa8c1  stloc.0
0xa8c2  ldnull
0xa8c3  stloc.1
0xa8c4  ldnull
0xa8c5  stloc.2
0xa8c6  call     class Microsoft.Internal.Performance.CodeMarkers System.Deployment.Application.CodeMarker_Singleton::get_Instance()
0xa8cb  ldc.i4   0x20D
0xa8d0  callvirt instance bool Microsoft.Internal.Performance.CodeMarkers::CodeMarker(int32 nTimerID)
0xa8d5  pop
0xa8d6  ldarg.1
0xa8d7  castclass object[]
0xa8dc  stloc.3
0xa8dd  ldloc.3
0xa8de  ldc.i4.0
0xa8df  ldelem.ref
0xa8e0  castclass [mscorlib]System.String
0xa8e5  dup
0xa8e6  brtrue.s loc_A8EE
0xa8e8  pop
0xa8e9  ldsfld   string [mscorlib]System.String::Empty
0xa8ee  stloc.0
0xa8ef  call     class LogIdentity System.Deployment.Application.Logger::StartCurrentThreadLogging()
0xa8f4  pop
0xa8f5  ldloc.0
0xa8f6  call     void System.Deployment.Application.Logger::SetSubscriptionUrl(string subscrioptionUrl)
0xa8fb  ldstr    aActivationThro// "Activation through dfsvc.exe started."
0xa900  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xa905  ldstr    aActivatedeploy// "ActivateDeploymentWorker({0},{1},{2},{3"...
0xa90a  ldloc.3
0xa90b  call     void System.Deployment.Application.Logger::AddMethodCall(string messageFormat, object[] args)
0xa910  ldloc.3
0xa911  ldc.i4.1
0xa912  ldelem.ref
0xa913  unbox.any [mscorlib]System.Boolean
0xa918  stloc.s  4
0xa91a  ldloc.3
0xa91b  ldc.i4.2
0xa91c  ldelem.ref
0xa91d  brfalse.s loc_A928
0xa91f  ldloc.3
0xa920  ldc.i4.2
0xa921  ldelem.ref
0xa922  castclass [mscorlib]System.String
0xa927  stloc.1
0xa928  ldloc.3
0xa929  ldc.i4.3
0xa92a  ldelem.ref
0xa92b  brfalse.s loc_A936
0xa92d  ldloc.3
0xa92e  ldc.i4.3
0xa92f  ldelem.ref
0xa930  castclass [mscorlib]System.String
0xa935  stloc.2
0xa936  ldnull
0xa937  stloc.s  5
0xa939  ldloc.3
0xa93a  ldc.i4.4
0xa93b  ldelem.ref
0xa93c  brfalse.s loc_A948
0xa93e  ldloc.3
0xa93f  ldc.i4.4
0xa940  ldelem.ref
0xa941  castclass BrowserSettings
0xa946  stloc.s  5
0xa948  ldnull
0xa949  stloc.s  6
0xa94b  ldnull
0xa94c  stloc.s  7
0xa94e  ldarg.0
0xa94f  ldloc.0
0xa950  call     instance int32 System.Deployment.Application.ApplicationActivator::CheckActivationInProgress(string activationUrl)
0xa955  stloc.s  8
0xa957  ldarg.0
0xa958  ldc.i4.0
0xa959  newobj   instance void System.Deployment.Application.UserInterface::.ctor(bool wait)
0xa95e  stfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xa963  call     bool System.Deployment.Application.PolicyKeys::SuppressLimitOnNumberOfActivations()
0xa968  brtrue.s loc_A981
0xa96a  ldloc.s  8
0xa96c  ldc.i4.8
0xa96d  ble.s    loc_A981
0xa96f  ldc.i4.s 9
0xa971  ldstr    aExToomanylivea// "Ex_TooManyLiveActivation"
0xa976  call     string System.Deployment.Application.Resources::GetString(string s)
0xa97b  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0xa980  throw
0xa981  ldloc.0
0xa982  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa987  ldc.i4   0x4000
0xa98c  ble.s    loc_A99F
0xa98e  ldc.i4.1
0xa98f  ldstr    aExUrltoolong// "Ex_UrlTooLong"
0xa994  call     string System.Deployment.Application.Resources::GetString(string s)
0xa999  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0xa99e  throw
0xa99f  ldloc.0
0xa9a0  newobj   instance void [System]System.Uri::.ctor(string)
0xa9a5  stloc.s  6
0xa9a7  ldloc.s  6
0xa9a9  ldstr    aActivationurl// "activationUrl"
0xa9ae  call     void System.Deployment.Application.UriHelper::ValidateSupportedSchemeInArgument(class [System]System.Uri uri, string argumentName)
0xa9b3  leave.s  loc_A9CB
0xa9b5  stloc.s  9
0xa9b7  ldc.i4.s 0x14
0xa9b9  ldstr    aExNotsupported// "Ex_NotSupportedUriScheme"
0xa9be  call     string System.Deployment.Application.Resources::GetString(string s)
0xa9c3  ldloc.s  9
0xa9c5  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0xa9ca  throw
0xa9cb  ldstr    aPhaselogStarto// "PhaseLog_StartOfActivation"
0xa9d0  call     string System.Deployment.Application.Resources::GetString(string s)
0xa9d5  ldc.i4.1
0xa9d6  newarr   [mscorlib]System.Object
0xa9db  dup
0xa9dc  ldc.i4.0
0xa9dd  ldloc.0
0xa9de  stelem.ref
0xa9df  call     void System.Deployment.Application.Logger::AddPhaseInformation(string messageFormat, object[] args)
0xa9e4  ldarg.0
0xa9e5  ldloc.s  6
0xa9e7  ldloc.s  4
0xa9e9  ldloc.1
0xa9ea  ldloc.2
0xa9eb  ldloc.s  5
0xa9ed  ldloca.s 7
0xa9ef  call     instance void System.Deployment.Application.ApplicationActivator::PerformDeploymentActivationWithRetry(class [System]System.Uri activationUri, bool isShortcut, string textualSubId, string deploymentProviderUrlFromExtension, class BrowserSettings browserSettings, string& errorPageUrl)
0xa9f4  ldstr    aActivatemanife// "ActivateManifestSucceeded"
0xa9f9  call     string System.Deployment.Application.Resources::GetString(string s)
0xa9fe  ldc.i4.1
0xa9ff  newarr   [mscorlib]System.Object
0xaa04  dup
0xaa05  ldc.i4.0
0xaa06  ldloc.0
0xaa07  stelem.ref
0xaa08  call     void System.Deployment.Application.Logger::AddPhaseInformation(string messageFormat, object[] args)
0xaa0d  leave    loc_ABCF
0xaa12  stloc.s  0xA
0xaa14  ldloc.s  0xA
0xaa16  ldstr    aActivatemanife_0// "ActivateManifestException"
0xaa1b  call     string System.Deployment.Application.Resources::GetString(string s)
0xaa20  ldc.i4.1
0xaa21  newarr   [mscorlib]System.Object
0xaa26  dup
0xaa27  ldc.i4.0
0xaa28  ldloc.0
0xaa29  stelem.ref
0xaa2a  call     void System.Deployment.Application.Logger::AddErrorInformation(class [mscorlib]System.Exception exception, string messageFormat, object[] args)
0xaa2f  ldarg.0
0xaa30  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xaa35  brtrue.s loc_AA42
0xaa37  ldarg.0
0xaa38  newobj   instance void System.Deployment.Application.UserInterface::.ctor()
0xaa3d  stfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xaa42  ldarg.0
0xaa43  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xaa48  callvirt instance bool System.Deployment.Application.UserInterface::SplashCancelled()
0xaa4d  brtrue.s loc_AA57
0xaa4f  ldarg.0
0xaa50  ldloc.s  0xA
0xaa52  call     instance void System.Deployment.Application.ApplicationActivator::DisplayPlatformDetectionFailureUI(class System.Deployment.Application.DependentPlatformMissingException ex)
0xaa57  leave    loc_ABCF
0xaa5c  stloc.s  0xB
0xaa5e  ldloc.s  0xB
0xaa60  ldstr    aActivatemanife_0// "ActivateManifestException"
0xaa65  call     string System.Deployment.Application.Resources::GetString(string s)
0xaa6a  ldc.i4.1
0xaa6b  newarr   [mscorlib]System.Object
0xaa70  dup
0xaa71  ldc.i4.0
0xaa72  ldloc.0
0xaa73  stelem.ref
0xaa74  call     void System.Deployment.Application.Logger::AddErrorInformation(class [mscorlib]System.Exception exception, string messageFormat, object[] args)
0xaa79  leave    loc_ABCF
0xaa7e  stloc.s  0xC
0xaa80  ldloc.s  0xC
0xaa82  ldstr    aActivatemanife_0// "ActivateManifestException"
0xaa87  call     string System.Deployment.Application.Resources::GetString(string s)
0xaa8c  ldc.i4.1
0xaa8d  newarr   [mscorlib]System.Object
0xaa92  dup
0xaa93  ldc.i4.0
0xaa94  ldloc.0
0xaa95  stelem.ref
0xaa96  call     void System.Deployment.Application.Logger::AddErrorInformation(class [mscorlib]System.Exception exception, string messageFormat, object[] args)
0xaa9b  leave    loc_ABCF
0xaaa0  stloc.s  0xD
0xaaa2  ldloc.s  0xD
0xaaa4  ldstr    aActivatemanife_0// "ActivateManifestException"
0xaaa9  call     string System.Deployment.Application.Resources::GetString(string s)
0xaaae  ldc.i4.1
0xaaaf  newarr   [mscorlib]System.Object
0xaab4  dup
0xaab5  ldc.i4.0
0xaab6  ldloc.0
0xaab7  stelem.ref
0xaab8  call     void System.Deployment.Application.Logger::AddErrorInformation(class [mscorlib]System.Exception exception, string messageFormat, object[] args)
0xaabd  ldloc.s  0xD
0xaabf  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xaac4  ldc.i4.3
0xaac5  bne.un.s loc_AACC
0xaac7  leave    loc_ABCF
0xaacc  ldarg.0
0xaacd  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xaad2  brtrue.s loc_AADF
0xaad4  ldarg.0
0xaad5  newobj   instance void System.Deployment.Application.UserInterface::.ctor()
0xaada  stfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xaadf  ldarg.0
0xaae0  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xaae5  callvirt instance bool System.Deployment.Application.UserInterface::SplashCancelled()
0xaaea  brtrue.s loc_AB28
0xaaec  ldloc.s  0xD
0xaaee  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xaaf3  ldc.i4.s 9
0xaaf5  bne.un.s loc_AB1E
0xaaf7  ldsflda  int32 System.Deployment.Application.ApplicationActivator::_liveActivationLimitUIStatus
0xaafc  ldc.i4.1
0xaafd  ldc.i4.0
0xaafe  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0xab03  brtrue.s loc_AB28
0xab05  ldarg.0
0xab06  ldloc.s  0xD
0xab08  ldloc.s  7
0xab0a  call     instance void System.Deployment.Application.ApplicationActivator::DisplayActivationFailureReason(class [mscorlib]System.Exception exception, string errorPageUrl)
0xab0f  ldsflda  int32 System.Deployment.Application.ApplicationActivator::_liveActivationLimitUIStatus
0xab14  ldc.i4.0
0xab15  ldc.i4.1
0xab16  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0xab1b  pop
0xab1c  br.s     loc_AB28
0xab1e  ldarg.0
0xab1f  ldloc.s  0xD
0xab21  ldloc.s  7
0xab23  call     instance void System.Deployment.Application.ApplicationActivator::DisplayActivationFailureReason(class [mscorlib]System.Exception exception, string errorPageUrl)
0xab28  leave    loc_ABCF
0xab2d  stloc.s  0xE
0xab2f  ldloc.s  0xE
0xab31  isinst   [mscorlib]System.AccessViolationException
0xab36  brtrue.s loc_AB41
0xab38  ldloc.s  0xE
0xab3a  isinst   [mscorlib]System.OutOfMemoryException
0xab3f  brfalse.s loc_AB43
0xab41  rethrow
0xab43  call     bool System.Deployment.Application.PolicyKeys::DisableGenericExceptionHandler()
0xab48  brfalse.s loc_AB4C
0xab4a  rethrow
0xab4c  ldloc.s  0xE
0xab4e  ldstr    aActivatemanife_0// "ActivateManifestException"
0xab53  call     string System.Deployment.Application.Resources::GetString(string s)
0xab58  ldc.i4.1
0xab59  newarr   [mscorlib]System.Object
0xab5e  dup
0xab5f  ldc.i4.0
0xab60  ldloc.0
0xab61  stelem.ref
0xab62  call     void System.Deployment.Application.Logger::AddErrorInformation(class [mscorlib]System.Exception exception, string messageFormat, object[] args)
0xab67  ldarg.0
0xab68  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xab6d  brtrue.s loc_AB7A
0xab6f  ldarg.0
0xab70  newobj   instance void System.Deployment.Application.UserInterface::.ctor()
0xab75  stfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xab7a  ldarg.0
0xab7b  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xab80  callvirt instance bool System.Deployment.Application.UserInterface::SplashCancelled()
0xab85  brtrue.s loc_AB91
0xab87  ldarg.0
0xab88  ldloc.s  0xE
0xab8a  ldloc.s  7
0xab8c  call     instance void System.Deployment.Application.ApplicationActivator::DisplayActivationFailureReason(class [mscorlib]System.Exception exception, string errorPageUrl)
0xab91  leave.s  loc_ABCF
0xab93  ldarg.0
0xab94  ldloc.0
0xab95  call     instance void System.Deployment.Application.ApplicationActivator::RemoveActivationInProgressEntry(string activationUrl)
0xab9a  ldarg.0
0xab9b  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xaba0  brfalse.s loc_ABB4
0xaba2  ldarg.0
0xaba3  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xaba8  callvirt instance void System.Deployment.Application.UserInterface::Dispose()
0xabad  ldarg.0
0xabae  ldnull
0xabaf  stfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xabb4  call     class Microsoft.Internal.Performance.CodeMarkers System.Deployment.Application.CodeMarker_Singleton::get_Instance()
0xabb9  ldc.i4   0x20E
0xabbe  callvirt instance bool Microsoft.Internal.Performance.CodeMarkers::CodeMarker(int32 nTimerID)
0xabc3  pop
0xabc4  call     void System.Deployment.Application.Logger::EndCurrentThreadLogging()
0xabc9  call     void System.Deployment.Application.LifetimeManager::EndOperation()
0xabce  endfinally
0xabcf  ret
```
