# Microsoft.VisualStudio.Setup.Activities.QueuePersistedNgenCommands::Invoke

- ea: `0x5f720`
- end: `0x5f919`
- name: `Microsoft.VisualStudio.Setup.Activities.QueuePersistedNgenCommands::Invoke`
- size: `505`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x596d0`
- `0x596f0`
- `0x5f720`
- `0x5f920`

## string_xrefs

- `0x5f7d7`: `Skipping persisted ngen commands: no persisted ngen state.`
- `0x5f811`: `Instance has no installation path`
- `0x5f82a`: `Skipping persisted ngen commands: instance has no installation path.`
- `0x5f8d5`: `Queued persisted ngen commands`
- `0x5f8e6`: `Queuing persisted ngen commands was cancelled`
- `0x5f901`: `Failed to queue persisted ngen commands`

## pseudocode

```c

```

## disassembly

```asm
0x5f720  ldarg.0
0x5f721  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5f726  ldc.i4.0
0x5f727  call     T0x2B0000A0
0x5f72c  dup
0x5f72d  brtrue.s loc_5F733
0x5f72f  pop
0x5f730  ldnull
0x5f731  br.s     loc_5F738
0x5f733  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager::GetInstance()
0x5f738  stloc.0
0x5f739  ldarg.0
0x5f73a  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5f73f  ldc.i4.0
0x5f740  call     T0x2B000039
0x5f745  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5f74a  dup
0x5f74b  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::QUEUEPERSISTEDNGENPERSISTEDCOMMANDSEXISTPROPERTY
0x5f750  ldloc.0
0x5f751  brtrue.s loc_5F756
0x5f753  ldc.i4.0
0x5f754  br.s     loc_5F77F
0x5f756  ldloc.0
0x5f757  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_NgenState()
0x5f75c  dup
0x5f75d  brtrue.s loc_5F76C
0x5f75f  pop
0x5f760  ldloca.s 5
0x5f762  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x5f768  ldloc.s  5
0x5f76a  br.s     loc_5F776
0x5f76c  call     instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::HasEntries()
0x5f771  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x5f776  stloc.s  5
0x5f778  ldloca.s 5
0x5f77a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x5f77f  box      [mscorlib]System.Boolean
0x5f784  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5f789  stloc.1
0x5f78a  dup
0x5f78b  brtrue.s loc_5F791
0x5f78d  pop
0x5f78e  ldnull
0x5f78f  br.s     loc_5F79E
0x5f791  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::QUEUEPERSISTEDNGENEVENT
0x5f796  ldloc.1
0x5f797  ldc.i4.0
0x5f798  ldc.i4.0
0x5f799  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x5f79e  stloc.2
0x5f79f  ldloc.0
0x5f7a0  brtrue.s loc_5F7A5
0x5f7a2  ldnull
0x5f7a3  br.s     loc_5F7AB
0x5f7a5  ldloc.0
0x5f7a6  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_NgenState()
0x5f7ab  stloc.3
0x5f7ac  ldloc.3
0x5f7ad  brfalse.s loc_5F7B7
0x5f7af  ldloc.3
0x5f7b0  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::HasEntries()
0x5f7b5  brtrue.s loc_5F7EB
0x5f7b7  ldloc.1
0x5f7b8  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::QUEUEPERSISTEDNGENSKIPPEDPROPERTY
0x5f7bd  ldc.i4.1
0x5f7be  box      [mscorlib]System.Boolean
0x5f7c3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5f7c8  ldarg.0
0x5f7c9  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5f7ce  dup
0x5f7cf  brtrue.s loc_5F7D7
0x5f7d1  pop
0x5f7d2  leave    loc_5F918
0x5f7d7  ldstr    aSkippingPersis// "Skipping persisted ngen commands: no pe"...
0x5f7dc  call     T0x2B000003
0x5f7e1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5f7e6  leave    loc_5F918
0x5f7eb  ldloc.0
0x5f7ec  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_InstallationPath()
0x5f7f1  stloc.s  4
0x5f7f3  ldloc.s  4
0x5f7f5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5f7fa  brfalse.s loc_5F83E
0x5f7fc  ldloc.1
0x5f7fd  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::QUEUEPERSISTEDNGENSKIPPEDPROPERTY
0x5f802  ldc.i4.1
0x5f803  box      [mscorlib]System.Boolean
0x5f808  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5f80d  ldloc.2
0x5f80e  brfalse.s loc_5F81B
0x5f810  ldloc.2
0x5f811  ldstr    aInstanceHasNoI// "Instance has no installation path"
0x5f816  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x5f81b  ldarg.0
0x5f81c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5f821  dup
0x5f822  brtrue.s loc_5F82A
0x5f824  pop
0x5f825  leave    loc_5F918
0x5f82a  ldstr    aSkippingPersis_0// "Skipping persisted ngen commands: insta"...
0x5f82f  call     T0x2B000003
0x5f834  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5f839  leave    loc_5F918
0x5f83e  ldloc.1
0x5f83f  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::QUEUEPERSISTEDNGENTOTALPROPERTY
0x5f844  ldloc.3
0x5f845  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::get_Priority1()
0x5f84a  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry>>::get_Count()
0x5f84f  ldloc.3
0x5f850  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::get_Priority2()
0x5f855  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry>>::get_Count()
0x5f85a  add
0x5f85b  ldloc.3
0x5f85c  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::get_Priority3()
0x5f861  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry>>::get_Count()
0x5f866  add
0x5f867  box      [mscorlib]System.Int32
0x5f86c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5f871  ldloc.1
0x5f872  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::QUEUEPERSISTEDNGENCOMMANDSP1PROPERTY
0x5f877  ldarg.0
0x5f878  ldloc.3
0x5f879  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::get_Priority1()
0x5f87e  ldc.i4.1
0x5f87f  ldloc.s  4
0x5f881  ldarg.1
0x5f882  call     instance int32 Microsoft.VisualStudio.Setup.Activities.QueuePersistedNgenCommands::QueueEntries(class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> entries, int32 priority, string instanceRoot, valuetype [mscorlib]System.Threading.CancellationToken token)
0x5f887  box      [mscorlib]System.Int32
0x5f88c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5f891  ldloc.1
0x5f892  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::QUEUEPERSISTEDNGENCOMMANDSP2PROPERTY
0x5f897  ldarg.0
0x5f898  ldloc.3
0x5f899  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::get_Priority2()
0x5f89e  ldc.i4.2
0x5f89f  ldloc.s  4
0x5f8a1  ldarg.1
0x5f8a2  call     instance int32 Microsoft.VisualStudio.Setup.Activities.QueuePersistedNgenCommands::QueueEntries(class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> entries, int32 priority, string instanceRoot, valuetype [mscorlib]System.Threading.CancellationToken token)
0x5f8a7  box      [mscorlib]System.Int32
0x5f8ac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5f8b1  ldloc.1
0x5f8b2  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::QUEUEPERSISTEDNGENCOMMANDSP3PROPERTY
0x5f8b7  ldarg.0
0x5f8b8  ldloc.3
0x5f8b9  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenState::get_Priority3()
0x5f8be  ldc.i4.3
0x5f8bf  ldloc.s  4
0x5f8c1  ldarg.1
0x5f8c2  call     instance int32 Microsoft.VisualStudio.Setup.Activities.QueuePersistedNgenCommands::QueueEntries(class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry> entries, int32 priority, string instanceRoot, valuetype [mscorlib]System.Threading.CancellationToken token)
0x5f8c7  box      [mscorlib]System.Int32
0x5f8cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5f8d1  ldloc.2
0x5f8d2  brfalse.s loc_5F8DF
0x5f8d4  ldloc.2
0x5f8d5  ldstr    aQueuedPersiste// "Queued persisted ngen commands"
0x5f8da  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x5f8df  leave.s  loc_5F918
0x5f8e1  pop
0x5f8e2  ldloc.2
0x5f8e3  brfalse.s loc_5F8F0
0x5f8e5  ldloc.2
0x5f8e6  ldstr    aQueuingPersist_0// "Queuing persisted ngen commands was can"...
0x5f8eb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordCancel(string)
0x5f8f0  rethrow
0x5f8f2  stloc.s  6
0x5f8f4  ldloc.2
0x5f8f5  brfalse.s loc_5F90C
0x5f8f7  ldloc.2
0x5f8f8  ldloc.s  6
0x5f8fa  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5f8ff  ldloc.s  6
0x5f901  ldstr    aFailedToQueueP// "Failed to queue persisted ngen commands"
0x5f906  ldc.i4.1
0x5f907  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x5f90c  rethrow
0x5f90e  ldloc.2
0x5f90f  brfalse.s loc_5F917
0x5f911  ldloc.2
0x5f912  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f917  endfinally
0x5f918  ret
```
