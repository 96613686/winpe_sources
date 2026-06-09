# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::CreateListItem

- ea: `0x3360`
- end: `0x3379`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::CreateListItem`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`

## pseudocode

```c

```

## disassembly

```asm
0x3360  ldarg.1
0x3361  ldarg.2
0x3362  newobj   instance void [System.Web]System.Web.UI.WebControls.ListItem::.ctor(string, string)
0x3367  dup
0x3368  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.ListItem::get_Attributes()
0x336d  ldstr    aAriaLabel// "aria-label"
0x3372  ldarg.1
0x3373  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x3378  ret
```
