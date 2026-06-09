# Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetDesignerParameterPropertyValue

- ea: `0xaf0`
- end: `0xb31`
- name: `Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetDesignerParameterPropertyValue`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xaf0`
- `0xb40`
- `0xb620`

## string_xrefs

- `0xb03`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/shareddatasetdefinition`

## pseudocode

```c

```

## disassembly

```asm
0xaf0  newobj   instance void <>c__DisplayClass31_0::.ctor()
0xaf5  stloc.0
0xaf6  ldloc.0
0xaf7  ldarg.1
0xaf8  stfld    string <>c__DisplayClass31_0::parameterName
0xafd  ldarg.0
0xafe  ldstr    aDatasetparamet// "DataSetParameter"
0xb03  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0xb08  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::Get(string, string)
0xb0d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0xb12  ldloc.0
0xb13  ldftn    instance bool <>c__DisplayClass31_0::<GetDesignerParameterPropertyValue>b__0(class [System.Xml.Linq]System.Xml.Linq.XElement x)
0xb19  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, bool>::.ctor(object, native int)
0xb1e  call     T0x2B000007
0xb23  stloc.1
0xb24  ldloc.1
0xb25  brfalse.s loc_B2F
0xb27  ldloc.1
0xb28  ldarg.2
0xb29  call     string Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetDesignerParameterPropertyValue(class [System.Xml.Linq]System.Xml.Linq.XElement parameterElement, string designerPropertyName)
0xb2e  ret
0xb2f  ldnull
0xb30  ret
```
