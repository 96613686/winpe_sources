# Microsoft.ReportingServices.WebServer.ReportViewerPage::HasScheduleReadyDataSources

- ea: `0x33f40`
- end: `0x33fae`
- name: `Microsoft.ReportingServices.WebServer.ReportViewerPage::HasScheduleReadyDataSources`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x33c60`

## callees

- `0x2db10`
- `0x33f40`

## string_xrefs

- `0x33f40`: `HasScheduleReadyDataSources`

## pseudocode

```c

```

## disassembly

```asm
0x33f40  ldstr    aHasschedulerea// "HasScheduleReadyDataSources"
0x33f45  stloc.0
0x33f46  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.WebServer.Global::get_Service()
0x33f4b  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_GetPropertiesAction()
0x33f50  stloc.1
0x33f51  ldloc.1
0x33f52  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters>::get_ActionParameters()
0x33f57  ldc.i4.0
0x33f58  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters::set_ItemNamespace(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ItemNamespaceEnum)
0x33f5d  ldloc.1
0x33f5e  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters>::get_ActionParameters()
0x33f63  ldarg.0
0x33f64  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters::set_ItemPath(string)
0x33f69  ldloc.1
0x33f6a  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters>::get_ActionParameters()
0x33f6f  ldc.i4.1
0x33f70  newarr   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property
0x33f75  dup
0x33f76  ldc.i4.0
0x33f77  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x33f7c  dup
0x33f7d  ldloc.0
0x33f7e  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x33f83  stelem.ref
0x33f84  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters::set_RequestedProperties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x33f89  ldloc.1
0x33f8a  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters>::Execute()
0x33f8f  ldloc.1
0x33f90  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters>::get_ActionParameters()
0x33f95  ldloc.0
0x33f96  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters::GetValue(string)
0x33f9b  stloc.2
0x33f9c  ldloc.2
0x33f9d  brfalse.s loc_33FAC
0x33f9f  ldloc.2
0x33fa0  ldstr    aTrue// "true"
0x33fa5  ldc.i4.3
0x33fa6  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x33fab  ret
0x33fac  ldc.i4.1
0x33fad  ret
```
