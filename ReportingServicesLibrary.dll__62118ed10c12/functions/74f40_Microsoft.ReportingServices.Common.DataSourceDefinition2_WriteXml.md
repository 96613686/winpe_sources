# Microsoft.ReportingServices.Common.DataSourceDefinition2::WriteXml

- ea: `0x74f40`
- end: `0x75096`
- name: `Microsoft.ReportingServices.Common.DataSourceDefinition2::WriteXml`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x754a0`

## callees

- `0x74d70`
- `0x74d90`
- `0x74db0`
- `0x74dd0`
- `0x74df0`
- `0x74e10`
- `0x74e30`
- `0x74e50`
- `0x74e70`
- `0x74e90`
- `0x74eb0`
- `0x74f40`
- `0x75770`

## string_xrefs

- `0x74fa2`: `ImpersonateUser`
- `0x7502f`: `PowerBiModelLastUpdatedTime`

## pseudocode

```c

```

## disassembly

```asm
0x74f40  ldarg.1
0x74f41  ldstr    aDatasourcedefi_2// "DataSourceDefinition2"
0x74f46  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x74f4b  ldarg.0
0x74f4c  call     instance string Microsoft.ReportingServices.Common.DataSourceDefinition2::get_ConnectString()
0x74f51  brfalse.s loc_74F64
0x74f53  ldarg.1
0x74f54  ldstr    aConnectstring// "ConnectString"
0x74f59  ldarg.0
0x74f5a  call     instance string Microsoft.ReportingServices.Common.DataSourceDefinition2::get_ConnectString()
0x74f5f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x74f64  ldarg.0
0x74f65  call     instance valuetype CredentialRetrievalTypes Microsoft.ReportingServices.Common.DataSourceDefinition2::get_CredentialRetrieval()
0x74f6a  brfalse.s loc_74F8B
0x74f6c  ldarg.1
0x74f6d  ldstr    aCredentialretr_0// "CredentialRetrieval"
0x74f72  ldarg.0
0x74f73  call     instance valuetype CredentialRetrievalTypes Microsoft.ReportingServices.Common.DataSourceDefinition2::get_CredentialRetrieval()
0x74f78  stloc.0
0x74f79  ldloca.s 0
0x74f7b  constrained. CredentialRetrievalTypes
0x74f81  callvirt instance string [mscorlib]System.Object::ToString()
0x74f86  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x74f8b  ldarg.1
0x74f8c  ldstr    aWindowscredent// "WindowsCredentials"
0x74f91  ldarg.0
0x74f92  call     instance bool Microsoft.ReportingServices.Common.DataSourceDefinition2::get_WindowsCredentials()
0x74f97  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x74f9c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x74fa1  ldarg.1
0x74fa2  ldstr    aImpersonateuse// "ImpersonateUser"
0x74fa7  ldarg.0
0x74fa8  call     instance bool Microsoft.ReportingServices.Common.DataSourceDefinition2::get_ImpersonateUser()
0x74fad  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x74fb2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x74fb7  ldarg.0
0x74fb8  call     instance class Microsoft.ReportingServices.Common.SecureStoreLookup Microsoft.ReportingServices.Common.DataSourceDefinition2::get_SecureStoreLookup()
0x74fbd  brfalse.s loc_74FCB
0x74fbf  ldarg.0
0x74fc0  call     instance class Microsoft.ReportingServices.Common.SecureStoreLookup Microsoft.ReportingServices.Common.DataSourceDefinition2::get_SecureStoreLookup()
0x74fc5  ldarg.1
0x74fc6  callvirt instance void Microsoft.ReportingServices.Common.SecureStoreLookup::WriteXml(class [System.Xml]System.Xml.XmlWriter writer)
0x74fcb  ldarg.0
0x74fcc  call     instance string Microsoft.ReportingServices.Common.DataSourceDefinition2::get_PerspectiveName()
0x74fd1  brfalse.s loc_74FE4
0x74fd3  ldarg.1
0x74fd4  ldstr    aPerspectivenam// "PerspectiveName"
0x74fd9  ldarg.0
0x74fda  call     instance string Microsoft.ReportingServices.Common.DataSourceDefinition2::get_PerspectiveName()
0x74fdf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x74fe4  ldarg.0
0x74fe5  call     instance string Microsoft.ReportingServices.Common.DataSourceDefinition2::get_OnPremiseModelIdentityClaims()
0x74fea  brfalse.s loc_74FFD
0x74fec  ldarg.1
0x74fed  ldstr    aOnpremiseident// "OnPremiseIdentity"
0x74ff2  ldarg.0
0x74ff3  call     instance string Microsoft.ReportingServices.Common.DataSourceDefinition2::get_OnPremiseModelIdentityClaims()
0x74ff8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x74ffd  ldarg.0
0x74ffe  call     instance int64 Microsoft.ReportingServices.Common.DataSourceDefinition2::get_PowerBIModelId()
0x75003  brfalse.s loc_7501E
0x75005  ldarg.1
0x75006  ldstr    aPowerbimodelid// "PowerBiModelId"
0x7500b  ldarg.0
0x7500c  call     instance int64 Microsoft.ReportingServices.Common.DataSourceDefinition2::get_PowerBIModelId()
0x75011  stloc.1
0x75012  ldloca.s 1
0x75014  call     instance string [mscorlib]System.Int64::ToString()
0x75019  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7501e  ldarg.0
0x7501f  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.ReportingServices.Common.DataSourceDefinition2::get_PowerBIModelLastUpdatedTime()
0x75024  stloc.2
0x75025  ldloca.s 2
0x75027  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x7502c  brfalse.s loc_75053
0x7502e  ldarg.1
0x7502f  ldstr    aPowerbimodella// "PowerBiModelLastUpdatedTime"
0x75034  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x75039  ldarg.1
0x7503a  ldarg.0
0x7503b  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.ReportingServices.Common.DataSourceDefinition2::get_PowerBIModelLastUpdatedTime()
0x75040  stloc.2
0x75041  ldloca.s 2
0x75043  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x75048  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(valuetype [mscorlib]System.DateTime)
0x7504d  ldarg.1
0x7504e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x75053  ldarg.0
0x75054  call     instance bool Microsoft.ReportingServices.Common.DataSourceDefinition2::get_IsMultiDimensional()
0x75059  brfalse.s loc_75071
0x7505b  ldarg.1
0x7505c  ldstr    aIsmultidimensi// "IsMultiDimensional"
0x75061  ldarg.0
0x75062  call     instance bool Microsoft.ReportingServices.Common.DataSourceDefinition2::get_IsMultiDimensional()
0x75067  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x7506c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x75071  ldarg.0
0x75072  call     instance bool Microsoft.ReportingServices.Common.DataSourceDefinition2::get_IsFullyFormedExternalConnectionString()
0x75077  brfalse.s loc_7508F
0x75079  ldarg.1
0x7507a  ldstr    aIsfullyformede// "IsFullyFormedExternalConnectionString"
0x7507f  ldarg.0
0x75080  call     instance bool Microsoft.ReportingServices.Common.DataSourceDefinition2::get_IsFullyFormedExternalConnectionString()
0x75085  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x7508a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7508f  ldarg.1
0x75090  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x75095  ret
```
