# Microsoft.SharePoint.Publishing.SitePageServiceServerStub::.cctor

- ea: `0x11650`
- end: `0x116a7`
- name: `Microsoft.SharePoint.Publishing.SitePageServiceServerStub::.cctor`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x1166e`: `CommunicationSite`

## pseudocode

```c

```

## disassembly

```asm
0x11650  ldc.i4.1
0x11651  newarr   [mscorlib]System.String
0x11656  stloc.0
0x11657  ldloc.0
0x11658  ldc.i4.0
0x11659  ldstr    aCustomcontenta// "CustomContentApprovalEnabled"
0x1165e  stelem.ref
0x1165f  ldloc.0
0x11660  stsfld   string[] Microsoft.SharePoint.Publishing.SitePageServiceServerStub::s_valueProperties
0x11665  ldc.i4.2
0x11666  newarr   [mscorlib]System.String
0x1166b  stloc.1
0x1166c  ldloc.1
0x1166d  ldc.i4.0
0x1166e  ldstr    aCommunications// "CommunicationSite"
0x11673  stelem.ref
0x11674  ldloc.1
0x11675  ldc.i4.1
0x11676  ldstr    aPages// "Pages"
0x1167b  stelem.ref
0x1167c  ldloc.1
0x1167d  stsfld   string[] Microsoft.SharePoint.Publishing.SitePageServiceServerStub::s_refProperties
0x11682  ldc.i4.1
0x11683  newarr   [mscorlib]System.String
0x11688  stloc.2
0x11689  ldloc.2
0x1168a  ldc.i4.0
0x1168b  ldstr    aCustomcontenta// "CustomContentApprovalEnabled"
0x11690  stelem.ref
0x11691  ldloc.2
0x11692  stsfld   string[] Microsoft.SharePoint.Publishing.SitePageServiceServerStub::s_excludeFromDefaultRetrieveProperties
0x11697  ldstr    aBd3b709a892e41// "{bd3b709a-892e-419b-9d14-56bbec1169b9}"
0x1169c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x116a1  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.SitePageServiceServerStub::s_targetTypeId
0x116a6  ret
```
