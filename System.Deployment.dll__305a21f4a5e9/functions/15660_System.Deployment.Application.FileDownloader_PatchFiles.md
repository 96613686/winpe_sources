# System.Deployment.Application.FileDownloader::PatchFiles

- ea: `0x15660`
- end: `0x157d6`
- name: `System.Deployment.Application.FileDownloader::PatchFiles`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x157e0`

## callees

- `0x14b40`
- `0x15210`
- `0x15400`
- `0x15660`
- `0x17d40`
- `0x1ecf0`
- `0x1ed00`
- `0x1ed40`
- `0x1ed60`
- `0x1ef20`
- `0x1ef60`
- `0x1fc50`
- `0x1fd30`
- `0x27fb0`

## string_xrefs

- `0x15668`: `Subscription is not installed. No patching.`
- `0x1568c`: `Subscription is not installed. No patching.`

## pseudocode

```c

```

## disassembly

```asm
0x15660  ldarg.1
0x15661  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0x15666  brtrue.s loc_15673
0x15668  ldstr    aSubscriptionIs// "Subscription is not installed. No patch"...
0x1566d  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x15672  ret
0x15673  ldnull
0x15674  stloc.0
0x15675  ldnull
0x15676  stloc.1
0x15677  ldarg.1
0x15678  callvirt instance class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionState::get_SubscriptionStore()
0x1567d  ldarg.1
0x1567e  callvirt instance class [mscorlib]System.IDisposable System.Deployment.Application.SubscriptionStore::AcquireSubscriptionReaderLock(class System.Deployment.Application.SubscriptionState subState)
0x15683  stloc.2
0x15684  ldarg.1
0x15685  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0x1568a  brtrue.s loc_1569B
0x1568c  ldstr    aSubscriptionIs// "Subscription is not installed. No patch"...
0x15691  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x15696  leave    loc_157D5
0x1569b  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x156a0  stloc.3
0x156a1  ldarg.1
0x156a2  callvirt instance class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionState::get_SubscriptionStore()
0x156a7  ldarg.1
0x156a8  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0x156ad  callvirt instance class IPathLock System.Deployment.Application.SubscriptionStore::LockApplicationPath(class System.Deployment.Application.DefinitionAppId definitionAppId)
0x156b2  stloc.0
0x156b3  ldloc.3
0x156b4  ldarg.1
0x156b5  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0x156ba  ldloc.0
0x156bb  callvirt instance string IPathLock::get_Path()
0x156c0  call     void System.Deployment.Application.FileDownloader::AddFilesInHashtable(class [mscorlib]System.Collections.Hashtable hashtable, class System.Deployment.Application.Manifest.AssemblyManifest applicationManifest, string applicationFolder)
0x156c5  ldarg.1
0x156c6  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_PreviousBind()
0x156cb  brfalse.s loc_156F1
0x156cd  ldarg.1
0x156ce  callvirt instance class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionState::get_SubscriptionStore()
0x156d3  ldarg.1
0x156d4  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_PreviousBind()
0x156d9  callvirt instance class IPathLock System.Deployment.Application.SubscriptionStore::LockApplicationPath(class System.Deployment.Application.DefinitionAppId definitionAppId)
0x156de  stloc.1
0x156df  ldloc.3
0x156e0  ldarg.1
0x156e1  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_PreviousApplicationManifest()
0x156e6  ldloc.1
0x156e7  callvirt instance string IPathLock::get_Path()
0x156ec  call     void System.Deployment.Application.FileDownloader::AddFilesInHashtable(class [mscorlib]System.Collections.Hashtable hashtable, class System.Deployment.Application.Manifest.AssemblyManifest applicationManifest, string applicationFolder)
0x156f1  newobj   instance void [mscorlib]System.Collections.Queue::.ctor()
0x156f6  stloc.s  4
0x156f8  ldnull
0x156f9  stloc.s  5
0x156fb  ldarg.0
0x156fc  ldfld    class [mscorlib]System.Collections.Queue System.Deployment.Application.FileDownloader::_fileQueue
0x15701  stloc.s  6
0x15703  ldc.i4.0
0x15704  stloc.s  7
0x15706  ldloc.s  6
0x15708  ldloca.s 7
0x1570a  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1570f  ldarg.0
0x15710  ldfld    class [mscorlib]System.Collections.Queue System.Deployment.Application.FileDownloader::_fileQueue
0x15715  callvirt instance int32 [mscorlib]System.Collections.Queue::get_Count()
0x1571a  ldc.i4.0
0x1571b  ble.s    loc_1572F
0x1571d  ldarg.0
0x1571e  ldfld    class [mscorlib]System.Collections.Queue System.Deployment.Application.FileDownloader::_fileQueue
0x15723  callvirt instance object [mscorlib]System.Collections.Queue::Dequeue()
0x15728  castclass DownloadQueueItem
0x1572d  stloc.s  5
0x1572f  leave.s  loc_1573D
0x15731  ldloc.s  7
0x15733  brfalse.s loc_1573C
0x15735  ldloc.s  6
0x15737  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1573c  endfinally
0x1573d  ldloc.s  5
0x1573f  brfalse.s loc_1575D
0x15741  ldarg.0
0x15742  ldloc.s  5
0x15744  ldloc.3
0x15745  call     instance bool System.Deployment.Application.FileDownloader::PatchSingleFile(class DownloadQueueItem item, class [mscorlib]System.Collections.Hashtable dependencyTable)
0x1574a  brtrue.s loc_15755
0x1574c  ldloc.s  4
0x1574e  ldloc.s  5
0x15750  callvirt instance void [mscorlib]System.Collections.Queue::Enqueue(object)
0x15755  ldarg.0
0x15756  ldfld    bool System.Deployment.Application.FileDownloader::_fCancelPending
0x1575b  brfalse.s loc_156F8
0x1575d  ldarg.0
0x1575e  ldfld    class [mscorlib]System.Collections.Queue System.Deployment.Application.FileDownloader::_fileQueue
0x15763  stloc.s  8
0x15765  ldc.i4.0
0x15766  stloc.s  9
0x15768  ldloc.s  8
0x1576a  ldloca.s 9
0x1576c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x15771  br.s     loc_15785
0x15773  ldloc.s  4
0x15775  ldarg.0
0x15776  ldfld    class [mscorlib]System.Collections.Queue System.Deployment.Application.FileDownloader::_fileQueue
0x1577b  callvirt instance object [mscorlib]System.Collections.Queue::Dequeue()
0x15780  callvirt instance void [mscorlib]System.Collections.Queue::Enqueue(object)
0x15785  ldarg.0
0x15786  ldfld    class [mscorlib]System.Collections.Queue System.Deployment.Application.FileDownloader::_fileQueue
0x1578b  callvirt instance int32 [mscorlib]System.Collections.Queue::get_Count()
0x15790  ldc.i4.0
0x15791  bgt.s    loc_15773
0x15793  ldarg.0
0x15794  ldloc.s  4
0x15796  stfld    class [mscorlib]System.Collections.Queue System.Deployment.Application.FileDownloader::_fileQueue
0x1579b  leave.s  loc_157C7
0x1579d  ldloc.s  9
0x1579f  brfalse.s loc_157A8
0x157a1  ldloc.s  8
0x157a3  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x157a8  endfinally
0x157a9  ldloc.1
0x157aa  brfalse.s loc_157B2
0x157ac  ldloc.1
0x157ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x157b2  endfinally
0x157b3  ldloc.0
0x157b4  brfalse.s loc_157BC
0x157b6  ldloc.0
0x157b7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x157bc  endfinally
0x157bd  ldloc.2
0x157be  brfalse.s loc_157C6
0x157c0  ldloc.2
0x157c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x157c6  endfinally
0x157c7  ldarg.0
0x157c8  ldfld    bool System.Deployment.Application.FileDownloader::_fCancelPending
0x157cd  brfalse.s loc_157D5
0x157cf  newobj   instance void System.Deployment.Application.DownloadCancelledException::.ctor()
0x157d4  throw
0x157d5  ret
```
