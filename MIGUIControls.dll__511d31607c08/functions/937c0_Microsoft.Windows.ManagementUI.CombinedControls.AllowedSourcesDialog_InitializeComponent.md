# Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::InitializeComponent

- ea: `0x937c0`
- end: `0x93f03`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::InitializeComponent`
- size: `1859`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x93360`

## string_xrefs

- `0x93abe`: `buttonAddDomainComputer`
- `0x93ace`: `buttonAddDomainComputer`
- `0x93b02`: `labelComputerGroups`
- `0x93b12`: `labelComputerGroups`
- `0x93b23`: `buttonAddNonDomainComputer`
- `0x93b33`: `buttonAddNonDomainComputer`
- `0x93b67`: `buttonRemove`
- `0x93b77`: `buttonRemove`
- `0x93e1e`: `buttonRemoveCertificate`
- `0x93e2e`: `buttonRemoveCertificate`

## pseudocode

```c

```

## disassembly

```asm
0x937c0  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog
0x937c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x937ca  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x937cf  ldarg.0
0x937d0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x937d5  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonCancel
0x937da  ldarg.0
0x937db  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x937e0  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonOK
0x937e5  ldarg.0
0x937e6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x937eb  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelOKCancel
0x937f0  ldarg.0
0x937f1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x937f6  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x937fb  ldarg.0
0x937fc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x93801  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddDomainComputer
0x93806  ldarg.0
0x93807  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x9380c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::labelComputerGroups
0x93811  ldarg.0
0x93812  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x93817  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddNonDomainComputer
0x9381c  ldarg.0
0x9381d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x93822  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonRemove
0x93827  ldarg.0
0x93828  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x9382d  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAllowDeny
0x93832  ldarg.0
0x93833  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x93838  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::listViewSources
0x9383d  ldarg.0
0x9383e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x93843  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::labelCertificateAuthority
0x93848  ldarg.0
0x93849  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x9384e  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::labelSeparator1
0x93853  ldarg.0
0x93854  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x93859  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::labelSeparatorOKCancel
0x9385e  ldarg.0
0x9385f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x93864  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::listViewCertificates
0x93869  ldarg.0
0x9386a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x9386f  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddCertificate
0x93874  ldarg.0
0x93875  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x9387a  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonRemoveCertificate
0x9387f  ldarg.0
0x93880  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelOKCancel
0x93885  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x9388a  ldarg.0
0x9388b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x93890  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x93895  ldarg.0
0x93896  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x9389b  dup
0x9389c  ldarg.0
0x9389d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonCancel
0x938a2  ldstr    aButtoncancel// "buttonCancel"
0x938a7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x938ac  ldarg.0
0x938ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonCancel
0x938b2  ldc.i4.2
0x938b3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x938b8  ldarg.0
0x938b9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonCancel
0x938be  ldstr    aButtoncancel// "buttonCancel"
0x938c3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x938c8  ldarg.0
0x938c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonCancel
0x938ce  ldc.i4.1
0x938cf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x938d4  dup
0x938d5  ldarg.0
0x938d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonOK
0x938db  ldstr    aButtonok// "buttonOK"
0x938e0  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x938e5  ldarg.0
0x938e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonOK
0x938eb  ldc.i4.1
0x938ec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x938f1  ldarg.0
0x938f2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonOK
0x938f7  ldstr    aButtonok// "buttonOK"
0x938fc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x93901  ldarg.0
0x93902  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonOK
0x93907  ldc.i4.1
0x93908  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x9390d  ldarg.0
0x9390e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonOK
0x93913  ldarg.0
0x93914  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonOK_Click(object sender, class [mscorlib]System.EventArgs e)
0x9391a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x9391f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x93924  dup
0x93925  ldarg.0
0x93926  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelOKCancel
0x9392b  ldstr    aTablelayoutpan_29// "tableLayoutPanelOKCancel"
0x93930  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x93935  ldarg.0
0x93936  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelOKCancel
0x9393b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x93940  ldarg.0
0x93941  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonOK
0x93946  ldc.i4.1
0x93947  ldc.i4.0
0x93948  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x9394d  ldarg.0
0x9394e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelOKCancel
0x93953  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x93958  ldarg.0
0x93959  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonCancel
0x9395e  ldc.i4.2
0x9395f  ldc.i4.0
0x93960  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x93965  ldarg.0
0x93966  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelOKCancel
0x9396b  ldstr    aTablelayoutpan_29// "tableLayoutPanelOKCancel"
0x93970  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x93975  dup
0x93976  ldarg.0
0x93977  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x9397c  ldstr    aTablelayoutpan_18// "tableLayoutPanelSelect"
0x93981  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x93986  ldarg.0
0x93987  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x9398c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x93991  ldarg.0
0x93992  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddDomainComputer
0x93997  ldc.i4.1
0x93998  ldc.i4.1
0x93999  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x9399e  ldarg.0
0x9399f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x939a4  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x939a9  ldarg.0
0x939aa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::labelComputerGroups
0x939af  ldc.i4.0
0x939b0  ldc.i4.0
0x939b1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x939b6  ldarg.0
0x939b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x939bc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x939c1  ldarg.0
0x939c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddNonDomainComputer
0x939c7  ldc.i4.1
0x939c8  ldc.i4.2
0x939c9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x939ce  ldarg.0
0x939cf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x939d4  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x939d9  ldarg.0
0x939da  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonRemove
0x939df  ldc.i4.1
0x939e0  ldc.i4.3
0x939e1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x939e6  ldarg.0
0x939e7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x939ec  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x939f1  ldarg.0
0x939f2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAllowDeny
0x939f7  ldc.i4.1
0x939f8  ldc.i4.4
0x939f9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x939fe  ldarg.0
0x939ff  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x93a04  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x93a09  ldarg.0
0x93a0a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::listViewSources
0x93a0f  ldc.i4.0
0x93a10  ldc.i4.1
0x93a11  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x93a16  ldarg.0
0x93a17  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x93a1c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x93a21  ldarg.0
0x93a22  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::labelCertificateAuthority
0x93a27  ldc.i4.0
0x93a28  ldc.i4.6
0x93a29  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x93a2e  ldarg.0
0x93a2f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x93a34  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x93a39  ldarg.0
0x93a3a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::labelSeparator1
0x93a3f  ldc.i4.0
0x93a40  ldc.i4.5
0x93a41  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x93a46  ldarg.0
0x93a47  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x93a4c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x93a51  ldarg.0
0x93a52  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::labelSeparatorOKCancel
0x93a57  ldc.i4.0
0x93a58  ldc.i4.s 9
0x93a5a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x93a5f  ldarg.0
0x93a60  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x93a65  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x93a6a  ldarg.0
0x93a6b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::listViewCertificates
0x93a70  ldc.i4.0
0x93a71  ldc.i4.7
0x93a72  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x93a77  ldarg.0
0x93a78  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x93a7d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x93a82  ldarg.0
0x93a83  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddCertificate
0x93a88  ldc.i4.1
0x93a89  ldc.i4.7
0x93a8a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x93a8f  ldarg.0
0x93a90  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x93a95  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x93a9a  ldarg.0
0x93a9b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonRemoveCertificate
0x93aa0  ldc.i4.1
0x93aa1  ldc.i4.8
0x93aa2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x93aa7  ldarg.0
0x93aa8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::tableLayoutPanelSelect
0x93aad  ldstr    aTablelayoutpan_18// "tableLayoutPanelSelect"
0x93ab2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x93ab7  dup
0x93ab8  ldarg.0
0x93ab9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddDomainComputer
0x93abe  ldstr    aButtonadddomai// "buttonAddDomainComputer"
0x93ac3  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x93ac8  ldarg.0
0x93ac9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddDomainComputer
0x93ace  ldstr    aButtonadddomai// "buttonAddDomainComputer"
0x93ad3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x93ad8  ldarg.0
0x93ad9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddDomainComputer
0x93ade  ldc.i4.1
0x93adf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x93ae4  ldarg.0
0x93ae5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddDomainComputer
0x93aea  ldarg.0
0x93aeb  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddDomainComputer_Click(object sender, class [mscorlib]System.EventArgs e)
0x93af1  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x93af6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x93afb  dup
0x93afc  ldarg.0
0x93afd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::labelComputerGroups
0x93b02  ldstr    aLabelcomputerg// "labelComputerGroups"
0x93b07  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x93b0c  ldarg.0
0x93b0d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::labelComputerGroups
0x93b12  ldstr    aLabelcomputerg// "labelComputerGroups"
0x93b17  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x93b1c  dup
0x93b1d  ldarg.0
0x93b1e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddNonDomainComputer
0x93b23  ldstr    aButtonaddnondo// "buttonAddNonDomainComputer"
0x93b28  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x93b2d  ldarg.0
0x93b2e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddNonDomainComputer
0x93b33  ldstr    aButtonaddnondo// "buttonAddNonDomainComputer"
0x93b38  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x93b3d  ldarg.0
0x93b3e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddNonDomainComputer
0x93b43  ldc.i4.1
0x93b44  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x93b49  ldarg.0
0x93b4a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddNonDomainComputer
0x93b4f  ldarg.0
0x93b50  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAddNonDomainComputer_Click(object sender, class [mscorlib]System.EventArgs e)
0x93b56  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x93b5b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x93b60  dup
0x93b61  ldarg.0
0x93b62  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonRemove
0x93b67  ldstr    aButtonremove// "buttonRemove"
0x93b6c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x93b71  ldarg.0
0x93b72  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonRemove
0x93b77  ldstr    aButtonremove// "buttonRemove"
0x93b7c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x93b81  ldarg.0
0x93b82  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonRemove
0x93b87  ldc.i4.1
0x93b88  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x93b8d  ldarg.0
0x93b8e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonRemove
0x93b93  ldarg.0
0x93b94  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonRemove_Click(object sender, class [mscorlib]System.EventArgs e)
0x93b9a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x93b9f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x93ba4  dup
0x93ba5  ldarg.0
0x93ba6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AllowedSourcesDialog::buttonAllowDeny
0x93bab  ldstr    aButtonallowden// "buttonAllowDeny"
0x93bb0  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
  ... truncated ...
```
