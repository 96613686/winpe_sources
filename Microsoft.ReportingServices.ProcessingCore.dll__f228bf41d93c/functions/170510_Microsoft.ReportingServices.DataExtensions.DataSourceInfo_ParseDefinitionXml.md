# Microsoft.ReportingServices.DataExtensions.DataSourceInfo::ParseDefinitionXml

- ea: `0x170510`
- end: `0x1707cb`
- name: `Microsoft.ReportingServices.DataExtensions.DataSourceInfo::ParseDefinitionXml`
- size: `699`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1707d0`

## callees

- `0x16fcd0`
- `0x16fd60`
- `0x16fef0`
- `0x16ff50`
- `0x16ffb0`
- `0x1700c0`
- `0x1701a0`
- `0x170510`

## string_xrefs

- `0x1705c8`: `Extension`
- `0x170646`: `ImpersonateUser`
- `0x170739`: `ImpersonateUser`

## pseudocode

```c

```

## disassembly

```asm
0x170510  ldarg.1
0x170511  brtrue.s loc_170519
0x170513  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0x170518  throw
0x170519  ldnull
0x17051a  stloc.0
0x17051b  ldc.i4.0
0x17051c  stloc.1
0x17051d  ldarg.1
0x17051e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x170523  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x170528  stloc.2
0x170529  br       loc_170786
0x17052e  ldloc.2
0x17052f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x170534  castclass [System.Xml]System.Xml.XmlNode
0x170539  dup
0x17053a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x17053f  stloc.3
0x170540  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x170545  stloc.s  4
0x170547  ldloc.3
0x170548  brfalse  loc_170780
0x17054d  ldloc.3
0x17054e  call     instance int32 [mscorlib]System.String::get_Length()
0x170553  stloc.s  5
0x170555  ldloc.s  5
0x170557  ldc.i4.6
0x170558  sub
0x170559  switch   loc_17065A, loc_170699, loc_1705A7, loc_1705C7, loc_170780, loc_170780, loc_170780, loc_1705DC, loc_170780, loc_170645, loc_170780, loc_170780, loc_170630, loc_17061B
0x170596  ldloc.s  5
0x170598  ldc.i4.s 0x18
0x17059a  beq.s    loc_1705F1
0x17059c  ldloc.s  5
0x17059e  ldc.i4.s 0x24
0x1705a0  beq.s    loc_170606
0x1705a2  br       loc_170780
0x1705a7  ldloc.3
0x1705a8  ldc.i4.0
0x1705a9  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1705ae  stloc.s  6
0x1705b0  ldloc.s  6
0x1705b2  ldc.i4.s 0x50
0x1705b4  beq      loc_170684
0x1705b9  ldloc.s  6
0x1705bb  ldc.i4.s 0x55
0x1705bd  beq      loc_17066F
0x1705c2  br       loc_170780
0x1705c7  ldloc.3
0x1705c8  ldstr    aExtension_0// "Extension"
0x1705cd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1705d2  brtrue   loc_1706AE
0x1705d7  br       loc_170780
0x1705dc  ldloc.3
0x1705dd  ldstr    aConnectstring// "ConnectString"
0x1705e2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1705e7  brtrue   loc_1706BB
0x1705ec  br       loc_170780
0x1705f1  ldloc.3
0x1705f2  ldstr    aUseoriginalcon// "UseOriginalConnectString"
0x1705f7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1705fc  brtrue   loc_1706C3
0x170601  br       loc_170780
0x170606  ldloc.3
0x170607  ldstr    aOriginalconnec_2// "OriginalConnectStringExpressionBased"
0x17060c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x170611  brtrue   loc_170786
0x170616  br       loc_170780
0x17061b  ldloc.3
0x17061c  ldstr    aCredentialretr// "CredentialRetrieval"
0x170621  call     bool [mscorlib]System.String::op_Equality(string, string)
0x170626  brtrue   loc_1706DD
0x17062b  br       loc_170780
0x170630  ldloc.3
0x170631  ldstr    aWindowscredent// "WindowsCredentials"
0x170636  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17063b  brtrue   loc_17070C
0x170640  br       loc_170780
0x170645  ldloc.3
0x170646  ldstr    aImpersonateuse// "ImpersonateUser"
0x17064b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x170650  brtrue   loc_170728
0x170655  br       loc_170780
0x17065a  ldloc.3
0x17065b  ldstr    aPrompt// "Prompt"
0x170660  call     bool [mscorlib]System.String::op_Equality(string, string)
0x170665  brtrue   loc_170744
0x17066a  br       loc_170780
0x17066f  ldloc.3
0x170670  ldstr    aUsername// "UserName"
0x170675  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17067a  brtrue   loc_17074E
0x17067f  br       loc_170780
0x170684  ldloc.3
0x170685  ldstr    aPassword// "Password"
0x17068a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17068f  brtrue   loc_170759
0x170694  br       loc_170780
0x170699  ldloc.3
0x17069a  ldstr    aEnabled// "Enabled"
0x17069f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1706a4  brtrue   loc_170764
0x1706a9  br       loc_170780
0x1706ae  ldarg.0
0x1706af  ldloc.s  4
0x1706b1  call     instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::set_Extension(string value)
0x1706b6  br       loc_170786
0x1706bb  ldloc.s  4
0x1706bd  stloc.0
0x1706be  br       loc_170786
0x1706c3  nop
0x1706c4  ldloc.s  4
0x1706c6  call     bool [mscorlib]System.Boolean::Parse(string)
0x1706cb  stloc.1
0x1706cc  leave    loc_170786
0x1706d1  pop
0x1706d2  ldstr    aUseoriginalcon// "UseOriginalConnectString"
0x1706d7  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ElementTypeMismatchException::.ctor(string)
0x1706dc  throw
0x1706dd  nop
0x1706de  ldarg.0
0x1706df  ldtoken  CredentialsRetrievalOption
0x1706e4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1706e9  ldloc.s  4
0x1706eb  ldc.i4.1
0x1706ec  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x1706f1  unbox.any CredentialsRetrievalOption
0x1706f6  stfld    valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_credentialsRetrieval
0x1706fb  leave    loc_170786
0x170700  pop
0x170701  ldstr    aCredentialretr// "CredentialRetrieval"
0x170706  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ElementTypeMismatchException::.ctor(string)
0x17070b  throw
0x17070c  nop
0x17070d  ldarg.0
0x17070e  ldloc.s  4
0x170710  call     bool [mscorlib]System.Boolean::Parse(string)
0x170715  call     instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::set_WindowsCredentials(bool value)
0x17071a  leave.s  loc_170786
0x17071c  pop
0x17071d  ldstr    aWindowscredent// "WindowsCredentials"
0x170722  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ElementTypeMismatchException::.ctor(string)
0x170727  throw
0x170728  nop
0x170729  ldarg.0
0x17072a  ldloc.s  4
0x17072c  call     bool [mscorlib]System.Boolean::Parse(string)
0x170731  call     instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::set_ImpersonateUser(bool value)
0x170736  leave.s  loc_170786
0x170738  pop
0x170739  ldstr    aImpersonateuse// "ImpersonateUser"
0x17073e  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ElementTypeMismatchException::.ctor(string)
0x170743  throw
0x170744  ldarg.0
0x170745  ldloc.s  4
0x170747  stfld    string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_prompt
0x17074c  br.s     loc_170786
0x17074e  ldarg.0
0x17074f  ldloc.s  4
0x170751  ldarg.2
0x170752  call     instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::SetUserName(string userName, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection dataProtection)
0x170757  br.s     loc_170786
0x170759  ldarg.0
0x17075a  ldloc.s  4
0x17075c  ldarg.2
0x17075d  call     instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::SetPassword(string password, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection dataProtection)
0x170762  br.s     loc_170786
0x170764  nop
0x170765  ldarg.0
0x170766  ldloc.s  4
0x170768  call     bool [mscorlib]System.Boolean::Parse(string)
0x17076d  call     instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::set_Enabled(bool value)
0x170772  leave.s  loc_170786
0x170774  pop
0x170775  ldstr    aEnabled// "Enabled"
0x17077a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ElementTypeMismatchException::.ctor(string)
0x17077f  throw
0x170780  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0x170785  throw
0x170786  ldloc.2
0x170787  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17078c  brtrue   loc_17052E
0x170791  leave.s  loc_1707A7
0x170793  ldloc.2
0x170794  isinst   [mscorlib]System.IDisposable
0x170799  stloc.s  7
0x17079b  ldloc.s  7
0x17079d  brfalse.s loc_1707A6
0x17079f  ldloc.s  7
0x1707a1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1707a6  endfinally
0x1707a7  ldloc.1
0x1707a8  brfalse.s loc_1707B4
0x1707aa  ldarg.0
0x1707ab  ldnull
0x1707ac  ldarg.2
0x1707ad  call     instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::SetConnectionString(string connectionString, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection dataProtection)
0x1707b2  br.s     loc_1707BC
0x1707b4  ldarg.0
0x1707b5  ldloc.0
0x1707b6  ldarg.2
0x1707b7  call     instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::SetConnectionString(string connectionString, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection dataProtection)
0x1707bc  ldloc.1
0x1707bd  stloc.s  8
0x1707bf  leave.s  loc_1707C8
0x1707c1  pop
0x1707c2  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0x1707c7  throw
0x1707c8  ldloc.s  8
0x1707ca  ret
```
