# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::OnGetVersionInfoOperationCompleted

- ea: `0xdca0`
- end: `0xdcd9`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::OnGetVersionInfoOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xdca0`
- `0x120f0`
- `0x12130`

## pseudocode

```c

```

## disassembly

```asm
0xdca0  ldarg.0
0xdca1  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetVersionInfoCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::GetVersionInfoCompleted
0xdca6  brfalse.s loc_DCD8
0xdca8  ldarg.1
0xdca9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xdcae  stloc.0
0xdcaf  ldarg.0
0xdcb0  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetVersionInfoCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::GetVersionInfoCompleted
0xdcb5  ldarg.0
0xdcb6  ldloc.0
0xdcb7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xdcbc  ldloc.0
0xdcbd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xdcc2  ldloc.0
0xdcc3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xdcc8  ldloc.0
0xdcc9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xdcce  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetVersionInfoCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xdcd3  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetVersionInfoCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetVersionInfoCompletedEventArgs e)
0xdcd8  ret
```
