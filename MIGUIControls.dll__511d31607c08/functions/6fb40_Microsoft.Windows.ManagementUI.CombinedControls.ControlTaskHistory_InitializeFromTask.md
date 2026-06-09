# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::InitializeFromTask

- ea: `0x6fb40`
- end: `0x6fe39`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::InitializeFromTask`
- size: `761`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `service_task, broker_com_uri`

## callees

- `0x12ed0`
- `0x13440`
- `0x16310`
- `0x1b7c0`
- `0x1b850`
- `0x2b490`
- `0x2b6a0`
- `0x2b6d0`
- `0x2b6f0`
- `0x2b710`
- `0x2b730`
- `0x2b740`
- `0x2b7f0`
- `0x2b8f0`
- `0x2ba80`
- `0x32a00`
- `0x32ab0`
- `0x37d10`
- `0x39b20`
- `0x3e2d0`
- `0x3eac0`
- `0x3ec50`
- `0x3ec70`
- `0x3ecf0`
- `0x4d630`
- `0x4dca0`
- `0x642a0`
- `0x64620`
- `0x64710`
- `0x67bb0`
- `0x67bc0`
- `0x67bd0`
- `0x67be0`
- `0x67c70`
- `0x67c90`
- `0x67ca0`
- `0x6bb00`
- `0x6fb40`

## string_xrefs

- `0x6fe06`: `ApplicationTaskScheduler`
- `0x6fe27`: `ApplicationTaskScheduler`
- `0x6fd7d`: `Microsoft-Windows-TaskScheduler/Operational`
- `0x6fd94`: `Microsoft-Windows-TaskScheduler/Operational`
- `0x6fdfc`: `MessageTaskCrimsonServiceNotRunning`
- `0x6fbd0`: `MessageTaskAccessViewHistory`
- `0x6fe1d`: `MessageTaskAccessViewHistory`
- `0x6fbff`: `MessageTaskHistoryNotSupported`
- `0x6fd4c`: `*[EventData/Data[@Name='TaskName']='`

## pseudocode

```c

```

## disassembly

```asm
0x6fb40  ldc.i4.0
0x6fb41  stloc.0
0x6fb42  ldarg.0
0x6fb43  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::InitializeControls()
0x6fb48  ldarg.0
0x6fb49  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::historyInitialized
0x6fb4e  brtrue.s loc_6FB5B
0x6fb50  ldarg.0
0x6fb51  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fb56  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::Initialize()
0x6fb5b  ldarg.0
0x6fb5c  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::historyInitialized
0x6fb61  brfalse.s loc_6FB7E
0x6fb63  ldarg.0
0x6fb64  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fb69  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::CloseResultSet()
0x6fb6e  ldarg.0
0x6fb6f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fb74  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_Context()
0x6fb79  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::Dispose()
0x6fb7e  ldarg.0
0x6fb7f  ldc.i4.0
0x6fb80  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::historyInitialized
0x6fb85  ldc.i4   0x10002
0x6fb8a  ldarg.0
0x6fb8b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x6fb90  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x6fb95  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_HighestVersion()
0x6fb9a  bgt.s    loc_6FBF9
0x6fb9c  ldarg.0
0x6fb9d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x6fba2  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x6fba7  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsConnectedToCrimson()
0x6fbac  brfalse.s loc_6FBCA
0x6fbae  ldarg.0
0x6fbaf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::labelErrorMessage
0x6fbb4  ldc.i4.0
0x6fbb5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6fbba  ldarg.0
0x6fbbb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fbc0  ldc.i4.1
0x6fbc1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6fbc6  ldc.i4.1
0x6fbc7  stloc.0
0x6fbc8  br.s     loc_6FC26
0x6fbca  ldarg.0
0x6fbcb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::labelErrorMessage
0x6fbd0  ldstr    aMessagetaskacc_6// "MessageTaskAccessViewHistory"
0x6fbd5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6fbda  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x6fbdf  ldarg.0
0x6fbe0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::labelErrorMessage
0x6fbe5  ldc.i4.1
0x6fbe6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6fbeb  ldarg.0
0x6fbec  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fbf1  ldc.i4.0
0x6fbf2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6fbf7  br.s     loc_6FC26
0x6fbf9  ldarg.0
0x6fbfa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::labelErrorMessage
0x6fbff  ldstr    aMessagetaskhis// "MessageTaskHistoryNotSupported"
0x6fc04  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6fc09  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x6fc0e  ldarg.0
0x6fc0f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::labelErrorMessage
0x6fc14  ldc.i4.1
0x6fc15  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6fc1a  ldarg.0
0x6fc1b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fc20  ldc.i4.0
0x6fc21  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6fc26  ldloc.0
0x6fc27  brfalse  loc_6FE38
0x6fc2c  ldarg.0
0x6fc2d  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::historyInitialized
0x6fc32  brtrue   loc_6FDB6
0x6fc37  ldarg.0
0x6fc38  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x6fc3d  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x6fc42  stloc.1
0x6fc43  ldarg.0
0x6fc44  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fc49  ldloc.1
0x6fc4a  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x6fc4f  ldloc.1
0x6fc50  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_Domain()
0x6fc55  ldloc.1
0x6fc56  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_User()
0x6fc5b  ldloc.1
0x6fc5c  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_EncryptedPassword()
0x6fc61  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x6fc66  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x6fc6b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::.ctor(string remoteComputerName, string userDomain, string userName, class [mscorlib]System.Security.SecureString encryptedPassword, int32 lcid)
0x6fc70  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_Context(class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext value)
0x6fc75  ldarg.0
0x6fc76  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fc7b  ldloc.1
0x6fc7c  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x6fc81  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_RemoteMachineAddress(string value)
0x6fc86  ldarg.0
0x6fc87  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumns Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::columns
0x6fc8c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ResultColumns::Clear()
0x6fc91  ldarg.0
0x6fc92  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumns Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::columns
0x6fc97  ldc.i4.0
0x6fc98  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AddStandardColumns(class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumns columns, bool isForwardedEventsChannel)
0x6fc9d  ldarg.0
0x6fc9e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumns Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::columns
0x6fca3  ldc.i4.0
0x6fca4  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ResultColumns::SetAllColumnsVisible(bool visible)
0x6fca9  ldc.i4.6
0x6fcaa  newarr   [mscorlib]System.Int32
0x6fcaf  dup
0x6fcb0  ldtoken  valuetype __StaticArrayInitTypeSize=24 <PrivateImplementationDetails>::'8064801B58F4C4AD7A59AD7332DDF11ACE73CBA35400E767AB5E85074A8F86C0'
0x6fcb5  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x6fcba  stloc.s  5
0x6fcbc  ldc.i4.0
0x6fcbd  stloc.s  6
0x6fcbf  br.s     loc_6FCE8
0x6fcc1  ldloc.s  5
0x6fcc3  ldloc.s  6
0x6fcc5  ldelem.i4
0x6fcc6  call     class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumn Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetStandardColumn(int32 columnIdentifier)
0x6fccb  stloc.s  7
0x6fccd  ldloc.s  7
0x6fccf  ldc.i4.1
0x6fcd0  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ResultColumn::set_Visible(bool value)
0x6fcd5  ldarg.0
0x6fcd6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumns Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::columns
0x6fcdb  ldloc.s  7
0x6fcdd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ResultColumns::SetColumn(class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumn column)
0x6fce2  ldloc.s  6
0x6fce4  ldc.i4.1
0x6fce5  add
0x6fce6  stloc.s  6
0x6fce8  ldloc.s  6
0x6fcea  ldloc.s  5
0x6fcec  ldlen
0x6fced  conv.i4
0x6fcee  blt.s    loc_6FCC1
0x6fcf0  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::CreateXmlDocument()
0x6fcf5  stloc.2
0x6fcf6  ldloc.2
0x6fcf7  ldloc.2
0x6fcf8  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ResultViewConfig
0x6fcfd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6fd02  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6fd07  pop
0x6fd08  ldloc.2
0x6fd09  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x6fd0e  ldarg.0
0x6fd0f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumns Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::columns
0x6fd14  ldloc.2
0x6fd15  callvirt instance class [System.Xml]System.Xml.XmlElement Microsoft.Windows.ManagementUI.CombinedControls.ResultColumns::GetConfigAsXmlElement(class [System.Xml]System.Xml.XmlDocument doc)
0x6fd1a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6fd1f  pop
0x6fd20  ldarg.0
0x6fd21  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fd26  ldloc.2
0x6fd27  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x6fd2c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_ResultsConfig(string value)
0x6fd31  ldarg.0
0x6fd32  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fd37  ldc.i4.1
0x6fd38  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_Preview(bool value)
0x6fd3d  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::.ctor()
0x6fd42  stloc.3
0x6fd43  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x6fd48  stloc.s  4
0x6fd4a  ldloc.s  4
0x6fd4c  ldstr    aEventdataDataN_0// "*[EventData/Data[@Name='TaskName']='"
0x6fd51  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6fd56  pop
0x6fd57  ldloc.s  4
0x6fd59  ldarg.0
0x6fd5a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x6fd5f  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_PreviewInfo()
0x6fd64  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo::get_Path()
0x6fd69  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6fd6e  pop
0x6fd6f  ldloc.s  4
0x6fd71  ldstr    asc_AD7C6// "']"
0x6fd76  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6fd7b  pop
0x6fd7c  ldloc.3
0x6fd7d  ldstr    aMicrosoftWindo_1// "Microsoft-Windows-TaskScheduler/Operati"...
0x6fd82  ldloc.s  4
0x6fd84  callvirt instance string [mscorlib]System.Object::ToString()
0x6fd89  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::AddSelector(string path, string selector)
0x6fd8e  ldarg.0
0x6fd8f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fd94  ldstr    aMicrosoftWindo_1// "Microsoft-Windows-TaskScheduler/Operati"...
0x6fd99  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_Channel(string value)
0x6fd9e  ldarg.0
0x6fd9f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fda4  ldloc.3
0x6fda5  callvirt instance string [mscorlib]System.Object::ToString()
0x6fdaa  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_Query(string value)
0x6fdaf  ldarg.0
0x6fdb0  ldc.i4.1
0x6fdb1  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::historyInitialized
0x6fdb6  ldarg.0
0x6fdb7  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::eventDetailControl2
0x6fdbc  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::RefreshView()
0x6fdc1  leave.s  loc_6FE38
0x6fdc3  stloc.s  8
0x6fdc5  ldarg.0
0x6fdc6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x6fdcb  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x6fdd0  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsConnectedToCrimson()
0x6fdd5  brfalse.s loc_6FE36
0x6fdd7  ldarg.0
0x6fdd8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x6fddd  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x6fde2  ldc.i4.0
0x6fde3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::set_IsConnectedToCrimson(bool value)
0x6fde8  ldloc.s  8
0x6fdea  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_ErrorNumber()
0x6fdef  call     bool Microsoft.Windows.ManagementUI.CombinedControls.UIException::ServiceNotAvailableError(int32 error)
0x6fdf4  brfalse.s loc_6FE17
0x6fdf6  ldarg.0
0x6fdf7  call     instance class [System.Windows.Forms]System.Windows.Forms.Form [System.Windows.Forms]System.Windows.Forms.ContainerControl::get_ParentForm()
0x6fdfc  ldstr    aMessagetaskcri// "MessageTaskCrimsonServiceNotRunning"
0x6fe01  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6fe06  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x6fe0b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6fe10  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x6fe15  br.s     loc_6FE36
0x6fe17  ldarg.0
0x6fe18  call     instance class [System.Windows.Forms]System.Windows.Forms.Form [System.Windows.Forms]System.Windows.Forms.ContainerControl::get_ParentForm()
0x6fe1d  ldstr    aMessagetaskacc_6// "MessageTaskAccessViewHistory"
0x6fe22  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6fe27  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x6fe2c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6fe31  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x6fe36  leave.s  loc_6FE38
0x6fe38  ret
```
