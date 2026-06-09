# Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::Initialize

- ea: `0x280e0`
- end: `0x28c3a`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::Initialize`
- size: `2906`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x12ed0`
- `0x1bb30`
- `0x1bc80`
- `0x1be50`
- `0x1d560`
- `0x1d5b0`
- `0x1dba0`
- `0x1dbc0`
- `0x1dbf0`
- `0x1dc10`
- `0x1de30`
- `0x1de80`
- `0x1e040`
- `0x1e060`
- `0x1fc40`
- `0x1fd20`
- `0x1fd40`
- `0x28010`
- `0x280e0`
- `0x290d0`
- `0x2a4c0`

## string_xrefs

- `0x28851`: `Created`

## pseudocode

```c

```

## disassembly

```asm
0x280e0  ldarg.0
0x280e1  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::initialized
0x280e6  brfalse.s loc_280E9
0x280e8  ret
0x280e9  ldarg.0
0x280ea  ldc.i4.1
0x280eb  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::initialized
0x280f0  ldarg.0
0x280f1  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x280f6  ldarg.0
0x280f7  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::hideDetailControlHolder
0x280fc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x28101  ldarg.0
0x28102  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x28107  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2810c  ldarg.0
0x2810d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryHideDetailControl
0x28112  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x28117  ldarg.0
0x28118  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::recentViewsHideDetailControl
0x2811d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x28122  ldarg.0
0x28123  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::logSummaryHideDetailControl
0x28128  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2812d  ldarg.0
0x2812e  ldc.i4.5
0x2812f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x28134  ldarg.0
0x28135  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx::.ctor()
0x2813a  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryListView
0x2813f  ldarg.0
0x28140  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx::.ctor()
0x28145  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::recentViewsListView
0x2814a  ldarg.0
0x2814b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx::.ctor()
0x28150  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::logSummaryListView
0x28155  ldarg.0
0x28156  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x2815b  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryLabel
0x28160  ldarg.0
0x28161  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x28166  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::logSummaryLabel
0x2816b  ldarg.0
0x2816c  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x28171  ldarg.0
0x28172  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::hideDetailControlHolder
0x28177  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2817c  ldarg.0
0x2817d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::hideDetailControlHolder
0x28182  ldc.i4.s 0xA
0x28184  ldc.i4.s 0xA
0x28186  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2818b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScrollMargin(valuetype [System.Drawing]System.Drawing.Size)
0x28190  ldarg.0
0x28191  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::hideDetailControlHolder
0x28196  ldc.i4.1
0x28197  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder::set_AdjustHeightOnHeightChange(bool value)
0x2819c  ldarg.0
0x2819d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::titlePanel
0x281a2  ldarg.0
0x281a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::titlePanel
0x281a8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x281ad  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Windows.Forms]System.Windows.Forms.Control::get_ClientSize()
0x281b2  stloc.s  6
0x281b4  ldloca.s 6
0x281b6  call     instance int32 [System.Drawing]System.Drawing.Size::get_Width()
0x281bb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Width(int32)
0x281c0  ldarg.0
0x281c1  ldarg.0
0x281c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventViewerLabel
0x281c7  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::VerticalCentralizeInParent(class [System.Windows.Forms]System.Windows.Forms.Control control)
0x281cc  call     class [System.Drawing]System.Drawing.Bitmap Microsoft.Windows.ManagementUI.CombinedControls.EvtResources::get_evtsnapin()
0x281d1  newobj   instance void [System.Drawing]System.Drawing.Bitmap::.ctor(class [System.Drawing]System.Drawing.Image)
0x281d6  stloc.0
0x281d7  ldloc.0
0x281d8  ldc.i4   0xFF
0x281dd  ldc.i4.0
0x281de  ldc.i4   0xFF
0x281e3  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::FromArgb(int32, int32, int32)
0x281e8  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent(valuetype [System.Drawing]System.Drawing.Color)
0x281ed  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x281f2  stloc.1
0x281f3  ldloc.1
0x281f4  ldc.i4.s 0xA
0x281f6  ldc.i4.s 0xA
0x281f8  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x281fd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x28202  ldloc.1
0x28203  ldc.i4.s 0x20
0x28205  ldc.i4.s 0x20
0x28207  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2820c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x28211  ldloc.1
0x28212  ldloc.0
0x28213  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_Image(class [System.Drawing]System.Drawing.Image)
0x28218  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x2821d  stloc.2
0x2821e  ldloc.2
0x2821f  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlText()
0x28224  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ForeColor(valuetype [System.Drawing]System.Drawing.Color)
0x28229  ldloc.2
0x2822a  ldc.i4.1
0x2822b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0x28230  ldloc.2
0x28231  ldstr    aOverviewofeven// "OverviewOfEventViewerText"
0x28236  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x2823b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x28240  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0x28245  stloc.3
0x28246  ldloc.3
0x28247  ldc.i4.s 0x2F
0x28249  ldc.i4.s 0xA
0x2824b  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x28250  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x28255  ldloc.3
0x28256  ldarg.0
0x28257  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x2825c  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::get_DetailPanelWidth()
0x28261  ldc.i4.s 0x14
0x28263  sub
0x28264  ldc.i4.s 0x20
0x28266  sub
0x28267  ldc.i4.5
0x28268  sub
0x28269  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Width(int32)
0x2826e  ldloc.3
0x2826f  ldc.i4.s 0x23
0x28271  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0x28276  ldloc.3
0x28277  ldc.i4.1
0x28278  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScroll(bool)
0x2827d  ldloc.3
0x2827e  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlText()
0x28283  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ForeColor(valuetype [System.Drawing]System.Drawing.Color)
0x28288  ldloc.3
0x28289  ldc.i4.1
0x2828a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0x2828f  ldloc.3
0x28290  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x28295  ldloc.2
0x28296  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2829b  ldloc.3
0x2829c  ldc.i4.s 0xD
0x2829e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x282a3  ldarg.0
0x282a4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::hideDetailControlHolder
0x282a9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x282ae  ldarg.0
0x282af  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x282b4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x282b9  ldarg.0
0x282ba  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x282bf  ldstr    aOverviewofeven_0// "OverviewOfEventViewer"
0x282c4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x282c9  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::SetTitleText(string newTitle)
0x282ce  ldarg.0
0x282cf  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x282d4  ldloc.1
0x282d5  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::AddControlToDetailPanel(class [System.Windows.Forms]System.Windows.Forms.Control control)
0x282da  ldarg.0
0x282db  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x282e0  ldloc.3
0x282e1  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::AddControlToDetailPanel(class [System.Windows.Forms]System.Windows.Forms.Control control)
0x282e6  ldarg.0
0x282e7  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x282ec  ldarg.0
0x282ed  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x282f2  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::get_HeaderPanelHeight()
0x282f7  ldloc.3
0x282f8  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0x282fd  add
0x282fe  ldc.i4.s 0x14
0x28300  add
0x28301  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0x28306  ldarg.0
0x28307  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x2830c  ldarg.0
0x2830d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x28312  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0x28317  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::set_FixedHeight(int32 value)
0x2831c  ldarg.0
0x2831d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x28322  ldc.i4.1
0x28323  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::set_IsFixedHeight(bool value)
0x28328  ldarg.0
0x28329  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x2832e  ldc.i4.s 0xA
0x28330  ldc.i4.s 0xA
0x28332  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x28337  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2833c  ldarg.0
0x2833d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x28342  ldc.i4.1
0x28343  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x28348  ldarg.0
0x28349  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryHideDetailControl
0x2834e  ldstr    aSummaryofallev// "SummaryOfAllEvents"
0x28353  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x28358  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::SetTitleText(string newTitle)
0x2835d  ldarg.0
0x2835e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryHideDetailControl
0x28363  ldarg.0
0x28364  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::OneOfListViewsVisibleChanged(object sender, class [mscorlib]System.EventArgs e)
0x2836a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x2836f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::AddDetailPanelVisibleChangedHandler(class [mscorlib]System.EventHandler handler)
0x28374  ldarg.0
0x28375  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryHideDetailControl
0x2837a  ldarg.0
0x2837b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryHideDetailControl
0x28380  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::get_HeaderPanelHeight()
0x28385  ldarg.0
0x28386  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryListView
0x2838b  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0x28390  add
0x28391  ldc.i4.s 0x14
0x28393  add
0x28394  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0x28399  ldarg.0
0x2839a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryHideDetailControl
0x2839f  ldarg.0
0x283a0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryHideDetailControl
0x283a5  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0x283aa  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::set_FixedHeight(int32 value)
0x283af  ldarg.0
0x283b0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryHideDetailControl
0x283b5  ldc.i4.0
0x283b6  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::set_IsFixedHeight(bool value)
0x283bb  ldarg.0
0x283bc  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryHideDetailControl
0x283c1  ldc.i4.s 0xA
0x283c3  ldarg.0
0x283c4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x283c9  callvirt instance valuetype [System.Drawing]System.Drawing.Point [System.Windows.Forms]System.Windows.Forms.Control::get_Location()
0x283ce  stloc.s  7
0x283d0  ldloca.s 7
0x283d2  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0x283d7  ldarg.0
0x283d8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::overviewHideDetailControl
0x283dd  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0x283e2  add
0x283e3  ldc.i4.s 0xA
0x283e5  add
0x283e6  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x283eb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x283f0  ldarg.0
0x283f1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryHideDetailControl
0x283f6  ldarg.0
0x283f7  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryListView
0x283fc  ldc.i4.1
0x283fd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::AddControlToDetailPanel(class [System.Windows.Forms]System.Windows.Forms.Control control, bool isMainControl)
0x28402  ldarg.0
0x28403  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryHideDetailControl
0x28408  ldarg.0
0x28409  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryLabel
0x2840e  ldc.i4.0
0x2840f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::AddControlToDetailPanel(class [System.Windows.Forms]System.Windows.Forms.Control control, bool isMainControl)
0x28414  ldarg.0
0x28415  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryHideDetailControl
0x2841a  ldc.i4.1
0x2841b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x28420  ldarg.0
0x28421  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryListView
0x28426  ldc.i4.1
0x28427  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HeaderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ColumnHeaderStyle)
0x2842c  ldarg.0
0x2842d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryListView
0x28432  ldc.i4.1
0x28433  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_FullRowSelect(bool)
0x28438  ldarg.0
0x28439  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryListView
0x2843e  ldc.i4.1
0x2843f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_ShowItemToolTips(bool)
0x28444  ldarg.0
0x28445  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryListView
0x2844a  ldc.i4.s 0xA
0x2844c  ldc.i4.s 0xA
0x2844e  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x28453  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x28458  ldarg.0
0x28459  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryListView
0x2845e  ldc.i4   0xC8
0x28463  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0x28468  ldarg.0
0x28469  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryListView
0x2846e  ldc.i4.0
0x2846f  ldarg.0
0x28470  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryListView
0x28475  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x2847a  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Windows.Forms]System.Windows.Forms.Control::get_ClientSize()
0x2847f  stloc.s  6
0x28481  ldloca.s 6
0x28483  call     instance int32 [System.Drawing]System.Drawing.Size::get_Width()
0x28488  ldc.i4.2
0x28489  ldarg.0
0x2848a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryListView
0x2848f  callvirt instance valuetype [System.Drawing]System.Drawing.Point [System.Windows.Forms]System.Windows.Forms.Control::get_Location()
0x28494  stloc.s  7
0x28496  ldloca.s 7
0x28498  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0x2849d  mul
  ... truncated ...
```
