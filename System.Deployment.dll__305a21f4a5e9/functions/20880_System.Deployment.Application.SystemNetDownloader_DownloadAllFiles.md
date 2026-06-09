# System.Deployment.Application.SystemNetDownloader::DownloadAllFiles

- ea: `0x20880`
- end: `0x20951`
- name: `System.Deployment.Application.SystemNetDownloader::DownloadAllFiles`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14b40`
- `0x17d40`
- `0x203a0`
- `0x20880`

## string_xrefs

- `0x20898`: ` Current TLS Protocol = `
- `0x208d0`: ` Default TLS protocol is changed to = {0} with implicit fallback `

## pseudocode

```c

```

## disassembly

```asm
0x20880  call     valuetype [System]System.Net.SecurityProtocolType [System]System.Net.ServicePointManager::get_SecurityProtocol()
0x20885  call     valuetype [System]System.Net.SecurityProtocolType [System]System.Net.ServicePointManager::get_SecurityProtocol()
0x2088a  ldc.i4   0x300
0x2088f  or
0x20890  ldc.i4   0xC00
0x20895  or
0x20896  beq.s    loc_208F2
0x20898  ldstr    aCurrentTlsProt// " Current TLS Protocol = "
0x2089d  call     valuetype [System]System.Net.SecurityProtocolType [System]System.Net.ServicePointManager::get_SecurityProtocol()
0x208a2  stloc.0
0x208a3  ldloca.s 0
0x208a5  constrained. [System]System.Net.SecurityProtocolType
0x208ab  callvirt instance string [mscorlib]System.Object::ToString()
0x208b0  call     string [mscorlib]System.String::Concat(string, string)
0x208b5  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x208ba  call     valuetype [System]System.Net.SecurityProtocolType [System]System.Net.ServicePointManager::get_SecurityProtocol()
0x208bf  ldc.i4   0x300
0x208c4  or
0x208c5  ldc.i4   0xC00
0x208ca  or
0x208cb  call     void [System]System.Net.ServicePointManager::set_SecurityProtocol(valuetype [System]System.Net.SecurityProtocolType)
0x208d0  ldstr    aDefaultTlsProt// " Default TLS protocol is changed to = {"...
0x208d5  call     valuetype [System]System.Net.SecurityProtocolType [System]System.Net.ServicePointManager::get_SecurityProtocol()
0x208da  stloc.0
0x208db  ldloca.s 0
0x208dd  constrained. [System]System.Net.SecurityProtocolType
0x208e3  callvirt instance string [mscorlib]System.Object::ToString()
0x208e8  call     string [mscorlib]System.String::Format(string, object)
0x208ed  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x208f2  ldnull
0x208f3  stloc.1
0x208f4  ldarg.0
0x208f5  ldfld    class [mscorlib]System.Collections.Queue System.Deployment.Application.FileDownloader::_fileQueue
0x208fa  stloc.2
0x208fb  ldc.i4.0
0x208fc  stloc.3
0x208fd  ldloc.2
0x208fe  ldloca.s 3
0x20900  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x20905  ldarg.0
0x20906  ldfld    class [mscorlib]System.Collections.Queue System.Deployment.Application.FileDownloader::_fileQueue
0x2090b  callvirt instance int32 [mscorlib]System.Collections.Queue::get_Count()
0x20910  ldc.i4.0
0x20911  ble.s    loc_20924
0x20913  ldarg.0
0x20914  ldfld    class [mscorlib]System.Collections.Queue System.Deployment.Application.FileDownloader::_fileQueue
0x20919  callvirt instance object [mscorlib]System.Collections.Queue::Dequeue()
0x2091e  castclass DownloadQueueItem
0x20923  stloc.1
0x20924  leave.s  loc_20930
0x20926  ldloc.3
0x20927  brfalse.s loc_2092F
0x20929  ldloc.2
0x2092a  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2092f  endfinally
0x20930  ldloc.1
0x20931  brfalse.s loc_20942
0x20933  ldarg.0
0x20934  ldloc.1
0x20935  call     instance void System.Deployment.Application.SystemNetDownloader::DownloadSingleFile(class DownloadQueueItem next)
0x2093a  ldarg.0
0x2093b  ldfld    bool System.Deployment.Application.FileDownloader::_fCancelPending
0x20940  brfalse.s loc_208F2
0x20942  ldarg.0
0x20943  ldfld    bool System.Deployment.Application.FileDownloader::_fCancelPending
0x20948  brfalse.s loc_20950
0x2094a  newobj   instance void System.Deployment.Application.DownloadCancelledException::.ctor()
0x2094f  throw
0x20950  ret
```
