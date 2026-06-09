# Microsoft.SharePoint.WebControls.FormToolBar::.cctor

- ea: `0x83f9a0`
- end: `0x83fd9a`
- name: `Microsoft.SharePoint.WebControls.FormToolBar::.cctor`
- size: `1018`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x83f9e9`: `Ribbon.ListForm.Display.Manage.ClaimReleaseTask`
- `0x83f9f1`: `Ribbon.ListForm.Display.Manage.ClaimReleaseTask`
- `0x83fd0a`: `Ribbon.ListForm.Display.Manage.ClaimReleaseTask`
- `0x83fae1`: `Ribbon.ListForm.Display.Manage.DeleteItemVersion`
- `0x83faea`: `Ribbon.ListForm.Display.Manage.DeleteItemVersion`
- `0x83fb61`: `Ribbon.ListForm.Display.HealthActions.HealthReportRepair`
- `0x83fb6a`: `Ribbon.ListForm.Display.HealthActions.HealthReportRepair`
- `0x83fbe1`: `Ribbon.DocLibListForm.Edit.Actions.DeleteItem`
- `0x83fbea`: `Ribbon.ListForm.Display.Manage.DeleteItem`
- `0x83fcca`: `Ribbon.ListForm.Display.Manage.DeleteItem`
- `0x83fd6a`: `Ribbon.ListForm.Display.Manage.DeleteItem`
- `0x83fc81`: `Ribbon.DocLibListForm.Edit.Actions.ViewWebPartXml`
- `0x83fc8a`: `Ribbon.DocLibListForm.Edit.Actions.ViewWebPartXml`
- `0x83fcc1`: `Ribbon.ListForm.Edit.Actions.DeleteItem`
- `0x83fd01`: `Ribbon.ListForm.Edit.Actions.ClaimReleaseTask`
- `0x83fd61`: `Ribbon.PostListForm.Edit.Actions.DeleteItem`

## pseudocode

```c

