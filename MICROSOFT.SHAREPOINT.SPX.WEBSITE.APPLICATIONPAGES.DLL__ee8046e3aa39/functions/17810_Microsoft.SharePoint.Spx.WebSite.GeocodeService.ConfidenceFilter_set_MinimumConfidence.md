# Microsoft.SharePoint.Spx.WebSite.GeocodeService.ConfidenceFilter::set_MinimumConfidence

- ea: `0x17810`
- end: `0x1783b`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.ConfidenceFilter::set_MinimumConfidence`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d30`

## callees

- `0x177c0`
- `0x17810`

## pseudocode

```c

```

## disassembly

```asm
0x17810  ldarg.0
0x17811  ldfld    valuetype Microsoft.SharePoint.Spx.WebSite.GeocodeService.Confidence Microsoft.SharePoint.Spx.WebSite.GeocodeService.ConfidenceFilter::MinimumConfidenceField
0x17816  box      Microsoft.SharePoint.Spx.WebSite.GeocodeService.Confidence
0x1781b  ldarg.1
0x1781c  box      Microsoft.SharePoint.Spx.WebSite.GeocodeService.Confidence
0x17821  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x17826  brtrue.s loc_1783A
0x17828  ldarg.0
0x17829  ldarg.1
0x1782a  stfld    valuetype Microsoft.SharePoint.Spx.WebSite.GeocodeService.Confidence Microsoft.SharePoint.Spx.WebSite.GeocodeService.ConfidenceFilter::MinimumConfidenceField
0x1782f  ldarg.0
0x17830  ldstr    aMinimumconfide// "MinimumConfidence"
0x17835  call     instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.FilterBase::RaisePropertyChanged(string propertyName)
0x1783a  ret
```
