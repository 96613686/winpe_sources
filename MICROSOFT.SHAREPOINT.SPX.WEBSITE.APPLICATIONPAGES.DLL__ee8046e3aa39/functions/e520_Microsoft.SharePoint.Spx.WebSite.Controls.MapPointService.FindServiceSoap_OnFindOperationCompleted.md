# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindOperationCompleted

- ea: `0xe520`
- end: `0xe559`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xe520`
- `0x12410`
- `0x12450`

## pseudocode

```c

```

## disassembly

```asm
0xe520  ldarg.0
0xe521  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindCompleted
0xe526  brfalse.s loc_E558
0xe528  ldarg.1
0xe529  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xe52e  stloc.0
0xe52f  ldarg.0
0xe530  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindCompleted
0xe535  ldarg.0
0xe536  ldloc.0
0xe537  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xe53c  ldloc.0
0xe53d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xe542  ldloc.0
0xe543  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xe548  ldloc.0
0xe549  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xe54e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xe553  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindCompletedEventArgs e)
0xe558  ret
```
