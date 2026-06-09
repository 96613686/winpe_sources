# Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::InitializeComponent

- ea: `0x8d8c0`
- end: `0x8dcfe`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::InitializeComponent`
- size: `1086`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x8d4e0`

## callees

- `0x5cf10`
- `0x5cf30`
- `0x5cf60`

## string_xrefs

- `0x8d955`: `deleteButton`
- `0x8d965`: `deleteButton`

## pseudocode

```c

```

## disassembly

```asm
0x8d8c0  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView
0x8d8c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8d8ca  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x8d8cf  ldarg.0
0x8d8d0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x8d8d5  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::deleteButton
0x8d8da  ldarg.0
0x8d8db  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x8d8e0  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::propertiesButton
0x8d8e5  ldarg.0
0x8d8e6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x8d8eb  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::enableDisableButton
0x8d8f0  ldarg.0
0x8d8f1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x8d8f6  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::retryButton
0x8d8fb  ldarg.0
0x8d8fc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x8d901  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::refreshButton
0x8d906  ldarg.0
0x8d907  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x8d90c  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8d911  ldarg.0
0x8d912  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x8d917  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::addButton
0x8d91c  ldarg.0
0x8d91d  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl::.ctor()
0x8d922  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::subscriptionDetailControl1
0x8d927  ldarg.0
0x8d928  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x8d92d  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::label1
0x8d932  ldarg.0
0x8d933  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x8d938  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::lblSummary
0x8d93d  ldarg.0
0x8d93e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8d943  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8d948  ldarg.0
0x8d949  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8d94e  dup
0x8d94f  ldarg.0
0x8d950  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::deleteButton
0x8d955  ldstr    aDeletebutton// "deleteButton"
0x8d95a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8d95f  ldarg.0
0x8d960  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::deleteButton
0x8d965  ldstr    aDeletebutton// "deleteButton"
0x8d96a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8d96f  ldarg.0
0x8d970  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::deleteButton
0x8d975  ldc.i4.1
0x8d976  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x8d97b  ldarg.0
0x8d97c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::deleteButton
0x8d981  ldarg.0
0x8d982  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::deleteButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x8d988  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8d98d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x8d992  dup
0x8d993  ldarg.0
0x8d994  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::propertiesButton
0x8d999  ldstr    aPropertiesbutt// "propertiesButton"
0x8d99e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8d9a3  ldarg.0
0x8d9a4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::propertiesButton
0x8d9a9  ldstr    aPropertiesbutt// "propertiesButton"
0x8d9ae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8d9b3  ldarg.0
0x8d9b4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::propertiesButton
0x8d9b9  ldc.i4.1
0x8d9ba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x8d9bf  ldarg.0
0x8d9c0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::propertiesButton
0x8d9c5  ldarg.0
0x8d9c6  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::propertiesButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x8d9cc  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8d9d1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x8d9d6  dup
0x8d9d7  ldarg.0
0x8d9d8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::enableDisableButton
0x8d9dd  ldstr    aEnabledisableb// "enableDisableButton"
0x8d9e2  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8d9e7  ldarg.0
0x8d9e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::enableDisableButton
0x8d9ed  ldstr    aEnabledisableb// "enableDisableButton"
0x8d9f2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8d9f7  ldarg.0
0x8d9f8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::enableDisableButton
0x8d9fd  ldc.i4.1
0x8d9fe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x8da03  ldarg.0
0x8da04  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::enableDisableButton
0x8da09  ldarg.0
0x8da0a  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::enableDisableButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x8da10  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8da15  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x8da1a  dup
0x8da1b  ldarg.0
0x8da1c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::retryButton
0x8da21  ldstr    aRetrybutton// "retryButton"
0x8da26  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8da2b  ldarg.0
0x8da2c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::retryButton
0x8da31  ldstr    aRetrybutton// "retryButton"
0x8da36  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8da3b  ldarg.0
0x8da3c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::retryButton
0x8da41  ldc.i4.1
0x8da42  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x8da47  ldarg.0
0x8da48  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::retryButton
0x8da4d  ldarg.0
0x8da4e  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::retryButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x8da54  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8da59  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x8da5e  dup
0x8da5f  ldarg.0
0x8da60  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::refreshButton
0x8da65  ldstr    aRefreshbutton// "refreshButton"
0x8da6a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8da6f  ldarg.0
0x8da70  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::refreshButton
0x8da75  ldstr    aRefreshbutton// "refreshButton"
0x8da7a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8da7f  ldarg.0
0x8da80  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::refreshButton
0x8da85  ldc.i4.1
0x8da86  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x8da8b  ldarg.0
0x8da8c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::refreshButton
0x8da91  ldarg.0
0x8da92  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::refreshButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x8da98  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8da9d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x8daa2  dup
0x8daa3  ldarg.0
0x8daa4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8daa9  ldstr    aTablelayoutpan// "tableLayoutPanel1"
0x8daae  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8dab3  ldarg.0
0x8dab4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8dab9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8dabe  ldarg.0
0x8dabf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::addButton
0x8dac4  ldc.i4.0
0x8dac5  ldc.i4.3
0x8dac6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8dacb  ldarg.0
0x8dacc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8dad1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8dad6  ldarg.0
0x8dad7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::refreshButton
0x8dadc  ldc.i4.6
0x8dadd  ldc.i4.3
0x8dade  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8dae3  ldarg.0
0x8dae4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8dae9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8daee  ldarg.0
0x8daef  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::subscriptionDetailControl1
0x8daf4  ldc.i4.0
0x8daf5  ldc.i4.2
0x8daf6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8dafb  ldarg.0
0x8dafc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8db01  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8db06  ldarg.0
0x8db07  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::label1
0x8db0c  ldc.i4.0
0x8db0d  ldc.i4.0
0x8db0e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8db13  ldarg.0
0x8db14  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8db19  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8db1e  ldarg.0
0x8db1f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::propertiesButton
0x8db24  ldc.i4.1
0x8db25  ldc.i4.3
0x8db26  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8db2b  ldarg.0
0x8db2c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8db31  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8db36  ldarg.0
0x8db37  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::deleteButton
0x8db3c  ldc.i4.2
0x8db3d  ldc.i4.3
0x8db3e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8db43  ldarg.0
0x8db44  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8db49  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8db4e  ldarg.0
0x8db4f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::retryButton
0x8db54  ldc.i4.5
0x8db55  ldc.i4.3
0x8db56  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8db5b  ldarg.0
0x8db5c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8db61  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8db66  ldarg.0
0x8db67  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::enableDisableButton
0x8db6c  ldc.i4.4
0x8db6d  ldc.i4.3
0x8db6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8db73  ldarg.0
0x8db74  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8db79  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8db7e  ldarg.0
0x8db7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::lblSummary
0x8db84  ldc.i4.0
0x8db85  ldc.i4.1
0x8db86  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8db8b  ldarg.0
0x8db8c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8db91  ldstr    aTablelayoutpan// "tableLayoutPanel1"
0x8db96  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8db9b  dup
0x8db9c  ldarg.0
0x8db9d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::addButton
0x8dba2  ldstr    aAddbutton// "addButton"
0x8dba7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8dbac  ldarg.0
0x8dbad  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::addButton
0x8dbb2  ldstr    aAddbutton// "addButton"
0x8dbb7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8dbbc  ldarg.0
0x8dbbd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::addButton
0x8dbc2  ldc.i4.1
0x8dbc3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x8dbc8  ldarg.0
0x8dbc9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::addButton
0x8dbce  ldarg.0
0x8dbcf  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::addButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x8dbd5  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8dbda  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x8dbdf  dup
0x8dbe0  ldarg.0
0x8dbe1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::subscriptionDetailControl1
0x8dbe6  ldstr    aSubscriptionde_0// "subscriptionDetailControl1"
0x8dbeb  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8dbf0  ldarg.0
0x8dbf1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::subscriptionDetailControl1
0x8dbf6  ldc.i4.2
0x8dbf7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.UserControl::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x8dbfc  ldarg.0
0x8dbfd  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8dc02  ldarg.0
0x8dc03  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::subscriptionDetailControl1
0x8dc08  ldc.i4.7
0x8dc09  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x8dc0e  ldarg.0
0x8dc0f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::subscriptionDetailControl1
0x8dc14  ldnull
0x8dc15  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl::set_CurrentNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode value)
0x8dc1a  ldarg.0
0x8dc1b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::subscriptionDetailControl1
0x8dc20  ldstr    aSubscriptionde_0// "subscriptionDetailControl1"
0x8dc25  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8dc2a  ldarg.0
0x8dc2b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::subscriptionDetailControl1
0x8dc30  ldnull
0x8dc31  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl::set_RootEventsNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode value)
0x8dc36  ldarg.0
0x8dc37  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8dc3c  ldarg.0
0x8dc3d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::label1
0x8dc42  ldc.i4.7
0x8dc43  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x8dc48  dup
0x8dc49  ldarg.0
0x8dc4a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::label1
0x8dc4f  ldstr    aLabel1// "label1"
0x8dc54  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8dc59  ldarg.0
0x8dc5a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::label1
0x8dc5f  ldstr    aLabel1// "label1"
0x8dc64  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8dc69  dup
0x8dc6a  ldarg.0
0x8dc6b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::lblSummary
0x8dc70  ldstr    aLblsummary// "lblSummary"
0x8dc75  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8dc7a  ldarg.0
0x8dc7b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
0x8dc80  ldarg.0
0x8dc81  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::lblSummary
0x8dc86  ldc.i4.7
0x8dc87  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x8dc8c  ldarg.0
0x8dc8d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::lblSummary
0x8dc92  ldstr    aLblsummary// "lblSummary"
0x8dc97  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8dc9c  ldarg.0
0x8dc9d  ldstr    aThis// "$this"
0x8dca2  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8dca7  ldarg.0
0x8dca8  ldc.i4.1
0x8dca9  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::set_AutoScaleMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoScaleMode)
0x8dcae  ldarg.0
0x8dcaf  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x8dcb4  ldarg.0
0x8dcb5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionListView::tableLayoutPanel1
  ... truncated ...
```