```

## disassembly

```asm
0x83f9a0  ldc.i4.s 0x20
0x83f9a2  newarr   string[]
0x83f9a7  stloc.0
0x83f9a8  ldloc.0
0x83f9a9  ldc.i4.0
0x83f9aa  ldc.i4.2
0x83f9ab  newarr   [mscorlib]System.String
0x83f9b0  stloc.1
0x83f9b1  ldloc.1
0x83f9b2  ldc.i4.0
0x83f9b3  ldstr    aRibbonListform// "Ribbon.ListForm.Display.Manage.EditSeri"...
0x83f9b8  stelem.ref
0x83f9b9  ldloc.1
0x83f9ba  ldc.i4.1
0x83f9bb  ldstr    aRibbonListform// "Ribbon.ListForm.Display.Manage.EditSeri"...
0x83f9c0  stelem.ref
0x83f9c1  ldloc.1
0x83f9c2  stelem.ref
0x83f9c3  ldloc.0
0x83f9c4  ldc.i4.1
0x83f9c5  ldc.i4.2
0x83f9c6  newarr   [mscorlib]System.String
0x83f9cb  stloc.2
0x83f9cc  ldloc.2
0x83f9cd  ldc.i4.0
0x83f9ce  ldstr    aRibbonListform_0// "Ribbon.ListForm.Display.Manage.EnterFol"...
0x83f9d3  stelem.ref
0x83f9d4  ldloc.2
0x83f9d5  ldc.i4.1
0x83f9d6  ldstr    aRibbonListform_0// "Ribbon.ListForm.Display.Manage.EnterFol"...
0x83f9db  stelem.ref
0x83f9dc  ldloc.2
0x83f9dd  stelem.ref
0x83f9de  ldloc.0
0x83f9df  ldc.i4.2
0x83f9e0  ldc.i4.2
0x83f9e1  newarr   [mscorlib]System.String
0x83f9e6  stloc.3
0x83f9e7  ldloc.3
0x83f9e8  ldc.i4.0
0x83f9e9  ldstr    aRibbonListform_1// "Ribbon.ListForm.Display.Manage.ClaimRel"...
0x83f9ee  stelem.ref
0x83f9ef  ldloc.3
0x83f9f0  ldc.i4.1
0x83f9f1  ldstr    aRibbonListform_1// "Ribbon.ListForm.Display.Manage.ClaimRel"...
0x83f9f6  stelem.ref
0x83f9f7  ldloc.3
0x83f9f8  stelem.ref
0x83f9f9  ldloc.0
0x83f9fa  ldc.i4.3
0x83f9fb  ldc.i4.2
0x83f9fc  newarr   [mscorlib]System.String
0x83fa01  stloc.s  4
0x83fa03  ldloc.s  4
0x83fa05  ldc.i4.0
0x83fa06  ldstr    aRibbonListform_2// "Ribbon.ListForm.Display.Manage.ManageCo"...
0x83fa0b  stelem.ref
0x83fa0c  ldloc.s  4
0x83fa0e  ldc.i4.1
0x83fa0f  ldstr    aRibbonListform_2// "Ribbon.ListForm.Display.Manage.ManageCo"...
0x83fa14  stelem.ref
0x83fa15  ldloc.s  4
0x83fa17  stelem.ref
0x83fa18  ldloc.0
0x83fa19  ldc.i4.4
0x83fa1a  ldc.i4.2
0x83fa1b  newarr   [mscorlib]System.String
0x83fa20  stloc.s  5
0x83fa22  ldloc.s  5
0x83fa24  ldc.i4.0
0x83fa25  ldstr    aRibbonListform_3// "Ribbon.ListForm.Display.Manage.CheckIn"
0x83fa2a  stelem.ref
0x83fa2b  ldloc.s  5
0x83fa2d  ldc.i4.1
0x83fa2e  ldstr    aRibbonListform_3// "Ribbon.ListForm.Display.Manage.CheckIn"
0x83fa33  stelem.ref
0x83fa34  ldloc.s  5
0x83fa36  stelem.ref
0x83fa37  ldloc.0
0x83fa38  ldc.i4.5
0x83fa39  ldc.i4.2
0x83fa3a  newarr   [mscorlib]System.String
0x83fa3f  stloc.s  6
0x83fa41  ldloc.s  6
0x83fa43  ldc.i4.0
0x83fa44  ldstr    aRibbonListform_4// "Ribbon.ListForm.Display.Manage.CheckOut"
0x83fa49  stelem.ref
0x83fa4a  ldloc.s  6
0x83fa4c  ldc.i4.1
0x83fa4d  ldstr    aRibbonListform_4// "Ribbon.ListForm.Display.Manage.CheckOut"
0x83fa52  stelem.ref
0x83fa53  ldloc.s  6
0x83fa55  stelem.ref
0x83fa56  ldloc.0
0x83fa57  ldc.i4.6
0x83fa58  ldc.i4.2
0x83fa59  newarr   [mscorlib]System.String
0x83fa5e  stloc.s  7
0x83fa60  ldloc.s  7
0x83fa62  ldc.i4.0
0x83fa63  ldstr    aRibbonListform_5// "Ribbon.ListForm.Display.Manage.ApproveR"...
0x83fa68  stelem.ref
0x83fa69  ldloc.s  7
0x83fa6b  ldc.i4.1
0x83fa6c  ldstr    aRibbonListform_5// "Ribbon.ListForm.Display.Manage.ApproveR"...
0x83fa71  stelem.ref
0x83fa72  ldloc.s  7
0x83fa74  stelem.ref
0x83fa75  ldloc.0
0x83fa76  ldc.i4.7
0x83fa77  ldc.i4.2
0x83fa78  newarr   [mscorlib]System.String
0x83fa7d  stloc.s  8
0x83fa7f  ldloc.s  8
0x83fa81  ldc.i4.0
0x83fa82  ldstr    aRibbonListform_6// "Ribbon.ListForm.Display.Manage.Workflow"...
0x83fa87  stelem.ref
0x83fa88  ldloc.s  8
0x83fa8a  ldc.i4.1
0x83fa8b  ldstr    aRibbonListform_6// "Ribbon.ListForm.Display.Manage.Workflow"...
0x83fa90  stelem.ref
0x83fa91  ldloc.s  8
0x83fa93  stelem.ref
0x83fa94  ldloc.0
0x83fa95  ldc.i4.8
0x83fa96  ldc.i4.2
0x83fa97  newarr   [mscorlib]System.String
0x83fa9c  stloc.s  9
0x83fa9e  ldloc.s  9
0x83faa0  ldc.i4.0
0x83faa1  ldstr    aRibbonListform_7// "Ribbon.ListForm.Display.Manage.Alert"
0x83faa6  stelem.ref
0x83faa7  ldloc.s  9
0x83faa9  ldc.i4.1
0x83faaa  ldstr    aRibbonListform_7// "Ribbon.ListForm.Display.Manage.Alert"
0x83faaf  stelem.ref
0x83fab0  ldloc.s  9
0x83fab2  stelem.ref
0x83fab3  ldloc.0
0x83fab4  ldc.i4.s 9
0x83fab6  ldc.i4.2
0x83fab7  newarr   [mscorlib]System.String
0x83fabc  stloc.s  0xA
0x83fabe  ldloc.s  0xA
0x83fac0  ldc.i4.0
0x83fac1  ldstr    aRibbonListform_8// "Ribbon.ListForm.Display.Manage.Distribu"...
0x83fac6  stelem.ref
0x83fac7  ldloc.s  0xA
0x83fac9  ldc.i4.1
0x83faca  ldstr    aRibbonListform_8// "Ribbon.ListForm.Display.Manage.Distribu"...
0x83facf  stelem.ref
0x83fad0  ldloc.s  0xA
0x83fad2  stelem.ref
0x83fad3  ldloc.0
0x83fad4  ldc.i4.s 0xA
0x83fad6  ldc.i4.2
0x83fad7  newarr   [mscorlib]System.String
0x83fadc  stloc.s  0xB
0x83fade  ldloc.s  0xB
0x83fae0  ldc.i4.0
0x83fae1  ldstr    aRibbonListform_9// "Ribbon.ListForm.Display.Manage.DeleteIt"...
0x83fae6  stelem.ref
0x83fae7  ldloc.s  0xB
0x83fae9  ldc.i4.1
0x83faea  ldstr    aRibbonListform_9// "Ribbon.ListForm.Display.Manage.DeleteIt"...
0x83faef  stelem.ref
0x83faf0  ldloc.s  0xB
0x83faf2  stelem.ref
0x83faf3  ldloc.0
0x83faf4  ldc.i4.s 0xB
0x83faf6  ldc.i4.2
0x83faf7  newarr   [mscorlib]System.String
0x83fafc  stloc.s  0xC
0x83fafe  ldloc.s  0xC
0x83fb00  ldc.i4.0
0x83fb01  ldstr    aRibbonListform_10// "Ribbon.ListForm.Display.Manage.RestoreI"...
0x83fb06  stelem.ref
0x83fb07  ldloc.s  0xC
0x83fb09  ldc.i4.1
0x83fb0a  ldstr    aRibbonListform_10// "Ribbon.ListForm.Display.Manage.RestoreI"...
0x83fb0f  stelem.ref
0x83fb10  ldloc.s  0xC
0x83fb12  stelem.ref
0x83fb13  ldloc.0
0x83fb14  ldc.i4.s 0xC
0x83fb16  ldc.i4.2
0x83fb17  newarr   [mscorlib]System.String
0x83fb1c  stloc.s  0xD
0x83fb1e  ldloc.s  0xD
0x83fb20  ldc.i4.0
0x83fb21  ldstr    aRibbonListform_11// "Ribbon.ListForm.Display.HealthActions.H"...
0x83fb26  stelem.ref
0x83fb27  ldloc.s  0xD
0x83fb29  ldc.i4.1
0x83fb2a  ldstr    aRibbonListform_11// "Ribbon.ListForm.Display.HealthActions.H"...
0x83fb2f  stelem.ref
0x83fb30  ldloc.s  0xD
0x83fb32  stelem.ref
0x83fb33  ldloc.0
0x83fb34  ldc.i4.s 0xD
0x83fb36  ldc.i4.2
0x83fb37  newarr   [mscorlib]System.String
0x83fb3c  stloc.s  0xE
0x83fb3e  ldloc.s  0xE
0x83fb40  ldc.i4.0
0x83fb41  ldstr    aRibbonListform_12// "Ribbon.ListForm.Display.HealthActions.H"...
0x83fb46  stelem.ref
0x83fb47  ldloc.s  0xE
0x83fb49  ldc.i4.1
0x83fb4a  ldstr    aRibbonListform_12// "Ribbon.ListForm.Display.HealthActions.H"...
0x83fb4f  stelem.ref
0x83fb50  ldloc.s  0xE
0x83fb52  stelem.ref
0x83fb53  ldloc.0
0x83fb54  ldc.i4.s 0xE
0x83fb56  ldc.i4.2
0x83fb57  newarr   [mscorlib]System.String
0x83fb5c  stloc.s  0xF
0x83fb5e  ldloc.s  0xF
0x83fb60  ldc.i4.0
0x83fb61  ldstr    aRibbonListform_13// "Ribbon.ListForm.Display.HealthActions.H"...
0x83fb66  stelem.ref
0x83fb67  ldloc.s  0xF
0x83fb69  ldc.i4.1
0x83fb6a  ldstr    aRibbonListform_13// "Ribbon.ListForm.Display.HealthActions.H"...
0x83fb6f  stelem.ref
0x83fb70  ldloc.s  0xF
0x83fb72  stelem.ref
0x83fb73  ldloc.0
0x83fb74  ldc.i4.s 0xF
0x83fb76  ldc.i4.2
0x83fb77  newarr   [mscorlib]System.String
0x83fb7c  stloc.s  0x10
0x83fb7e  ldloc.s  0x10
0x83fb80  ldc.i4.0
0x83fb81  ldstr    aRibbonListform_14// "Ribbon.ListForm.Display.Solution.Activa"...
0x83fb86  stelem.ref
0x83fb87  ldloc.s  0x10
0x83fb89  ldc.i4.1
0x83fb8a  ldstr    aRibbonListform_15// "Ribbon.ListForm.Display.Solution.Activa"...
0x83fb8f  stelem.ref
0x83fb90  ldloc.s  0x10
0x83fb92  stelem.ref
0x83fb93  ldloc.0
0x83fb94  ldc.i4.s 0x10
0x83fb96  ldc.i4.2
0x83fb97  newarr   [mscorlib]System.String
0x83fb9c  stloc.s  0x11
0x83fb9e  ldloc.s  0x11
0x83fba0  ldc.i4.0
0x83fba1  ldstr    aRibbonListform_16// "Ribbon.ListForm.Display.Solution.Deacti"...
0x83fba6  stelem.ref
0x83fba7  ldloc.s  0x11
0x83fba9  ldc.i4.1
0x83fbaa  ldstr    aRibbonListform_17// "Ribbon.ListForm.Display.Solution.Deacti"...
0x83fbaf  stelem.ref
0x83fbb0  ldloc.s  0x11
0x83fbb2  stelem.ref
0x83fbb3  ldloc.0
0x83fbb4  ldc.i4.s 0x11
0x83fbb6  ldc.i4.2
0x83fbb7  newarr   [mscorlib]System.String
0x83fbbc  stloc.s  0x12
0x83fbbe  ldloc.s  0x12
0x83fbc0  ldc.i4.0
0x83fbc1  ldstr    aRibbonListform_18// "Ribbon.ListForm.Display.Solution.Upgrad"...
0x83fbc6  stelem.ref
0x83fbc7  ldloc.s  0x12
0x83fbc9  ldc.i4.1
0x83fbca  ldstr    aRibbonListform_19// "Ribbon.ListForm.Display.Solution.Upgrad"...
0x83fbcf  stelem.ref
0x83fbd0  ldloc.s  0x12
0x83fbd2  stelem.ref
0x83fbd3  ldloc.0
0x83fbd4  ldc.i4.s 0x12
0x83fbd6  ldc.i4.2
0x83fbd7  newarr   [mscorlib]System.String
0x83fbdc  stloc.s  0x13
0x83fbde  ldloc.s  0x13
0x83fbe0  ldc.i4.0
0x83fbe1  ldstr    aRibbonDoclibli// "Ribbon.DocLibListForm.Edit.Actions.Dele"...
0x83fbe6  stelem.ref
0x83fbe7  ldloc.s  0x13
0x83fbe9  ldc.i4.1
0x83fbea  ldstr    aRibbonListform_20// "Ribbon.ListForm.Display.Manage.DeleteIt"...
0x83fbef  stelem.ref
0x83fbf0  ldloc.s  0x13
0x83fbf2  stelem.ref
0x83fbf3  ldloc.0
0x83fbf4  ldc.i4.s 0x13
0x83fbf6  ldc.i4.2
0x83fbf7  newarr   [mscorlib]System.String
0x83fbfc  stloc.s  0x14
0x83fbfe  ldloc.s  0x14
0x83fc00  ldc.i4.0
0x83fc01  ldstr    aRibbonDoclibli_0// "Ribbon.DocLibListForm.Edit.Actions.Chec"...
0x83fc06  stelem.ref
0x83fc07  ldloc.s  0x14
0x83fc09  ldc.i4.1
0x83fc0a  ldstr    aRibbonListform_3// "Ribbon.ListForm.Display.Manage.CheckIn"
  ... truncated ...
```
