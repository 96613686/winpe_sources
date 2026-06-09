# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnParseAddressOperationCompleted

- ea: `0xe6a0`
- end: `0xe6d9`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnParseAddressOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xe6a0`
- `0x12550`
- `0x12590`

## pseudocode

```c

```

## disassembly

```asm
0xe6a0  ldarg.0
0xe6a1  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ParseAddressCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::ParseAddressCompleted
0xe6a6  brfalse.s loc_E6D8
0xe6a8  ldarg.1
0xe6a9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xe6ae  stloc.0
0xe6af  ldarg.0
0xe6b0  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ParseAddressCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::ParseAddressCompleted
0xe6b5  ldarg.0
0xe6b6  ldloc.0
0xe6b7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xe6bc  ldloc.0
0xe6bd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xe6c2  ldloc.0
0xe6c3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xe6c8  ldloc.0
0xe6c9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xe6ce  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ParseAddressCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xe6d3  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ParseAddressCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ParseAddressCompletedEventArgs e)
0xe6d8  ret
```
