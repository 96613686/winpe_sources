# Microsoft.ReportingServices.Common.XsdUtil::.cctor

- ea: `0x39f60`
- end: `0x39fc5`
- name: `Microsoft.ReportingServices.Common.XsdUtil::.cctor`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x39f7e`: `Microsoft.ReportingServices.ReportDefinition.xsd`
- `0x39f8d`: `/ComponentDefinition.xsd`
- `0x39f9c`: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentDefinition.xsd`
- `0x39fba`: `Microsoft.ReportingServices.SharedDataSetDefinition.xsd`

## pseudocode

```c

```

## disassembly

```asm
0x39f60  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x39f65  stsfld   class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Common.XsdUtil::m_xsdResourceMappings
0x39f6a  ldsfld   class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Common.XsdUtil::m_xsdResourceMappings
0x39f6f  ldstr    aReportdefiniti// "/ReportDefinition.xsd"
0x39f74  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x39f79  ldsfld   class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Common.XsdUtil::m_xsdResourceMappings
0x39f7e  ldstr    aMicrosoftRepor_147// "Microsoft.ReportingServices.ReportDefin"...
0x39f83  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x39f88  ldsfld   class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Common.XsdUtil::m_xsdResourceMappings
0x39f8d  ldstr    aComponentdefin// "/ComponentDefinition.xsd"
0x39f92  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x39f97  ldsfld   class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Common.XsdUtil::m_xsdResourceMappings
0x39f9c  ldstr    aMicrosoftRepor_148// "Microsoft.ReportingServices.ComponentLi"...
0x39fa1  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x39fa6  ldsfld   class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Common.XsdUtil::m_xsdResourceMappings
0x39fab  ldstr    aShareddatasetd// "/SharedDataSetDefinition.xsd"
0x39fb0  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x39fb5  ldsfld   class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Common.XsdUtil::m_xsdResourceMappings
0x39fba  ldstr    aMicrosoftRepor_149// "Microsoft.ReportingServices.SharedDataS"...
0x39fbf  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x39fc4  ret
```
