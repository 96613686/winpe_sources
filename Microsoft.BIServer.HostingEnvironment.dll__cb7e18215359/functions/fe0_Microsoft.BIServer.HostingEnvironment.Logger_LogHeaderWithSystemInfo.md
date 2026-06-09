# Microsoft.BIServer.HostingEnvironment.Logger::LogHeaderWithSystemInfo

- ea: `0xfe0`
- end: `0x1138`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::LogHeaderWithSystemInfo`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x55b0`

## callees

- `0xfe0`
- `0x1550`
- `0x1590`
- `0x1aa0`
- `0x1ad0`
- `0x1af0`
- `0x1b10`
- `0x1b40`
- `0x1b90`

## string_xrefs

- `0x103f`: `<Header>\n  <Product>{0}</Product>\n  <Locale>{1}</Locale>\n  <TimeZone>{2}</TimeZone>\n  <Path>{3}</Path>\n  <SystemName>{4}</SystemName>\n  <OSName>{5}</OSName>\n  <OSVersion>{6}</OSVersion>\n  <ProcessID>{7}</ProcessID>\n  <Virtualization>{8}</Virtualization>\n</Header>\n<ProcessorArchitecture>{9}</ProcessorArchitecture>\n<ApplicationArchitecture>{10}</ApplicationArchitecture>`

## pseudocode

```c

```

## disassembly

```asm
0xfe0  ldsfld   class [mscorlib]System.Func`2<int32, string> <>c::<>9__47_0
0xfe5  dup
0xfe6  brtrue.s loc_FFF
0xfe8  pop
0xfe9  ldsfld   class <>c <>c::<>9
0xfee  ldftn    instance string <>c::<LogHeaderWithSystemInfo>b__47_0(int32 deltaHours)
0xff4  newobj   instance void class [mscorlib]System.Func`2<int32, string>::.ctor(object, native int)
0xff9  dup
0xffa  stsfld   class [mscorlib]System.Func`2<int32, string> <>c::<>9__47_0
0xfff  stloc.0
0x1000  volatile.
0x1002  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) string Microsoft.BIServer.HostingEnvironment.Logger::LogHeader
0x1007  brtrue   loc_1106
0x100c  ldsfld   object Microsoft.BIServer.HostingEnvironment.Logger::LogHeaderLock
0x1011  stloc.1
0x1012  ldc.i4.0
0x1013  stloc.2
0x1014  ldloc.1
0x1015  ldloca.s 2
0x1017  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x101c  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x1021  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x1026  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0x102b  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0x1030  stloc.3
0x1031  ldstr    aMicrosoftPower// "Microsoft Power BI Report Server"
0x1036  stloc.s  4
0x1038  newobj   instance void Microsoft.BIServer.HostingEnvironment.OsInfoProvider::.ctor()
0x103d  stloc.s  5
0x103f  ldstr    aHeaderProduct0// "<Header>\r\n  <Product>{0}</Product>\r"...
0x1044  ldc.i4.s 0xB
0x1046  newarr   [mscorlib]System.Object
0x104b  dup
0x104c  ldc.i4.0
0x104d  ldstr    a012// "{0} {1} ({2})"
0x1052  ldloc.s  4
0x1054  ldloc.s  5
0x1056  ldloc.s  4
0x1058  callvirt instance string Microsoft.BIServer.HostingEnvironment.OsInfoProvider::GetAppProductVersion(string productName)
0x105d  ldloc.3
0x105e  call     string [mscorlib]System.String::Format(string, object, object, object)
0x1063  stelem.ref
0x1064  dup
0x1065  ldc.i4.1
0x1066  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x106b  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_NativeName()
0x1070  dup
0x1071  brtrue.s loc_1079
0x1073  pop
0x1074  ldstr    asc_7C08// ""
0x1079  stelem.ref
0x107a  dup
0x107b  ldc.i4.2
0x107c  ldloc.0
0x107d  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::get_Now()
0x1082  stloc.s  6
0x1084  ldloca.s 6
0x1086  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTimeOffset::get_Offset()
0x108b  stloc.s  7
0x108d  ldloca.s 7
0x108f  call     instance int32 [mscorlib]System.TimeSpan::get_Hours()
0x1094  callvirt instance var<u1> class [mscorlib]System.Func`2<int32, string>::Invoke(void)
0x1099  stelem.ref
0x109a  dup
0x109b  ldc.i4.3
0x109c  ldarg.0
0x109d  stelem.ref
0x109e  dup
0x109f  ldc.i4.4
0x10a0  call     string [mscorlib]System.Environment::get_MachineName()
0x10a5  stelem.ref
0x10a6  dup
0x10a7  ldc.i4.5
0x10a8  ldloc.s  5
0x10aa  callvirt instance string Microsoft.BIServer.HostingEnvironment.OsInfoProvider::GetOsName()
0x10af  stelem.ref
0x10b0  dup
0x10b1  ldc.i4.6
0x10b2  ldloc.s  5
0x10b4  callvirt instance string Microsoft.BIServer.HostingEnvironment.OsInfoProvider::GetOsVersion()
0x10b9  stelem.ref
0x10ba  dup
0x10bb  ldc.i4.7
0x10bc  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x10c1  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x10c6  stloc.s  8
0x10c8  ldloca.s 8
0x10ca  call     instance string [mscorlib]System.Int32::ToString()
0x10cf  stelem.ref
0x10d0  dup
0x10d1  ldc.i4.8
0x10d2  ldloc.s  5
0x10d4  callvirt instance string Microsoft.BIServer.HostingEnvironment.OsInfoProvider::GetVirtualizationEnabled()
0x10d9  stelem.ref
0x10da  dup
0x10db  ldc.i4.s 9
0x10dd  ldloc.s  5
0x10df  callvirt instance string Microsoft.BIServer.HostingEnvironment.OsInfoProvider::GetCpuArchitecture()
0x10e4  stelem.ref
0x10e5  dup
0x10e6  ldc.i4.s 0xA
0x10e8  ldstr    aAmd64// "AMD64"
0x10ed  stelem.ref
0x10ee  call     string [mscorlib]System.String::Format(string, object[])
0x10f3  volatile.
0x10f5  stsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) string Microsoft.BIServer.HostingEnvironment.Logger::LogHeader
0x10fa  leave.s  loc_1106
0x10fc  ldloc.2
0x10fd  brfalse.s loc_1105
0x10ff  ldloc.1
0x1100  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1105  endfinally
0x1106  volatile.
0x1108  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) string Microsoft.BIServer.HostingEnvironment.Logger::LogHeader
0x110d  call     T0x2B00000A
0x1112  call     void Microsoft.BIServer.HostingEnvironment.Logger::Info(string formatString, object[] formatParams)
0x1117  leave.s  loc_1137
0x1119  stloc.s  9
0x111b  ldstr    aErrorLoggingHe// "Error logging header with system/hardwa"...
0x1120  ldc.i4.1
0x1121  newarr   [mscorlib]System.Object
0x1126  dup
0x1127  ldc.i4.0
0x1128  ldloc.s  9
0x112a  callvirt instance string [mscorlib]System.Object::ToString()
0x112f  stelem.ref
0x1130  call     void Microsoft.BIServer.HostingEnvironment.Logger::Warning(string formatString, object[] formatParams)
0x1135  leave.s  loc_1137
0x1137  ret
```
