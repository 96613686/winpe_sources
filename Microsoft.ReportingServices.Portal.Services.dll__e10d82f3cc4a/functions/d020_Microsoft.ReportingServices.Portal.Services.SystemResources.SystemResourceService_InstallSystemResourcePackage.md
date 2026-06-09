# Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::InstallSystemResourcePackage

- ea: `0xd020`
- end: `0xd1bc`
- name: `Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::InstallSystemResourcePackage`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x9e80`
- `0xa8c0`
- `0xd020`
- `0xd340`
- `0xd3b0`
- `0xd4c0`
- `0x21c90`

## pseudocode

```c

```

## disassembly

```asm
0xd020  ldarg.0
0xd021  ldarg.1
0xd022  call     instance void Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::CheckAccess(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal)
0xd027  ldarg.2
0xd028  brtrue.s loc_D035
0xd02a  ldstr    aPackagebytes// "packageBytes"
0xd02f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd034  throw
0xd035  ldarg.3
0xd036  brtrue.s loc_D043
0xd038  ldstr    aPackagefilenam// "packageFileName"
0xd03d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd042  throw
0xd043  ldarg.s  4
0xd045  brtrue.s loc_D052
0xd047  ldstr    aTypename// "typeName"
0xd04c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd051  throw
0xd052  ldarg.s  4
0xd054  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourceType Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::GetSystemResourceType(string typeName)
0xd059  ldc.i4.2
0xd05a  bne.un.s loc_D067
0xd05c  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_SystemResourcePackageException()
0xd061  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.SystemResourcePackageException::.ctor(string)
0xd066  throw
0xd067  ldnull
0xd068  stloc.0
0xd069  ldsfld   class [mscorlib]System.Func`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ISystemResourcePackageContentValidator> <>c::<>9__10_0
0xd06e  dup
0xd06f  brtrue.s loc_D088
0xd071  pop
0xd072  ldsfld   class <>c <>c::<>9
0xd077  ldftn    instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ISystemResourcePackageContentValidator <>c::<InstallSystemResourcePackage>b__10_0(string t)
0xd07d  newobj   instance void class [mscorlib]System.Func`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ISystemResourcePackageContentValidator>::.ctor(object, native int)
0xd082  dup
0xd083  stsfld   class [mscorlib]System.Func`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ISystemResourcePackageContentValidator> <>c::<>9__10_0
0xd088  stloc.1
0xd089  ldarg.2
0xd08a  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0xd08f  stloc.2
0xd090  newobj   instance void <>c__DisplayClass10_0::.ctor()
0xd095  stloc.3
0xd096  ldloc.3
0xd097  ldloc.2
0xd098  ldc.i4.0
0xd099  ldc.i4.0
0xd09a  newobj   instance void [System.IO.Compression]System.IO.Compression.ZipArchive::.ctor(class [mscorlib]System.IO.Stream, valuetype [System.IO.Compression]System.IO.Compression.ZipArchiveMode, bool)
0xd09f  stfld    class [System.IO.Compression]System.IO.Compression.ZipArchive <>c__DisplayClass10_0::archive
0xd0a4  ldloc.3
0xd0a5  ldftn    instance class [mscorlib]System.IO.Stream <>c__DisplayClass10_0::<InstallSystemResourcePackage>b__1()
0xd0ab  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream>::.ctor(object, native int)
0xd0b0  stloc.s  4
0xd0b2  ldloc.3
0xd0b3  ldfld    class [System.IO.Compression]System.IO.Compression.ZipArchive <>c__DisplayClass10_0::archive
0xd0b8  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry> [System.IO.Compression]System.IO.Compression.ZipArchive::get_Entries()
0xd0bd  ldsfld   class [mscorlib]System.Func`2<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, bool> <>c::<>9__10_2
0xd0c2  dup
0xd0c3  brtrue.s loc_D0DC
0xd0c5  pop
0xd0c6  ldsfld   class <>c <>c::<>9
0xd0cb  ldftn    instance bool <>c::<InstallSystemResourcePackage>b__10_2(class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry x)
0xd0d1  newobj   instance void class [mscorlib]System.Func`2<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, bool>::.ctor(object, native int)
0xd0d6  dup
0xd0d7  stsfld   class [mscorlib]System.Func`2<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, bool> <>c::<>9__10_2
0xd0dc  call     T0x2B0000BE
0xd0e1  ldsfld   class [mscorlib]System.Func`2<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, bool> <>c::<>9__10_3
0xd0e6  dup
0xd0e7  brtrue.s loc_D100
0xd0e9  pop
0xd0ea  ldsfld   class <>c <>c::<>9
0xd0ef  ldftn    instance bool <>c::<InstallSystemResourcePackage>b__10_3(class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry x)
0xd0f5  newobj   instance void class [mscorlib]System.Func`2<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, bool>::.ctor(object, native int)
0xd0fa  dup
0xd0fb  stsfld   class [mscorlib]System.Func`2<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, bool> <>c::<>9__10_3
0xd100  call     T0x2B0000BE
0xd105  ldsfld   class [mscorlib]System.Func`2<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, string> <>c::<>9__10_4
0xd10a  dup
0xd10b  brtrue.s loc_D124
0xd10d  pop
0xd10e  ldsfld   class <>c <>c::<>9
0xd113  ldftn    instance string <>c::<InstallSystemResourcePackage>b__10_4(class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry x)
0xd119  newobj   instance void class [mscorlib]System.Func`2<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, string>::.ctor(object, native int)
0xd11e  dup
0xd11f  stsfld   class [mscorlib]System.Func`2<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, string> <>c::<>9__10_4
0xd124  ldsfld   class [mscorlib]System.Func`2<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream>> <>c::<>9__10_5
0xd129  dup
0xd12a  brtrue.s loc_D143
0xd12c  pop
0xd12d  ldsfld   class <>c <>c::<>9
0xd132  ldftn    instance class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream> <>c::<InstallSystemResourcePackage>b__10_5(class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry x)
0xd138  newobj   instance void class [mscorlib]System.Func`2<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream>>::.ctor(object, native int)
0xd13d  dup
0xd13e  stsfld   class [mscorlib]System.Func`2<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream>> <>c::<>9__10_5
0xd143  call     T0x2B0000BF
0xd148  stloc.s  5
0xd14a  ldarg.1
0xd14b  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0xd150  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__10_6
0xd155  dup
0xd156  brtrue.s loc_D16F
0xd158  pop
0xd159  ldsfld   class <>c <>c::<>9
0xd15e  ldftn    instance string <>c::<InstallSystemResourcePackage>b__10_6(string fn)
0xd164  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0xd169  dup
0xd16a  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__10_6
0xd16f  stloc.s  6
0xd171  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceManager [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SystemResourceManager()
0xd176  ldloc.s  4
0xd178  ldloc.s  5
0xd17a  ldarg.2
0xd17b  ldarg.3
0xd17c  ldarg.s  4
0xd17e  ldloc.1
0xd17f  ldloc.s  6
0xd181  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceManager::Install(class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream>, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream>>, unsigned int8[], string, string, class [mscorlib]System.Func`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ISystemResourcePackageContentValidator>, class [mscorlib]System.Func`2<string, string>)
0xd186  stloc.0
0xd187  leave.s  loc_D19D
0xd189  ldloc.3
0xd18a  ldfld    class [System.IO.Compression]System.IO.Compression.ZipArchive <>c__DisplayClass10_0::archive
0xd18f  brfalse.s loc_D19C
0xd191  ldloc.3
0xd192  ldfld    class [System.IO.Compression]System.IO.Compression.ZipArchive <>c__DisplayClass10_0::archive
0xd197  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd19c  endfinally
0xd19d  leave.s  loc_D1B5
0xd19f  pop
0xd1a0  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_SystemResourcePackageException()
0xd1a5  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.SystemResourcePackageException::.ctor(string)
0xd1aa  throw
0xd1ab  ldloc.2
0xd1ac  brfalse.s loc_D1B4
0xd1ae  ldloc.2
0xd1af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1b4  endfinally
0xd1b5  ldloc.0
0xd1b6  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::ConvertToSystemResourceModel(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource systemResource)
0xd1bb  ret
```
