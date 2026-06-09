# Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::InitializeComponent

- ea: `0x27470`
- end: `0x27b89`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::InitializeComponent`
- size: `1817`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x27170`

## string_xrefs

- `0x2772d`: `createdTime`
- `0x2773d`: `createdTime`
- `0x2776f`: `accessed`
- `0x2777f`: `accessed`
- `0x279b4`: `textBoxAccessed`
- `0x279c4`: `textBoxAccessed`
- `0x27a5f`: `textBoxCreated`
- `0x27a6f`: `textBoxCreated`
- `0x27a98`: `textBoxPath`
- `0x27aa8`: `textBoxPath`

## pseudocode

```c

```

## disassembly

```asm
0x27470  ldarg.0
0x27471  newobj   instance void [System]System.ComponentModel.Container::.ctor()
0x27476  stfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::components
0x2747b  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties
0x27480  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27485  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x2748a  ldarg.0
0x2748b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x27490  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::btnCancel
0x27495  ldarg.0
0x27496  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x2749b  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::btnOk
0x274a0  ldarg.0
0x274a1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x274a6  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::txtDesc
0x274ab  ldarg.0
0x274ac  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x274b1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::label2
0x274b6  ldarg.0
0x274b7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x274bc  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::txtName
0x274c1  ldarg.0
0x274c2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x274c7  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::label1
0x274cc  ldarg.0
0x274cd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x274d2  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::lblFile
0x274d7  ldarg.0
0x274d8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x274dd  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::lblSize
0x274e2  ldarg.0
0x274e3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x274e8  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::createdTime
0x274ed  ldarg.0
0x274ee  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x274f3  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::modifiedTime
0x274f8  ldarg.0
0x274f9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x274fe  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::accessed
0x27503  ldarg.0
0x27504  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x27509  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::groupBox1
0x2750e  ldarg.0
0x2750f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x27514  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelGeneral
0x27519  ldarg.0
0x2751a  ldarg.0
0x2751b  ldfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::components
0x27520  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolTip::.ctor(class [System]System.ComponentModel.IContainer)
0x27525  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolTip Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::toolTip1
0x2752a  ldarg.0
0x2752b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x27530  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::groupBox2
0x27535  ldarg.0
0x27536  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x2753b  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelLog
0x27540  ldarg.0
0x27541  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x27546  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::textBoxAccessed
0x2754b  ldarg.0
0x2754c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x27551  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::textBoxModified
0x27556  ldarg.0
0x27557  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x2755c  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::textBoxSize
0x27561  ldarg.0
0x27562  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x27567  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::textBoxCreated
0x2756c  ldarg.0
0x2756d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x27572  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::textBoxPath
0x27577  ldarg.0
0x27578  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::groupBox1
0x2757d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x27582  ldarg.0
0x27583  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelGeneral
0x27588  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2758d  ldarg.0
0x2758e  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::groupBox2
0x27593  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x27598  ldarg.0
0x27599  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelLog
0x2759e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x275a3  ldarg.0
0x275a4  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x275a9  ldarg.0
0x275aa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::btnCancel
0x275af  ldc.i4.2
0x275b0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x275b5  dup
0x275b6  ldarg.0
0x275b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::btnCancel
0x275bc  ldstr    aBtncancel// "btnCancel"
0x275c1  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x275c6  ldarg.0
0x275c7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::btnCancel
0x275cc  ldstr    aBtncancel// "btnCancel"
0x275d1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x275d6  ldarg.0
0x275d7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::btnCancel
0x275dc  ldc.i4.1
0x275dd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x275e2  ldarg.0
0x275e3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::btnOk
0x275e8  ldc.i4.1
0x275e9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x275ee  dup
0x275ef  ldarg.0
0x275f0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::btnOk
0x275f5  ldstr    aBtnok// "btnOk"
0x275fa  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x275ff  ldarg.0
0x27600  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::btnOk
0x27605  ldstr    aBtnok// "btnOk"
0x2760a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2760f  ldarg.0
0x27610  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::btnOk
0x27615  ldc.i4.1
0x27616  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x2761b  ldarg.0
0x2761c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::btnOk
0x27621  ldarg.0
0x27622  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::btnOk_Click(object sender, class [mscorlib]System.EventArgs e)
0x27628  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x2762d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x27632  dup
0x27633  ldarg.0
0x27634  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::txtDesc
0x27639  ldstr    aTxtdesc// "txtDesc"
0x2763e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x27643  ldarg.0
0x27644  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::txtDesc
0x27649  ldstr    aTxtdesc// "txtDesc"
0x2764e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x27653  ldarg.0
0x27654  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::txtDesc
0x27659  ldarg.0
0x2765a  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::txtDesc_TextChanged(object sender, class [mscorlib]System.EventArgs e)
0x27660  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x27665  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x2766a  dup
0x2766b  ldarg.0
0x2766c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::label2
0x27671  ldstr    aLabel2// "label2"
0x27676  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x2767b  ldarg.0
0x2767c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::label2
0x27681  ldstr    aLabel2// "label2"
0x27686  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2768b  dup
0x2768c  ldarg.0
0x2768d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::txtName
0x27692  ldstr    aTxtname// "txtName"
0x27697  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x2769c  ldarg.0
0x2769d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::txtName
0x276a2  ldstr    aTxtname// "txtName"
0x276a7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x276ac  ldarg.0
0x276ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::txtName
0x276b2  ldarg.0
0x276b3  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::txtName_TextChanged(object sender, class [mscorlib]System.EventArgs e)
0x276b9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x276be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x276c3  dup
0x276c4  ldarg.0
0x276c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::label1
0x276ca  ldstr    aLabel1// "label1"
0x276cf  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x276d4  ldarg.0
0x276d5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::label1
0x276da  ldstr    aLabel1// "label1"
0x276df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x276e4  dup
0x276e5  ldarg.0
0x276e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::lblFile
0x276eb  ldstr    aLblfile// "lblFile"
0x276f0  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x276f5  ldarg.0
0x276f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::lblFile
0x276fb  ldstr    aLblfile// "lblFile"
0x27700  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x27705  dup
0x27706  ldarg.0
0x27707  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::lblSize
0x2770c  ldstr    aLblsize// "lblSize"
0x27711  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x27716  ldarg.0
0x27717  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::lblSize
0x2771c  ldstr    aLblsize// "lblSize"
0x27721  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x27726  dup
0x27727  ldarg.0
0x27728  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::createdTime
0x2772d  ldstr    aCreatedtime// "createdTime"
0x27732  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x27737  ldarg.0
0x27738  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::createdTime
0x2773d  ldstr    aCreatedtime// "createdTime"
0x27742  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x27747  dup
0x27748  ldarg.0
0x27749  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::modifiedTime
0x2774e  ldstr    aModifiedtime// "modifiedTime"
0x27753  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x27758  ldarg.0
0x27759  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::modifiedTime
0x2775e  ldstr    aModifiedtime// "modifiedTime"
0x27763  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x27768  dup
0x27769  ldarg.0
0x2776a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::accessed
0x2776f  ldstr    aAccessed// "accessed"
0x27774  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x27779  ldarg.0
0x2777a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::accessed
0x2777f  ldstr    aAccessed// "accessed"
0x27784  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x27789  ldarg.0
0x2778a  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::groupBox1
0x2778f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x27794  ldarg.0
0x27795  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelGeneral
0x2779a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2779f  dup
0x277a0  ldarg.0
0x277a1  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::groupBox1
0x277a6  ldstr    aGroupbox1// "groupBox1"
0x277ab  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x277b0  ldarg.0
0x277b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::groupBox1
0x277b6  ldstr    aGroupbox1// "groupBox1"
0x277bb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x277c0  ldarg.0
0x277c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::groupBox1
0x277c6  ldc.i4.0
0x277c7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_TabStop(bool)
0x277cc  dup
0x277cd  ldarg.0
0x277ce  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelGeneral
0x277d3  ldstr    aTablelayoutpan_2// "tableLayoutPanelGeneral"
0x277d8  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x277dd  ldarg.0
0x277de  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelGeneral
0x277e3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x277e8  ldarg.0
0x277e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::txtDesc
0x277ee  ldc.i4.1
0x277ef  ldc.i4.1
0x277f0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x277f5  ldarg.0
0x277f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelGeneral
0x277fb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x27800  ldarg.0
0x27801  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::label2
0x27806  ldc.i4.0
0x27807  ldc.i4.1
0x27808  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x2780d  ldarg.0
0x2780e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelGeneral
0x27813  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x27818  ldarg.0
0x27819  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::txtName
0x2781e  ldc.i4.1
0x2781f  ldc.i4.0
0x27820  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x27825  ldarg.0
0x27826  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelGeneral
0x2782b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x27830  ldarg.0
0x27831  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::label1
0x27836  ldc.i4.0
0x27837  ldc.i4.0
0x27838  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x2783d  ldarg.0
0x2783e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelGeneral
0x27843  ldstr    aTablelayoutpan_2// "tableLayoutPanelGeneral"
0x27848  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2784d  ldarg.0
0x2784e  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::groupBox2
0x27853  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x27858  ldarg.0
0x27859  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelLog
0x2785e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x27863  dup
0x27864  ldarg.0
0x27865  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::groupBox2
0x2786a  ldstr    aGroupbox2// "groupBox2"
0x2786f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x27874  ldarg.0
0x27875  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::groupBox2
0x2787a  ldstr    aGroupbox2// "groupBox2"
0x2787f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x27884  ldarg.0
0x27885  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::groupBox2
0x2788a  ldc.i4.0
0x2788b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_TabStop(bool)
0x27890  dup
0x27891  ldarg.0
0x27892  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ExternalLogProperties::tableLayoutPanelLog
  ... truncated ...
```
