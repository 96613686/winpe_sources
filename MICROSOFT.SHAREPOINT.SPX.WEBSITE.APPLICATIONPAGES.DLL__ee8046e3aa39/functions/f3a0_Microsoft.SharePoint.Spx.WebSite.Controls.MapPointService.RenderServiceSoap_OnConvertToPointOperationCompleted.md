# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::OnConvertToPointOperationCompleted

- ea: `0xf3a0`
- end: `0xf3d9`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::OnConvertToPointOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xf3a0`
- `0x12b90`
- `0x12bd0`

## pseudocode

```c

```

## disassembly

```asm
0xf3a0  ldarg.0
0xf3a1  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ConvertToPointCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::ConvertToPointCompleted
0xf3a6  brfalse.s loc_F3D8
0xf3a8  ldarg.1
0xf3a9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xf3ae  stloc.0
0xf3af  ldarg.0
0xf3b0  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ConvertToPointCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::ConvertToPointCompleted
0xf3b5  ldarg.0
0xf3b6  ldloc.0
0xf3b7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xf3bc  ldloc.0
0xf3bd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xf3c2  ldloc.0
0xf3c3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xf3c8  ldloc.0
0xf3c9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xf3ce  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ConvertToPointCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xf3d3  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ConvertToPointCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ConvertToPointCompletedEventArgs e)
0xf3d8  ret
```
