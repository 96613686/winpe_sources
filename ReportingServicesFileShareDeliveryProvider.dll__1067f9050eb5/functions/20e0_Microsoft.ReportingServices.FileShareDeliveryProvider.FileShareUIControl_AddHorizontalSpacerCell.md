# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddHorizontalSpacerCell

- ea: `0x20e0`
- end: `0x213d`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddHorizontalSpacerCell`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`
- `0x3390`

## callees

- `0x1ef0`
- `0x20a0`
- `0x21b0`

## pseudocode

```c

```

## disassembly

```asm
0x20e0  ldarg.0
0x20e1  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell()
0x20e6  pop
0x20e7  ldarg.0
0x20e8  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x20ed  ldarga.s 1
0x20ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20f4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x20f9  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_Width(string)
0x20fe  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0x2103  stloc.0
0x2104  ldloc.0
0x2105  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_BlankImageUrl()
0x210a  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x210f  ldloc.0
0x2110  ldarg.1
0x2111  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Width(int32)
0x2116  ldloc.0
0x2117  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x211c  ldstr    aAriaHidden// "aria-hidden"
0x2121  ldstr    aTrue// "true"
0x2126  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x212b  ldarg.0
0x212c  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x2131  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2136  ldloc.0
0x2137  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x213c  ret
```
