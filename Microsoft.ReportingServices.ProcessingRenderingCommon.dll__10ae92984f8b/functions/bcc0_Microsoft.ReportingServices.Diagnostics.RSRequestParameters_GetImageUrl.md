# Microsoft.ReportingServices.Diagnostics.RSRequestParameters::GetImageUrl

- ea: `0xbcc0`
- end: `0xbd84`
- name: `Microsoft.ReportingServices.Diagnostics.RSRequestParameters::GetImageUrl`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x8660`
- `0x8820`
- `0xbcc0`
- `0xc420`
- `0xc460`
- `0xc5a0`

## pseudocode

```c

```

## disassembly

```asm
0xbcc0  ldnull
0xbcc1  stloc.0
0xbcc2  ldarg.0
0xbcc3  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_renderingParameters
0xbcc8  brfalse.s loc_BCDB
0xbcca  ldarg.0
0xbccb  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_renderingParameters
0xbcd0  ldstr    aStreamroot// "StreamRoot"
0xbcd5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbcda  stloc.0
0xbcdb  ldloc.0
0xbcdc  brfalse.s loc_BD07
0xbcde  ldloc.0
0xbcdf  ldsfld   string [mscorlib]System.String::Empty
0xbce4  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xbce9  brfalse.s loc_BD07
0xbceb  ldloc.0
0xbcec  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0xbcf1  stloc.s  5
0xbcf3  ldarg.2
0xbcf4  brfalse.s loc_BCFF
0xbcf6  ldloc.s  5
0xbcf8  ldarg.2
0xbcf9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbcfe  pop
0xbcff  ldloc.s  5
0xbd01  callvirt instance string [mscorlib]System.Object::ToString()
0xbd06  ret
0xbd07  ldarg.3
0xbd08  newobj   instance void Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::.ctor(class Microsoft.ReportingServices.Diagnostics.ICatalogItemContext ctx)
0xbd0d  stloc.1
0xbd0e  ldarg.0
0xbd0f  call     instance string Microsoft.ReportingServices.Diagnostics.RSRequestParameters::get_SnapshotParamValue()
0xbd14  stloc.2
0xbd15  ldloc.2
0xbd16  brfalse.s loc_BD24
0xbd18  ldloc.1
0xbd19  ldstr    aSnapshot// "Snapshot"
0xbd1e  ldloc.2
0xbd1f  callvirt instance void Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendCatalogParameter(string name, string val)
0xbd24  ldarg.0
0xbd25  call     instance string Microsoft.ReportingServices.Diagnostics.RSRequestParameters::get_SessionIDParamValue()
0xbd2a  stloc.3
0xbd2b  ldloc.3
0xbd2c  brfalse.s loc_BD3C
0xbd2e  ldloc.1
0xbd2f  ldstr    aSessionid// "SessionID"
0xbd34  ldloc.3
0xbd35  callvirt instance void Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendCatalogParameter(string name, string val)
0xbd3a  br.s     loc_BD58
0xbd3c  ldarg.1
0xbd3d  brfalse.s loc_BD58
0xbd3f  ldarg.0
0xbd40  ldfld    string Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_SessionId
0xbd45  brfalse.s loc_BD58
0xbd47  ldloc.1
0xbd48  ldstr    aSessionid// "SessionID"
0xbd4d  ldarg.0
0xbd4e  ldfld    string Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_SessionId
0xbd53  callvirt instance void Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendCatalogParameter(string name, string val)
0xbd58  ldarg.0
0xbd59  call     instance string Microsoft.ReportingServices.Diagnostics.RSRequestParameters::get_FormatParamValue()
0xbd5e  stloc.s  4
0xbd60  ldloc.s  4
0xbd62  brfalse.s loc_BD71
0xbd64  ldloc.1
0xbd65  ldstr    aFormat// "Format"
0xbd6a  ldloc.s  4
0xbd6c  callvirt instance void Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendCatalogParameter(string name, string val)
0xbd71  ldloc.1
0xbd72  ldstr    aImageid// "ImageID"
0xbd77  ldarg.2
0xbd78  callvirt instance void Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendCatalogParameter(string name, string val)
0xbd7d  ldloc.1
0xbd7e  callvirt instance string [mscorlib]System.Object::ToString()
0xbd83  ret
```
