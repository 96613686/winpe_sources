# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::OnGetMapOperationCompleted

- ea: `0xf2b0`
- end: `0xf2e9`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::OnGetMapOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xf2b0`
- `0x12af0`
- `0x12b30`

## pseudocode

```c

```

## disassembly

```asm
0xf2b0  ldarg.0
0xf2b1  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetMapCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::GetMapCompleted
0xf2b6  brfalse.s loc_F2E8
0xf2b8  ldarg.1
0xf2b9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xf2be  stloc.0
0xf2bf  ldarg.0
0xf2c0  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetMapCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::GetMapCompleted
0xf2c5  ldarg.0
0xf2c6  ldloc.0
0xf2c7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xf2cc  ldloc.0
0xf2cd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xf2d2  ldloc.0
0xf2d3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xf2d8  ldloc.0
0xf2d9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xf2de  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetMapCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xf2e3  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetMapCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetMapCompletedEventArgs e)
0xf2e8  ret
```
