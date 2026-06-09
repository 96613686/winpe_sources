# Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::.cctor

- ea: `0x78e0`
- end: `0x7983`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::.cctor`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x792a`: `SimpleLinkUrl`

## pseudocode

```c

```

## disassembly

```asm
0x78e0  ldc.i4.s 9
0x78e2  newarr   [mscorlib]System.String
0x78e7  stloc.0
0x78e8  ldloc.0
0x78e9  ldc.i4.0
0x78ea  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x78ef  stelem.ref
0x78f0  ldloc.0
0x78f1  ldc.i4.1
0x78f2  ldstr    aCategoryimageu// "CategoryImageUrl"
0x78f7  stelem.ref
0x78f8  ldloc.0
0x78f9  ldc.i4.2
0x78fa  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x78ff  stelem.ref
0x7900  ldloc.0
0x7901  ldc.i4.3
0x7902  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x7907  stelem.ref
0x7908  ldloc.0
0x7909  ldc.i4.4
0x790a  ldstr    aHovertext// "HoverText"
0x790f  stelem.ref
0x7910  ldloc.0
0x7911  ldc.i4.5
0x7912  ldstr    aIsdeprecated// "IsDeprecated"
0x7917  stelem.ref
0x7918  ldloc.0
0x7919  ldc.i4.6
0x791a  ldstr    aIspinned// "IsPinned"
0x791f  stelem.ref
0x7920  ldloc.0
0x7921  ldc.i4.7
0x7922  ldstr    aIspinnedroot// "IsPinnedRoot"
0x7927  stelem.ref
0x7928  ldloc.0
0x7929  ldc.i4.8
0x792a  ldstr    aSimplelinkurl// "SimpleLinkUrl"
0x792f  stelem.ref
0x7930  ldloc.0
0x7931  stsfld   string[] Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::s_valueProperties
0x7936  ldc.i4.6
0x7937  newarr   [mscorlib]System.String
0x793c  stloc.1
0x793d  ldloc.1
0x793e  ldc.i4.0
0x793f  ldstr    aCatalogtargetu_0// "CatalogTargetUrl"
0x7944  stelem.ref
0x7945  ldloc.1
0x7946  ldc.i4.1
0x7947  ldstr    aExcludedprovid// "ExcludedProviders"
0x794c  stelem.ref
0x794d  ldloc.1
0x794e  ldc.i4.2
0x794f  ldstr    aFriendlyurlseg// "FriendlyUrlSegment"
0x7954  stelem.ref
0x7955  ldloc.1
0x7956  ldc.i4.3
0x7957  ldstr    aParent// "Parent"
0x795c  stelem.ref
0x795d  ldloc.1
0x795e  ldc.i4.4
0x795f  ldstr    aTargeturl// "TargetUrl"
0x7964  stelem.ref
0x7965  ldloc.1
0x7966  ldc.i4.5
0x7967  ldstr    aTermset// "TermSet"
0x796c  stelem.ref
0x796d  ldloc.1
0x796e  stsfld   string[] Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::s_refProperties
0x7973  ldstr    a74b7367aE30343// "{74b7367a-e303-43e8-891e-dac764c96e53}"
0x7978  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x797d  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::s_targetTypeId
0x7982  ret
```
