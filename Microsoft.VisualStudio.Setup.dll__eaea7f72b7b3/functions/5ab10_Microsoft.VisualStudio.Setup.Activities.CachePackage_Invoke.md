# Microsoft.VisualStudio.Setup.Activities.CachePackage::Invoke

- ea: `0x5ab10`
- end: `0x5ac41`
- name: `Microsoft.VisualStudio.Setup.Activities.CachePackage::Invoke`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x596d0`
- `0x59710`
- `0x5aa50`
- `0x5ab10`
- `0x5e1b0`
- `0x5f050`

## string_xrefs

- `0x5abcd`: `Skipping cache of package '`
- `0x5ac0a`: `Skipping cache of package '`
- `0x5abdd`: `' since installing or downloading it failed`

## pseudocode

```c

```

## disassembly

```asm
0x5ab10  ldarg.0
0x5ab11  ldfld    class Microsoft.VisualStudio.Setup.Activities.ISynchronizedActivity Microsoft.VisualStudio.Setup.Activities.CachePackage::installOrDownload
0x5ab16  dup
0x5ab17  brtrue.s loc_5AB1C
0x5ab19  pop
0x5ab1a  br.s     loc_5AB21
0x5ab1c  callvirt instance void Microsoft.VisualStudio.Setup.Activities.ISynchronizedActivity::Wait()
0x5ab21  ldarg.0
0x5ab22  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5ab27  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x5ab2c  ldc.i4.1
0x5ab2d  beq.s    loc_5AB45
0x5ab2f  ldarg.0
0x5ab30  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5ab35  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x5ab3a  ldc.i4.4
0x5ab3b  beq.s    loc_5AB45
0x5ab3d  ldarg.0
0x5ab3e  call     instance bool Microsoft.VisualStudio.Setup.Activities.CachePackage::get_Replace()
0x5ab43  brfalse.s loc_5AB76
0x5ab45  ldarg.0
0x5ab46  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5ab4b  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_CurrentState()
0x5ab50  ldc.i4.3
0x5ab51  beq.s    loc_5AB64
0x5ab53  ldarg.0
0x5ab54  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5ab59  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_CurrentState()
0x5ab5e  ldc.i4.2
0x5ab5f  bne.un   loc_5AC40
0x5ab64  ldarg.0
0x5ab65  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Activities.CachePackage::cache
0x5ab6a  ldarg.0
0x5ab6b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5ab70  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager::RemovePackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage)
0x5ab75  ret
0x5ab76  ldarg.0
0x5ab77  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5ab7c  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x5ab81  ldc.i4.3
0x5ab82  bne.un   loc_5AC40
0x5ab87  ldarg.0
0x5ab88  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5ab8d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ApplicabilityState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_ApplicabilityState()
0x5ab92  dup
0x5ab93  brtrue.s loc_5AB99
0x5ab95  pop
0x5ab96  ldc.i4.1
0x5ab97  br.s     loc_5AB9E
0x5ab99  call     instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ApplicabilityState::get_IsValid()
0x5ab9e  brfalse  loc_5AC40
0x5aba3  ldarg.0
0x5aba4  ldfld    class Microsoft.VisualStudio.Setup.Activities.ISynchronizedActivity Microsoft.VisualStudio.Setup.Activities.CachePackage::installOrDownload
0x5aba9  dup
0x5abaa  brtrue.s loc_5ABB0
0x5abac  pop
0x5abad  ldnull
0x5abae  br.s     loc_5ABB5
0x5abb0  callvirt instance class [mscorlib]System.Exception Microsoft.VisualStudio.Setup.Activities.IActivity::get_Error()
0x5abb5  brfalse.s loc_5ABF2
0x5abb7  ldarg.0
0x5abb8  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5abbd  dup
0x5abbe  brtrue.s loc_5ABC2
0x5abc0  pop
0x5abc1  ret
0x5abc2  ldarg.0
0x5abc3  ldfld    class Microsoft.VisualStudio.Setup.Activities.ISynchronizedActivity Microsoft.VisualStudio.Setup.Activities.CachePackage::installOrDownload
0x5abc8  callvirt instance class [mscorlib]System.Exception Microsoft.VisualStudio.Setup.Activities.IActivity::get_Error()
0x5abcd  ldstr    aSkippingCacheO// "Skipping cache of package '"
0x5abd2  ldarg.0
0x5abd3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5abd8  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x5abdd  ldstr    aSinceInstallin// "' since installing or downloading it fa"...
0x5abe2  call     string [mscorlib]System.String::Concat(string, string, string)
0x5abe7  call     T0x2B000003
0x5abec  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x5abf1  ret
0x5abf2  ldarg.0
0x5abf3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5abf8  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::ShouldSkip(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage)
0x5abfd  brfalse.s loc_5AC2F
0x5abff  ldarg.0
0x5ac00  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5ac05  dup
0x5ac06  brtrue.s loc_5AC0A
0x5ac08  pop
0x5ac09  ret
0x5ac0a  ldstr    aSkippingCacheO// "Skipping cache of package '"
0x5ac0f  ldarg.0
0x5ac10  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5ac15  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x5ac1a  ldstr    aSinceThePackag_0// "' since the package or a parent package"...
0x5ac1f  call     string [mscorlib]System.String::Concat(string, string, string)
0x5ac24  call     T0x2B000003
0x5ac29  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5ac2e  ret
0x5ac2f  ldarg.0
0x5ac30  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Activities.CachePackage::cache
0x5ac35  ldarg.0
0x5ac36  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5ac3b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager::AddPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage)
0x5ac40  ret
```
