# Microsoft.BIServer.Management.WebHost.Program::Main

- ea: `0x80`
- end: `0x1a3`
- name: `Microsoft.BIServer.Management.WebHost.Program::Main`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x80`
- `0x3e0`

## string_xrefs

- `0x11e`: `Installation has expired.`

## pseudocode

```c

```

## disassembly

```asm
0x80  .entrypoint
0x85  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Args::PauseIfDebugSwitch()
0x8a  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x8f  stloc.0
0x90  ldstr    aRsmanagement// "RSManagement"
0x95  ldc.i4.4
0x96  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Create(string, valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger/Level)
0x9b  stloc.1
0x9c  newobj   instance void <>c__DisplayClass1_0::.ctor()
0xa1  stloc.2
0xa2  ldloc.0
0xa3  newobj   instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.SqlDumperAdapter::.ctor()
0xa8  call     void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Dumper::Create(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.IDumperAdapter)
0xad  ldloc.0
0xae  ldstr    aListenerurl// "listenerUrl"
0xb3  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrException(string)
0xb8  stloc.3
0xb9  ldloc.2
0xba  ldc.i4.0
0xbb  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0xc0  stfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass1_0::resetEvent
0xc5  ldloc.2
0xc6  ldftn    instance void <>c__DisplayClass1_0::<Main>b__0(object s, class [mscorlib]System.ConsoleCancelEventArgs e)
0xcc  newobj   instance void [mscorlib]System.ConsoleCancelEventHandler::.ctor(object, native int)
0xd1  call     void [mscorlib]System.Console::add_CancelKeyPress(class [mscorlib]System.ConsoleCancelEventHandler)
0xd6  newobj   instance void [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::.ctor()
0xdb  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0xe0  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_InstanceId()
0xe5  callvirt instance class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::Load(string)
0xea  stloc.s  4
0xec  ldstr    aSku0// "SKU: {0}"
0xf1  ldc.i4.1
0xf2  newarr   [mscorlib]System.Object
0xf7  dup
0xf8  ldc.i4.0
0xf9  ldloc.s  4
0xfb  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo::get_SkuType()
0x100  call     class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStrings [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.EnumExtensions::GetStrings(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0x105  ldfld    string [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStrings::FullName
0x10a  stelem.ref
0x10b  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x110  ldloc.s  4
0x112  callvirt instance class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuTimebomb [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo::get_Timebomb()
0x117  callvirt instance bool [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuTimebomb::HasExpired()
0x11c  brfalse.s loc_12F
0x11e  ldstr    aInstallationHa// "Installation has expired."
0x123  call     T0x2B000001
0x128  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x12d  leave.s  loc_1A2
0x12f  ldloc.3
0x130  ldsfld   class [mscorlib]System.Action`1<class [Owin]Owin.IAppBuilder> <>c::<>9__1_1
0x135  dup
0x136  brtrue.s loc_14F
0x138  pop
0x139  ldsfld   class <>c <>c::<>9
0x13e  ldftn    instance void <>c::<Main>b__1_1(class [Owin]Owin.IAppBuilder appBuilder)
0x144  newobj   instance void class [mscorlib]System.Action`1<class [Owin]Owin.IAppBuilder>::.ctor(object, native int)
0x149  dup
0x14a  stsfld   class [mscorlib]System.Action`1<class [Owin]Owin.IAppBuilder> <>c::<>9__1_1
0x14f  call     class [mscorlib]System.IDisposable [Microsoft.Owin.Hosting]Microsoft.Owin.Hosting.WebApp::Start(string, class [mscorlib]System.Action`1<class [Owin]Owin.IAppBuilder>)
0x154  stloc.s  5
0x156  ldstr    aTheWebServerNe// "The web server needs to run elevated"
0x15b  call     T0x2B000001
0x160  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x165  ldstr    aWebServerIsRun// "Web Server is running."
0x16a  call     T0x2B000001
0x16f  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x174  ldstr    aPressCToExit// "Press ^C to exit...\r\n\r\n"
0x179  call     void [mscorlib]System.Console::WriteLine(string)
0x17e  ldloc.2
0x17f  ldfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass1_0::resetEvent
0x184  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x189  pop
0x18a  leave.s  loc_1A2
0x18c  ldloc.s  5
0x18e  brfalse.s loc_197
0x190  ldloc.s  5
0x192  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x197  endfinally
0x198  ldloc.1
0x199  brfalse.s loc_1A1
0x19b  ldloc.1
0x19c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a1  endfinally
0x1a2  ret
```
