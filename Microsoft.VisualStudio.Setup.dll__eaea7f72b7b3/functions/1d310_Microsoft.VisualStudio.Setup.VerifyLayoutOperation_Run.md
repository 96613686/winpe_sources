# Microsoft.VisualStudio.Setup.VerifyLayoutOperation::Run

- ea: `0x1d310`
- end: `0x1d812`
- name: `Microsoft.VisualStudio.Setup.VerifyLayoutOperation::Run`
- size: `1282`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14c00`
- `0x14df0`
- `0x14ec0`
- `0x15030`
- `0x15c20`
- `0x15c30`
- `0x15c90`
- `0x15cd0`
- `0x15cf0`
- `0x15d10`
- `0x15d30`
- `0x15e10`
- `0x15e30`
- `0x163d0`
- `0x1af10`
- `0x1af30`
- `0x1af50`
- `0x1d310`
- `0x1d940`
- `0x27720`
- `0x29280`
- `0x3a6a0`
- `0x59710`
- `0x5a220`
- `0x5ae70`
- `0x5aed0`
- `0x5b510`
- `0x5b550`
- `0x5b5e0`
- `0x613c0`
- `0x613e0`
- `0x61400`

## string_xrefs

- `0x1d6cd`: `' will not be deleted because it is outside of the layout directory '`
- `0x1d7ec`: `Completed '{0}' operation`
- `0x1d4c4`: `These files are missing from the layout directory:`
- `0x1d578`: `These files are invalid in the layout directory:`
- `0x1d61c`: `Verification completed. No problem was found.`
- `0x1d64d`: `Starting to fix this layout directory`

## pseudocode

```c

