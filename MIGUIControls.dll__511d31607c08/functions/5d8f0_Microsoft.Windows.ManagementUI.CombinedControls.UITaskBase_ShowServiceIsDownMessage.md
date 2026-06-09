# Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowServiceIsDownMessage

- ea: `0x5d8f0`
- end: `0x5d9aa`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowServiceIsDownMessage`
- size: `186`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d9b0`
- `0x67e80`

## callees

- `0x12ed0`
- `0x133f0`
- `0x13430`
- `0x5d760`
- `0x5d8f0`
- `0x67bb0`
- `0x67bc0`
- `0x67bd0`
- `0x67be0`
- `0x67c50`
- `0x67f40`
- `0x85930`

## string_xrefs

- `0x5d91a`: `MessageServiceDown`
- `0x5d92b`: `MessageServiceDown`
- `0x5d99a`: `MessageServiceDown`
- `0x5d94a`: `MessageServiceDownRestart`

## pseudocode

```c

```

## disassembly

```asm
0x5d8f0  ldarg.1
0x5d8f1  brfalse.s loc_5D92B
0x5d8f3  ldarg.1
0x5d8f4  isinst   [mscorlib]System.BadImageFormatException
0x5d8f9  stloc.0
0x5d8fa  ldloc.0
0x5d8fb  brfalse.s loc_5D91A
0x5d8fd  ldloc.0
0x5d8fe  callvirt instance string [mscorlib]System.BadImageFormatException::get_FileName()
0x5d903  ldstr    asc_AAAB6// " "
0x5d908  ldloc.0
0x5d909  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5d90e  call     string [mscorlib]System.String::Concat(string, string, string)
0x5d913  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x5d918  br.s     loc_5D93A
0x5d91a  ldstr    aMessageservice_1// "MessageServiceDown"
0x5d91f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5d924  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x5d929  br.s     loc_5D93A
0x5d92b  ldstr    aMessageservice_1// "MessageServiceDown"
0x5d930  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5d935  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x5d93a  ldarg.0
0x5d93b  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x5d940  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x5d945  brtrue.s loc_5D9A9
0x5d947  ldarg.2
0x5d948  brfalse.s loc_5D99A
0x5d94a  ldstr    aMessageservice_2// "MessageServiceDownRestart"
0x5d94f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5d954  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x5d959  ldarg.0
0x5d95a  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x5d95f  ldarg.0
0x5d960  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x5d965  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x5d96a  ldarg.0
0x5d96b  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x5d970  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_User()
0x5d975  ldarg.0
0x5d976  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x5d97b  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_Domain()
0x5d980  ldarg.0
0x5d981  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x5d986  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_EncryptedPassword()
0x5d98b  ldc.i4.1
0x5d98c  ldc.i4.0
0x5d98d  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ConnectToMachine(string computerName, string user, string domain, class [mscorlib]System.Security.SecureString encryptedPassword, bool forceReconnect, bool showServiceErrorMessage)
0x5d992  brtrue.s loc_5D9A9
0x5d994  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ServiceUnavailableException::.ctor()
0x5d999  throw
0x5d99a  ldstr    aMessageservice_1// "MessageServiceDown"
0x5d99f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5d9a4  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x5d9a9  ret
```
