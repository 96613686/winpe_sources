# Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::WriteToXml

- ea: `0x70080`
- end: `0x701dd`
- name: `Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::WriteToXml`
- size: `349`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x70050`
- `0x702c0`

## callees

- `0x70080`

## string_xrefs

- `0x70094`: `Extension`
- `0x70171`: `ImpersonateUser`

## pseudocode

```c

```

## disassembly

```asm
0x70080  ldarg.1
0x70081  ldstr    aDatasourcedefi// "DataSourceDefinition"
0x70086  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x7008b  ldarg.0
0x7008c  ldfld    string Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Extension
0x70091  brfalse.s loc_700A4
0x70093  ldarg.1
0x70094  ldstr    aExtension_0// "Extension"
0x70099  ldarg.0
0x7009a  ldfld    string Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Extension
0x7009f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x700a4  ldarg.0
0x700a5  ldfld    string Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::ConnectString
0x700aa  brfalse.s loc_700BD
0x700ac  ldarg.1
0x700ad  ldstr    aConnectstring// "ConnectString"
0x700b2  ldarg.0
0x700b3  ldfld    string Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::ConnectString
0x700b8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x700bd  ldarg.1
0x700be  ldstr    aUseoriginalcon// "UseOriginalConnectString"
0x700c3  ldarg.0
0x700c4  ldfld    bool Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::UseOriginalConnectString
0x700c9  brtrue.s loc_700D2
0x700cb  ldstr    aFalse// "False"
0x700d0  br.s     loc_700D7
0x700d2  ldstr    aTrue_0// "True"
0x700d7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x700dc  ldarg.1
0x700dd  ldstr    aOriginalconnec_2// "OriginalConnectStringExpressionBased"
0x700e2  ldarg.0
0x700e3  ldfld    bool Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::OriginalConnectStringExpressionBased
0x700e8  brtrue.s loc_700F1
0x700ea  ldstr    aFalse// "False"
0x700ef  br.s     loc_700F6
0x700f1  ldstr    aTrue_0// "True"
0x700f6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x700fb  ldarg.1
0x700fc  ldstr    aCredentialretr_0// "CredentialRetrieval"
0x70101  ldarg.0
0x70102  ldflda   valuetype Microsoft.ReportingServices.Library.Soap.CredentialRetrievalEnum Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::CredentialRetrieval
0x70107  constrained. Microsoft.ReportingServices.Library.Soap.CredentialRetrievalEnum
0x7010d  callvirt instance string [mscorlib]System.Object::ToString()
0x70112  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x70117  ldarg.0
0x70118  ldfld    valuetype Microsoft.ReportingServices.Library.Soap.CredentialRetrievalEnum Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::CredentialRetrieval
0x7011d  brfalse.s loc_70128
0x7011f  ldarg.0
0x70120  ldfld    valuetype Microsoft.ReportingServices.Library.Soap.CredentialRetrievalEnum Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::CredentialRetrieval
0x70125  ldc.i4.1
0x70126  bne.un.s loc_7013E
0x70128  ldarg.1
0x70129  ldstr    aWindowscredent// "WindowsCredentials"
0x7012e  ldarg.0
0x7012f  ldflda   bool Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::WindowsCredentials
0x70134  call     instance string [mscorlib]System.Boolean::ToString()
0x70139  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7013e  ldarg.0
0x7013f  ldfld    string Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Prompt
0x70144  brfalse.s loc_7015F
0x70146  ldarg.0
0x70147  ldfld    valuetype Microsoft.ReportingServices.Library.Soap.CredentialRetrievalEnum Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::CredentialRetrieval
0x7014c  brtrue.s loc_7015F
0x7014e  ldarg.1
0x7014f  ldstr    aPrompt_0// "Prompt"
0x70154  ldarg.0
0x70155  ldfld    string Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Prompt
0x7015a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7015f  ldarg.0
0x70160  ldfld    valuetype Microsoft.ReportingServices.Library.Soap.CredentialRetrievalEnum Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::CredentialRetrieval
0x70165  ldc.i4.1
0x70166  bne.un.s loc_701B8
0x70168  ldarg.0
0x70169  ldfld    bool Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::ImpersonateUserSpecified
0x7016e  brfalse.s loc_70186
0x70170  ldarg.1
0x70171  ldstr    aImpersonateuse// "ImpersonateUser"
0x70176  ldarg.0
0x70177  ldflda   bool Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::ImpersonateUser
0x7017c  call     instance string [mscorlib]System.Boolean::ToString()
0x70181  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x70186  ldarg.0
0x70187  ldfld    string Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::UserName
0x7018c  brfalse.s loc_7019F
0x7018e  ldarg.1
0x7018f  ldstr    aUsername// "UserName"
0x70194  ldarg.0
0x70195  ldfld    string Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::UserName
0x7019a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7019f  ldarg.0
0x701a0  ldfld    string Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Password
0x701a5  brfalse.s loc_701B8
0x701a7  ldarg.1
0x701a8  ldstr    aPassword// "Password"
0x701ad  ldarg.0
0x701ae  ldfld    string Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Password
0x701b3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x701b8  ldarg.0
0x701b9  ldfld    bool Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::EnabledSpecified
0x701be  brfalse.s loc_701D6
0x701c0  ldarg.1
0x701c1  ldstr    aEnabled// "Enabled"
0x701c6  ldarg.0
0x701c7  ldflda   bool Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Enabled
0x701cc  call     instance string [mscorlib]System.Boolean::ToString()
0x701d1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x701d6  ldarg.1
0x701d7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x701dc  ret
```
