# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ErrorMessage

- ea: `0x2730`
- end: `0x2870`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ErrorMessage`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2500`
- `0x28d0`

## callees

- `0x3a60`

## pseudocode

```c

```

## disassembly

```asm
0x2730  ldarg.0
0x2731  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x2736  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x273b  callvirt instance string [System.Web]System.Web.HttpRequest::get_ApplicationPath()
0x2740  ldstr    aImagesLineErr1// "/images/line_err1.gif"
0x2745  call     string [mscorlib]System.String::Concat(string, string)
0x274a  stloc.0
0x274b  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0x2750  stloc.1
0x2751  ldloc.1
0x2752  ldloc.0
0x2753  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x2758  ldloc.1
0x2759  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_HtmlImgAlt()
0x275e  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0x2763  ldloc.1
0x2764  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2769  ldstr    aAriaHidden// "aria-hidden"
0x276e  ldstr    aTrue// "true"
0x2773  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2778  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::.ctor()
0x277d  dup
0x277e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2783  ldstr    aRole// "role"
0x2788  ldstr    aPresentation// "presentation"
0x278d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2792  dup
0x2793  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0x2798  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::.ctor()
0x279d  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow)
0x27a2  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0x27a7  stloc.2
0x27a8  ldloc.2
0x27a9  ldstr    aMiddle// "middle"
0x27ae  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_VAlign(string)
0x27b3  ldloc.2
0x27b4  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x27b9  ldstr    aClass// "class"
0x27be  ldstr    aMsrsValidation// "msrs-validationerror"
0x27c3  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x27c8  ldloc.2
0x27c9  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x27ce  ldstr    aAriaLive// "aria-live"
0x27d3  ldstr    aAssertive// "assertive"
0x27d8  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x27dd  ldloc.2
0x27de  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x27e3  ldstr    aAriaAtomic// "aria-atomic"
0x27e8  ldstr    aTrue// "true"
0x27ed  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x27f2  ldloc.2
0x27f3  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x27f8  ldloc.1
0x27f9  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x27fe  dup
0x27ff  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0x2804  ldc.i4.0
0x2805  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::get_Item(int32)
0x280a  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::get_Cells()
0x280f  ldloc.2
0x2810  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell)
0x2815  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0x281a  stloc.2
0x281b  ldloc.2
0x281c  ldarg.2
0x281d  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_NoWrap(bool)
0x2822  ldloc.2
0x2823  ldstr    aMiddle// "middle"
0x2828  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_VAlign(string)
0x282d  ldloc.2
0x282e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2833  ldstr    aClass// "class"
0x2838  ldstr    aMsrsValidation// "msrs-validationerror"
0x283d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2842  ldloc.2
0x2843  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2848  ldarg.1
0x2849  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x284e  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0x2853  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2858  dup
0x2859  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0x285e  ldc.i4.0
0x285f  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::get_Item(int32)
0x2864  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::get_Cells()
0x2869  ldloc.2
0x286a  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell)
0x286f  ret
```
