# Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetDataSetParameterCardinalities

- ea: `0xa70`
- end: `0xaed`
- name: `Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetDataSetParameterCardinalities`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa70`

## string_xrefs

- `0xa76`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/shareddatasetdefinition`

## pseudocode

```c

```

## disassembly

```asm
0xa70  ldarg.0
0xa71  ldstr    aDatasetparamet// "DataSetParameter"
0xa76  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0xa7b  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::Get(string, string)
0xa80  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0xa85  ldsfld   class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>> <>c::<>9__30_0
0xa8a  dup
0xa8b  brtrue.s loc_AA4
0xa8d  pop
0xa8e  ldsfld   class <>c <>c::<>9
0xa93  ldftn    instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool> <>c::<GetDataSetParameterCardinalities>b__30_0(class [System.Xml.Linq]System.Xml.Linq.XElement x)
0xa99  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>>::.ctor(object, native int)
0xa9e  dup
0xa9f  stsfld   class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>> <>c::<>9__30_0
0xaa4  call     T0x2B000005
0xaa9  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>, string> <>c::<>9__30_1
0xaae  dup
0xaaf  brtrue.s loc_AC8
0xab1  pop
0xab2  ldsfld   class <>c <>c::<>9
0xab7  ldftn    instance string <>c::<GetDataSetParameterCardinalities>b__30_1(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool> k)
0xabd  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>, string>::.ctor(object, native int)
0xac2  dup
0xac3  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>, string> <>c::<>9__30_1
0xac8  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>, bool> <>c::<>9__30_2
0xacd  dup
0xace  brtrue.s loc_AE7
0xad0  pop
0xad1  ldsfld   class <>c <>c::<>9
0xad6  ldftn    instance bool <>c::<GetDataSetParameterCardinalities>b__30_2(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool> v)
0xadc  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>, bool>::.ctor(object, native int)
0xae1  dup
0xae2  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>, bool> <>c::<>9__30_2
0xae7  call     T0x2B000006
0xaec  ret
```
