# Microsoft.Windows.ManagementUI.CombinedControls.UITask::GetXml

- ea: `0x64c50`
- end: `0x64d62`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITask::GetXml`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x12ed0`
- `0x133f0`
- `0x13430`
- `0x5d760`
- `0x5de60`
- `0x645c0`
- `0x64c50`
- `0x67c50`
- `0x67e80`
- `0x83c00`

## string_xrefs

- `0x64ce9`: `MessageTaskDoesNotExist`
- `0x64c8d`: `MessageInvalidTaskFormat`

## pseudocode

```c

```

## disassembly

```asm
0x64c50  ldsfld   string [mscorlib]System.String::Empty
0x64c55  stloc.0
0x64c56  ldarg.0
0x64c57  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureIRegisteredTask
0x64c5c  brfalse.s loc_64C6A
0x64c5e  ldarg.0
0x64c5f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureIRegisteredTask
0x64c64  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask::get_XML()
0x64c69  stloc.0
0x64c6a  leave    loc_64D60
0x64c6f  stloc.1
0x64c70  ldloc.1
0x64c71  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x64c76  stloc.2
0x64c77  ldloc.2
0x64c78  ldc.i4   0xC00CEE04
0x64c7d  bne.un.s loc_64CB2
0x64c7f  ldarg.0
0x64c80  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64c85  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x64c8a  brtrue.s loc_64CD5
0x64c8c  ldnull
0x64c8d  ldstr    aMessageinvalid_3// "MessageInvalidTaskFormat"
0x64c92  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64c97  ldc.i4.1
0x64c98  newarr   [mscorlib]System.Object
0x64c9d  dup
0x64c9e  ldc.i4.0
0x64c9f  ldarg.0
0x64ca0  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x64ca5  stelem.ref
0x64ca6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x64cab  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x64cb0  br.s     loc_64CD5
0x64cb2  ldloc.2
0x64cb3  ldc.i4   0x8000FFFF
0x64cb8  bne.un.s loc_64CC7
0x64cba  ldloc.1
0x64cbb  callvirt instance string [mscorlib]System.Object::ToString()
0x64cc0  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x64cc5  br.s     loc_64CD5
0x64cc7  ldarg.0
0x64cc8  ldloc.1
0x64cc9  ldarg.0
0x64cca  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x64ccf  ldc.i4.1
0x64cd0  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ProcessExternalErrors(class [mscorlib]System.Runtime.InteropServices.ExternalException e, string taskName, bool showToUser)
0x64cd5  leave    loc_64D60
0x64cda  stloc.3
0x64cdb  ldarg.0
0x64cdc  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64ce1  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x64ce6  brtrue.s loc_64D14
0x64ce8  ldnull
0x64ce9  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x64cee  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64cf3  ldc.i4.2
0x64cf4  newarr   [mscorlib]System.Object
0x64cf9  dup
0x64cfa  ldc.i4.0
0x64cfb  ldarg.0
0x64cfc  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x64d01  stelem.ref
0x64d02  dup
0x64d03  ldc.i4.1
0x64d04  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x64d09  stelem.ref
0x64d0a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x64d0f  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x64d14  ldloc.3
0x64d15  callvirt instance string [mscorlib]System.Exception::get_Message()
0x64d1a  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x64d1f  leave.s  loc_64D60
0x64d21  ldarg.0
0x64d22  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64d27  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x64d2c  brtrue.s loc_64D3D
0x64d2e  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x64d33  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64d38  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x64d3d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x64d42  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x64d47  leave.s  loc_64D60
0x64d49  stloc.s  4
0x64d4b  ldarg.0
0x64d4c  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64d51  ldloc.s  4
0x64d53  ldarg.0
0x64d54  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x64d59  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e, string taskName)
0x64d5e  leave.s  loc_64D60
0x64d60  ldloc.0
0x64d61  ret
```
