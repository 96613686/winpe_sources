# Microsoft.SharePoint.Publishing.SitePageVersionInfoValueTypeConverter::GetProperty

- ea: `0x117e0`
- end: `0x11859`
- name: `Microsoft.SharePoint.Publishing.SitePageVersionInfoValueTypeConverter::GetProperty`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x117e0`

## string_xrefs

- `0x11821`: `LastVersionCreated`
- `0x1182e`: `LastVersionCreatedBy`

## pseudocode

```c

```

## disassembly

```asm
0x117e0  ldarg.3
0x117e1  brtrue.s loc_117EE
0x117e3  ldstr    aProxycontext// "proxyContext"
0x117e8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x117ed  throw
0x117ee  ldarg.1
0x117ef  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageVersionInfo
0x117f4  stloc.0
0x117f5  ldloc.0
0x117f6  brtrue.s loc_11803
0x117f8  ldstr    aTarget// "target"
0x117fd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11802  throw
0x11803  ldarg.2
0x11804  brtrue.s loc_11811
0x11806  ldstr    aPropname// "propName"
0x1180b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11810  throw
0x11811  ldarg.0
0x11812  ldarg.2
0x11813  ldarg.3
0x11814  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11819  starg.s  2
0x1181b  ldarg.2
0x1181c  dup
0x1181d  stloc.1
0x1181e  brfalse.s loc_1184F
0x11820  ldloc.1
0x11821  ldstr    aLastversioncre// "LastVersionCreated"
0x11826  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1182b  brtrue.s loc_1183C
0x1182d  ldloc.1
0x1182e  ldstr    aLastversioncre_0// "LastVersionCreatedBy"
0x11833  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11838  brtrue.s loc_11848
0x1183a  br.s     loc_1184F
0x1183c  ldloc.0
0x1183d  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageVersionInfo::get_LastVersionCreated()
0x11842  box      [mscorlib]System.DateTime
0x11847  ret
0x11848  ldloc.0
0x11849  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageVersionInfo::get_LastVersionCreatedBy()
0x1184e  ret
0x1184f  ldarg.0
0x11850  ldarg.1
0x11851  ldarg.2
0x11852  ldarg.3
0x11853  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11858  ret
```
