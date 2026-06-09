# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::OnGetEntityTypesOperationCompleted

- ea: `0xde20`
- end: `0xde59`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::OnGetEntityTypesOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xde20`
- `0x12230`
- `0x12270`

## pseudocode

```c

```

## disassembly

```asm
0xde20  ldarg.0
0xde21  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetEntityTypesCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::GetEntityTypesCompleted
0xde26  brfalse.s loc_DE58
0xde28  ldarg.1
0xde29  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xde2e  stloc.0
0xde2f  ldarg.0
0xde30  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetEntityTypesCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::GetEntityTypesCompleted
0xde35  ldarg.0
0xde36  ldloc.0
0xde37  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xde3c  ldloc.0
0xde3d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xde42  ldloc.0
0xde43  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xde48  ldloc.0
0xde49  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xde4e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetEntityTypesCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xde53  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetEntityTypesCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.GetEntityTypesCompletedEventArgs e)
0xde58  ret
```
