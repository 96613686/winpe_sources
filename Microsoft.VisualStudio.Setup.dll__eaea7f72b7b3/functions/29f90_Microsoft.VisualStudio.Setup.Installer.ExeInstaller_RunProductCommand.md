# Microsoft.VisualStudio.Setup.Installer.ExeInstaller::RunProductCommand

- ea: `0x29f90`
- end: `0x2a465`
- name: `Microsoft.VisualStudio.Setup.Installer.ExeInstaller::RunProductCommand`
- size: `1237`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x29e40`
- `0x29ea0`
- `0x29f00`
- `0x29f40`

## callees

- `0x19350`
- `0x29f90`
- `0x2a9e0`
- `0x2b920`
- `0x2b940`
- `0x2b9a0`
- `0x2be00`
- `0x2c3f0`
- `0x2d1b0`
- `0x2d380`
- `0x6c550`

## string_xrefs

- `0x2a2e4`: `Failure reading exe package error telemetry file: {0}.`
- `0x2a348`: `User canceled during package `

## pseudocode

```c

```

## disassembly

```asm
0x29f90  newobj   instance void <>c__DisplayClass18_0::.ctor()
0x29f95  stloc.0
0x29f96  ldloc.0
0x29f97  ldarg.0
0x29f98  stfld    class Microsoft.VisualStudio.Setup.Installer.ExeInstaller <>c__DisplayClass18_0::<>4__this
0x29f9d  ldloc.0
0x29f9e  ldarg.2
0x29f9f  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter <>c__DisplayClass18_0::parameter
0x29fa4  ldloc.0
0x29fa5  ldarg.1
0x29fa6  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x29fab  ldloc.0
0x29fac  ldarg.s  5
0x29fae  stfld    string <>c__DisplayClass18_0::logOperation
0x29fb3  ldloc.0
0x29fb4  ldarg.s  9
0x29fb6  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> <>c__DisplayClass18_0::additionalProperties
0x29fbb  ldloc.0
0x29fbc  ldarg.s  0xA
0x29fbe  stfld    bool <>c__DisplayClass18_0::waitForExit
0x29fc3  ldloc.0
0x29fc4  ldarg.s  7
0x29fc6  stfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction <>c__DisplayClass18_0::action
0x29fcb  ldarg.0
0x29fcc  call     instance void Microsoft.VisualStudio.Setup.Installer.InstallerBase::Initialize()
0x29fd1  ldarg.s  8
0x29fd3  ldnull
0x29fd4  stind.ref
0x29fd5  ldloc.0
0x29fd6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x29fdb  brtrue.s loc_29FE8
0x29fdd  ldstr    aProduct// "product"
0x29fe2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x29fe7  throw
0x29fe8  ldnull
0x29fe9  stloc.1
0x29fea  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x29fef  dup
0x29ff0  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ENGINEOPERATIONTYPE
0x29ff5  ldarg.3
0x29ff6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x29ffb  dup
0x29ffc  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEIDPROPERTY
0x2a001  ldloc.0
0x2a002  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a007  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x2a00c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a011  dup
0x2a012  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEUNIQUEIDPROPERTY
0x2a017  ldloc.0
0x2a018  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a01d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2a022  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a027  dup
0x2a028  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGELANGUAGEPROPERTY
0x2a02d  ldloc.0
0x2a02e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a033  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Language()
0x2a038  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a03d  dup
0x2a03e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGESTATEPROPERTY
0x2a043  ldloc.0
0x2a044  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a049  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_CurrentState()
0x2a04e  stloc.3
0x2a04f  ldloca.s 3
0x2a051  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState
0x2a057  callvirt instance string [mscorlib]System.Object::ToString()
0x2a05c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a061  dup
0x2a062  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEREQUESTEDSTATEPROPERTY
0x2a067  ldloc.0
0x2a068  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a06d  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_RequestedState()
0x2a072  stloc.s  4
0x2a074  ldloca.s 4
0x2a076  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState
0x2a07c  callvirt instance string [mscorlib]System.Object::ToString()
0x2a081  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a086  dup
0x2a087  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGECHIPPROPERTY
0x2a08c  ldloc.0
0x2a08d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a092  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Chip()
0x2a097  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a09c  dup
0x2a09d  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEPRODUCTARCHPROPERTY
0x2a0a2  ldloc.0
0x2a0a3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a0a8  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_ProductArch()
0x2a0ad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a0b2  dup
0x2a0b3  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEMACHINEARCHPROPERTY
0x2a0b8  ldloc.0
0x2a0b9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a0be  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_MachineArch()
0x2a0c3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a0c8  dup
0x2a0c9  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEVERSIONPROPERTY
0x2a0ce  ldloc.0
0x2a0cf  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a0d4  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Version()
0x2a0d9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a0de  dup
0x2a0df  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGETYPEPROPERTY
0x2a0e4  ldloc.0
0x2a0e5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a0ea  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Type()
0x2a0ef  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType
0x2a0f4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a0f9  dup
0x2a0fa  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PARENTSPROPERTY
0x2a0ff  ldloc.0
0x2a100  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a105  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_TelemetryCorrelatedParents()
0x2a10a  ldstr    asc_82420// ";"
0x2a10f  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::TryJoin(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, string)
0x2a114  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a119  dup
0x2a11a  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ANCESTORWORKLOADSPROPERTY
0x2a11f  ldloc.0
0x2a120  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a125  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_AncestorWorkloads()
0x2a12a  ldstr    asc_82420// ";"
0x2a12f  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::TryJoin(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, string)
0x2a134  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a139  stloc.2
0x2a13a  ldarg.0
0x2a13b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_TelemetryService()
0x2a140  dup
0x2a141  brtrue.s loc_2A147
0x2a143  pop
0x2a144  ldnull
0x2a145  br.s     loc_2A154
0x2a147  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEOPERATIONEVENT
0x2a14c  ldloc.2
0x2a14d  ldc.i4.0
0x2a14e  ldc.i4.0
0x2a14f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x2a154  stloc.s  5
0x2a156  ldloc.0
0x2a157  ldnull
0x2a158  stfld    string <>c__DisplayClass18_0::command
0x2a15d  ldarg.s  8
0x2a15f  ldarg.0
0x2a160  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2a165  ldloc.0
0x2a166  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a16b  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x2a170  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::GenerateLogFileName(string)
0x2a175  stind.ref
0x2a176  ldarg.0
0x2a177  ldloc.0
0x2a178  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a17d  ldnull
0x2a17e  ldc.i4.3
0x2a17f  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetDisplayName(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, class [mscorlib]System.Globalization.CultureInfo, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResourceFallback)
0x2a184  ldc.r8   0.0
0x2a18d  ldnull
0x2a18e  newobj   instance void Microsoft.VisualStudio.Setup.ProgressDataEventArgs::.ctor(string packageInfo, float64 progress, [opt] string stepInfo)
0x2a193  callvirt instance void Microsoft.VisualStudio.Setup.Installer.InstallerBase::OnProgressReceived(class Microsoft.VisualStudio.Setup.ProgressDataEventArgs e)
0x2a198  ldloc.0
0x2a199  ldarg.s  8
0x2a19b  ldind.ref
0x2a19c  stfld    string <>c__DisplayClass18_0::logFileName
0x2a1a1  ldarg.0
0x2a1a2  ldnull
0x2a1a3  ldloc.0
0x2a1a4  ldftn    instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult <>c__DisplayClass18_0::<RunProductCommand>b__0()
0x2a1aa  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::.ctor(object, native int)
0x2a1af  ldarg.0
0x2a1b0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> Microsoft.VisualStudio.Setup.Installer.ExeInstaller::retryCodes
0x2a1b5  ldloc.0
0x2a1b6  ldfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction <>c__DisplayClass18_0::action
0x2a1bb  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.InstallerBase::ExecutePackageWithMessageBusRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage package, class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult> action, class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry> retryCodes, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction bootstrapperAction)
0x2a1c0  stloc.1
0x2a1c1  ldarg.0
0x2a1c2  ldloc.0
0x2a1c3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product <>c__DisplayClass18_0::product
0x2a1c8  ldnull
0x2a1c9  ldc.i4.3
0x2a1ca  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetDisplayName(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, class [mscorlib]System.Globalization.CultureInfo, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResourceFallback)
0x2a1cf  ldc.r8   1.0
0x2a1d8  ldnull
0x2a1d9  newobj   instance void Microsoft.VisualStudio.Setup.ProgressDataEventArgs::.ctor(string packageInfo, float64 progress, [opt] string stepInfo)
0x2a1de  callvirt instance void Microsoft.VisualStudio.Setup.Installer.InstallerBase::OnProgressReceived(class Microsoft.VisualStudio.Setup.ProgressDataEventArgs e)
0x2a1e3  ldloc.1
0x2a1e4  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::INSTALLRESULTPROPERTY
0x2a1e9  ldloc.s  5
0x2a1eb  brtrue.s loc_2A1F0
0x2a1ed  ldnull
0x2a1ee  br.s     loc_2A1F7
0x2a1f0  ldloc.s  5
0x2a1f2  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x2a1f7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::AddTelemetryProperties(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>)
0x2a1fc  ldloc.0
0x2a1fd  ldfld    string <>c__DisplayClass18_0::logFileName
0x2a202  ldstr    aErr// ".err"
0x2a207  call     string [mscorlib]System.IO.Path::ChangeExtension(string, string)
0x2a20c  stloc.s  6
0x2a20e  ldarg.0
0x2a20f  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x2a214  ldc.i4.1
0x2a215  call     T0x2B00000C
0x2a21a  stloc.s  7
0x2a21c  ldloc.s  7
0x2a21e  ldloc.s  6
0x2a220  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x2a225  brfalse  loc_2A2E0
0x2a22a  ldloc.s  5
0x2a22c  brtrue.s loc_2A231
0x2a22e  ldnull
0x2a22f  br.s     loc_2A238
0x2a231  ldloc.s  5
0x2a233  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x2a238  brfalse  loc_2A2E0
0x2a23d  ldloc.s  7
0x2a23f  ldloc.s  6
0x2a241  callvirt instance class [mscorlib]System.IO.TextReader [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenText(string)
0x2a246  stloc.s  8
0x2a248  ldloc.s  8
0x2a24a  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x2a24f  call     T0x2B000165
0x2a254  stloc.s  9
0x2a256  ldloc.s  9
0x2a258  brfalse.s loc_2A2D2
0x2a25a  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::INSTALLPROPERTYPREFIX
0x2a25f  ldloc.0
0x2a260  ldfld    string <>c__DisplayClass18_0::logOperation
0x2a265  callvirt instance string [mscorlib]System.String::Trim()
0x2a26a  ldc.i4.s 0x20
0x2a26c  ldc.i4.s 0x2E
0x2a26e  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x2a273  ldstr    aErr// ".err"
0x2a278  call     string [mscorlib]System.String::Concat(string, string, string)
0x2a27d  stloc.s  0xA
0x2a27f  ldloc.s  9
0x2a281  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x2a286  stloc.s  0xB
0x2a288  br.s     loc_2A2B9
0x2a28a  ldloca.s 0xB
0x2a28c  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x2a291  stloc.s  0xC
0x2a293  ldloc.s  5
0x2a295  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x2a29a  ldloc.s  0xA
0x2a29c  ldstr    asc_80DBA// "."
0x2a2a1  ldloca.s 0xC
0x2a2a3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x2a2a8  call     string [mscorlib]System.String::Concat(string, string, string)
0x2a2ad  ldloca.s 0xC
0x2a2af  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x2a2b4  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a2b9  ldloca.s 0xB
0x2a2bb  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x2a2c0  brtrue.s loc_2A28A
0x2a2c2  leave.s  loc_2A2D2
0x2a2c4  ldloca.s 0xB
0x2a2c6  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x2a2cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a2d1  endfinally
0x2a2d2  leave.s  loc_2A2E0
0x2a2d4  ldloc.s  8
0x2a2d6  brfalse.s loc_2A2DF
0x2a2d8  ldloc.s  8
0x2a2da  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a2df  endfinally
0x2a2e0  leave.s  loc_2A306
0x2a2e2  stloc.s  0xD
0x2a2e4  ldstr    aFailureReading// "Failure reading exe package error telem"...
0x2a2e9  ldloc.s  0xD
0x2a2eb  call     string [mscorlib]System.String::Format(string, object)
0x2a2f0  stloc.s  0xE
0x2a2f2  ldarg.0
0x2a2f3  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2a2f8  ldloc.s  0xE
0x2a2fa  call     T0x2B000003
0x2a2ff  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x2a304  leave.s  loc_2A306
0x2a306  ldloc.1
0x2a307  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsSuccess(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult)
0x2a30c  brfalse.s loc_2A321
0x2a30e  ldloc.s  5
0x2a310  brfalse.s loc_2A342
0x2a312  ldloc.s  5
0x2a314  ldloc.1
0x2a315  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Details()
0x2a31a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x2a31f  br.s     loc_2A342
0x2a321  ldloc.s  5
0x2a323  brfalse.s loc_2A342
0x2a325  ldloc.s  5
0x2a327  ldstr    a01_0// "{0} - {1}"
0x2a32c  ldc.i4.2
0x2a32d  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryEnums/OperationResult
0x2a332  ldloc.1
0x2a333  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Details()
0x2a338  call     string [mscorlib]System.String::Format(string, object, object)
0x2a33d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x2a342  leave    loc_2A3F0
  ... truncated ...
```
