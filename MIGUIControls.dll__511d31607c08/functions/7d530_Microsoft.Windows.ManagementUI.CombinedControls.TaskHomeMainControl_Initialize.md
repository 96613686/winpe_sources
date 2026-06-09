# Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::Initialize

- ea: `0x7d530`
- end: `0x7dac2`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::Initialize`
- size: `1426`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x12ed0`
- `0x1d560`
- `0x1d5b0`
- `0x1dba0`
- `0x1dbc0`
- `0x1dbe0`
- `0x1dbf0`
- `0x1dc10`
- `0x1de80`
- `0x1e040`
- `0x1e060`
- `0x7d3b0`
- `0x7d470`
- `0x7d530`
- `0x7dae0`
- `0x7ef40`
- `0x8b850`
- `0xa26e0`

## string_xrefs

- `0x7d6c6`: `DescriptionTaskSchedulerOverview`
- `0x7d7c1`: `TitleTaskSchedulerOverview`
- `0x7d85b`: `TitlePastTasks`
- `0x7d955`: `TitleActiveTasks`

## pseudocode

```c

```

## disassembly

```asm
0x7d530  ldarg.0
0x7d531  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::isInitialized
0x7d536  brtrue   loc_7DAC1
0x7d53b  ldarg.0
0x7d53c  newobj   instance void [System]System.ComponentModel.BackgroundWorker::.ctor()
0x7d541  stfld    class [System]System.ComponentModel.BackgroundWorker Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::dataReaderThread
0x7d546  ldarg.0
0x7d547  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7d54c  ldc.i4.1
0x7d54d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0x7d552  ldarg.0
0x7d553  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshStatusLabel
0x7d558  ldc.i4.1
0x7d559  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0x7d55e  ldarg.0
0x7d55f  ldarg.0
0x7d560  ldfld    class [mscorlib]System.EventHandler`1<class TaskHomePageUpdateUiArgs> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::uiUpdateDelegate
0x7d565  ldarg.0
0x7d566  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::UpdateUiDirectly(object sender, class TaskHomePageUpdateUiArgs updateUiArgs)
0x7d56c  newobj   instance void class [mscorlib]System.EventHandler`1<class TaskHomePageUpdateUiArgs>::.ctor(object, native int)
0x7d571  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x7d576  castclass class [mscorlib]System.EventHandler`1<class TaskHomePageUpdateUiArgs>
0x7d57b  stfld    class [mscorlib]System.EventHandler`1<class TaskHomePageUpdateUiArgs> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::uiUpdateDelegate
0x7d580  ldarg.0
0x7d581  ldfld    class [System]System.ComponentModel.BackgroundWorker Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::dataReaderThread
0x7d586  ldc.i4.1
0x7d587  callvirt instance void [System]System.ComponentModel.BackgroundWorker::set_WorkerSupportsCancellation(bool)
0x7d58c  ldarg.0
0x7d58d  ldfld    class [System]System.ComponentModel.BackgroundWorker Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::dataReaderThread
0x7d592  ldarg.0
0x7d593  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::ReadDataInBackgroundThread(object sender, class [System]System.ComponentModel.DoWorkEventArgs e)
0x7d599  newobj   instance void [System]System.ComponentModel.DoWorkEventHandler::.ctor(object, native int)
0x7d59e  callvirt instance void [System]System.ComponentModel.BackgroundWorker::add_DoWork(class [System]System.ComponentModel.DoWorkEventHandler)
0x7d5a3  ldarg.0
0x7d5a4  ldfld    class [System]System.ComponentModel.BackgroundWorker Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::dataReaderThread
0x7d5a9  ldarg.0
0x7d5aa  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::ReadDataInBackgroundCompleted(object sender, class [System]System.ComponentModel.RunWorkerCompletedEventArgs e)
0x7d5b0  newobj   instance void [System]System.ComponentModel.RunWorkerCompletedEventHandler::.ctor(object, native int)
0x7d5b5  callvirt instance void [System]System.ComponentModel.BackgroundWorker::add_RunWorkerCompleted(class [System]System.ComponentModel.RunWorkerCompletedEventHandler)
0x7d5ba  ldarg.0
0x7d5bb  ldc.i4.1
0x7d5bc  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::isInitialized
0x7d5c1  ldarg.0
0x7d5c2  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7d5c7  ldarg.0
0x7d5c8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::hideDetailControlHolder
0x7d5cd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7d5d2  ldarg.0
0x7d5d3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d5d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7d5dd  ldarg.0
0x7d5de  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTasksSummaryHideDetailControl
0x7d5e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7d5e8  ldarg.0
0x7d5e9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::activeTasksHideDetailControl
0x7d5ee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7d5f3  ldarg.0
0x7d5f4  ldc.i4.5
0x7d5f5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x7d5fa  ldarg.0
0x7d5fb  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x7d600  ldarg.0
0x7d601  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::hideDetailControlHolder
0x7d606  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x7d60b  ldarg.0
0x7d60c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::titlePanel
0x7d611  ldarg.0
0x7d612  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::titlePanel
0x7d617  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x7d61c  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Windows.Forms]System.Windows.Forms.Control::get_ClientSize()
0x7d621  stloc.s  4
0x7d623  ldloca.s 4
0x7d625  call     instance int32 [System.Drawing]System.Drawing.Size::get_Width()
0x7d62a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Width(int32)
0x7d62f  ldarg.0
0x7d630  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::titleLabel
0x7d635  call     void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::VerticalCentralizeInParent(class [System.Windows.Forms]System.Windows.Forms.Control control)
0x7d63a  ldarg.0
0x7d63b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshStatusLabel
0x7d640  call     void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::VerticalCentralizeInParent(class [System.Windows.Forms]System.Windows.Forms.Control control)
0x7d645  ldarg.0
0x7d646  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7d64b  call     void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::VerticalCentralizeInParent(class [System.Windows.Forms]System.Windows.Forms.Control control)
0x7d650  ldarg.0
0x7d651  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::AdjustRefreshButtonLocation()
0x7d656  call     class [System.Drawing]System.Drawing.Bitmap Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_SummaryIcon()
0x7d65b  newobj   instance void [System.Drawing]System.Drawing.Bitmap::.ctor(class [System.Drawing]System.Drawing.Image)
0x7d660  stloc.0
0x7d661  ldloc.0
0x7d662  ldc.i4   0xFF
0x7d667  ldc.i4.0
0x7d668  ldc.i4   0xFF
0x7d66d  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::FromArgb(int32, int32, int32)
0x7d672  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent(valuetype [System.Drawing]System.Drawing.Color)
0x7d677  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x7d67c  stloc.1
0x7d67d  ldloc.1
0x7d67e  ldc.i4.s 0xA
0x7d680  ldc.i4.s 0xA
0x7d682  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x7d687  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x7d68c  ldloc.1
0x7d68d  ldc.i4.s 0x20
0x7d68f  ldc.i4.s 0x20
0x7d691  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x7d696  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x7d69b  ldloc.1
0x7d69c  ldloc.0
0x7d69d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_Image(class [System.Drawing]System.Drawing.Image)
0x7d6a2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7d6a7  stloc.2
0x7d6a8  ldloc.2
0x7d6a9  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0x7d6ae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x7d6b3  ldloc.2
0x7d6b4  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlText()
0x7d6b9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ForeColor(valuetype [System.Drawing]System.Drawing.Color)
0x7d6be  ldloc.2
0x7d6bf  ldc.i4.1
0x7d6c0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0x7d6c5  ldloc.2
0x7d6c6  ldstr    aDescriptiontas// "DescriptionTaskSchedulerOverview"
0x7d6cb  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d6d0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7d6d5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0x7d6da  stloc.3
0x7d6db  ldloc.3
0x7d6dc  ldc.i4.s 0x2F
0x7d6de  ldc.i4.s 0xA
0x7d6e0  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x7d6e5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x7d6ea  ldloc.3
0x7d6eb  ldarg.0
0x7d6ec  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d6f1  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::get_DetailPanelWidth()
0x7d6f6  ldc.i4.s 0x14
0x7d6f8  sub
0x7d6f9  ldc.i4.s 0x20
0x7d6fb  sub
0x7d6fc  ldc.i4.5
0x7d6fd  sub
0x7d6fe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Width(int32)
0x7d703  ldloc.3
0x7d704  ldc.i4.s 0x23
0x7d706  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0x7d70b  ldloc.3
0x7d70c  ldc.i4.1
0x7d70d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScroll(bool)
0x7d712  ldloc.3
0x7d713  ldc.i4.1
0x7d714  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0x7d719  ldloc.3
0x7d71a  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0x7d71f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x7d724  ldloc.3
0x7d725  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlText()
0x7d72a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ForeColor(valuetype [System.Drawing]System.Drawing.Color)
0x7d72f  ldloc.3
0x7d730  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x7d735  ldloc.2
0x7d736  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x7d73b  ldloc.3
0x7d73c  ldc.i4.s 0xD
0x7d73e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x7d743  ldarg.0
0x7d744  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::hideDetailControlHolder
0x7d749  ldc.i4.1
0x7d74a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder::set_AdjustHeightOnHeightChange(bool value)
0x7d74f  ldarg.0
0x7d750  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::hideDetailControlHolder
0x7d755  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7d75a  ldarg.0
0x7d75b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::hideDetailControlHolder
0x7d760  ldc.i4.s 0xA
0x7d762  ldc.i4.s 0xA
0x7d764  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x7d769  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScrollMargin(valuetype [System.Drawing]System.Drawing.Size)
0x7d76e  ldarg.0
0x7d76f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::hideDetailControlHolder
0x7d774  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x7d779  ldarg.0
0x7d77a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d77f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x7d784  ldarg.0
0x7d785  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::hideDetailControlHolder
0x7d78a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x7d78f  ldarg.0
0x7d790  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTasksSummaryHideDetailControl
0x7d795  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x7d79a  ldarg.0
0x7d79b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControlHolder Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::hideDetailControlHolder
0x7d7a0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x7d7a5  ldarg.0
0x7d7a6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::activeTasksHideDetailControl
0x7d7ab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x7d7b0  ldarg.0
0x7d7b1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d7b6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7d7bb  ldarg.0
0x7d7bc  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d7c1  ldstr    aTitletasksched// "TitleTaskSchedulerOverview"
0x7d7c6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d7cb  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::SetTitleText(string newTitle)
0x7d7d0  ldarg.0
0x7d7d1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d7d6  ldloc.1
0x7d7d7  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::AddControlToDetailPanel(class [System.Windows.Forms]System.Windows.Forms.Control control)
0x7d7dc  ldarg.0
0x7d7dd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d7e2  ldloc.3
0x7d7e3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::AddControlToDetailPanel(class [System.Windows.Forms]System.Windows.Forms.Control control)
0x7d7e8  ldarg.0
0x7d7e9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d7ee  ldc.i4.s 0xA
0x7d7f0  ldc.i4.s 0xA
0x7d7f2  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x7d7f7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x7d7fc  ldarg.0
0x7d7fd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d802  ldarg.0
0x7d803  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d808  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::get_HeaderPanelHeight()
0x7d80d  ldloc.3
0x7d80e  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0x7d813  add
0x7d814  ldc.i4.s 0x14
0x7d816  add
0x7d817  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0x7d81c  ldarg.0
0x7d81d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d822  ldc.i4.1
0x7d823  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::set_IsFixedHeight(bool value)
0x7d828  ldarg.0
0x7d829  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d82e  ldarg.0
0x7d82f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d834  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0x7d839  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::set_FixedHeight(int32 value)
0x7d83e  ldarg.0
0x7d83f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d844  ldc.i4.1
0x7d845  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x7d84a  ldarg.0
0x7d84b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTasksSummaryHideDetailControl
0x7d850  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7d855  ldarg.0
0x7d856  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTasksSummaryHideDetailControl
0x7d85b  ldstr    aTitlepasttasks// "TitlePastTasks"
0x7d860  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d865  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::SetTitleText(string newTitle)
0x7d86a  ldarg.0
0x7d86b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTasksSummaryHideDetailControl
0x7d870  ldarg.0
0x7d871  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityControl
0x7d876  ldc.i4.1
0x7d877  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::AddControlToDetailPanel(class [System.Windows.Forms]System.Windows.Forms.Control control, bool isMainControl)
0x7d87c  ldarg.0
0x7d87d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTasksSummaryHideDetailControl
0x7d882  ldarg.0
0x7d883  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTasksSummaryHideDetailControl
0x7d888  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::get_HeaderPanelHeight()
0x7d88d  ldarg.0
0x7d88e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityControl
0x7d893  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0x7d898  add
0x7d899  ldc.i4.s 0x14
0x7d89b  add
0x7d89c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0x7d8a1  ldarg.0
0x7d8a2  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTasksSummaryHideDetailControl
0x7d8a7  ldc.i4.s 0xA
0x7d8a9  ldarg.0
0x7d8aa  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d8af  callvirt instance valuetype [System.Drawing]System.Drawing.Point [System.Windows.Forms]System.Windows.Forms.Control::get_Location()
0x7d8b4  stloc.s  5
0x7d8b6  ldloca.s 5
0x7d8b8  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0x7d8bd  ldarg.0
0x7d8be  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::overviewHideDetailControl
0x7d8c3  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0x7d8c8  add
0x7d8c9  ldc.i4.s 0xA
0x7d8cb  add
0x7d8cc  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x7d8d1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x7d8d6  ldarg.0
0x7d8d7  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTasksSummaryHideDetailControl
0x7d8dc  ldc.i4.0
0x7d8dd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::set_IsFixedHeight(bool value)
0x7d8e2  ldarg.0
0x7d8e3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTasksSummaryHideDetailControl
0x7d8e8  ldarg.0
0x7d8e9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTasksSummaryHideDetailControl
0x7d8ee  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0x7d8f3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl::set_MinHeight(int32 value)
0x7d8f8  ldarg.0
0x7d8f9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.HideDetailControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTasksSummaryHideDetailControl
0x7d8fe  ldc.i4.1
0x7d8ff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x7d904  ldarg.0
  ... truncated ...
```
