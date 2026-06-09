# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindNearbyOperationCompleted

- ea: `0xe830`
- end: `0xe869`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindNearbyOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xe830`
- `0x12690`
- `0x126d0`

## pseudocode

```c

```

## disassembly

```asm
0xe830  ldarg.0
0xe831  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindNearbyCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindNearbyCompleted
0xe836  brfalse.s loc_E868
0xe838  ldarg.1
0xe839  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xe83e  stloc.0
0xe83f  ldarg.0
0xe840  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindNearbyCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindNearbyCompleted
0xe845  ldarg.0
0xe846  ldloc.0
0xe847  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xe84c  ldloc.0
0xe84d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xe852  ldloc.0
0xe853  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xe858  ldloc.0
0xe859  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xe85e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindNearbyCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xe863  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindNearbyCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindNearbyCompletedEventArgs e)
0xe868  ret
```
