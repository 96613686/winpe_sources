# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataRegionExprHost::get_FilterHostsRemotable

- ea: `0x1820`
- end: `0x1848`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataRegionExprHost::get_FilterHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1820`

## pseudocode

```c

```

## disassembly

```asm
0x1820  ldarg.0
0x1821  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataRegionExprHost::m_filterHostsRemotable
0x1826  brtrue.s loc_1841
0x1828  ldarg.0
0x1829  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataRegionExprHost::FilterHosts
0x182e  brfalse.s loc_1841
0x1830  ldarg.0
0x1831  ldarg.0
0x1832  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataRegionExprHost::FilterHosts
0x1837  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost>::.ctor(var<u1>[])
0x183c  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataRegionExprHost::m_filterHostsRemotable
0x1841  ldarg.0
0x1842  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataRegionExprHost::m_filterHostsRemotable
0x1847  ret
```
