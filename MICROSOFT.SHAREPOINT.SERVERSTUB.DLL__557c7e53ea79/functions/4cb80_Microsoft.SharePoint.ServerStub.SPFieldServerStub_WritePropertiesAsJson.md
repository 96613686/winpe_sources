# Microsoft.SharePoint.ServerStub.SPFieldServerStub::WritePropertiesAsJson

- ea: `0x4cb80`
- end: `0x4d383`
- name: `Microsoft.SharePoint.ServerStub.SPFieldServerStub::WritePropertiesAsJson`
- size: `2051`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x4e350`
- `0x4ea30`
- `0x4fcf0`
- `0x508a0`
- `0x51270`
- `0x53bf0`
- `0x54820`
- `0x55e90`
- `0x56240`

## callees

- `0x4cb80`

## string_xrefs

- `0x4d091`: `SchemaXml`
- `0x4d09d`: `SchemaXml`
- `0x4d0a8`: `SchemaXml`
- `0x4d0c0`: `SchemaXml`
- `0x4cfa9`: `JSLink`
- `0x4cfb5`: `JSLink`
- `0x4cfc0`: `JSLink`
- `0x4cfd8`: `JSLink`
- `0x4cc09`: `ClientSideComponentId`
- `0x4cc15`: `ClientSideComponentId`
- `0x4cc20`: `ClientSideComponentId`
- `0x4cc38`: `ClientSideComponentId`
- `0x4cc43`: `ClientSideComponentProperties`
- `0x4cc4f`: `ClientSideComponentProperties`
- `0x4cc5a`: `ClientSideComponentProperties`
- `0x4cc72`: `ClientSideComponentProperties`
- `0x4cbcf`: `CanBeDeleted`
- `0x4cbdb`: `CanBeDeleted`
- `0x4cbe6`: `CanBeDeleted`
- `0x4cbfe`: `CanBeDeleted`
- `0x4d01d`: `ReadOnlyField`
- `0x4d029`: `ReadOnlyField`
- `0x4d034`: `ReadOnlyField`
- `0x4d04c`: `ReadOnlyField`

## pseudocode

```c

