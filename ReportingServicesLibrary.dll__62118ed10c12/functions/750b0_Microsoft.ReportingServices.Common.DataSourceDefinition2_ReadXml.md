# Microsoft.ReportingServices.Common.DataSourceDefinition2::ReadXml

- ea: `0x750b0`
- end: `0x75398`
- name: `Microsoft.ReportingServices.Common.DataSourceDefinition2::ReadXml`
- size: `744`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x74ed0`
- `0x75460`

## callees

- `0x74d80`
- `0x74da0`
- `0x74dc0`
- `0x74de0`
- `0x74df0`
- `0x74e00`
- `0x74e20`
- `0x74e40`
- `0x74e60`
- `0x74e80`
- `0x74ea0`
- `0x74ec0`
- `0x750b0`
- `0x753a0`
- `0x756b0`
- `0x757c0`
- `0x757f0`
- `0x87790`

## string_xrefs

- `0x751b6`: `ImpersonateUser`
- `0x7521f`: `PowerBiModelLastUpdatedTime`

## pseudocode

```c

```

## disassembly

```asm
0x750b0  br       loc_7538C
0x750b5  ldarg.1
0x750b6  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x750bb  brtrue   loc_7538C
0x750c0  ldarg.1
0x750c1  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x750c6  ldc.i4.1
0x750c7  bne.un   loc_75370
0x750cc  ldarg.1
0x750cd  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x750d2  stloc.0
0x750d3  ldloc.0
0x750d4  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x750d9  stloc.1
0x750da  ldloc.1
0x750db  ldc.i4   0x233A3AB6
0x750e0  bgt.un.s loc_75128
0x750e2  ldloc.1
0x750e3  ldc.i4   0x14DAC5B5
0x750e8  bgt.un.s loc_75105
0x750ea  ldloc.1
0x750eb  ldc.i4   0x40718F7
0x750f0  beq      loc_751CA
0x750f5  ldloc.1
0x750f6  ldc.i4   0x14DAC5B5
0x750fb  beq      loc_751B5
0x75100  br       loc_75363
0x75105  ldloc.1
0x75106  ldc.i4   0x1CB892B4
0x7510b  beq.s    loc_75176
0x7510d  ldloc.1
0x7510e  ldc.i4   0x2083F13E
0x75113  beq      loc_75248
0x75118  ldloc.1
0x75119  ldc.i4   0x233A3AB6
0x7511e  beq      loc_751DF
0x75123  br       loc_75363
0x75128  ldloc.1
0x75129  ldc.i4   0xC6B46ED1
0x7512e  bgt.un.s loc_75153
0x75130  ldloc.1
0x75131  ldc.i4   0x59BAD0C2
0x75136  beq      loc_7521E
0x7513b  ldloc.1
0x7513c  ldc.i4   0xB5DAE4AC
0x75141  beq.s    loc_751A0
0x75143  ldloc.1
0x75144  ldc.i4   0xC6B46ED1
0x75149  beq      loc_75209
0x7514e  br       loc_75363
0x75153  ldloc.1
0x75154  ldc.i4   0xD163D79D
0x75159  beq      loc_751F4
0x7515e  ldloc.1
0x7515f  ldc.i4   0xF5713C74
0x75164  beq.s    loc_7518B
0x75166  ldloc.1
0x75167  ldc.i4   0xFBBF4687
0x7516c  beq      loc_75233
0x75171  br       loc_75363
0x75176  ldloc.0
0x75177  ldstr    aConnectstring// "ConnectString"
0x7517c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x75181  brtrue   loc_7525D
0x75186  br       loc_75363
0x7518b  ldloc.0
0x7518c  ldstr    aCredentialretr_0// "CredentialRetrieval"
0x75191  call     bool [mscorlib]System.String::op_Equality(string, string)
0x75196  brtrue   loc_75275
0x7519b  br       loc_75363
0x751a0  ldloc.0
0x751a1  ldstr    aWindowscredent// "WindowsCredentials"
0x751a6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x751ab  brtrue   loc_7528E
0x751b0  br       loc_75363
0x751b5  ldloc.0
0x751b6  ldstr    aImpersonateuse// "ImpersonateUser"
0x751bb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x751c0  brtrue   loc_752A6
0x751c5  br       loc_75363
0x751ca  ldloc.0
0x751cb  ldstr    aSecurestoreloo// "SecureStoreLookup"
0x751d0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x751d5  brtrue   loc_752BE
0x751da  br       loc_75363
0x751df  ldloc.0
0x751e0  ldstr    aPerspectivenam// "PerspectiveName"
0x751e5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x751ea  brtrue   loc_752DA
0x751ef  br       loc_75363
0x751f4  ldloc.0
0x751f5  ldstr    aOnpremiseident// "OnPremiseIdentity"
0x751fa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x751ff  brtrue   loc_752F2
0x75204  br       loc_75363
0x75209  ldloc.0
0x7520a  ldstr    aPowerbimodelid// "PowerBiModelId"
0x7520f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x75214  brtrue   loc_7530A
0x75219  br       loc_75363
0x7521e  ldloc.0
0x7521f  ldstr    aPowerbimodella// "PowerBiModelLastUpdatedTime"
0x75224  call     bool [mscorlib]System.String::op_Equality(string, string)
0x75229  brtrue   loc_7531F
0x7522e  br       loc_75363
0x75233  ldloc.0
0x75234  ldstr    aIsmultidimensi// "IsMultiDimensional"
0x75239  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7523e  brtrue   loc_75339
0x75243  br       loc_75363
0x75248  ldloc.0
0x75249  ldstr    aIsfullyformede// "IsFullyFormedExternalConnectionString"
0x7524e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x75253  brtrue   loc_7534E
0x75258  br       loc_75363
0x7525d  ldarg.1
0x7525e  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x75263  pop
0x75264  ldarg.0
0x75265  ldarg.1
0x75266  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadContentAsString()
0x7526b  call     instance void Microsoft.ReportingServices.Common.DataSourceDefinition2::set_ConnectString(string value)
0x75270  br       loc_7538C
0x75275  ldarg.1
0x75276  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x7527b  pop
0x7527c  ldarg.0
0x7527d  ldarg.0
0x7527e  ldarg.1
0x7527f  call     instance valuetype CredentialRetrievalTypes Microsoft.ReportingServices.Common.DataSourceDefinition2::ReadCredentialRetrieval(class [System.Xml]System.Xml.XmlReader reader)
0x75284  call     instance void Microsoft.ReportingServices.Common.DataSourceDefinition2::set_CredentialRetrieval(valuetype CredentialRetrievalTypes value)
0x75289  br       loc_7538C
0x7528e  ldarg.1
0x7528f  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x75294  pop
0x75295  ldarg.0
0x75296  ldarg.1
0x75297  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadContentAsBoolean()
0x7529c  call     instance void Microsoft.ReportingServices.Common.DataSourceDefinition2::set_WindowsCredentials(bool value)
0x752a1  br       loc_7538C
0x752a6  ldarg.1
0x752a7  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x752ac  pop
0x752ad  ldarg.0
0x752ae  ldarg.1
0x752af  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadContentAsBoolean()
0x752b4  call     instance void Microsoft.ReportingServices.Common.DataSourceDefinition2::set_ImpersonateUser(bool value)
0x752b9  br       loc_7538C
0x752be  ldarg.0
0x752bf  newobj   instance void Microsoft.ReportingServices.Common.SecureStoreLookup::.ctor()
0x752c4  call     instance void Microsoft.ReportingServices.Common.DataSourceDefinition2::set_SecureStoreLookup(class Microsoft.ReportingServices.Common.SecureStoreLookup value)
0x752c9  ldarg.0
0x752ca  call     instance class Microsoft.ReportingServices.Common.SecureStoreLookup Microsoft.ReportingServices.Common.DataSourceDefinition2::get_SecureStoreLookup()
0x752cf  ldarg.1
0x752d0  callvirt instance void Microsoft.ReportingServices.Common.SecureStoreLookup::ReadXml(class [System.Xml]System.Xml.XmlReader reader)
0x752d5  br       loc_7538C
0x752da  ldarg.1
0x752db  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x752e0  pop
0x752e1  ldarg.0
0x752e2  ldarg.1
0x752e3  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadContentAsString()
0x752e8  call     instance void Microsoft.ReportingServices.Common.DataSourceDefinition2::set_PerspectiveName(string value)
0x752ed  br       loc_7538C
0x752f2  ldarg.1
0x752f3  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x752f8  pop
0x752f9  ldarg.0
0x752fa  ldarg.1
0x752fb  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadContentAsString()
0x75300  call     instance void Microsoft.ReportingServices.Common.DataSourceDefinition2::set_OnPremiseModelIdentityClaims(string value)
0x75305  br       loc_7538C
0x7530a  ldarg.1
0x7530b  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x75310  pop
0x75311  ldarg.0
0x75312  ldarg.1
0x75313  callvirt instance int64 [System.Xml]System.Xml.XmlReader::ReadContentAsLong()
0x75318  call     instance void Microsoft.ReportingServices.Common.DataSourceDefinition2::set_PowerBIModelId(int64 value)
0x7531d  br.s     loc_7538C
0x7531f  ldarg.1
0x75320  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x75325  pop
0x75326  ldarg.0
0x75327  ldarg.1
0x75328  callvirt instance valuetype [mscorlib]System.DateTime [System.Xml]System.Xml.XmlReader::ReadContentAsDateTime()
0x7532d  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x75332  call     instance void Microsoft.ReportingServices.Common.DataSourceDefinition2::set_PowerBIModelLastUpdatedTime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x75337  br.s     loc_7538C
0x75339  ldarg.1
0x7533a  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x7533f  pop
0x75340  ldarg.0
0x75341  ldarg.1
0x75342  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadContentAsBoolean()
0x75347  call     instance void Microsoft.ReportingServices.Common.DataSourceDefinition2::set_IsMultiDimensional(bool value)
0x7534c  br.s     loc_7538C
0x7534e  ldarg.1
0x7534f  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x75354  pop
0x75355  ldarg.0
0x75356  ldarg.1
0x75357  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadContentAsBoolean()
0x7535c  call     instance void Microsoft.ReportingServices.Common.DataSourceDefinition2::set_IsFullyFormedExternalConnectionString(bool value)
0x75361  br.s     loc_7538C
0x75363  ldarg.1
0x75364  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x75369  call     void Microsoft.ReportingServices.Common.DSD2ErrorHandlingUtils::ThrowIfUnrecognizedElement(string elementName)
0x7536e  br.s     loc_7538C
0x75370  ldarg.1
0x75371  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x75376  ldc.i4.s 0xF
0x75378  bne.un.s loc_7538C
0x7537a  ldarg.1
0x7537b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x75380  ldstr    aDatasourcedefi_2// "DataSourceDefinition2"
0x75385  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7538a  brtrue.s loc_75397
0x7538c  ldarg.1
0x7538d  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x75392  brtrue   loc_750B5
0x75397  ret
```
