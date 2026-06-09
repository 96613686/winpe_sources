# Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::ReplaceParametersWithExecParameterId

- ea: `0x87d0`
- end: `0x87fd`
- name: `Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::ReplaceParametersWithExecParameterId`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x8770`
- `0x87b0`

## callees

- `0x87d0`
- `0x8820`
- `0xcca0`

## string_xrefs

- `0x87ee`: `StoredParametersID`

## pseudocode

```c

```

## disassembly

```asm
0x87d0  ldnull
0x87d1  stloc.0
0x87d2  ldarg.0
0x87d3  ldfld    class Microsoft.ReportingServices.Diagnostics.IReportParameterLookup Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::m_paramLookup
0x87d8  brfalse.s loc_87EA
0x87da  ldarg.1
0x87db  brfalse.s loc_87EA
0x87dd  ldarg.0
0x87de  ldfld    class Microsoft.ReportingServices.Diagnostics.IReportParameterLookup Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::m_paramLookup
0x87e3  ldarg.1
0x87e4  callvirt instance string Microsoft.ReportingServices.Diagnostics.IReportParameterLookup::GetReportParamsInstanceId(class [System]System.Collections.Specialized.NameValueCollection reportParameters)
0x87e9  stloc.0
0x87ea  ldloc.0
0x87eb  brfalse.s loc_87FB
0x87ed  ldarg.0
0x87ee  ldstr    aStoredparamete// "StoredParametersID"
0x87f3  ldloc.0
0x87f4  call     instance void Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendCatalogParameter(string name, string val)
0x87f9  ldc.i4.1
0x87fa  ret
0x87fb  ldc.i4.0
0x87fc  ret
```