```

## disassembly

```asm
0x4cb80  ldarg.2
0x4cb81  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPField
0x4cb86  stloc.0
0x4cb87  ldloc.0
0x4cb88  brtrue.s loc_4CB8B
0x4cb8a  ret
0x4cb8b  ldarg.0
0x4cb8c  ldarg.1
0x4cb8d  ldarg.2
0x4cb8e  ldarg.3
0x4cb8f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cb94  ldarg.0
0x4cb95  ldstr    aAutoindexed// "AutoIndexed"
0x4cb9a  ldarg.3
0x4cb9b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cba0  ldarg.1
0x4cba1  ldstr    aAutoindexed// "AutoIndexed"
0x4cba6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4cbab  ldarg.3
0x4cbac  ldstr    aAutoindexed// "AutoIndexed"
0x4cbb1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cbb6  ldarg.1
0x4cbb7  ldloc.0
0x4cbb8  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_AutoIndexed()
0x4cbbd  ldarg.3
0x4cbbe  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cbc3  ldarg.3
0x4cbc4  ldstr    aAutoindexed// "AutoIndexed"
0x4cbc9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4cbce  ldarg.0
0x4cbcf  ldstr    aCanbedeleted// "CanBeDeleted"
0x4cbd4  ldarg.3
0x4cbd5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cbda  ldarg.1
0x4cbdb  ldstr    aCanbedeleted// "CanBeDeleted"
0x4cbe0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4cbe5  ldarg.3
0x4cbe6  ldstr    aCanbedeleted// "CanBeDeleted"
0x4cbeb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cbf0  ldarg.1
0x4cbf1  ldloc.0
0x4cbf2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_CanBeDeleted()
0x4cbf7  ldarg.3
0x4cbf8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cbfd  ldarg.3
0x4cbfe  ldstr    aCanbedeleted// "CanBeDeleted"
0x4cc03  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4cc08  ldarg.0
0x4cc09  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4cc0e  ldarg.3
0x4cc0f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cc14  ldarg.1
0x4cc15  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4cc1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4cc1f  ldarg.3
0x4cc20  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4cc25  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cc2a  ldarg.1
0x4cc2b  ldloc.0
0x4cc2c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_ClientSideComponentId()
0x4cc31  ldarg.3
0x4cc32  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cc37  ldarg.3
0x4cc38  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4cc3d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4cc42  ldarg.0
0x4cc43  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4cc48  ldarg.3
0x4cc49  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cc4e  ldarg.1
0x4cc4f  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4cc54  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4cc59  ldarg.3
0x4cc5a  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4cc5f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cc64  ldarg.1
0x4cc65  ldloc.0
0x4cc66  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_ClientSideComponentProperties()
0x4cc6b  ldarg.3
0x4cc6c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cc71  ldarg.3
0x4cc72  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4cc77  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4cc7c  ldarg.0
0x4cc7d  ldstr    aCustomformatte// "CustomFormatter"
0x4cc82  ldarg.3
0x4cc83  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cc88  ldarg.1
0x4cc89  ldstr    aCustomformatte// "CustomFormatter"
0x4cc8e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4cc93  ldarg.3
0x4cc94  ldstr    aCustomformatte// "CustomFormatter"
0x4cc99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cc9e  ldarg.1
0x4cc9f  ldloc.0
0x4cca0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_CustomFormatter()
0x4cca5  ldarg.3
0x4cca6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ccab  ldarg.3
0x4ccac  ldstr    aCustomformatte// "CustomFormatter"
0x4ccb1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4ccb6  ldarg.0
0x4ccb7  ldstr    aDefaultformula// "DefaultFormula"
0x4ccbc  ldarg.3
0x4ccbd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ccc2  ldarg.1
0x4ccc3  ldstr    aDefaultformula// "DefaultFormula"
0x4ccc8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4cccd  ldarg.3
0x4ccce  ldstr    aDefaultformula// "DefaultFormula"
0x4ccd3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4ccd8  ldarg.1
0x4ccd9  ldloc.0
0x4ccda  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_DefaultFormula()
0x4ccdf  ldarg.3
0x4cce0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cce5  ldarg.3
0x4cce6  ldstr    aDefaultformula// "DefaultFormula"
0x4cceb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4ccf0  ldarg.0
0x4ccf1  ldstr    aDefaultvalue// "DefaultValue"
0x4ccf6  ldarg.3
0x4ccf7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ccfc  ldarg.1
0x4ccfd  ldstr    aDefaultvalue// "DefaultValue"
0x4cd02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4cd07  ldarg.3
0x4cd08  ldstr    aDefaultvalue// "DefaultValue"
0x4cd0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cd12  ldarg.1
0x4cd13  ldloc.0
0x4cd14  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_DefaultValue()
0x4cd19  ldarg.3
0x4cd1a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cd1f  ldarg.3
0x4cd20  ldstr    aDefaultvalue// "DefaultValue"
0x4cd25  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4cd2a  ldarg.0
0x4cd2b  ldstr    aDescription// "Description"
0x4cd30  ldarg.3
0x4cd31  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cd36  ldarg.1
0x4cd37  ldstr    aDescription// "Description"
0x4cd3c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4cd41  ldarg.3
0x4cd42  ldstr    aDescription// "Description"
0x4cd47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cd4c  ldarg.1
0x4cd4d  ldloc.0
0x4cd4e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Description()
0x4cd53  ldarg.3
0x4cd54  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cd59  ldarg.3
0x4cd5a  ldstr    aDescription// "Description"
0x4cd5f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4cd64  ldarg.0
0x4cd65  ldstr    aDirection// "Direction"
0x4cd6a  ldarg.3
0x4cd6b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cd70  ldarg.1
0x4cd71  ldstr    aDirection// "Direction"
0x4cd76  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4cd7b  ldarg.3
0x4cd7c  ldstr    aDirection// "Direction"
0x4cd81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cd86  ldarg.1
0x4cd87  ldloc.0
0x4cd88  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Direction()
0x4cd8d  ldarg.3
0x4cd8e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cd93  ldarg.3
0x4cd94  ldstr    aDirection// "Direction"
0x4cd99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4cd9e  ldarg.0
0x4cd9f  ldstr    aEnforceuniquev// "EnforceUniqueValues"
0x4cda4  ldarg.3
0x4cda5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cdaa  ldarg.1
0x4cdab  ldstr    aEnforceuniquev// "EnforceUniqueValues"
0x4cdb0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4cdb5  ldarg.3
0x4cdb6  ldstr    aEnforceuniquev// "EnforceUniqueValues"
0x4cdbb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cdc0  ldarg.1
0x4cdc1  ldloc.0
0x4cdc2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_EnforceUniqueValues()
0x4cdc7  ldarg.3
0x4cdc8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cdcd  ldarg.3
0x4cdce  ldstr    aEnforceuniquev// "EnforceUniqueValues"
0x4cdd3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4cdd8  ldarg.0
0x4cdd9  ldstr    aEntityproperty// "EntityPropertyName"
0x4cdde  ldarg.3
0x4cddf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cde4  ldarg.1
0x4cde5  ldstr    aEntityproperty// "EntityPropertyName"
0x4cdea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4cdef  ldarg.3
0x4cdf0  ldstr    aEntityproperty// "EntityPropertyName"
0x4cdf5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cdfa  ldarg.1
0x4cdfb  ldloc.0
0x4cdfc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_EntityPropertyName()
0x4ce01  ldarg.3
0x4ce02  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ce07  ldarg.3
0x4ce08  ldstr    aEntityproperty// "EntityPropertyName"
0x4ce0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4ce12  ldarg.0
0x4ce13  ldstr    aFilterable// "Filterable"
0x4ce18  ldarg.3
0x4ce19  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ce1e  ldarg.1
0x4ce1f  ldstr    aFilterable// "Filterable"
0x4ce24  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4ce29  ldarg.3
0x4ce2a  ldstr    aFilterable// "Filterable"
0x4ce2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4ce34  ldarg.1
0x4ce35  ldloc.0
0x4ce36  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Filterable()
0x4ce3b  ldarg.3
0x4ce3c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ce41  ldarg.3
0x4ce42  ldstr    aFilterable// "Filterable"
0x4ce47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4ce4c  ldarg.0
0x4ce4d  ldstr    aFrombasetype// "FromBaseType"
0x4ce52  ldarg.3
0x4ce53  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ce58  ldarg.1
0x4ce59  ldstr    aFrombasetype// "FromBaseType"
0x4ce5e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4ce63  ldarg.3
0x4ce64  ldstr    aFrombasetype// "FromBaseType"
0x4ce69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4ce6e  ldarg.1
0x4ce6f  ldloc.0
0x4ce70  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_FromBaseType()
0x4ce75  ldarg.3
0x4ce76  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ce7b  ldarg.3
0x4ce7c  ldstr    aFrombasetype// "FromBaseType"
0x4ce81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4ce86  ldarg.0
0x4ce87  ldstr    aGroup// "Group"
0x4ce8c  ldarg.3
0x4ce8d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ce92  ldarg.1
0x4ce93  ldstr    aGroup// "Group"
0x4ce98  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4ce9d  ldarg.3
0x4ce9e  ldstr    aGroup// "Group"
0x4cea3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cea8  ldarg.1
0x4cea9  ldloc.0
0x4ceaa  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Group()
0x4ceaf  ldarg.3
0x4ceb0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ceb5  ldarg.3
0x4ceb6  ldstr    aGroup// "Group"
0x4cebb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4cec0  ldarg.0
0x4cec1  ldstr    aHidden// "Hidden"
0x4cec6  ldarg.3
0x4cec7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cecc  ldarg.1
0x4cecd  ldstr    aHidden// "Hidden"
0x4ced2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4ced7  ldarg.3
0x4ced8  ldstr    aHidden// "Hidden"
0x4cedd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cee2  ldarg.1
0x4cee3  ldloc.0
0x4cee4  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Hidden()
0x4cee9  ldarg.3
0x4ceea  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ceef  ldarg.3
0x4cef0  ldstr    aHidden// "Hidden"
0x4cef5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4cefa  ldarg.0
0x4cefb  ldstr    aId_0// "Id"
0x4cf00  ldarg.3
0x4cf01  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cf06  ldarg.1
0x4cf07  ldstr    aId_0// "Id"
0x4cf0c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4cf11  ldarg.3
0x4cf12  ldstr    aId_0// "Id"
0x4cf17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4cf1c  ldarg.1
0x4cf1d  ldloc.0
0x4cf1e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Id()
0x4cf23  ldarg.3
0x4cf24  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4cf29  ldarg.3
0x4cf2a  ldstr    aId_0// "Id"
0x4cf2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4cf34  ldarg.0
  ... truncated ...
```
