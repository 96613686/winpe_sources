# Microsoft.ReportingServices.DataExtensions.DataSourceInfo::GetXmlBytes

- ea: `0x1703d0`
- end: `0x170505`
- name: `Microsoft.ReportingServices.DataExtensions.DataSourceInfo::GetXmlBytes`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x16fcc0`
- `0x16fd20`
- `0x16fec0`
- `0x16fee0`
- `0x16ff20`
- `0x16ff40`
- `0x170190`
- `0x1703d0`

## string_xrefs

- `0x170409`: `Extension`
- `0x1704af`: `ImpersonateUser`
- `0x1703fe`: `http://schemas.microsoft.com/sqlserver/reporting/2006/03/reportdatasource`

## pseudocode

```c

```

## disassembly

```asm
0x1703d0  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x1703d5  stloc.0
0x1703d6  ldloc.0
0x1703d7  ldc.i4.1
0x1703d8  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x1703dd  ldloc.0
0x1703de  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x1703e3  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Encoding(class [mscorlib]System.Text.Encoding)
0x1703e8  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x1703ed  stloc.1
0x1703ee  ldloc.1
0x1703ef  ldloc.0
0x1703f0  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.Stream, class [System.Xml]System.Xml.XmlWriterSettings)
0x1703f5  stloc.2
0x1703f6  ldloc.2
0x1703f7  stloc.3
0x1703f8  ldloc.2
0x1703f9  ldstr    aDatasourcedefi// "DataSourceDefinition"
0x1703fe  ldstr    aHttpSchemasMic_15// "http://schemas.microsoft.com/sqlserver/"...
0x170403  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x170408  ldloc.2
0x170409  ldstr    aExtension_0// "Extension"
0x17040e  ldarg.0
0x17040f  call     instance string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Extension()
0x170414  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x170419  ldloc.2
0x17041a  ldstr    aConnectstring// "ConnectString"
0x17041f  ldarg.0
0x170420  ldarg.1
0x170421  call     instance string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::GetConnectionString(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection dataProtection)
0x170426  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x17042b  ldloc.2
0x17042c  ldstr    aCredentialretr// "CredentialRetrieval"
0x170431  ldarg.0
0x170432  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x170437  stloc.s  4
0x170439  ldloca.s 4
0x17043b  constrained. CredentialsRetrievalOption
0x170441  callvirt instance string [mscorlib]System.Object::ToString()
0x170446  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x17044b  ldarg.0
0x17044c  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x170451  ldc.i4.1
0x170452  beq.s    loc_17045D
0x170454  ldarg.0
0x170455  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x17045a  ldc.i4.2
0x17045b  bne.un.s loc_170477
0x17045d  ldloc.2
0x17045e  ldstr    aWindowscredent// "WindowsCredentials"
0x170463  ldarg.0
0x170464  call     instance bool Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_WindowsCredentials()
0x170469  stloc.s  5
0x17046b  ldloca.s 5
0x17046d  call     instance string [mscorlib]System.Boolean::ToString()
0x170472  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x170477  ldarg.0
0x170478  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x17047d  ldc.i4.1
0x17047e  bne.un.s loc_1704A5
0x170480  ldloc.2
0x170481  ldstr    aPrompt// "Prompt"
0x170486  ldarg.0
0x170487  call     instance string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Prompt()
0x17048c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x170491  brtrue.s loc_17049B
0x170493  ldarg.0
0x170494  call     instance string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Prompt()
0x170499  br.s     loc_1704A0
0x17049b  ldstr    asc_27B730// ""
0x1704a0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1704a5  ldarg.0
0x1704a6  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x1704ab  ldc.i4.2
0x1704ac  bne.un.s loc_1704C8
0x1704ae  ldloc.2
0x1704af  ldstr    aImpersonateuse// "ImpersonateUser"
0x1704b4  ldarg.0
0x1704b5  call     instance bool Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_ImpersonateUser()
0x1704ba  stloc.s  5
0x1704bc  ldloca.s 5
0x1704be  call     instance string [mscorlib]System.Boolean::ToString()
0x1704c3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1704c8  ldloc.2
0x1704c9  ldstr    aEnabled// "Enabled"
0x1704ce  ldarg.0
0x1704cf  call     instance bool Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Enabled()
0x1704d4  stloc.s  5
0x1704d6  ldloca.s 5
0x1704d8  call     instance string [mscorlib]System.Boolean::ToString()
0x1704dd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1704e2  ldloc.2
0x1704e3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1704e8  ldloc.2
0x1704e9  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1704ee  ldloc.1
0x1704ef  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x1704f4  stloc.s  6
0x1704f6  leave.s  loc_170502
0x1704f8  ldloc.3
0x1704f9  brfalse.s loc_170501
0x1704fb  ldloc.3
0x1704fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x170501  endfinally
0x170502  ldloc.s  6
0x170504  ret
```
