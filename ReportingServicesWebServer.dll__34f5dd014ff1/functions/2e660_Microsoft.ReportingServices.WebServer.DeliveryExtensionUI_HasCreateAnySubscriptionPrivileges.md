# Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::HasCreateAnySubscriptionPrivileges

- ea: `0x2e660`
- end: `0x2e6c9`
- name: `Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::HasCreateAnySubscriptionPrivileges`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x2e5e0`

## callees

- `0x2e2c0`
- `0x2e2d0`
- `0x2e660`

## string_xrefs

- `0x2e69a`: `Create Any Subscription`

## pseudocode

```c

```

## disassembly

```asm
0x2e660  ldarg.0
0x2e661  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_Service()
0x2e666  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPermissionsAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_GetPermissionsAction()
0x2e66b  dup
0x2e66c  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPermissionsActionParameters>::get_ActionParameters()
0x2e671  ldarg.0
0x2e672  call     instance string Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_ItemPath()
0x2e677  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPermissionsActionParameters::set_ItemPath(string)
0x2e67c  dup
0x2e67d  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPermissionsActionParameters>::Execute()
0x2e682  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPermissionsActionParameters>::get_ActionParameters()
0x2e687  callvirt instance class [System]System.Collections.Specialized.StringCollection [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPermissionsActionParameters::get_Operations()
0x2e68c  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x2e691  stloc.0
0x2e692  br.s     loc_2E6AA
0x2e694  ldloc.0
0x2e695  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x2e69a  ldstr    aCreateAnySubsc// "Create Any Subscription"
0x2e69f  callvirt instance bool [mscorlib]System.String::Equals(string)
0x2e6a4  brfalse.s loc_2E6AA
0x2e6a6  ldc.i4.1
0x2e6a7  stloc.1
0x2e6a8  leave.s  loc_2E6C7
0x2e6aa  ldloc.0
0x2e6ab  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x2e6b0  brtrue.s loc_2E694
0x2e6b2  leave.s  loc_2E6C5
0x2e6b4  ldloc.0
0x2e6b5  isinst   [mscorlib]System.IDisposable
0x2e6ba  stloc.2
0x2e6bb  ldloc.2
0x2e6bc  brfalse.s loc_2E6C4
0x2e6be  ldloc.2
0x2e6bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e6c4  endfinally
0x2e6c5  ldc.i4.0
0x2e6c6  ret
0x2e6c7  ldloc.1
0x2e6c8  ret
```
