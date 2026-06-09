# Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::Create

- ea: `0xcbb0`
- end: `0xcdcf`
- name: `Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::Create`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0xd4f0`

## callees

- `0xc9d0`
- `0xcba0`
- `0xcbb0`
- `0xcdf0`
- `0x219b0`
- `0x21a80`

## pseudocode

```c

```

## disassembly

```asm
0xcbb0  ldsfld   class Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::_instance
0xcbb5  brtrue   loc_CDC9
0xcbba  ldsfld   object Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::_mutex
0xcbbf  stloc.0
0xcbc0  ldc.i4.0
0xcbc1  stloc.1
0xcbc2  ldloc.0
0xcbc3  ldloca.s 1
0xcbc5  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xcbca  ldsfld   class Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::_instance
0xcbcf  brtrue   loc_CDBD
0xcbd4  newobj   instance void Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::.ctor()
0xcbd9  stloc.2
0xcbda  ldsfld   class [mscorlib]System.Reflection.Assembly Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::ResourceAssembly
0xcbdf  callvirt instance string[] [mscorlib]System.Reflection.Assembly::GetManifestResourceNames()
0xcbe4  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__13_0
0xcbe9  dup
0xcbea  brtrue.s loc_CC03
0xcbec  pop
0xcbed  ldsfld   class <>c <>c::<>9
0xcbf2  ldftn    instance bool <>c::<Create>b__13_0(string x)
0xcbf8  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xcbfd  dup
0xcbfe  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__13_0
0xcc03  call     T0x2B0000B6
0xcc08  stloc.3
0xcc09  ldloc.3
0xcc0a  call     T0x2B000036
0xcc0f  brfalse  loc_CDB7
0xcc14  ldloc.3
0xcc15  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__13_1
0xcc1a  dup
0xcc1b  brtrue.s loc_CC34
0xcc1d  pop
0xcc1e  ldsfld   class <>c <>c::<>9
0xcc23  ldftn    instance string <>c::<Create>b__13_1(string x)
0xcc29  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0xcc2e  dup
0xcc2f  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__13_1
0xcc34  call     T0x2B00006B
0xcc39  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__13_2
0xcc3e  dup
0xcc3f  brtrue.s loc_CC58
0xcc41  pop
0xcc42  ldsfld   class <>c <>c::<>9
0xcc47  ldftn    instance string <>c::<Create>b__13_2(string x)
0xcc4d  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0xcc52  dup
0xcc53  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__13_2
0xcc58  call     T0x2B00006B
0xcc5d  call     T0x2B0000B7
0xcc62  stloc.s  4
0xcc64  ldloc.s  4
0xcc66  call     T0x2B000036
0xcc6b  brfalse  loc_CDB7
0xcc70  ldloc.s  4
0xcc72  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0xcc77  stloc.s  5
0xcc79  br       loc_CD9D
0xcc7e  newobj   instance void <>c__DisplayClass13_0::.ctor()
0xcc83  stloc.s  6
0xcc85  ldloc.s  6
0xcc87  ldloc.s  5
0xcc89  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0xcc8e  stfld    string <>c__DisplayClass13_0::typeName
0xcc93  newobj   instance void <>c__DisplayClass13_1::.ctor()
0xcc98  stloc.s  7
0xcc9a  ldloc.3
0xcc9b  ldloc.s  6
0xcc9d  ldftn    instance bool <>c__DisplayClass13_0::<Create>b__3(string x)
0xcca3  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xcca8  call     T0x2B0000B6
0xccad  stloc.s  8
0xccaf  ldloc.s  8
0xccb1  call     T0x2B000036
0xccb6  brfalse  loc_CD9D
0xccbb  ldloc.s  7
0xccbd  ldloc.s  8
0xccbf  ldloc.s  6
0xccc1  ldftn    instance bool <>c__DisplayClass13_0::<Create>b__4(string x)
0xccc7  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xcccc  call     T0x2B0000B8
0xccd1  stfld    string <>c__DisplayClass13_1::metadataLocation
0xccd6  ldloc.s  7
0xccd8  ldfld    string <>c__DisplayClass13_1::metadataLocation
0xccdd  brfalse  loc_CD9D
0xcce2  ldloc.s  8
0xcce4  ldloc.s  6
0xcce6  ldftn    instance bool <>c__DisplayClass13_0::<Create>b__5(string x)
0xccec  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xccf1  call     T0x2B0000B6
0xccf6  stloc.s  9
0xccf8  ldloc.s  9
0xccfa  call     T0x2B000036
0xccff  brfalse  loc_CD9D
0xcd04  ldloc.s  8
0xcd06  ldloc.s  7
0xcd08  ldftn    instance bool <>c__DisplayClass13_1::<Create>b__6(string x)
0xcd0e  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xcd13  call     T0x2B0000B6
0xcd18  ldloc.s  9
0xcd1a  call     T0x2B00004F
0xcd1f  call     T0x2B0000B9
0xcd24  stloc.s  0xA
0xcd26  ldloc.s  0xA
0xcd28  brfalse.s loc_CD9D
0xcd2a  ldloc.2
0xcd2b  ldloc.s  7
0xcd2d  ldftn    instance class [mscorlib]System.IO.Stream <>c__DisplayClass13_1::<Create>b__7()
0xcd33  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream>::.ctor(object, native int)
0xcd38  ldloc.s  9
0xcd3a  ldloc.s  6
0xcd3c  ldftn    instance string <>c__DisplayClass13_0::<Create>b__8(string x)
0xcd42  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0xcd47  ldsfld   class [mscorlib]System.Func`2<string, class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream>> <>c::<>9__13_9
0xcd4c  dup
0xcd4d  brtrue.s loc_CD66
0xcd4f  pop
0xcd50  ldsfld   class <>c <>c::<>9
0xcd55  ldftn    instance class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream> <>c::<Create>b__13_9(string x)
0xcd5b  newobj   instance void class [mscorlib]System.Func`2<string, class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream>>::.ctor(object, native int)
0xcd60  dup
0xcd61  stsfld   class [mscorlib]System.Func`2<string, class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream>> <>c::<>9__13_9
0xcd66  call     T0x2B0000BA
0xcd6b  ldloc.s  0xA
0xcd6d  call     unsigned int8[] Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::GetBytes(string location)
0xcd72  ldloc.s  0xA
0xcd74  ldstr    a01_1// "{0}.{1}."
0xcd79  ldsfld   string Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::ResourceRoot
0xcd7e  ldloc.s  6
0xcd80  ldfld    string <>c__DisplayClass13_0::typeName
0xcd85  call     string [mscorlib]System.String::Format(string, object, object)
0xcd8a  callvirt instance int32 [mscorlib]System.String::get_Length()
0xcd8f  callvirt instance string [mscorlib]System.String::Substring(int32)
0xcd94  ldnull
0xcd95  ldnull
0xcd96  ldnull
0xcd97  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::Install(class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream> metadataStream, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream>> contentStreams, unsigned int8[] packageBytes, string packageName, string typeName, class [mscorlib]System.Func`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ISystemResourcePackageContentValidator> validator, class [mscorlib]System.Func`2<string, string> contentTypeMapper)
0xcd9c  pop
0xcd9d  ldloc.s  5
0xcd9f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcda4  brtrue   loc_CC7E
0xcda9  leave.s  loc_CDB7
0xcdab  ldloc.s  5
0xcdad  brfalse.s loc_CDB6
0xcdaf  ldloc.s  5
0xcdb1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcdb6  endfinally
0xcdb7  ldloc.2
0xcdb8  stsfld   class Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::_instance
0xcdbd  leave.s  loc_CDC9
0xcdbf  ldloc.1
0xcdc0  brfalse.s loc_CDC8
0xcdc2  ldloc.0
0xcdc3  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xcdc8  endfinally
0xcdc9  ldsfld   class Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::_instance
0xcdce  ret
```
