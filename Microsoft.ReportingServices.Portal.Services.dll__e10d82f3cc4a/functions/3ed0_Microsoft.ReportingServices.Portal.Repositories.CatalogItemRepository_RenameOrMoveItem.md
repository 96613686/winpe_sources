# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::RenameOrMoveItem

- ea: `0x3ed0`
- end: `0x3f2a`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::RenameOrMoveItem`
- size: `90`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d770`
- `0x1d7f0`
- `0x1da30`
- `0x1dbf0`
- `0x1dc70`
- `0x1dd50`
- `0x1de90`
- `0x1df00`
- `0x1df70`
- `0x1e0b0`
- `0x1e1b0`

## callees

- `0x3ed0`

## pseudocode

```c

```

## disassembly

```asm
0x3ed0  ldarg.2
0x3ed1  ldstr    asc_25576// "/"
0x3ed6  ldc.i4.4
0x3ed7  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x3edc  brtrue.s loc_3EEB
0x3ede  ldstr    asc_25576// "/"
0x3ee3  ldarg.2
0x3ee4  call     string [mscorlib]System.String::Concat(string, string)
0x3ee9  starg.s  2
0x3eeb  ldarg.3
0x3eec  ldstr    asc_25576// "/"
0x3ef1  ldc.i4.4
0x3ef2  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x3ef7  brtrue.s loc_3F06
0x3ef9  ldstr    asc_25576// "/"
0x3efe  ldarg.3
0x3eff  call     string [mscorlib]System.String::Concat(string, string)
0x3f04  starg.s  3
0x3f06  ldarg.1
0x3f07  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.MoveItemAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_MoveItemAction()
0x3f0c  dup
0x3f0d  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.MoveItemActionParameters>::get_ActionParameters()
0x3f12  ldarg.2
0x3f13  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.MoveItemActionParameters::set_SourceItemPath(string)
0x3f18  dup
0x3f19  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.MoveItemActionParameters>::get_ActionParameters()
0x3f1e  ldarg.3
0x3f1f  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.MoveItemActionParameters::set_TargetItemPath(string)
0x3f24  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.MoveItemActionParameters>::PerformActionNow()
0x3f29  ret
```
