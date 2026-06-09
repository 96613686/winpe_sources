# System.Deployment.Application.ShellExposure::RemoveSubscriptionShellExposure

- ea: `0x1d5f0`
- end: `0x1d6eb`
- name: `System.Deployment.Application.ShellExposure::RemoveSubscriptionShellExposure`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x12a70`
- `0x1ffc0`

## callees

- `0x146f0`
- `0x17d40`
- `0x1d5f0`
- `0x1dd40`
- `0x1e740`
- `0x1ece0`
- `0x1ecf0`
- `0x1fc80`
- `0x23020`
- `0x2c1e0`
- `0x2c500`
- `0x2c510`
- `0x2c520`
- `0x2c530`
- `0x2c540`

## string_xrefs

- `0x1d635`: `Remove shortcut entries Failed: `

## pseudocode

```c

```

## disassembly

```asm
0x1d5f0  ldarg.0
0x1d5f1  callvirt instance class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionState::get_SubscriptionStore()
0x1d5f6  callvirt instance class [mscorlib]System.IDisposable System.Deployment.Application.SubscriptionStore::AcquireStoreWriterLock()
0x1d5fb  stloc.0
0x1d5fc  ldarg.0
0x1d5fd  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1d602  stloc.1
0x1d603  ldc.i4.0
0x1d604  stloc.2
0x1d605  ldloc.1
0x1d606  call     class ShellExposureInformation ShellExposureInformation::CreateShellExposureInformation(class System.Deployment.Application.DefinitionIdentity subscriptionIdentity)
0x1d60b  stloc.3
0x1d60c  ldloc.3
0x1d60d  brtrue.s loc_1D616
0x1d60f  ldc.i4.1
0x1d610  stloc.2
0x1d611  br       loc_1D6C4
0x1d616  ldc.i4.1
0x1d617  stloc.s  4
0x1d619  br       loc_1D6BC
0x1d61e  nop
0x1d61f  ldloc.3
0x1d620  call     void System.Deployment.Application.ShellExposure::RemoveShortcuts(class ShellExposureInformation shellExposureInformation)
0x1d625  leave    loc_1D6C4
0x1d62a  stloc.s  5
0x1d62c  ldc.i4.s 0xA
0x1d62e  newarr   [mscorlib]System.String
0x1d633  dup
0x1d634  ldc.i4.0
0x1d635  ldstr    aRemoveShortcut// "Remove shortcut entries Failed: "
0x1d63a  stelem.ref
0x1d63b  dup
0x1d63c  ldc.i4.1
0x1d63d  ldloc.3
0x1d63e  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1d643  stelem.ref
0x1d644  dup
0x1d645  ldc.i4.2
0x1d646  ldstr    asc_308B8// ","
0x1d64b  stelem.ref
0x1d64c  dup
0x1d64d  ldc.i4.3
0x1d64e  ldloc.3
0x1d64f  callvirt instance string ShellExposureInformation::get_SupportShortcutPath()
0x1d654  stelem.ref
0x1d655  dup
0x1d656  ldc.i4.4
0x1d657  ldstr    asc_308B8// ","
0x1d65c  stelem.ref
0x1d65d  dup
0x1d65e  ldc.i4.5
0x1d65f  ldloc.3
0x1d660  callvirt instance string ShellExposureInformation::get_DesktopShortcutPath()
0x1d665  stelem.ref
0x1d666  dup
0x1d667  ldc.i4.6
0x1d668  ldstr    asc_308B8// ","
0x1d66d  stelem.ref
0x1d66e  dup
0x1d66f  ldc.i4.7
0x1d670  ldloc.3
0x1d671  callvirt instance string ShellExposureInformation::get_ApplicationFolderPath()
0x1d676  stelem.ref
0x1d677  dup
0x1d678  ldc.i4.8
0x1d679  ldstr    asc_308B8// ","
0x1d67e  stelem.ref
0x1d67f  dup
0x1d680  ldc.i4.s 9
0x1d682  ldloc.3
0x1d683  callvirt instance string ShellExposureInformation::get_ApplicationRootFolderPath()
0x1d688  stelem.ref
0x1d689  call     string [mscorlib]System.String::Concat(string[])
0x1d68e  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1d693  ldloc.s  4
0x1d695  ldc.i4.2
0x1d696  bge.s    loc_1D6A4
0x1d698  ldc.i4   0x3E8
0x1d69d  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x1d6a2  br.s     loc_1D6B4
0x1d6a4  ldloc.s  5
0x1d6a6  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x1d6ab  isinst   [mscorlib]System.UnauthorizedAccessException
0x1d6b0  brtrue.s loc_1D6B4
0x1d6b2  rethrow
0x1d6b4  leave.s  loc_1D6B6
0x1d6b6  ldloc.s  4
0x1d6b8  ldc.i4.1
0x1d6b9  add
0x1d6ba  stloc.s  4
0x1d6bc  ldloc.s  4
0x1d6be  ldc.i4.2
0x1d6bf  ble      loc_1D61E
0x1d6c4  ldloc.1
0x1d6c5  call     void System.Deployment.Application.ShellExposure::RemoveArpEntry(class System.Deployment.Application.DefinitionIdentity subId)
0x1d6ca  ldloc.2
0x1d6cb  brfalse.s loc_1D6DE
0x1d6cd  ldc.i4.7
0x1d6ce  ldstr    aExShortcutremo// "Ex_ShortcutRemovalFailureDueToInvalidPu"...
0x1d6d3  call     string System.Deployment.Application.Resources::GetString(string s)
0x1d6d8  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1d6dd  throw
0x1d6de  leave.s  loc_1D6EA
0x1d6e0  ldloc.0
0x1d6e1  brfalse.s loc_1D6E9
0x1d6e3  ldloc.0
0x1d6e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d6e9  endfinally
0x1d6ea  ret
```
