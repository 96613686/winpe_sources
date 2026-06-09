# System.Web.Handlers.TraceHandler::ShowRequests

- ea: `0x4adb0`
- end: `0x4b170`
- name: `System.Web.Handlers.TraceHandler::ShowRequests`
- size: `960`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `loader_planting`

## callers

- `0x4a930`

## callees

- `0x1bed0`
- `0x1bef0`
- `0x23f90`
- `0x241c0`
- `0x26030`
- `0x34fa0`
- `0x4adb0`
- `0x4b170`
- `0x4b190`
- `0x4b1b0`
- `0x57600`
- `0x5b120`
- `0x60ef0`
- `0x611a0`
- `0x66310`
- `0x88580`
- `0x885f0`
- `0x88bf0`
- `0x88d10`
- `0xdce40`
- `0xdcf50`
- `0xdcf90`
- `0xdd450`
- `0xdd4a0`
- `0xde160`
- `0xe9000`
- `0xea690`
- `0xea9c0`

## string_xrefs

- `0x4ae35`: `[ <a href="Trace.axd?clear=1" class="link">`
- `0x4ae62`: `Trace_Physical_Directory`

## pseudocode

```c

```

## disassembly

```asm
0x4adb0  newobj   instance void System.Web.UI.WebControls.Table::.ctor()
0x4adb5  stloc.0
0x4adb6  ldloc.0
0x4adb7  ldc.i4.0
0x4adb8  callvirt instance void System.Web.UI.WebControls.Table::set_CellPadding(int32 value)
0x4adbd  ldloc.0
0x4adbe  ldc.i4.0
0x4adbf  callvirt instance void System.Web.UI.WebControls.Table::set_CellSpacing(int32 value)
0x4adc4  ldloc.0
0x4adc5  ldc.r8   100.0
0x4adce  call     valuetype System.Web.UI.WebControls.Unit System.Web.UI.WebControls.Unit::Percentage(float64 n)
0x4add3  callvirt instance void System.Web.UI.WebControls.WebControl::set_Width(valuetype System.Web.UI.WebControls.Unit value)
0x4add8  ldloc.0
0x4add9  call     class System.Web.UI.WebControls.TableRow System.Web.Handlers.TraceHandler::AddRow(class System.Web.UI.WebControls.Table t)
0x4adde  stloc.1
0x4addf  ldloc.1
0x4ade0  ldstr    aTraceApplicati_1// "Trace_Application_Trace"
0x4ade5  call     string System.Web.SR::GetString(string name)
0x4adea  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4adef  pop
0x4adf0  ldarg.0
0x4adf1  ldfld    class System.Web.HttpRequest System.Web.Handlers.TraceHandler::_request
0x4adf6  callvirt instance string System.Web.HttpRequest::get_ApplicationPath()
0x4adfb  stloc.3
0x4adfc  ldloc.3
0x4adfd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4ae02  stloc.s  4
0x4ae04  ldloc.0
0x4ae05  call     class System.Web.UI.WebControls.TableRow System.Web.Handlers.TraceHandler::AddRow(class System.Web.UI.WebControls.Table t)
0x4ae0a  stloc.1
0x4ae0b  ldloc.1
0x4ae0c  ldstr    aH2// "<h2>"
0x4ae11  ldloc.3
0x4ae12  ldc.i4.1
0x4ae13  callvirt instance string [mscorlib]System.String::Substring(int32)
0x4ae18  call     string System.Web.HttpUtility::HtmlEncode(string s)
0x4ae1d  ldstr    aH2P// "<h2><p>"
0x4ae22  call     string [mscorlib]System.String::Concat(string, string, string)
0x4ae27  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4ae2c  pop
0x4ae2d  ldloc.0
0x4ae2e  call     class System.Web.UI.WebControls.TableRow System.Web.Handlers.TraceHandler::AddRow(class System.Web.UI.WebControls.Table t)
0x4ae33  stloc.1
0x4ae34  ldloc.1
0x4ae35  ldstr    aAHrefTraceAxdC// "[ <a href=\"Trace.axd?clear=1\" class="...
0x4ae3a  ldstr    aTraceClearCurr// "Trace_Clear_Current"
0x4ae3f  call     string System.Web.SR::GetString(string name)
0x4ae44  ldstr    aA_0// "</a> ]"
0x4ae49  call     string [mscorlib]System.String::Concat(string, string, string)
0x4ae4e  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4ae53  pop
0x4ae54  ldstr    aNbsp_0// "&nbsp"
0x4ae59  stloc.s  5
0x4ae5b  call     bool System.Web.HttpRuntime::HasAppPathDiscoveryPermission()
0x4ae60  brfalse.s loc_4AE7E
0x4ae62  ldstr    aTracePhysicalD// "Trace_Physical_Directory"
0x4ae67  call     string System.Web.SR::GetString(string name)
0x4ae6c  ldarg.0
0x4ae6d  ldfld    class System.Web.HttpRequest System.Web.Handlers.TraceHandler::_request
0x4ae72  callvirt instance string System.Web.HttpRequest::get_PhysicalApplicationPath()
0x4ae77  call     string [mscorlib]System.String::Concat(string, string)
0x4ae7c  stloc.s  5
0x4ae7e  ldloc.0
0x4ae7f  call     class System.Web.UI.WebControls.TableRow System.Web.Handlers.TraceHandler::AddRow(class System.Web.UI.WebControls.Table t)
0x4ae84  stloc.1
0x4ae85  ldloc.1
0x4ae86  ldloc.s  5
0x4ae88  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4ae8d  stloc.2
0x4ae8e  ldloc.0
0x4ae8f  ldarg.0
0x4ae90  ldfld    class System.Web.UI.HtmlTextWriter System.Web.Handlers.TraceHandler::_writer
0x4ae95  callvirt instance void System.Web.UI.Control::RenderControl(class System.Web.UI.HtmlTextWriter writer)
0x4ae9a  newobj   instance void System.Web.UI.WebControls.Table::.ctor()
0x4ae9f  stloc.0
0x4aea0  ldloc.0
0x4aea1  ldc.i4.0
0x4aea2  callvirt instance void System.Web.UI.WebControls.Table::set_CellPadding(int32 value)
0x4aea7  ldloc.0
0x4aea8  ldc.i4.0
0x4aea9  callvirt instance void System.Web.UI.WebControls.Table::set_CellSpacing(int32 value)
0x4aeae  ldloc.0
0x4aeaf  ldc.r8   100.0
0x4aeb8  call     valuetype System.Web.UI.WebControls.Unit System.Web.UI.WebControls.Unit::Percentage(float64 n)
0x4aebd  callvirt instance void System.Web.UI.WebControls.WebControl::set_Width(valuetype System.Web.UI.WebControls.Unit value)
0x4aec2  ldloc.0
0x4aec3  call     class System.Web.UI.WebControls.TableRow System.Web.Handlers.TraceHandler::AddRow(class System.Web.UI.WebControls.Table t)
0x4aec8  stloc.1
0x4aec9  ldloc.1
0x4aeca  ldstr    aH3B// "<h3><b>"
0x4aecf  ldstr    aTraceRequestsT// "Trace_Requests_This"
0x4aed4  call     string System.Web.SR::GetString(string name)
0x4aed9  ldstr    aBH3// "</b></h3>"
0x4aede  call     string [mscorlib]System.String::Concat(string, string, string)
0x4aee3  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddHeaderCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4aee8  stloc.2
0x4aee9  ldloc.2
0x4aeea  ldc.i4.5
0x4aeeb  callvirt instance void System.Web.UI.WebControls.TableCell::set_ColumnSpan(int32 value)
0x4aef0  ldloc.2
0x4aef1  ldstr    aAlt// "alt"
0x4aef6  callvirt instance void System.Web.UI.WebControls.WebControl::set_CssClass(string value)
0x4aefb  ldloc.2
0x4aefc  ldc.i4.1
0x4aefd  callvirt instance void System.Web.UI.WebControls.TableCell::set_HorizontalAlign(valuetype System.Web.UI.WebControls.HorizontalAlign value)
0x4af02  ldloc.1
0x4af03  ldstr    aTraceRemaining// "Trace_Remaining"
0x4af08  call     string System.Web.SR::GetString(string name)
0x4af0d  ldstr    asc_1B0CBE// " "
0x4af12  call     class System.Web.Util.Profiler System.Web.HttpRuntime::get_Profile()
0x4af17  callvirt instance int32 System.Web.Util.Profiler::get_RequestsRemaining()
0x4af1c  stloc.s  7
0x4af1e  ldloca.s 7
0x4af20  call     class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.NumberFormatInfo::get_InvariantInfo()
0x4af25  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4af2a  call     string [mscorlib]System.String::Concat(string, string, string)
0x4af2f  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddHeaderCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4af34  stloc.2
0x4af35  ldloc.2
0x4af36  ldstr    aAlt// "alt"
0x4af3b  callvirt instance void System.Web.UI.WebControls.WebControl::set_CssClass(string value)
0x4af40  ldloc.2
0x4af41  ldc.i4.3
0x4af42  callvirt instance void System.Web.UI.WebControls.TableCell::set_HorizontalAlign(valuetype System.Web.UI.WebControls.HorizontalAlign value)
0x4af47  ldloc.0
0x4af48  call     class System.Web.UI.WebControls.TableRow System.Web.Handlers.TraceHandler::AddRow(class System.Web.UI.WebControls.Table t)
0x4af4d  stloc.1
0x4af4e  ldloc.1
0x4af4f  ldc.i4.1
0x4af50  callvirt instance void System.Web.UI.WebControls.TableRow::set_HorizontalAlign(valuetype System.Web.UI.WebControls.HorizontalAlign value)
0x4af55  ldloc.1
0x4af56  ldstr    aSubhead// "subhead"
0x4af5b  callvirt instance void System.Web.UI.WebControls.WebControl::set_CssClass(string value)
0x4af60  ldloc.1
0x4af61  ldstr    aTraceNo// "Trace_No"
0x4af66  call     string System.Web.SR::GetString(string name)
0x4af6b  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddHeaderCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4af70  pop
0x4af71  ldloc.1
0x4af72  ldstr    aTraceTimeOfReq// "Trace_Time_of_Request"
0x4af77  call     string System.Web.SR::GetString(string name)
0x4af7c  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddHeaderCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4af81  pop
0x4af82  ldloc.1
0x4af83  ldstr    aTraceFile// "Trace_File"
0x4af88  call     string System.Web.SR::GetString(string name)
0x4af8d  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddHeaderCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4af92  pop
0x4af93  ldloc.1
0x4af94  ldstr    aTraceStatusCod// "Trace_Status_Code"
0x4af99  call     string System.Web.SR::GetString(string name)
0x4af9e  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddHeaderCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4afa3  pop
0x4afa4  ldloc.1
0x4afa5  ldstr    aTraceVerb// "Trace_Verb"
0x4afaa  call     string System.Web.SR::GetString(string name)
0x4afaf  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddHeaderCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4afb4  pop
0x4afb5  ldloc.1
0x4afb6  ldstr    aNbsp_0// "&nbsp"
0x4afbb  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddHeaderCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4afc0  pop
0x4afc1  ldc.i4.1
0x4afc2  stloc.s  6
0x4afc4  ldc.i4.0
0x4afc5  stloc.s  8
0x4afc7  br       loc_4B156
0x4afcc  ldarg.1
0x4afcd  ldloc.s  8
0x4afcf  callvirt instance object [mscorlib]System.Collections.IList::get_Item(int32)
0x4afd4  castclass [System.Data]System.Data.DataSet
0x4afd9  stloc.s  9
0x4afdb  ldloc.0
0x4afdc  call     class System.Web.UI.WebControls.TableRow System.Web.Handlers.TraceHandler::AddRow(class System.Web.UI.WebControls.Table t)
0x4afe1  stloc.1
0x4afe2  ldloc.s  6
0x4afe4  brfalse.s loc_4AFF1
0x4afe6  ldloc.1
0x4afe7  ldstr    aAlt// "alt"
0x4afec  callvirt instance void System.Web.UI.WebControls.WebControl::set_CssClass(string value)
0x4aff1  ldloc.1
0x4aff2  ldloc.s  8
0x4aff4  ldc.i4.1
0x4aff5  add
0x4aff6  stloc.s  7
0x4aff8  ldloca.s 7
0x4affa  call     class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.NumberFormatInfo::get_InvariantInfo()
0x4afff  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4b004  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4b009  pop
0x4b00a  ldloc.1
0x4b00b  ldloc.s  9
0x4b00d  callvirt instance class [System.Data]System.Data.DataTableCollection [System.Data]System.Data.DataSet::get_Tables()
0x4b012  ldstr    aTraceRequest// "Trace_Request"
0x4b017  callvirt instance class [System.Data]System.Data.DataTable [System.Data]System.Data.DataTableCollection::get_Item(string)
0x4b01c  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x4b021  ldc.i4.0
0x4b022  callvirt instance class [System.Data]System.Data.DataRow [System.Data]System.Data.DataRowCollection::get_Item(int32)
0x4b027  ldstr    aTraceTimeOfReq// "Trace_Time_of_Request"
0x4b02c  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x4b031  castclass [mscorlib]System.String
0x4b036  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4b03b  pop
0x4b03c  ldloc.1
0x4b03d  ldloc.s  9
0x4b03f  callvirt instance class [System.Data]System.Data.DataTableCollection [System.Data]System.Data.DataSet::get_Tables()
0x4b044  ldstr    aTraceRequest// "Trace_Request"
0x4b049  callvirt instance class [System.Data]System.Data.DataTable [System.Data]System.Data.DataTableCollection::get_Item(string)
0x4b04e  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x4b053  ldc.i4.0
0x4b054  callvirt instance class [System.Data]System.Data.DataRow [System.Data]System.Data.DataRowCollection::get_Item(int32)
0x4b059  ldstr    aTraceUrl// "Trace_Url"
0x4b05e  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x4b063  castclass [mscorlib]System.String
0x4b068  call     string System.Web.HttpUtility::HtmlEncode(string s)
0x4b06d  ldloc.s  4
0x4b06f  callvirt instance string [mscorlib]System.String::Substring(int32)
0x4b074  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4b079  pop
0x4b07a  ldloc.1
0x4b07b  ldloc.s  9
0x4b07d  callvirt instance class [System.Data]System.Data.DataTableCollection [System.Data]System.Data.DataSet::get_Tables()
0x4b082  ldstr    aTraceRequest// "Trace_Request"
0x4b087  callvirt instance class [System.Data]System.Data.DataTable [System.Data]System.Data.DataTableCollection::get_Item(string)
0x4b08c  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x4b091  ldc.i4.0
0x4b092  callvirt instance class [System.Data]System.Data.DataRow [System.Data]System.Data.DataRowCollection::get_Item(int32)
0x4b097  ldstr    aTraceStatusCod// "Trace_Status_Code"
0x4b09c  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x4b0a1  callvirt instance string [mscorlib]System.Object::ToString()
0x4b0a6  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4b0ab  pop
0x4b0ac  ldloc.1
0x4b0ad  ldloc.s  9
0x4b0af  callvirt instance class [System.Data]System.Data.DataTableCollection [System.Data]System.Data.DataSet::get_Tables()
0x4b0b4  ldstr    aTraceRequest// "Trace_Request"
0x4b0b9  callvirt instance class [System.Data]System.Data.DataTable [System.Data]System.Data.DataTableCollection::get_Item(string)
0x4b0be  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x4b0c3  ldc.i4.0
0x4b0c4  callvirt instance class [System.Data]System.Data.DataRow [System.Data]System.Data.DataRowCollection::get_Item(int32)
0x4b0c9  ldstr    aTraceRequestTy// "Trace_Request_Type"
0x4b0ce  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x4b0d3  castclass [mscorlib]System.String
0x4b0d8  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4b0dd  pop
0x4b0de  ldloc.1
0x4b0df  ldsfld   string [mscorlib]System.String::Empty
0x4b0e4  call     class System.Web.UI.WebControls.TableCell System.Web.Handlers.TraceHandler::AddCell(class System.Web.UI.WebControls.TableRow trow, string text)
0x4b0e9  stloc.s  0xA
0x4b0eb  newobj   instance void System.Web.UI.HtmlControls.HtmlAnchor::.ctor()
0x4b0f0  stloc.s  0xB
0x4b0f2  ldloc.s  0xB
0x4b0f4  ldstr    aTraceAxdId// "Trace.axd?id="
0x4b0f9  ldloca.s 8
0x4b0fb  call     instance string [mscorlib]System.Int32::ToString()
0x4b100  call     string [mscorlib]System.String::Concat(string, string)
0x4b105  callvirt instance void System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string value)
0x4b10a  ldloc.s  0xB
0x4b10c  ldstr    aNobr// "<nobr>"
0x4b111  ldstr    aTraceViewDetai// "Trace_View_Details"
0x4b116  call     string System.Web.SR::GetString(string name)
0x4b11b  call     string [mscorlib]System.String::Concat(string, string)
0x4b120  callvirt instance void System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string value)
0x4b125  ldloc.s  0xB
0x4b127  callvirt instance class System.Web.UI.AttributeCollection System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x4b12c  ldstr    aClass// "class"
0x4b131  ldstr    aLink// "link"
0x4b136  callvirt instance void System.Web.UI.AttributeCollection::set_Item(string key, string value)
0x4b13b  ldloc.s  0xA
0x4b13d  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0x4b142  ldloc.s  0xB
0x4b144  callvirt instance void System.Web.UI.ControlCollection::Add(class System.Web.UI.Control child)
0x4b149  ldloc.s  6
0x4b14b  ldc.i4.0
0x4b14c  ceq
0x4b14e  stloc.s  6
0x4b150  ldloc.s  8
0x4b152  ldc.i4.1
0x4b153  add
0x4b154  stloc.s  8
0x4b156  ldloc.s  8
0x4b158  ldarg.1
0x4b159  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x4b15e  blt      loc_4AFCC
0x4b163  ldloc.0
0x4b164  ldarg.0
0x4b165  ldfld    class System.Web.UI.HtmlTextWriter System.Web.Handlers.TraceHandler::_writer
0x4b16a  callvirt instance void System.Web.UI.Control::RenderControl(class System.Web.UI.HtmlTextWriter writer)
0x4b16f  ret
```
