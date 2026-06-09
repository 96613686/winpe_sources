# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindByIDOperationCompleted

- ea: `0xe9b0`
- end: `0xe9e9`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindByIDOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xe9b0`
- `0x127d0`
- `0x12810`

## pseudocode

```c

```

## disassembly

```asm
0xe9b0  ldarg.0
0xe9b1  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindByIDCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindByIDCompleted
0xe9b6  brfalse.s loc_E9E8
0xe9b8  ldarg.1
0xe9b9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xe9be  stloc.0
0xe9bf  ldarg.0
0xe9c0  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindByIDCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindByIDCompleted
0xe9c5  ldarg.0
0xe9c6  ldloc.0
0xe9c7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xe9cc  ldloc.0
0xe9cd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xe9d2  ldloc.0
0xe9d3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xe9d8  ldloc.0
0xe9d9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xe9de  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindByIDCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xe9e3  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindByIDCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindByIDCompletedEventArgs e)
0xe9e8  ret
```
