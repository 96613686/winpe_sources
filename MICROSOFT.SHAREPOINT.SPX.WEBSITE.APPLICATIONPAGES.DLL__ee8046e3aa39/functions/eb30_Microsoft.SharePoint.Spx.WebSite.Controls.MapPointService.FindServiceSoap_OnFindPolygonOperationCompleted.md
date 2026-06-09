# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindPolygonOperationCompleted

- ea: `0xeb30`
- end: `0xeb69`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindPolygonOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xeb30`
- `0x12910`
- `0x12950`

## pseudocode

```c

```

## disassembly

```asm
0xeb30  ldarg.0
0xeb31  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindPolygonCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindPolygonCompleted
0xeb36  brfalse.s loc_EB68
0xeb38  ldarg.1
0xeb39  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xeb3e  stloc.0
0xeb3f  ldarg.0
0xeb40  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindPolygonCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindPolygonCompleted
0xeb45  ldarg.0
0xeb46  ldloc.0
0xeb47  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xeb4c  ldloc.0
0xeb4d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xeb52  ldloc.0
0xeb53  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xeb58  ldloc.0
0xeb59  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xeb5e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindPolygonCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xeb63  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindPolygonCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindPolygonCompletedEventArgs e)
0xeb68  ret
```
