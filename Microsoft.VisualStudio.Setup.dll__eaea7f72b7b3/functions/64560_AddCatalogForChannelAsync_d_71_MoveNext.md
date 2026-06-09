# <AddCatalogForChannelAsync>d__71::MoveNext

- ea: `0x64560`
- end: `0x64a1d`
- name: `<AddCatalogForChannelAsync>d__71::MoveNext`
- size: `1213`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x48b0`
- `0x4a40`
- `0x4aa0`
- `0x4d60`
- `0x5000`
- `0x52c0`
- `0x55200`
- `0x64560`

## string_xrefs

- `0x64578`: `channelManifestPair`
- `0x6497d`: `Failed to download Catalog using channel URI: `
- `0x6498a`: ` and install channel URI: `

## pseudocode

```c

```

## disassembly

```asm
0x64560  ldarg.0
0x64561  ldfld    int32 <AddCatalogForChannelAsync>d__71::<>1__state
0x64566  stloc.0
0x64567  ldarg.0
0x64568  ldfld    class Microsoft.VisualStudio.Setup.ChannelManager <AddCatalogForChannelAsync>d__71::<>4__this
0x6456d  stloc.1
0x6456e  ldloc.0
0x6456f  ldc.i4.3
0x64570  ble.un.s loc_64588
0x64572  ldarg.0
0x64573  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
0x64578  ldstr    aChannelmanifes// "channelManifestPair"
0x6457d  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x64582  ldloc.1
0x64583  callvirt instance void Microsoft.VisualStudio.Setup.ChannelManagerBase::Initialize()
0x64588  nop
0x64589  ldloc.0
0x6458a  switch   loc_64666, loc_646E1, loc_647B4, loc_6482F
0x6459f  ldarg.0
0x645a0  ldnull
0x645a1  stfld    string <AddCatalogForChannelAsync>d__71::<channelCatalogTempPath>5__2
0x645a6  ldarg.0
0x645a7  ldnull
0x645a8  stfld    string <AddCatalogForChannelAsync>d__71::<installChannelCatalogTempPath>5__3
0x645ad  ldloc.1
0x645ae  ldarg.0
0x645af  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
0x645b4  ldloca.s 3
0x645b6  ldarg.0
0x645b7  ldflda   string <AddCatalogForChannelAsync>d__71::<installChannelCatalogPath>5__4
0x645bc  call     instance void Microsoft.VisualStudio.Setup.ChannelManager::GetCatalogPathsForChannel(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelManifestPair, [out] string& channelCatalogFileName, [out] string& installChannelCatalogFileName)
0x645c1  ldarg.0
0x645c2  ldarg.0
0x645c3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
0x645c8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x645cd  dup
0x645ce  brtrue.s loc_645D4
0x645d0  pop
0x645d1  ldnull
0x645d2  br.s     loc_645D9
0x645d4  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_InstallCatalogUri()
0x645d9  ldnull
0x645da  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x645df  stfld    bool <AddCatalogForChannelAsync>d__71::<installFromLayout>5__5
0x645e4  ldarg.0
0x645e5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
0x645ea  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x645ef  brfalse  loc_6470F
0x645f4  ldloc.1
0x645f5  ldarg.0
0x645f6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
0x645fb  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x64600  ldloc.3
0x64601  call     instance bool Microsoft.VisualStudio.Setup.ChannelManager::IsCatalogUpToDate(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, string channelCatalogPath)
0x64606  brtrue   loc_6470F
0x6460b  ldarg.0
0x6460c  ldfld    bool <AddCatalogForChannelAsync>d__71::<installFromLayout>5__5
0x64611  brfalse  loc_64696
0x64616  ldloc.1
0x64617  ldarg.0
0x64618  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
0x6461d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x64622  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_InstallCatalogUri()
0x64627  ldarg.0
0x64628  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <AddCatalogForChannelAsync>d__71::cancellationToken
0x6462d  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.ChannelManager::DownloadCatalogAsync(class [System]System.Uri catalogUri, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x64632  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x64637  stloc.s  5
0x64639  ldloca.s 5
0x6463b  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x64640  brtrue.s loc_64683
0x64642  ldarg.0
0x64643  ldc.i4.0
0x64644  dup
0x64645  stloc.0
0x64646  stfld    int32 <AddCatalogForChannelAsync>d__71::<>1__state
0x6464b  ldarg.0
0x6464c  ldloc.s  5
0x6464e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <AddCatalogForChannelAsync>d__71::<>u__1
0x64653  ldarg.0
0x64654  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <AddCatalogForChannelAsync>d__71::<>t__builder
0x64659  ldloca.s 5
0x6465b  ldarg.0
0x6465c  call     T0x2B0002B9
0x64661  leave    loc_64A1C
0x64666  ldarg.0
0x64667  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <AddCatalogForChannelAsync>d__71::<>u__1
0x6466c  stloc.s  5
0x6466e  ldarg.0
0x6466f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <AddCatalogForChannelAsync>d__71::<>u__1
0x64674  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x6467a  ldarg.0
0x6467b  ldc.i4.m1
0x6467c  dup
0x6467d  stloc.0
0x6467e  stfld    int32 <AddCatalogForChannelAsync>d__71::<>1__state
0x64683  ldloca.s 5
0x64685  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x6468a  stloc.s  4
0x6468c  ldarg.0
0x6468d  ldloc.s  4
0x6468f  stfld    string <AddCatalogForChannelAsync>d__71::<channelCatalogTempPath>5__2
0x64694  br.s     loc_6470F
0x64696  ldloc.1
0x64697  ldarg.0
0x64698  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
0x6469d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x646a2  ldarg.0
0x646a3  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <AddCatalogForChannelAsync>d__71::cancellationToken
0x646a8  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.ChannelManager::DownloadCatalogAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x646ad  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x646b2  stloc.s  5
0x646b4  ldloca.s 5
0x646b6  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x646bb  brtrue.s loc_646FE
0x646bd  ldarg.0
0x646be  ldc.i4.1
0x646bf  dup
0x646c0  stloc.0
0x646c1  stfld    int32 <AddCatalogForChannelAsync>d__71::<>1__state
0x646c6  ldarg.0
0x646c7  ldloc.s  5
0x646c9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <AddCatalogForChannelAsync>d__71::<>u__1
0x646ce  ldarg.0
0x646cf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <AddCatalogForChannelAsync>d__71::<>t__builder
0x646d4  ldloca.s 5
0x646d6  ldarg.0
0x646d7  call     T0x2B0002B9
0x646dc  leave    loc_64A1C
0x646e1  ldarg.0
0x646e2  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <AddCatalogForChannelAsync>d__71::<>u__1
0x646e7  stloc.s  5
0x646e9  ldarg.0
0x646ea  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <AddCatalogForChannelAsync>d__71::<>u__1
0x646ef  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x646f5  ldarg.0
0x646f6  ldc.i4.m1
0x646f7  dup
0x646f8  stloc.0
0x646f9  stfld    int32 <AddCatalogForChannelAsync>d__71::<>1__state
0x646fe  ldloca.s 5
0x64700  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x64705  stloc.s  4
0x64707  ldarg.0
0x64708  ldloc.s  4
0x6470a  stfld    string <AddCatalogForChannelAsync>d__71::<channelCatalogTempPath>5__2
0x6470f  ldarg.0
0x64710  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
0x64715  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x6471a  brfalse  loc_6485D
0x6471f  ldloc.1
0x64720  ldarg.0
0x64721  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
0x64726  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x6472b  ldarg.0
0x6472c  ldfld    string <AddCatalogForChannelAsync>d__71::<installChannelCatalogPath>5__4
0x64731  call     instance bool Microsoft.VisualStudio.Setup.ChannelManager::IsCatalogUpToDate(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, string channelCatalogPath)
0x64736  brtrue   loc_6485D
0x6473b  ldarg.0
0x6473c  ldfld    bool <AddCatalogForChannelAsync>d__71::<installFromLayout>5__5
0x64741  brfalse  loc_647E4
0x64746  ldarg.0
0x64747  ldfld    string <AddCatalogForChannelAsync>d__71::<channelCatalogTempPath>5__2
0x6474c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x64751  brtrue.s loc_64764
0x64753  ldarg.0
0x64754  ldarg.0
0x64755  ldfld    string <AddCatalogForChannelAsync>d__71::<channelCatalogTempPath>5__2
0x6475a  stfld    string <AddCatalogForChannelAsync>d__71::<installChannelCatalogTempPath>5__3
0x6475f  br       loc_6485D
0x64764  ldloc.1
0x64765  ldarg.0
0x64766  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
0x6476b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x64770  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_InstallCatalogUri()
0x64775  ldarg.0
0x64776  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <AddCatalogForChannelAsync>d__71::cancellationToken
0x6477b  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.ChannelManager::DownloadCatalogAsync(class [System]System.Uri catalogUri, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x64780  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x64785  stloc.s  5
0x64787  ldloca.s 5
0x64789  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x6478e  brtrue.s loc_647D1
0x64790  ldarg.0
0x64791  ldc.i4.2
0x64792  dup
0x64793  stloc.0
0x64794  stfld    int32 <AddCatalogForChannelAsync>d__71::<>1__state
0x64799  ldarg.0
0x6479a  ldloc.s  5
0x6479c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <AddCatalogForChannelAsync>d__71::<>u__1
0x647a1  ldarg.0
0x647a2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <AddCatalogForChannelAsync>d__71::<>t__builder
0x647a7  ldloca.s 5
0x647a9  ldarg.0
0x647aa  call     T0x2B0002B9
0x647af  leave    loc_64A1C
0x647b4  ldarg.0
0x647b5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <AddCatalogForChannelAsync>d__71::<>u__1
0x647ba  stloc.s  5
0x647bc  ldarg.0
0x647bd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <AddCatalogForChannelAsync>d__71::<>u__1
0x647c2  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x647c8  ldarg.0
0x647c9  ldc.i4.m1
0x647ca  dup
0x647cb  stloc.0
0x647cc  stfld    int32 <AddCatalogForChannelAsync>d__71::<>1__state
0x647d1  ldloca.s 5
0x647d3  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x647d8  stloc.s  4
0x647da  ldarg.0
0x647db  ldloc.s  4
0x647dd  stfld    string <AddCatalogForChannelAsync>d__71::<installChannelCatalogTempPath>5__3
0x647e2  br.s     loc_6485D
0x647e4  ldloc.1
0x647e5  ldarg.0
0x647e6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
0x647eb  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x647f0  ldarg.0
0x647f1  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <AddCatalogForChannelAsync>d__71::cancellationToken
0x647f6  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.ChannelManager::DownloadCatalogAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x647fb  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x64800  stloc.s  5
0x64802  ldloca.s 5
0x64804  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x64809  brtrue.s loc_6484C
0x6480b  ldarg.0
0x6480c  ldc.i4.3
0x6480d  dup
0x6480e  stloc.0
0x6480f  stfld    int32 <AddCatalogForChannelAsync>d__71::<>1__state
0x64814  ldarg.0
0x64815  ldloc.s  5
0x64817  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <AddCatalogForChannelAsync>d__71::<>u__1
0x6481c  ldarg.0
0x6481d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <AddCatalogForChannelAsync>d__71::<>t__builder
0x64822  ldloca.s 5
0x64824  ldarg.0
0x64825  call     T0x2B0002B9
0x6482a  leave    loc_64A1C
0x6482f  ldarg.0
0x64830  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <AddCatalogForChannelAsync>d__71::<>u__1
0x64835  stloc.s  5
0x64837  ldarg.0
0x64838  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <AddCatalogForChannelAsync>d__71::<>u__1
0x6483d  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x64843  ldarg.0
0x64844  ldc.i4.m1
0x64845  dup
0x64846  stloc.0
0x64847  stfld    int32 <AddCatalogForChannelAsync>d__71::<>1__state
0x6484c  ldloca.s 5
0x6484e  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x64853  stloc.s  4
0x64855  ldarg.0
0x64856  ldloc.s  4
0x64858  stfld    string <AddCatalogForChannelAsync>d__71::<installChannelCatalogTempPath>5__3
0x6485d  ldloc.1
0x6485e  ldfld    class Microsoft.VisualStudio.Setup.Cache.IChannelRepository Microsoft.VisualStudio.Setup.ChannelManager::channelRepository
0x64863  ldarg.0
0x64864  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
0x64869  ldarg.0
0x6486a  ldfld    string <AddCatalogForChannelAsync>d__71::<channelCatalogTempPath>5__2
0x6486f  ldarg.0
0x64870  ldfld    string <AddCatalogForChannelAsync>d__71::<installChannelCatalogTempPath>5__3
0x64875  callvirt instance void Microsoft.VisualStudio.Setup.Cache.IChannelRepository::AddCatalogForChannel(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelManifestPair, string channelProductManifest, string installChannelProductManifest)
0x6487a  ldloc.1
0x6487b  ldarg.0
0x6487c  ldfld    string <AddCatalogForChannelAsync>d__71::<channelCatalogTempPath>5__2
0x64881  call     instance void Microsoft.VisualStudio.Setup.ChannelManager::DeleteTemporaryFiles(string path)
0x64886  ldloc.1
0x64887  ldarg.0
0x64888  ldfld    string <AddCatalogForChannelAsync>d__71::<installChannelCatalogTempPath>5__3
0x6488d  call     instance void Microsoft.VisualStudio.Setup.ChannelManager::DeleteTemporaryFiles(string path)
0x64892  ldc.i4.1
0x64893  stloc.2
0x64894  leave    loc_64A08
0x64899  pop
0x6489a  rethrow
0x6489c  stloc.s  6
0x6489e  ldloc.1
0x6489f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x648a4  dup
0x648a5  brtrue.s loc_648AA
0x648a7  pop
0x648a8  br.s     loc_648C7
0x648aa  ldloc.s  6
0x648ac  ldstr    aFailedToDownlo_1// "Failed to download the catalog: "
0x648b1  ldloc.s  6
0x648b3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x648b8  call     string [mscorlib]System.String::Concat(string, string)
0x648bd  call     T0x2B000003
0x648c2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x648c7  ldnull
0x648c8  stloc.s  7
0x648ca  ldnull
0x648cb  stloc.s  8
0x648cd  ldarg.0
0x648ce  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair <AddCatalogForChannelAsync>d__71::channelManifestPair
  ... truncated ...
```
