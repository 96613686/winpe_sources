# Microsoft.ManagementConsole.Status::InternalComplete

- ea: `0x71f0`
- end: `0x7241`
- name: `Microsoft.ManagementConsole.Status::InternalComplete`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x71e0`
- `0x7410`
- `0x74a0`

## callees

- `0x60`
- `0x71f0`
- `0x8430`

## pseudocode

```c

```

## disassembly

```asm
0x71f0  ldarg.0
0x71f1  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus Microsoft.ManagementConsole.Status::_requestStatus
0x71f6  brfalse.s loc_7226
0x71f8  ldarg.0
0x71f9  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus Microsoft.ManagementConsole.Status::_requestStatus
0x71fe  ldarg.1
0x71ff  ldarg.2
0x7200  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus::SetCompletionText(string, bool)
0x7205  ldarg.0
0x7206  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus Microsoft.ManagementConsole.Status::_requestStatus
0x720b  callvirt instance valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestState [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus::get_RequestState()
0x7210  brfalse.s loc_7240
0x7212  ldarg.0
0x7213  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus Microsoft.ManagementConsole.Status::_requestStatus
0x7218  ldc.i4.2
0x7219  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus::set_RequestState(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestState)
0x721e  ldarg.0
0x721f  ldnull
0x7220  stfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus Microsoft.ManagementConsole.Status::_requestStatus
0x7225  ret
0x7226  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ManagementConsole.Internal.Utility::get_Resources()
0x722b  call     string Microsoft.ManagementConsole.Internal.Strings::get_MicrosoftManagementConsoleInternalStatusRequestNotStarted()
0x7230  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7235  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x723a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x723f  throw
0x7240  ret
```
