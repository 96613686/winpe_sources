# Microsoft.SharePoint.Publishing.PageLayoutCreationInformationValueTypeConverter::SetProperty

- ea: `0xaa60`
- end: `0xab43`
- name: `Microsoft.SharePoint.Publishing.PageLayoutCreationInformationValueTypeConverter::SetProperty`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xaa60`

## string_xrefs

- `0xaace`: `NewPageLayoutEditablePath`
- `0xaadb`: `NewPageLayoutNameWithoutExtension`

## pseudocode

```c

```

## disassembly

```asm
0xaa60  ldarg.s  4
0xaa62  brtrue.s loc_AA6F
0xaa64  ldstr    aProxycontext// "proxyContext"
0xaa69  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaa6e  throw
0xaa6f  ldarg.1
0xaa70  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation
0xaa75  stloc.0
0xaa76  ldloc.0
0xaa77  brtrue.s loc_AA84
0xaa79  ldstr    aTarget// "target"
0xaa7e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaa83  throw
0xaa84  ldarg.2
0xaa85  brtrue.s loc_AA92
0xaa87  ldstr    aPropname// "propName"
0xaa8c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaa91  throw
0xaa92  ldarg.3
0xaa93  brtrue.s loc_AAA0
0xaa95  ldstr    aPropvalue// "propValue"
0xaa9a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaa9f  throw
0xaaa0  ldarg.0
0xaaa1  ldarg.2
0xaaa2  ldarg.s  4
0xaaa4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaaa9  starg.s  2
0xaaab  ldarg.2
0xaaac  dup
0xaaad  stloc.1
0xaaae  brfalse  loc_AB37
0xaab3  ldloc.1
0xaab4  ldstr    aAssociatedcont// "AssociatedContentTypeId"
0xaab9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaabe  brtrue.s loc_AAF6
0xaac0  ldloc.1
0xaac1  ldstr    aMasterpageurl// "MasterPageUrl"
0xaac6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaacb  brtrue.s loc_AB03
0xaacd  ldloc.1
0xaace  ldstr    aNewpagelayoute// "NewPageLayoutEditablePath"
0xaad3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaad8  brtrue.s loc_AB10
0xaada  ldloc.1
0xaadb  ldstr    aNewpagelayoutn// "NewPageLayoutNameWithoutExtension"
0xaae0  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaae5  brtrue.s loc_AB1D
0xaae7  ldloc.1
0xaae8  ldstr    aWeb_0// "Web"
0xaaed  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaaf2  brtrue.s loc_AB2A
0xaaf4  br.s     loc_AB37
0xaaf6  ldloc.0
0xaaf7  ldarg.3
0xaaf8  callvirt T0x2B000001
0xaafd  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::set_AssociatedContentTypeId(string)
0xab02  ret
0xab03  ldloc.0
0xab04  ldarg.3
0xab05  callvirt T0x2B000001
0xab0a  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::set_MasterPageUrl(string)
0xab0f  ret
0xab10  ldloc.0
0xab11  ldarg.3
0xab12  callvirt T0x2B000001
0xab17  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::set_NewPageLayoutEditablePath(string)
0xab1c  ret
0xab1d  ldloc.0
0xab1e  ldarg.3
0xab1f  callvirt T0x2B000001
0xab24  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::set_NewPageLayoutNameWithoutExtension(string)
0xab29  ret
0xab2a  ldloc.0
0xab2b  ldarg.3
0xab2c  callvirt T0x2B00001F
0xab31  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::set_Web(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0xab36  ret
0xab37  ldarg.0
0xab38  ldarg.1
0xab39  ldarg.2
0xab3a  ldarg.3
0xab3b  ldarg.s  4
0xab3d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab42  ret
```
