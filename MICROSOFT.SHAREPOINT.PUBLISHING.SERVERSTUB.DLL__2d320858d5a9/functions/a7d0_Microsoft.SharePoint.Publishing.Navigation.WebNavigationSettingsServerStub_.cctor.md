# Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::.cctor

- ea: `0xa7d0`
- end: `0xa81a`
- name: `Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::.cctor`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0xa7e1`: `CreateFriendlyUrlsForNewPages`

## pseudocode

```c

```

## disassembly

```asm
0xa7d0  ldc.i4.2
0xa7d1  newarr   [mscorlib]System.String
0xa7d6  stloc.0
0xa7d7  ldloc.0
0xa7d8  ldc.i4.0
0xa7d9  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa7de  stelem.ref
0xa7df  ldloc.0
0xa7e0  ldc.i4.1
0xa7e1  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa7e6  stelem.ref
0xa7e7  ldloc.0
0xa7e8  stsfld   string[] Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::s_valueProperties
0xa7ed  ldc.i4.2
0xa7ee  newarr   [mscorlib]System.String
0xa7f3  stloc.1
0xa7f4  ldloc.1
0xa7f5  ldc.i4.0
0xa7f6  ldstr    aCurrentnavigat// "CurrentNavigation"
0xa7fb  stelem.ref
0xa7fc  ldloc.1
0xa7fd  ldc.i4.1
0xa7fe  ldstr    aGlobalnavigati// "GlobalNavigation"
0xa803  stelem.ref
0xa804  ldloc.1
0xa805  stsfld   string[] Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::s_refProperties
0xa80a  ldstr    a00ac02aa86e24d// "{00ac02aa-86e2-4d48-aa73-341ed7962374}"
0xa80f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa814  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::s_targetTypeId
0xa819  ret
```