```

## disassembly

```asm
0x1d310  ldarga.s 1
0x1d312  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x1d317  ldarg.0
0x1d318  call     instance void Microsoft.VisualStudio.Setup.LayoutOperationBase::Initialize()
0x1d31d  ldarg.0
0x1d31e  call     instance bool Microsoft.VisualStudio.Setup.LayoutOperationBase::Plan()
0x1d323  brtrue.s loc_1D326
0x1d325  ret
0x1d326  ldarg.0
0x1d327  call     instance class Microsoft.VisualStudio.Setup.Services.ProgressAggregator Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Progress()
0x1d32c  ldarg.0
0x1d32d  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Activities.VerifyPackage> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::verifyPackages
0x1d332  ldarg.0
0x1d333  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Services()
0x1d338  ldnull
0x1d339  ldc.i4.m1
0x1d33a  callvirt instance void Microsoft.VisualStudio.Setup.Services.ProgressAggregatorBase::Initialize(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackageProgress> packageProgressCollection, [opt] class [mscorlib]System.IServiceProvider services, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance instance, [opt] valuetype Microsoft.VisualStudio.Setup.ProgressType type)
0x1d33f  ldarg.0
0x1d340  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x1d345  dup
0x1d346  brtrue.s loc_1D34B
0x1d348  pop
0x1d349  br.s     loc_1D36F
0x1d34b  ldstr    aStarting0Opera// "Starting '{0}' operation"
0x1d350  ldarg.0
0x1d351  call     instance class Microsoft.VisualStudio.Setup.LayoutContext Microsoft.VisualStudio.Setup.LayoutOperationBase::get_LayoutContext()
0x1d356  callvirt instance valuetype Microsoft.VisualStudio.Setup.LayoutMode Microsoft.VisualStudio.Setup.LayoutContext::get_LayoutMode()
0x1d35b  box      Microsoft.VisualStudio.Setup.LayoutMode
0x1d360  call     string [mscorlib]System.String::Format(string, object)
0x1d365  call     T0x2B000003
0x1d36a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1d36f  ldarg.0
0x1d370  ldfld    class Microsoft.VisualStudio.Setup.Activities.AsyncCoordinator Microsoft.VisualStudio.Setup.VerifyLayoutOperation::parallelVerifies
0x1d375  ldarg.1
0x1d376  callvirt instance void Microsoft.VisualStudio.Setup.Activities.Coordinator::Run(valuetype [mscorlib]System.Threading.CancellationToken token)
0x1d37b  ldarg.0
0x1d37c  ldfld    class Microsoft.VisualStudio.Setup.Activities.AsyncCoordinator Microsoft.VisualStudio.Setup.VerifyLayoutOperation::parallelVerifies
0x1d381  callvirt instance void Microsoft.VisualStudio.Setup.Activities.AsyncCoordinator::Wait()
0x1d386  leave.s  loc_1D38B
0x1d388  pop
0x1d389  leave.s  loc_1D38B
0x1d38b  ldnull
0x1d38c  stloc.0
0x1d38d  ldarg.0
0x1d38e  call     instance class Microsoft.VisualStudio.Setup.LayoutContext Microsoft.VisualStudio.Setup.LayoutOperationBase::get_LayoutContext()
0x1d393  callvirt instance valuetype Microsoft.VisualStudio.Setup.LayoutMode Microsoft.VisualStudio.Setup.LayoutContext::get_LayoutMode()
0x1d398  ldc.i4.4
0x1d399  bne.un.s loc_1D3A1
0x1d39b  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::.ctor()
0x1d3a0  stloc.0
0x1d3a1  ldc.i4.0
0x1d3a2  stloc.1
0x1d3a3  ldarg.0
0x1d3a4  ldfld    class Microsoft.VisualStudio.Setup.Activities.AsyncCoordinator Microsoft.VisualStudio.Setup.VerifyLayoutOperation::parallelVerifies
0x1d3a9  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Activities.IActivity> Microsoft.VisualStudio.Setup.Activities.Coordinator::get_AllActivities()
0x1d3ae  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Activities.IActivity>::GetEnumerator()
0x1d3b3  stloc.s  4
0x1d3b5  br       loc_1D474
0x1d3ba  ldloc.s  4
0x1d3bc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Activities.IActivity>::get_Current()
0x1d3c1  ldc.i4.0
0x1d3c2  stloc.s  5
0x1d3c4  isinst   Microsoft.VisualStudio.Setup.Activities.VerifyPackage
0x1d3c9  stloc.s  6
0x1d3cb  ldloc.s  6
0x1d3cd  brfalse  loc_1D474
0x1d3d2  ldloc.s  6
0x1d3d4  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Activities.VerifyPackage::get_MissingPayloads()
0x1d3d9  dup
0x1d3da  brtrue.s loc_1D3E0
0x1d3dc  pop
0x1d3dd  ldc.i4.0
0x1d3de  br.s     loc_1D3E5
0x1d3e0  call     T0x2B000015
0x1d3e5  brfalse.s loc_1D40F
0x1d3e7  ldarg.0
0x1d3e8  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::missingPayloads
0x1d3ed  brtrue.s loc_1D3FA
0x1d3ef  ldarg.0
0x1d3f0  newobj   instance void class [System]System.Collections.Concurrent.ConcurrentBag`1<string>::.ctor()
0x1d3f5  stfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::missingPayloads
0x1d3fa  ldarg.0
0x1d3fb  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::missingPayloads
0x1d400  ldloc.s  6
0x1d402  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Activities.VerifyPackage::get_MissingPayloads()
0x1d407  call     T0x2B000118
0x1d40c  ldc.i4.1
0x1d40d  stloc.s  5
0x1d40f  ldloc.s  6
0x1d411  callvirt instance class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.Activities.VerifyPackage::get_InvalidPayloads()
0x1d416  dup
0x1d417  brtrue.s loc_1D41D
0x1d419  pop
0x1d41a  ldc.i4.0
0x1d41b  br.s     loc_1D422
0x1d41d  call     T0x2B000015
0x1d422  brfalse.s loc_1D44C
0x1d424  ldarg.0
0x1d425  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::invalidPayloads
0x1d42a  brtrue.s loc_1D437
0x1d42c  ldarg.0
0x1d42d  newobj   instance void class [System]System.Collections.Concurrent.ConcurrentBag`1<string>::.ctor()
0x1d432  stfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::invalidPayloads
0x1d437  ldarg.0
0x1d438  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::invalidPayloads
0x1d43d  ldloc.s  6
0x1d43f  callvirt instance class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.Activities.VerifyPackage::get_InvalidPayloads()
0x1d444  call     T0x2B000118
0x1d449  ldc.i4.1
0x1d44a  stloc.s  5
0x1d44c  ldloc.1
0x1d44d  ldloc.s  6
0x1d44f  callvirt instance int32 Microsoft.VisualStudio.Setup.Activities.VerifyPackage::get_TotalPayloads()
0x1d454  add
0x1d455  stloc.1
0x1d456  ldloc.s  5
0x1d458  brfalse.s loc_1D474
0x1d45a  ldloc.s  6
0x1d45c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x1d461  brfalse.s loc_1D474
0x1d463  ldloc.0
0x1d464  brfalse.s loc_1D474
0x1d466  ldloc.0
0x1d467  ldloc.s  6
0x1d469  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x1d46e  callvirt instance bool class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::Add(var<u1>)
0x1d473  pop
0x1d474  ldloc.s  4
0x1d476  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d47b  brtrue   loc_1D3BA
0x1d480  leave.s  loc_1D48E
0x1d482  ldloc.s  4
0x1d484  brfalse.s loc_1D48D
0x1d486  ldloc.s  4
0x1d488  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d48d  endfinally
0x1d48e  ldarg.0
0x1d48f  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::VERIFYLAYOUTTOTALPAYLOADCOUNTPPROPERTY
0x1d494  ldloc.1
0x1d495  box      [mscorlib]System.Int32
0x1d49a  call     instance void Microsoft.VisualStudio.Setup.LayoutOperationBase::AddTelemetryProperty(string propertyName, object propertyValue)
0x1d49f  ldc.i4.0
0x1d4a0  stloc.2
0x1d4a1  ldarg.0
0x1d4a2  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::missingPayloads
0x1d4a7  dup
0x1d4a8  brtrue.s loc_1D4AE
0x1d4aa  pop
0x1d4ab  ldc.i4.0
0x1d4ac  br.s     loc_1D4B3
0x1d4ae  call     T0x2B000015
0x1d4b3  brfalse  loc_1D542
0x1d4b8  ldarg.0
0x1d4b9  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x1d4be  dup
0x1d4bf  brtrue.s loc_1D4C4
0x1d4c1  pop
0x1d4c2  br.s     loc_1D4D3
0x1d4c4  ldstr    aTheseFilesAreM// "These files are missing from the layout"...
0x1d4c9  call     T0x2B000003
0x1d4ce  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1d4d3  ldarg.0
0x1d4d4  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::missingPayloads
0x1d4d9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [System]System.Collections.Concurrent.ConcurrentBag`1<string>::GetEnumerator()
0x1d4de  stloc.s  7
0x1d4e0  br.s     loc_1D503
0x1d4e2  ldloc.s  7
0x1d4e4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x1d4e9  stloc.s  8
0x1d4eb  ldarg.0
0x1d4ec  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x1d4f1  dup
0x1d4f2  brtrue.s loc_1D4F7
0x1d4f4  pop
0x1d4f5  br.s     loc_1D503
0x1d4f7  ldloc.s  8
0x1d4f9  call     T0x2B000003
0x1d4fe  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1d503  ldloc.s  7
0x1d505  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d50a  brtrue.s loc_1D4E2
0x1d50c  leave.s  loc_1D51A
0x1d50e  ldloc.s  7
0x1d510  brfalse.s loc_1D519
0x1d512  ldloc.s  7
0x1d514  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d519  endfinally
0x1d51a  ldarg.0
0x1d51b  ldarg.0
0x1d51c  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::missingPayloads
0x1d521  ldstr    aVerifylayoutmi// "VerifyLayoutMissingPackages"
0x1d526  ldnull
0x1d527  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::GetNeutralResourceString(string resourceId, [opt] class [mscorlib]System.Resources.ResourceManager resourceManager)
0x1d52c  call     string Microsoft.VisualStudio.Setup.Resources::get_VerifyLayoutMissingPackages()
0x1d531  call     instance void Microsoft.VisualStudio.Setup.VerifyLayoutOperation::ReportMessages(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> messageBag, string neutralMessageContent, string localizedMessageContent)
0x1d536  ldarg.0
0x1d537  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::missingPayloads
0x1d53c  callvirt instance int32 class [System]System.Collections.Concurrent.ConcurrentBag`1<string>::get_Count()
0x1d541  stloc.2
0x1d542  ldarg.0
0x1d543  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::VERIFYLAYOUTMISSINGPAYLOADCOUNTPROPERTY
0x1d548  ldloc.2
0x1d549  box      [mscorlib]System.Int32
0x1d54e  call     instance void Microsoft.VisualStudio.Setup.LayoutOperationBase::AddTelemetryProperty(string propertyName, object propertyValue)
0x1d553  ldc.i4.0
0x1d554  stloc.3
0x1d555  ldarg.0
0x1d556  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::invalidPayloads
0x1d55b  dup
0x1d55c  brtrue.s loc_1D562
0x1d55e  pop
0x1d55f  ldc.i4.0
0x1d560  br.s     loc_1D567
0x1d562  call     T0x2B000015
0x1d567  brfalse  loc_1D5F6
0x1d56c  ldarg.0
0x1d56d  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x1d572  dup
0x1d573  brtrue.s loc_1D578
0x1d575  pop
0x1d576  br.s     loc_1D587
0x1d578  ldstr    aTheseFilesAreI// "These files are invalid in the layout d"...
0x1d57d  call     T0x2B000003
0x1d582  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1d587  ldarg.0
0x1d588  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::invalidPayloads
0x1d58d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [System]System.Collections.Concurrent.ConcurrentBag`1<string>::GetEnumerator()
0x1d592  stloc.s  7
0x1d594  br.s     loc_1D5B7
0x1d596  ldloc.s  7
0x1d598  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x1d59d  stloc.s  9
0x1d59f  ldarg.0
0x1d5a0  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x1d5a5  dup
0x1d5a6  brtrue.s loc_1D5AB
0x1d5a8  pop
0x1d5a9  br.s     loc_1D5B7
0x1d5ab  ldloc.s  9
0x1d5ad  call     T0x2B000003
0x1d5b2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1d5b7  ldloc.s  7
0x1d5b9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d5be  brtrue.s loc_1D596
0x1d5c0  leave.s  loc_1D5CE
0x1d5c2  ldloc.s  7
0x1d5c4  brfalse.s loc_1D5CD
0x1d5c6  ldloc.s  7
0x1d5c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d5cd  endfinally
0x1d5ce  ldarg.0
0x1d5cf  ldarg.0
0x1d5d0  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::invalidPayloads
0x1d5d5  ldstr    aVerifylayoutin// "VerifyLayoutInvalidPackages"
0x1d5da  ldnull
0x1d5db  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::GetNeutralResourceString(string resourceId, [opt] class [mscorlib]System.Resources.ResourceManager resourceManager)
0x1d5e0  call     string Microsoft.VisualStudio.Setup.Resources::get_VerifyLayoutInvalidPackages()
0x1d5e5  call     instance void Microsoft.VisualStudio.Setup.VerifyLayoutOperation::ReportMessages(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> messageBag, string neutralMessageContent, string localizedMessageContent)
0x1d5ea  ldarg.0
0x1d5eb  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.VerifyLayoutOperation::invalidPayloads
0x1d5f0  callvirt instance int32 class [System]System.Collections.Concurrent.ConcurrentBag`1<string>::get_Count()
0x1d5f5  stloc.3
0x1d5f6  ldarg.0
0x1d5f7  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::VERIFYLAYOUTINVALIDPAYLOADCOUNTPPROPERTY
0x1d5fc  ldloc.3
0x1d5fd  box      [mscorlib]System.Int32
0x1d602  call     instance void Microsoft.VisualStudio.Setup.LayoutOperationBase::AddTelemetryProperty(string propertyName, object propertyValue)
0x1d607  ldloc.2
0x1d608  brtrue.s loc_1D630
0x1d60a  ldloc.3
0x1d60b  brtrue.s loc_1D630
0x1d60d  ldarg.0
0x1d60e  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x1d613  dup
0x1d614  brtrue.s loc_1D61C
0x1d616  pop
0x1d617  leave    loc_1D811
0x1d61c  ldstr    aVerificationCo// "Verification completed. No problem was "...
0x1d621  call     T0x2B000003
0x1d626  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x1d62b  leave    loc_1D811
0x1d630  ldloc.0
0x1d631  brfalse  loc_1D775
0x1d636  ldloc.0
0x1d637  call     T0x2B0000E1
0x1d63c  brfalse  loc_1D775
0x1d641  ldarg.0
0x1d642  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x1d647  dup
0x1d648  brtrue.s loc_1D64D
0x1d64a  pop
0x1d64b  br.s     loc_1D65C
0x1d64d  ldstr    aStartingToFixT// "Starting to fix this layout directory"
0x1d652  call     T0x2B000003
0x1d657  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1d65c  ldloc.0
0x1d65d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x1d662  stloc.s  0xA
0x1d664  br       loc_1D71B
0x1d669  ldloc.s  0xA
  ... truncated ...
```
