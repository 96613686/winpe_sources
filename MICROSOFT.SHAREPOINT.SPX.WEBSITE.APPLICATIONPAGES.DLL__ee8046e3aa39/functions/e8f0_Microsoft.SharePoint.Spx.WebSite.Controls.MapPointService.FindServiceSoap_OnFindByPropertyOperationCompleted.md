# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindByPropertyOperationCompleted

- ea: `0xe8f0`
- end: `0xe929`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::OnFindByPropertyOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xe8f0`
- `0x12730`
- `0x12770`

## pseudocode

```c

```

## disassembly

```asm
0xe8f0  ldarg.0
0xe8f1  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindByPropertyCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindByPropertyCompleted
0xe8f6  brfalse.s loc_E928
0xe8f8  ldarg.1
0xe8f9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0xe8fe  stloc.0
0xe8ff  ldarg.0
0xe900  ldfld    class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindByPropertyCompletedEventHandler Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::FindByPropertyCompleted
0xe905  ldarg.0
0xe906  ldloc.0
0xe907  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0xe90c  ldloc.0
0xe90d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xe912  ldloc.0
0xe913  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xe918  ldloc.0
0xe919  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0xe91e  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindByPropertyCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0xe923  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindByPropertyCompletedEventHandler::Invoke(object sender, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindByPropertyCompletedEventArgs e)
0xe928  ret
```
