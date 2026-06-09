# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindAddressOperationCompleted

- ea: `0xe5e0`
- end: `0xe619`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindAddressOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xe5e0`
- `0x124b0`
- `0x124f0`

## pseudocode

```c

```

## disassembly

```asm
0xe5e0  ldarg.0
0xe5e1  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindAddressCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindAddressCompleted
0xe5e6  brfalse.s loc_E618
0xe5e8  ldarg.1
0xe5e9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xe5ee  stloc.0
0xe5ef  ldarg.0
0xe5f0  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindAddressCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindAddressCompleted
0xe5f5  ldarg.0
0xe5f6  ldloc.0
0xe5f7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xe5fc  ldloc.0
0xe5fd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xe602  ldloc.0
0xe603  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xe608  ldloc.0
0xe609  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xe60e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindAddressCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xe613  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindAddressCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindAddressCompletedEventArgs e)
0xe618  ret
```
