# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnGetLocationInfoOperationCompleted

- ea: `0xe770`
- end: `0xe7a9`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnGetLocationInfoOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xe770`
- `0x125f0`
- `0x12630`

## pseudocode

```c

```

## disassembly

```asm
0xe770  ldarg.0
0xe771  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetLocationInfoCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::GetLocationInfoCompleted
0xe776  brfalse.s loc_E7A8
0xe778  ldarg.1
0xe779  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xe77e  stloc.0
0xe77f  ldarg.0
0xe780  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetLocationInfoCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::GetLocationInfoCompleted
0xe785  ldarg.0
0xe786  ldloc.0
0xe787  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xe78c  ldloc.0
0xe78d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xe792  ldloc.0
0xe793  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xe798  ldloc.0
0xe799  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xe79e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetLocationInfoCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xe7a3  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetLocationInfoCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetLocationInfoCompletedEventArgs e)
0xe7a8  ret
```
