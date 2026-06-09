# Microsoft.SharePoint.Publishing.SitePageVersionInfoValueTypeConverter::SetProperty

- ea: `0x11860`
- end: `0x118f2`
- name: `Microsoft.SharePoint.Publishing.SitePageVersionInfoValueTypeConverter::SetProperty`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x11860`

## string_xrefs

- `0x118b1`: `LastVersionCreated`
- `0x118be`: `LastVersionCreatedBy`

## pseudocode

```c

```

## disassembly

```asm
0x11860  ldarg.s  4
0x11862  brtrue.s loc_1186F
0x11864  ldstr    aProxycontext// "proxyContext"
0x11869  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1186e  throw
0x1186f  ldarg.1
0x11870  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageVersionInfo
0x11875  stloc.0
0x11876  ldloc.0
0x11877  brtrue.s loc_11884
0x11879  ldstr    aTarget// "target"
0x1187e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11883  throw
0x11884  ldarg.2
0x11885  brtrue.s loc_11892
0x11887  ldstr    aPropname// "propName"
0x1188c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11891  throw
0x11892  ldarg.3
0x11893  brtrue.s loc_118A0
0x11895  ldstr    aPropvalue// "propValue"
0x1189a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1189f  throw
0x118a0  ldarg.0
0x118a1  ldarg.2
0x118a2  ldarg.s  4
0x118a4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x118a9  starg.s  2
0x118ab  ldarg.2
0x118ac  dup
0x118ad  stloc.1
0x118ae  brfalse.s loc_118E6
0x118b0  ldloc.1
0x118b1  ldstr    aLastversioncre// "LastVersionCreated"
0x118b6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x118bb  brtrue.s loc_118CC
0x118bd  ldloc.1
0x118be  ldstr    aLastversioncre_0// "LastVersionCreatedBy"
0x118c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x118c8  brtrue.s loc_118D9
0x118ca  br.s     loc_118E6
0x118cc  ldloc.0
0x118cd  ldarg.3
0x118ce  callvirt T0x2B00002B
0x118d3  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageVersionInfo::set_LastVersionCreated(valuetype [mscorlib]System.DateTime)
0x118d8  ret
0x118d9  ldloc.0
0x118da  ldarg.3
0x118db  callvirt T0x2B000001
0x118e0  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageVersionInfo::set_LastVersionCreatedBy(string)
0x118e5  ret
0x118e6  ldarg.0
0x118e7  ldarg.1
0x118e8  ldarg.2
0x118e9  ldarg.3
0x118ea  ldarg.s  4
0x118ec  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x118f1  ret
```
