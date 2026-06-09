# Microsoft.VisualStudio.Setup.Services.Telemetry::CreateFaultEvent

- ea: `0x464b0`
- end: `0x46841`
- name: `Microsoft.VisualStudio.Setup.Services.Telemetry::CreateFaultEvent`
- size: `913`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x460a0`

## callees

- `0xd360`
- `0xd3a0`
- `0x45c30`
- `0x46460`
- `0x464b0`

## string_xrefs

- `0x46720`: `Adding Install Log to Watson=`
- `0x46754`: `' to Watson as full path could not be found`
- `0x467f5`: `Adding NGEN Install Log to Watson=`
- `0x46820`: `Adding NGEN Install Log to Watson=`

## pseudocode

```c

```

## disassembly

```asm
0x464b0  ldarg.1
0x464b1  ldarg.2
0x464b2  ldarg.s  4
0x464b4  ldnull
0x464b5  newobj   instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::.ctor(string, string, class [mscorlib]System.Exception, class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.IFaultUtility, int32>)
0x464ba  dup
0x464bb  ldc.i4.0
0x464bc  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x464c1  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::set_IsIncludedInWatsonSample(valuetype [mscorlib]System.Nullable`1<bool>)
0x464c6  stloc.0
0x464c7  ldarg.s  5
0x464c9  brfalse.s loc_464E7
0x464cb  ldarg.s  5
0x464cd  unbox.any [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEventCorrelation
0x464d2  stloc.1
0x464d3  ldloc.0
0x464d4  ldc.i4.1
0x464d5  newarr   [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEventCorrelation
0x464da  dup
0x464db  ldc.i4.0
0x464dc  ldloc.1
0x464dd  stelem   [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEventCorrelation
0x464e2  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEvent::Correlate(valuetype [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEventCorrelation[])
0x464e7  ldarg.0
0x464e8  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryEventCorrelation> Microsoft.VisualStudio.Setup.Services.Telemetry::get_SerializedCorrelations()
0x464ed  brfalse.s loc_46532
0x464ef  ldarg.0
0x464f0  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryEventCorrelation> Microsoft.VisualStudio.Setup.Services.Telemetry::get_SerializedCorrelations()
0x464f5  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryEventCorrelation>::get_Count()
0x464fa  ldc.i4.0
0x464fb  ble.s    loc_46532
0x464fd  ldloc.0
0x464fe  ldarg.0
0x464ff  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryEventCorrelation> Microsoft.VisualStudio.Setup.Services.Telemetry::get_SerializedCorrelations()
0x46504  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryEventCorrelation, valuetype [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEventCorrelation> <>c::<>9__61_0
0x46509  dup
0x4650a  brtrue.s loc_46523
0x4650c  pop
0x4650d  ldsfld   class <>c <>c::<>9
0x46512  ldftn    instance valuetype [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEventCorrelation <>c::<CreateFaultEvent>b__61_0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryEventCorrelation x)
0x46518  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryEventCorrelation, valuetype [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEventCorrelation>::.ctor(object, native int)
0x4651d  dup
0x4651e  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryEventCorrelation, valuetype [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEventCorrelation> <>c::<>9__61_0
0x46523  call     T0x2B000206
0x46528  call     T0x2B000208
0x4652d  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEvent::Correlate(valuetype [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEventCorrelation[])
0x46532  ldarg.3
0x46533  brfalse.s loc_46572
0x46535  ldarg.3
0x46536  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::GetEnumerator()
0x4653b  stloc.2
0x4653c  br.s     loc_4655E
0x4653e  ldloc.2
0x4653f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::get_Current()
0x46544  stloc.3
0x46545  ldloc.0
0x46546  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEvent::get_Properties()
0x4654b  ldloca.s 3
0x4654d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x46552  ldloca.s 3
0x46554  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x46559  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x4655e  ldloc.2
0x4655f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x46564  brtrue.s loc_4653E
0x46566  leave.s  loc_46572
0x46568  ldloc.2
0x46569  brfalse.s loc_46571
0x4656b  ldloc.2
0x4656c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x46571  endfinally
0x46572  ldarg.s  6
0x46574  brtrue   loc_4661C
0x46579  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::.ctor()
0x4657e  dup
0x4657f  call     string Microsoft.VisualStudio.Setup.EngineInfo::get_AssemblyName()
0x46584  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::set_Param0(string)
0x46589  dup
0x4658a  call     string Microsoft.VisualStudio.Setup.EngineInfo::get_EngineFileVersion()
0x4658f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::set_Param1(string)
0x46594  starg.s  6
0x46596  ldarg.3
0x46597  brfalse.s loc_46605
0x46599  ldarg.3
0x4659a  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x4659f  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::ContainsKey(var<u1>)
0x465a4  brfalse.s loc_465BD
0x465a6  ldarg.s  6
0x465a8  ldarg.3
0x465a9  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x465ae  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x465b3  callvirt instance string [mscorlib]System.Object::ToString()
0x465b8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::set_Param3(string)
0x465bd  ldarg.3
0x465be  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x465c3  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::ContainsKey(var<u1>)
0x465c8  brfalse.s loc_465E1
0x465ca  ldarg.s  6
0x465cc  ldarg.3
0x465cd  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x465d2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x465d7  callvirt instance string [mscorlib]System.Object::ToString()
0x465dc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::set_Param4(string)
0x465e1  ldarg.3
0x465e2  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTDESCRIPTIONPROPERTY
0x465e7  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::ContainsKey(var<u1>)
0x465ec  brfalse.s loc_46605
0x465ee  ldarg.s  6
0x465f0  ldarg.3
0x465f1  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTDESCRIPTIONPROPERTY
0x465f6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x465fb  callvirt instance string [mscorlib]System.Object::ToString()
0x46600  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::set_Param5(string)
0x46605  ldarg.s  4
0x46607  brfalse.s loc_4661C
0x46609  ldarg.s  6
0x4660b  ldarg.s  4
0x4660d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x46612  callvirt instance string [mscorlib]System.Object::ToString()
0x46617  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::set_Param6(string)
0x4661c  ldloc.0
0x4661d  ldc.i4.0
0x4661e  ldarg.s  6
0x46620  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::get_Param0()
0x46625  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::SetBucketParameter(int32, string)
0x4662a  ldloc.0
0x4662b  ldc.i4.1
0x4662c  ldarg.s  6
0x4662e  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::get_Param1()
0x46633  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::SetBucketParameter(int32, string)
0x46638  ldloc.0
0x46639  ldc.i4.3
0x4663a  ldarg.s  6
0x4663c  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::get_Param3()
0x46641  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::SetBucketParameter(int32, string)
0x46646  ldloc.0
0x46647  ldc.i4.4
0x46648  ldarg.s  6
0x4664a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::get_Param4()
0x4664f  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::SetBucketParameter(int32, string)
0x46654  ldloc.0
0x46655  ldc.i4.5
0x46656  ldarg.s  6
0x46658  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::get_Param5()
0x4665d  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::SetBucketParameter(int32, string)
0x46662  ldloc.0
0x46663  ldc.i4.6
0x46664  ldarg.s  6
0x46666  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::get_Param6()
0x4666b  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::SetBucketParameter(int32, string)
0x46670  ldloc.0
0x46671  ldc.i4.7
0x46672  ldarg.s  6
0x46674  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::get_Param7()
0x46679  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::SetBucketParameter(int32, string)
0x4667e  ldloc.0
0x4667f  ldc.i4.8
0x46680  ldarg.s  6
0x46682  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::get_Param8()
0x46687  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::SetBucketParameter(int32, string)
0x4668c  ldloc.0
0x4668d  ldc.i4.s 9
0x4668f  ldarg.s  6
0x46691  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::get_Param9()
0x46696  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::SetBucketParameter(int32, string)
0x4669b  ldarg.s  9
0x4669d  brfalse.s loc_466B5
0x4669f  ldloc.0
0x466a0  ldarg.0
0x466a1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Services.Telemetry::processService
0x466a6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService::GetCurrentProcess()
0x466ab  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::get_Id()
0x466b0  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::AddProcessDump(int32)
0x466b5  ldarg.s  7
0x466b7  brfalse  loc_46782
0x466bc  ldloc.0
0x466bd  ldc.i4.1
0x466be  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x466c3  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::set_IsIncludedInWatsonSample(valuetype [mscorlib]System.Nullable`1<bool>)
0x466c8  ldarg.s  8
0x466ca  call     T0x2B0000B4
0x466cf  brtrue   loc_46782
0x466d4  ldarg.s  8
0x466d6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x466db  stloc.s  4
0x466dd  br       loc_46768
0x466e2  ldloc.s  4
0x466e4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x466e9  stloc.s  5
0x466eb  ldarg.0
0x466ec  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.Telemetry::fileSystem
0x466f1  ldloc.s  5
0x466f3  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x466f8  brfalse.s loc_46768
0x466fa  ldnull
0x466fb  stloc.s  6
0x466fd  ldloc.s  5
0x466ff  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x46704  stloc.s  6
0x46706  leave.s  loc_4670B
0x46708  pop
0x46709  leave.s  loc_4670B
0x4670b  ldloc.s  6
0x4670d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x46712  brtrue.s loc_46741
0x46714  ldarg.0
0x46715  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Telemetry::logger
0x4671a  dup
0x4671b  brtrue.s loc_46720
0x4671d  pop
0x4671e  br.s     loc_46736
0x46720  ldstr    aAddingInstallL// "Adding Install Log to Watson="
0x46725  ldloc.s  5
0x46727  call     string [mscorlib]System.String::Concat(string, string)
0x4672c  call     T0x2B000003
0x46731  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x46736  ldarg.0
0x46737  ldloc.0
0x46738  ldloc.s  6
0x4673a  callvirt instance void Microsoft.VisualStudio.Setup.Services.Telemetry::AddFile(class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent evt, string path)
0x4673f  br.s     loc_46768
0x46741  ldarg.0
0x46742  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Telemetry::logger
0x46747  dup
0x46748  brtrue.s loc_4674D
0x4674a  pop
0x4674b  br.s     loc_46768
0x4674d  ldstr    aCouldNotAddFil// "Could not add file '"
0x46752  ldloc.s  5
0x46754  ldstr    aToWatsonAsFull// "' to Watson as full path could not be f"...
0x46759  call     string [mscorlib]System.String::Concat(string, string, string)
0x4675e  call     T0x2B000003
0x46763  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x46768  ldloc.s  4
0x4676a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4676f  brtrue   loc_466E2
0x46774  leave.s  loc_46782
0x46776  ldloc.s  4
0x46778  brfalse.s loc_46781
0x4677a  ldloc.s  4
0x4677c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x46781  endfinally
0x46782  ldarg.s  6
0x46784  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::get_Param8()
0x46789  brfalse  loc_4683F
0x4678e  ldstr    a1935// "1935"
0x46793  ldarg.s  6
0x46795  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::get_Param8()
0x4679a  ldc.i4.4
0x4679b  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x467a0  brtrue.s loc_467B9
0x467a2  ldstr    a1937// "1937"
0x467a7  ldarg.s  6
0x467a9  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters::get_Param8()
0x467ae  ldc.i4.4
0x467af  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x467b4  brfalse  loc_4683F
0x467b9  ldloc.0
0x467ba  ldc.i4.1
0x467bb  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x467c0  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent::set_IsIncludedInWatsonSample(valuetype [mscorlib]System.Nullable`1<bool>)
0x467c5  ldarg.0
0x467c6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.Telemetry::fileSystem
0x467cb  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_OperatingSystemDirectory()
0x467d0  dup
0x467d1  ldstr    aMicrosoftNetFr_2// "microsoft.net\\framework\\v4.0.30319\\n"...
0x467d6  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x467db  stloc.s  7
0x467dd  ldstr    aMicrosoftNetFr_3// "microsoft.net\\framework64\\v4.0.30319"...
0x467e2  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x467e7  stloc.s  8
0x467e9  ldarg.0
0x467ea  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Telemetry::logger
0x467ef  dup
0x467f0  brtrue.s loc_467F5
0x467f2  pop
0x467f3  br.s     loc_4680B
0x467f5  ldstr    aAddingNgenInst// "Adding NGEN Install Log to Watson="
0x467fa  ldloc.s  7
0x467fc  call     string [mscorlib]System.String::Concat(string, string)
0x46801  call     T0x2B000003
0x46806  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x4680b  ldarg.0
0x4680c  ldloc.0
0x4680d  ldloc.s  7
0x4680f  callvirt instance void Microsoft.VisualStudio.Setup.Services.Telemetry::AddFile(class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.FaultEvent evt, string path)
0x46814  ldarg.0
0x46815  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Telemetry::logger
0x4681a  dup
0x4681b  brtrue.s loc_46820
0x4681d  pop
0x4681e  br.s     loc_46836
0x46820  ldstr    aAddingNgenInst// "Adding NGEN Install Log to Watson="
0x46825  ldloc.s  8
0x46827  call     string [mscorlib]System.String::Concat(string, string)
0x4682c  call     T0x2B000003
0x46831  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x46836  ldarg.0
0x46837  ldloc.0
0x46838  ldloc.s  8
  ... truncated ...
```
