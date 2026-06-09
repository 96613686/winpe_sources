# Microsoft.Reporting.WebForms.GenericDropDownInputControl::get_RelativeDivID

- ea: `0xd900`
- end: `0xd92a`
- name: `Microsoft.Reporting.WebForms.GenericDropDownInputControl::get_RelativeDivID`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xdea0`
- `0xe030`

## callees

- `0xd900`

## string_xrefs

- `0xd90e`: `ClientID accessed before control added to page.`

## pseudocode

```c

```

## disassembly

```asm
0xd900  ldarg.0
0xd901  callvirt instance void [System.Web]System.Web.UI.Control::EnsureChildControls()
0xd906  ldarg.0
0xd907  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xd90c  brtrue.s loc_D919
0xd90e  ldstr    aClientidAccess// "ClientID accessed before control added "...
0xd913  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0xd918  throw
0xd919  ldarg.0
0xd91a  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xd91f  ldstr    aRelativediv// "_RelativeDiv"
0xd924  call     string [mscorlib]System.String::Concat(string, string)
0xd929  ret
```
