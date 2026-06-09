# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::OnGetLineDriveMapOperationCompleted

- ea: `0xf610`
- end: `0xf649`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::OnGetLineDriveMapOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xf610`
- `0x12d70`
- `0x12db0`

## pseudocode

```c

```

## disassembly

```asm
0xf610  ldarg.0
0xf611  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetLineDriveMapCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::GetLineDriveMapCompleted
0xf616  brfalse.s loc_F648
0xf618  ldarg.1
0xf619  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xf61e  stloc.0
0xf61f  ldarg.0
0xf620  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetLineDriveMapCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::GetLineDriveMapCompleted
0xf625  ldarg.0
0xf626  ldloc.0
0xf627  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xf62c  ldloc.0
0xf62d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xf632  ldloc.0
0xf633  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xf638  ldloc.0
0xf639  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xf63e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetLineDriveMapCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xf643  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetLineDriveMapCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetLineDriveMapCompletedEventArgs e)
0xf648  ret
```
