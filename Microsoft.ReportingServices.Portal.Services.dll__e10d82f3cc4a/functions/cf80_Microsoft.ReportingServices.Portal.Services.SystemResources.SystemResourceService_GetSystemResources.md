# Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::GetSystemResources

- ea: `0xcf80`
- end: `0xd01c`
- name: `Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::GetSystemResources`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x9e80`
- `0xc820`
- `0xcb20`
- `0xcf80`
- `0xd560`

## pseudocode

```c

```

## disassembly

```asm
0xcf80  ldarg.1
0xcf81  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0xcf86  stloc.0
0xcf87  ldloc.0
0xcf88  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceManager [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SystemResourceManager()
0xcf8d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource> [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceManager::LoadAll()
0xcf92  ldsfld   class Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::_embeddedResources
0xcf97  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource> Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::LoadAll()
0xcf9c  newobj   instance void Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceTypeNameComparer::.ctor()
0xcfa1  call     T0x2B0000BB
0xcfa6  stloc.1
0xcfa7  ldc.i4.2
0xcfa8  newarr   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ISystemResourceManager
0xcfad  dup
0xcfae  ldc.i4.0
0xcfaf  ldloc.0
0xcfb0  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceManager [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SystemResourceManager()
0xcfb5  stelem.ref
0xcfb6  dup
0xcfb7  ldc.i4.1
0xcfb8  ldsfld   class Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::_embeddedResources
0xcfbd  stelem.ref
0xcfbe  stloc.2
0xcfbf  ldloc.1
0xcfc0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource>::GetEnumerator()
0xcfc5  stloc.3
0xcfc6  br.s     loc_CFDD
0xcfc8  ldloc.3
0xcfc9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource>::get_Current()
0xcfce  stloc.s  4
0xcfd0  ldsfld   class Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceProcessingManager Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::_processingManager
0xcfd5  ldloc.s  4
0xcfd7  ldloc.2
0xcfd8  callvirt instance void Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceProcessingManager::ProcessResource(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource resource, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ISystemResourceManager> resourceManagers)
0xcfdd  ldloc.3
0xcfde  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcfe3  brtrue.s loc_CFC8
0xcfe5  leave.s  loc_CFF1
0xcfe7  ldloc.3
0xcfe8  brfalse.s loc_CFF0
0xcfea  ldloc.3
0xcfeb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcff0  endfinally
0xcff1  ldloc.1
0xcff2  ldsfld   class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource, class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource> <>c::<>9__9_0
0xcff7  dup
0xcff8  brtrue.s loc_D011
0xcffa  pop
0xcffb  ldsfld   class <>c <>c::<>9
0xd000  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource <>c::<GetSystemResources>b__9_0(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource x)
0xd006  newobj   instance void class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource, class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource>::.ctor(object, native int)
0xd00b  dup
0xd00c  stsfld   class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource, class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource> <>c::<>9__9_0
0xd011  call     T0x2B0000BC
0xd016  call     T0x2B0000BD
0xd01b  ret
```
