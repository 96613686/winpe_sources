# Microsoft.ReportingServices.Library.SystemResourceManager::ParseMetadata

- ea: `0x56f50`
- end: `0x57055`
- name: `Microsoft.ReportingServices.Library.SystemResourceManager::ParseMetadata`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x57130`

## callees

- `0x56f50`

## string_xrefs

- `0x56f68`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/systemresourcepackagemetadata`
- `0x56fc5`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/systemresourcepackagemetadata`
- `0x56fd9`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/systemresourcepackagemetadata`

## pseudocode

```c

```

## disassembly

```asm
0x56f50  ldarg.0
0x56f51  brtrue.s loc_56F68
0x56f53  ldstr    aMetadata// "metadata"
0x56f58  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStringsWrapper::rsMissingParameter(string)
0x56f5d  ldstr    aMetadata// "metadata"
0x56f62  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x56f67  throw
0x56f68  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/sqlserver/"...
0x56f6d  call     class [System.Xml.Linq]System.Xml.Linq.XNamespace [System.Xml.Linq]System.Xml.Linq.XNamespace::Get(string)
0x56f72  pop
0x56f73  ldarg.0
0x56f74  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XDocument::get_Root()
0x56f79  stloc.0
0x56f7a  ldarg.1
0x56f7b  ldloc.0
0x56f7c  ldstr    aType_1// "type"
0x56f81  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::Get(string)
0x56f86  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x56f8b  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x56f90  stind.ref
0x56f91  ldarg.2
0x56f92  ldloc.0
0x56f93  ldstr    aVersion_1// "version"
0x56f98  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::Get(string)
0x56f9d  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x56fa2  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x56fa7  stind.ref
0x56fa8  ldarg.3
0x56fa9  ldloc.0
0x56faa  ldstr    aName_1// "name"
0x56faf  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::Get(string)
0x56fb4  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x56fb9  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x56fbe  stind.ref
0x56fbf  ldloc.0
0x56fc0  ldstr    aContents// "Contents"
0x56fc5  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/sqlserver/"...
0x56fca  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::Get(string, string)
0x56fcf  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x56fd4  ldstr    aItem// "Item"
0x56fd9  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/sqlserver/"...
0x56fde  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::Get(string, string)
0x56fe3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Elements(class [System.Xml.Linq]System.Xml.Linq.XName)
0x56fe8  stloc.1
0x56fe9  ldarg.s  4
0x56feb  ldloc.1
0x56fec  ldsfld   class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, class Microsoft.ReportingServices.Library.SystemResourceContentItem> <>c::<>9__6_0
0x56ff1  dup
0x56ff2  brtrue.s loc_5700B
0x56ff4  pop
0x56ff5  ldsfld   class <>c <>c::<>9
0x56ffa  ldftn    instance class Microsoft.ReportingServices.Library.SystemResourceContentItem <>c::<ParseMetadata>b__6_0(class [System.Xml.Linq]System.Xml.Linq.XElement x)
0x57000  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, class Microsoft.ReportingServices.Library.SystemResourceContentItem>::.ctor(object, native int)
0x57005  dup
0x57006  stsfld   class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, class Microsoft.ReportingServices.Library.SystemResourceContentItem> <>c::<>9__6_0
0x5700b  call     T0x2B000032
0x57010  ldsfld   class [mscorlib]System.Func`2<class Microsoft.ReportingServices.Library.SystemResourceContentItem, string> <>c::<>9__6_1
0x57015  dup
0x57016  brtrue.s loc_5702F
0x57018  pop
0x57019  ldsfld   class <>c <>c::<>9
0x5701e  ldftn    instance string <>c::<ParseMetadata>b__6_1(class Microsoft.ReportingServices.Library.SystemResourceContentItem x)
0x57024  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.ReportingServices.Library.SystemResourceContentItem, string>::.ctor(object, native int)
0x57029  dup
0x5702a  stsfld   class [mscorlib]System.Func`2<class Microsoft.ReportingServices.Library.SystemResourceContentItem, string> <>c::<>9__6_1
0x5702f  ldsfld   class [mscorlib]System.Func`2<class Microsoft.ReportingServices.Library.SystemResourceContentItem, class Microsoft.ReportingServices.Library.SystemResourceContentItem> <>c::<>9__6_2
0x57034  dup
0x57035  brtrue.s loc_5704E
0x57037  pop
0x57038  ldsfld   class <>c <>c::<>9
0x5703d  ldftn    instance class Microsoft.ReportingServices.Library.SystemResourceContentItem <>c::<ParseMetadata>b__6_2(class Microsoft.ReportingServices.Library.SystemResourceContentItem x)
0x57043  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.ReportingServices.Library.SystemResourceContentItem, class Microsoft.ReportingServices.Library.SystemResourceContentItem>::.ctor(object, native int)
0x57048  dup
0x57049  stsfld   class [mscorlib]System.Func`2<class Microsoft.ReportingServices.Library.SystemResourceContentItem, class Microsoft.ReportingServices.Library.SystemResourceContentItem> <>c::<>9__6_2
0x5704e  call     T0x2B000033
0x57053  stind.ref
0x57054  ret
```
