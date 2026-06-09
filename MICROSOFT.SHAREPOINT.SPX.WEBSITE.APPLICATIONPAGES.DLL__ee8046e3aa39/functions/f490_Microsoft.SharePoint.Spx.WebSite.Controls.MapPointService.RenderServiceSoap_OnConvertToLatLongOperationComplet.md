# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::OnConvertToLatLongOperationCompleted

- ea: `0xf490`
- end: `0xf4c9`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::OnConvertToLatLongOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xf490`
- `0x12c30`
- `0x12c70`

## pseudocode

```c

```

## disassembly

```asm
0xf490  ldarg.0
0xf491  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ConvertToLatLongCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::ConvertToLatLongCompleted
0xf496  brfalse.s loc_F4C8
0xf498  ldarg.1
0xf499  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xf49e  stloc.0
0xf49f  ldarg.0
0xf4a0  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ConvertToLatLongCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::ConvertToLatLongCompleted
0xf4a5  ldarg.0
0xf4a6  ldloc.0
0xf4a7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xf4ac  ldloc.0
0xf4ad  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xf4b2  ldloc.0
0xf4b3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xf4b8  ldloc.0
0xf4b9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xf4be  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ConvertToLatLongCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xf4c3  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ConvertToLatLongCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ConvertToLatLongCompletedEventArgs e)
0xf4c8  ret
```
