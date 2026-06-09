# Microsoft.VisualStudio.Setup.BackgroundDownloader::DownloadUpdatesForInstance

- ea: `0x1480`
- end: `0x166a`
- name: `Microsoft.VisualStudio.Setup.BackgroundDownloader::DownloadUpdatesForInstance`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1070`

## callees

- `0x1480`
- `0x1670`
- `0x1890`
- `0x18a0`
- `0x18b0`
- `0x18d0`
- `0x1900`
- `0x3ad0`

## pseudocode

```c

```

## disassembly

```asm
0x1480  newobj   instance void <>c__DisplayClass23_0::.ctor()
0x1485  stloc.0
0x1486  ldloc.0
0x1487  ldarg.2
0x1488  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance <>c__DisplayClass23_0::instance
0x148d  ldarga.s 1
0x148f  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x1494  ldarg.0
0x1495  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.BackgroundDownloader::currentInstance
0x149a  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_UserProperties()
0x149f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>> class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string>::get_Keys()
0x14a4  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::UpdateDownloadedSize
0x14a9  call     T0x2B00000D
0x14ae  brfalse.s loc_14D1
0x14b0  ldarg.0
0x14b1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.BackgroundDownloader::currentInstance
0x14b6  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_UserProperties()
0x14bb  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::UpdateDownloadedSize
0x14c0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string>::get_Item(void)
0x14c5  ldarg.0
0x14c6  ldflda   int64 Microsoft.VisualStudio.Setup.BackgroundDownloader::previouslyDownloadedSize
0x14cb  call     bool [mscorlib]System.Int64::TryParse(string, int64&)
0x14d0  pop
0x14d1  ldarg.0
0x14d2  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0x14d7  ldloc.0
0x14d8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance <>c__DisplayClass23_0::instance
0x14dd  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstanceId()
0x14e2  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Engine::.ctor(class [mscorlib]System.IServiceProvider, string)
0x14e7  stloc.1
0x14e8  ldloc.1
0x14e9  ldstr    a0100SetupLog// "{0}_{1:00}_setup.log"
0x14ee  ldarg.0
0x14ef  call     instance string Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_LogFilePrefix()
0x14f4  ldarg.0
0x14f5  call     instance int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Sequence()
0x14fa  box      [mscorlib]System.Int32
0x14ff  call     string [mscorlib]System.String::Format(string, object, object)
0x1504  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Engine::set_LogFilePath(string)
0x1509  ldloc.1
0x150a  ldstr    a0100SetupError// "{0}_{1:00}_setup_errors.log"
0x150f  ldarg.0
0x1510  call     instance string Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_LogFilePrefix()
0x1515  ldarg.0
0x1516  call     instance int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Sequence()
0x151b  box      [mscorlib]System.Int32
0x1520  call     string [mscorlib]System.String::Format(string, object, object)
0x1525  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Engine::set_ErrorLogFilePath(string)
0x152a  ldarg.0
0x152b  call     instance int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Sequence()
0x1530  stloc.s  5
0x1532  ldarg.0
0x1533  ldloc.s  5
0x1535  ldc.i4.1
0x1536  add
0x1537  call     instance void Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::set_Sequence(int32 value)
0x153c  ldc.i4.2
0x153d  stloc.2
0x153e  ldloc.1
0x153f  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.VariableCollection [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Engine::get_Properties()
0x1544  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::OperationMode
0x1549  ldloc.2
0x154a  stloc.s  5
0x154c  ldloca.s 5
0x154e  call     instance string [mscorlib]System.Int32::ToString()
0x1553  ldc.i4.1
0x1554  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.VariableCollection::Add(string, string, bool)
0x1559  ldloc.1
0x155a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Engine::GetProducts()
0x155f  ldloc.0
0x1560  ldftn    instance bool <>c__DisplayClass23_0::<DownloadUpdatesForInstance>b__0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product x)
0x1566  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product, bool>::.ctor(object, native int)
0x156b  call     T0x2B00000E
0x1570  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product> <>c::<>9__23_1
0x1575  dup
0x1576  brtrue.s loc_158F
0x1578  pop
0x1579  ldsfld   class <>c <>c::<>9
0x157e  ldftn    instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c::<DownloadUpdatesForInstance>b__23_1(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product l, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product r)
0x1584  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product>::.ctor(object, native int)
0x1589  dup
0x158a  stsfld   class [mscorlib]System.Func`3<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product> <>c::<>9__23_1
0x158f  call     T0x2B00000F
0x1594  stloc.3
0x1595  ldloc.3
0x1596  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product::get_SupportsDownloadThenUpdate()
0x159b  brtrue.s loc_15D1
0x159d  ldarg.0
0x159e  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x15a3  dup
0x15a4  brtrue.s loc_15AC
0x15a6  pop
0x15a7  leave    loc_1669
0x15ac  ldstr    aProductDoesNot// "Product does not support Background Dow"...
0x15b1  ldloc.3
0x15b2  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x15b7  ldloc.3
0x15b8  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Version()
0x15bd  call     string [mscorlib]System.String::Format(string, object, object)
0x15c2  call     T0x2B00000A
0x15c7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x15cc  leave    loc_1669
0x15d1  ldarg.0
0x15d2  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager Microsoft.VisualStudio.Setup.BackgroundDownloader::channelManager
0x15d7  ldloc.0
0x15d8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance <>c__DisplayClass23_0::instance
0x15dd  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::GetChannelProductForInstance(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance)
0x15e2  stloc.s  4
0x15e4  ldarg.3
0x15e5  brfalse.s loc_1623
0x15e7  ldarg.3
0x15e8  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x15ed  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADINSTANCEPREVIOUSDLSIZE
0x15f2  ldarg.0
0x15f3  ldflda   int64 Microsoft.VisualStudio.Setup.BackgroundDownloader::previouslyDownloadedSize
0x15f8  call     instance string [mscorlib]System.Int64::ToString()
0x15fd  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1602  ldarg.3
0x1603  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x1608  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADINSTANCEUPDATEVERSION
0x160d  ldloc.s  4
0x160f  callvirt instance var<u1> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem>::get_Item()
0x1614  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x1619  callvirt instance string [mscorlib]System.Object::ToString()
0x161e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1623  nop
0x1624  ldloc.1
0x1625  ldloc.s  4
0x1627  ldarg.1
0x1628  ldc.i4.0
0x1629  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Engine::Load(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem>, valuetype [mscorlib]System.Threading.CancellationToken, bool)
0x162e  ldloc.1
0x162f  ldloc.3
0x1630  ldloc.0
0x1631  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance <>c__DisplayClass23_0::instance
0x1636  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstallationPath()
0x163b  ldarg.1
0x163c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Engine::Install(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product, string, valuetype [mscorlib]System.Threading.CancellationToken)
0x1641  pop
0x1642  leave.s  loc_1669
0x1644  ldarg.0
0x1645  ldarg.3
0x1646  ldloc.1
0x1647  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Engine::get_Instance()
0x164c  dup
0x164d  brtrue.s loc_1653
0x164f  pop
0x1650  ldnull
0x1651  br.s     loc_1658
0x1653  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_UserProperties()
0x1658  call     instance bool Microsoft.VisualStudio.Setup.BackgroundDownloader::SetInstanceTelemetryProperties(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> userProps)
0x165d  pop
0x165e  endfinally
0x165f  ldloc.1
0x1660  brfalse.s loc_1668
0x1662  ldloc.1
0x1663  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1668  endfinally
0x1669  ret
```
