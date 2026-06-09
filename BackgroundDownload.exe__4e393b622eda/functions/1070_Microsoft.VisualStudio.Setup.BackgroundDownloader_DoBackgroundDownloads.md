# Microsoft.VisualStudio.Setup.BackgroundDownloader::DoBackgroundDownloads

- ea: `0x1070`
- end: `0x1275`
- name: `Microsoft.VisualStudio.Setup.BackgroundDownloader::DoBackgroundDownloads`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3c10`

## callees

- `0x1070`
- `0x1480`
- `0x18f0`
- `0x1900`
- `0x2950`
- `0x3780`

## string_xrefs

- `0x117d`: `Downloading updates for '{0} ({1})'`
- `0x11b3`: `Downloading updates finished for '{0}  {1}'`

## pseudocode

```c

```

## disassembly

```asm
0x1070  ldarg.0
0x1071  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x1076  ldstr    aPerformBackgro// "Perform background downloads"
0x107b  newobj   instance void Microsoft.VisualStudio.Setup.OperationLogger::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, string text)
0x1080  stloc.0
0x1081  ldarg.0
0x1082  ldfld    class Microsoft.VisualStudio.Setup.Services.IBackgroundDownloadInstanceProvider Microsoft.VisualStudio.Setup.BackgroundDownloader::instanceProvider
0x1087  ldarg.0
0x1088  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery Microsoft.VisualStudio.Setup.BackgroundDownloader::query
0x108d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> Microsoft.VisualStudio.Setup.Services.IBackgroundDownloadInstanceProvider::GetInstances(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery query)
0x1092  ldarg.0
0x1093  ldftn    instance bool Microsoft.VisualStudio.Setup.BackgroundDownloader::UserProfileCheck(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance instance)
0x1099  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance, bool>::.ctor(object, native int)
0x109e  call     T0x2B00000B
0x10a3  ldarga.s 1
0x10a5  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x10aa  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::GetEnumerator()
0x10af  stloc.1
0x10b0  br       loc_1252
0x10b5  ldloc.1
0x10b6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::get_Current()
0x10bb  stloc.2
0x10bc  ldarg.0
0x10bd  ldloc.2
0x10be  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.BackgroundDownloader::currentInstance
0x10c3  ldarga.s 1
0x10c5  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x10ca  ldnull
0x10cb  stloc.3
0x10cc  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x10d1  dup
0x10d2  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADINSTANCEINSTANCEID
0x10d7  ldloc.2
0x10d8  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstanceId()
0x10dd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x10e2  dup
0x10e3  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADINSTANCECHANNELID
0x10e8  ldloc.2
0x10e9  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstalledChannelId()
0x10ee  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x10f3  dup
0x10f4  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADINSTANCEPRODUCTID
0x10f9  ldloc.2
0x10fa  ldc.i4.0
0x10fb  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.CommonExtensions::GetProduct(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance, bool)
0x1100  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x1105  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x110a  dup
0x110b  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADINSTANCECURRENTVERSION
0x1110  ldloc.2
0x1111  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstallationVersion()
0x1116  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x111b  stloc.3
0x111c  leave.s  loc_1155
0x111e  pop
0x111f  ldarg.0
0x1120  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x1125  dup
0x1126  brtrue.s loc_112B
0x1128  pop
0x1129  br.s     loc_1150
0x112b  ldstr    aSkippingBackgr// "Skipping BackgroundDownload for the ins"...
0x1130  ldloc.2
0x1131  brtrue.s loc_1136
0x1133  ldnull
0x1134  br.s     loc_113C
0x1136  ldloc.2
0x1137  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstanceId()
0x113c  ldstr    aAsTheInstanceI// "' as the instance is corrupted."
0x1141  call     string [mscorlib]System.String::Concat(string, string, string)
0x1146  call     T0x2B00000A
0x114b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1150  leave    loc_1252
0x1155  ldarg.0
0x1156  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Telemetry()
0x115b  dup
0x115c  brtrue.s loc_1162
0x115e  pop
0x115f  ldnull
0x1160  br.s     loc_116F
0x1162  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADPERINSTANCEEVENT
0x1167  ldloc.3
0x1168  ldc.i4.0
0x1169  ldc.i4.0
0x116a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x116f  stloc.s  4
0x1171  ldarg.0
0x1172  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x1177  dup
0x1178  brtrue.s loc_117D
0x117a  pop
0x117b  br.s     loc_119D
0x117d  ldstr    aDownloadingUpd// "Downloading updates for '{0} ({1})'"
0x1182  ldloc.2
0x1183  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstallationName()
0x1188  ldloc.2
0x1189  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IPackageReference [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_Product()
0x118e  call     string [mscorlib]System.String::Format(string, object, object)
0x1193  call     T0x2B00000A
0x1198  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x119d  ldarg.0
0x119e  ldarg.1
0x119f  ldloc.2
0x11a0  ldloc.s  4
0x11a2  call     instance void Microsoft.VisualStudio.Setup.BackgroundDownloader::DownloadUpdatesForInstance(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance instance, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryInstanceOperation)
0x11a7  ldarg.0
0x11a8  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x11ad  dup
0x11ae  brtrue.s loc_11B3
0x11b0  pop
0x11b1  br.s     loc_11D3
0x11b3  ldstr    aDownloadingUpd_0// "Downloading updates finished for '{0}  "...
0x11b8  ldloc.2
0x11b9  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstallationName()
0x11be  ldloc.2
0x11bf  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IPackageReference [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_Product()
0x11c4  call     string [mscorlib]System.String::Format(string, object, object)
0x11c9  call     T0x2B00000A
0x11ce  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x11d3  leave.s  loc_1252
0x11d5  pop
0x11d6  ldarg.0
0x11d7  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x11dc  dup
0x11dd  brtrue.s loc_11E2
0x11df  pop
0x11e0  br.s     loc_11F1
0x11e2  ldstr    aDobackgrounddo// "DoBackgroundDownloads operation cancell"...
0x11e7  call     T0x2B00000A
0x11ec  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x11f1  ldloc.s  4
0x11f3  brfalse.s loc_1201
0x11f5  ldloc.s  4
0x11f7  ldstr    aCanceled// "Canceled"
0x11fc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordCancel(string)
0x1201  rethrow
0x1203  stloc.s  5
0x1205  ldstr    aBackgrounddown// "BackgroundDownload Instance Failed: "
0x120a  ldloc.s  5
0x120c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1211  call     string [mscorlib]System.String::Concat(string, string)
0x1216  stloc.s  6
0x1218  ldloc.s  4
0x121a  brfalse.s loc_122A
0x121c  ldloc.s  4
0x121e  ldloc.s  6
0x1220  ldloc.s  5
0x1222  ldloc.s  6
0x1224  ldc.i4.1
0x1225  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x122a  ldarg.0
0x122b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x1230  dup
0x1231  brtrue.s loc_1236
0x1233  pop
0x1234  br.s     loc_1244
0x1236  ldloc.s  5
0x1238  ldloc.s  6
0x123a  call     T0x2B00000A
0x123f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x1244  leave.s  loc_1252
0x1246  ldloc.s  4
0x1248  brfalse.s loc_1251
0x124a  ldloc.s  4
0x124c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1251  endfinally
0x1252  ldloc.1
0x1253  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1258  brtrue   loc_10B5
0x125d  leave.s  loc_1273
0x125f  ldloc.1
0x1260  brfalse.s loc_1268
0x1262  ldloc.1
0x1263  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1268  endfinally
0x1269  ldloc.0
0x126a  brfalse.s loc_1272
0x126c  ldloc.0
0x126d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1272  endfinally
0x1273  ldc.i4.0
0x1274  ret
```
