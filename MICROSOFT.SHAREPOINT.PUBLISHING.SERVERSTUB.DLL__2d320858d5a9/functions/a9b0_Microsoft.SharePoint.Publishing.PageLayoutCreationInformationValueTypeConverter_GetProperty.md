# Microsoft.SharePoint.Publishing.PageLayoutCreationInformationValueTypeConverter::GetProperty

- ea: `0xa9b0`
- end: `0xaa60`
- name: `Microsoft.SharePoint.Publishing.PageLayoutCreationInformationValueTypeConverter::GetProperty`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xa9b0`

## string_xrefs

- `0xaa0b`: `NewPageLayoutEditablePath`
- `0xaa18`: `NewPageLayoutNameWithoutExtension`

## pseudocode

```c

```

## disassembly

```asm
0xa9b0  ldarg.3
0xa9b1  brtrue.s loc_A9BE
0xa9b3  ldstr    aProxycontext// "proxyContext"
0xa9b8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa9bd  throw
0xa9be  ldarg.1
0xa9bf  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation
0xa9c4  stloc.0
0xa9c5  ldloc.0
0xa9c6  brtrue.s loc_A9D3
0xa9c8  ldstr    aTarget// "target"
0xa9cd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa9d2  throw
0xa9d3  ldarg.2
0xa9d4  brtrue.s loc_A9E1
0xa9d6  ldstr    aPropname// "propName"
0xa9db  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa9e0  throw
0xa9e1  ldarg.0
0xa9e2  ldarg.2
0xa9e3  ldarg.3
0xa9e4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa9e9  starg.s  2
0xa9eb  ldarg.2
0xa9ec  dup
0xa9ed  stloc.1
0xa9ee  brfalse.s loc_AA56
0xa9f0  ldloc.1
0xa9f1  ldstr    aAssociatedcont// "AssociatedContentTypeId"
0xa9f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9fb  brtrue.s loc_AA33
0xa9fd  ldloc.1
0xa9fe  ldstr    aMasterpageurl// "MasterPageUrl"
0xaa03  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaa08  brtrue.s loc_AA3A
0xaa0a  ldloc.1
0xaa0b  ldstr    aNewpagelayoute// "NewPageLayoutEditablePath"
0xaa10  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaa15  brtrue.s loc_AA41
0xaa17  ldloc.1
0xaa18  ldstr    aNewpagelayoutn// "NewPageLayoutNameWithoutExtension"
0xaa1d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaa22  brtrue.s loc_AA48
0xaa24  ldloc.1
0xaa25  ldstr    aWeb_0// "Web"
0xaa2a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaa2f  brtrue.s loc_AA4F
0xaa31  br.s     loc_AA56
0xaa33  ldloc.0
0xaa34  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::get_AssociatedContentTypeId()
0xaa39  ret
0xaa3a  ldloc.0
0xaa3b  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::get_MasterPageUrl()
0xaa40  ret
0xaa41  ldloc.0
0xaa42  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::get_NewPageLayoutEditablePath()
0xaa47  ret
0xaa48  ldloc.0
0xaa49  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::get_NewPageLayoutNameWithoutExtension()
0xaa4e  ret
0xaa4f  ldloc.0
0xaa50  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::get_Web()
0xaa55  ret
0xaa56  ldarg.0
0xaa57  ldarg.1
0xaa58  ldarg.2
0xaa59  ldarg.3
0xaa5a  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaa5f  ret
```
