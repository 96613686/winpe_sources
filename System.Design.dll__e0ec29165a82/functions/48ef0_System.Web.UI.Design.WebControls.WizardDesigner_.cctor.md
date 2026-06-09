# System.Web.UI.Design.WebControls.WizardDesigner::.cctor

- ea: `0x48ef0`
- end: `0x490c2`
- name: `System.Web.UI.Design.WebControls.WizardDesigner::.cctor`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## string_xrefs

- `0x48ef8`: `ContentTemplate`
- `0x48f13`: `HeaderTemplate`
- `0x48f23`: `StartNavigationTemplate`
- `0x48f2b`: `StepNavigationTemplate`
- `0x48f33`: `FinishNavigationTemplate`
- `0x48f1b`: `SideBarTemplate`
- `0x48f00`: `CustomNavigationTemplate`
- `0x48fbc`: `FinishCompleteButtonText`
- `0x48fc4`: `FinishCompleteButtonType`
- `0x48fcc`: `FinishCompleteButtonImageUrl`
- `0x48fec`: `FinishCompleteButtonStyle`
- `0x49055`: `SideBarButtonStyle`

## pseudocode

```c

```

## disassembly

```asm
0x48ef0  ldc.i4.2
0x48ef1  newarr   [mscorlib]System.String
0x48ef6  dup
0x48ef7  ldc.i4.0
0x48ef8  ldstr    aContenttemplat// "ContentTemplate"
0x48efd  stelem.ref
0x48efe  dup
0x48eff  ldc.i4.1
0x48f00  ldstr    aCustomnavigati_0// "CustomNavigationTemplate"
0x48f05  stelem.ref
0x48f06  stsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_stepTemplateNames
0x48f0b  ldc.i4.5
0x48f0c  newarr   [mscorlib]System.String
0x48f11  dup
0x48f12  ldc.i4.0
0x48f13  ldstr    aHeadertemplate// "HeaderTemplate"
0x48f18  stelem.ref
0x48f19  dup
0x48f1a  ldc.i4.1
0x48f1b  ldstr    aSidebartemplat// "SideBarTemplate"
0x48f20  stelem.ref
0x48f21  dup
0x48f22  ldc.i4.2
0x48f23  ldstr    aStartnavigatio// "StartNavigationTemplate"
0x48f28  stelem.ref
0x48f29  dup
0x48f2a  ldc.i4.3
0x48f2b  ldstr    aStepnavigation// "StepNavigationTemplate"
0x48f30  stelem.ref
0x48f31  dup
0x48f32  ldc.i4.4
0x48f33  ldstr    aFinishnavigati// "FinishNavigationTemplate"
0x48f38  stelem.ref
0x48f39  stsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_controlTemplateNames
0x48f3e  ldc.i4.4
0x48f3f  newarr   [mscorlib]System.String
0x48f44  dup
0x48f45  ldc.i4.0
0x48f46  ldstr    aStartnextbutto// "StartNextButtonText"
0x48f4b  stelem.ref
0x48f4c  dup
0x48f4d  ldc.i4.1
0x48f4e  ldstr    aStartnextbutto_0// "StartNextButtonType"
0x48f53  stelem.ref
0x48f54  dup
0x48f55  ldc.i4.2
0x48f56  ldstr    aStartnextbutto_1// "StartNextButtonImageUrl"
0x48f5b  stelem.ref
0x48f5c  dup
0x48f5d  ldc.i4.3
0x48f5e  ldstr    aStartnextbutto_2// "StartNextButtonStyle"
0x48f63  stelem.ref
0x48f64  stsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_startNavigationTemplateProperties
0x48f69  ldc.i4.8
0x48f6a  newarr   [mscorlib]System.String
0x48f6f  dup
0x48f70  ldc.i4.0
0x48f71  ldstr    aStepnextbutton_3// "StepNextButtonText"
0x48f76  stelem.ref
0x48f77  dup
0x48f78  ldc.i4.1
0x48f79  ldstr    aStepnextbutton_4// "StepNextButtonType"
0x48f7e  stelem.ref
0x48f7f  dup
0x48f80  ldc.i4.2
0x48f81  ldstr    aStepnextbutton_5// "StepNextButtonImageUrl"
0x48f86  stelem.ref
0x48f87  dup
0x48f88  ldc.i4.3
0x48f89  ldstr    aSteppreviousbu_2// "StepPreviousButtonText"
0x48f8e  stelem.ref
0x48f8f  dup
0x48f90  ldc.i4.4
0x48f91  ldstr    aSteppreviousbu_3// "StepPreviousButtonType"
0x48f96  stelem.ref
0x48f97  dup
0x48f98  ldc.i4.5
0x48f99  ldstr    aSteppreviousbu_4// "StepPreviousButtonImageUrl"
0x48f9e  stelem.ref
0x48f9f  dup
0x48fa0  ldc.i4.6
0x48fa1  ldstr    aSteppreviousbu_5// "StepPreviousButtonStyle"
0x48fa6  stelem.ref
0x48fa7  dup
0x48fa8  ldc.i4.7
0x48fa9  ldstr    aStepnextbutton_6// "StepNextButtonStyle"
0x48fae  stelem.ref
0x48faf  stsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_stepNavigationTemplateProperties
0x48fb4  ldc.i4.8
0x48fb5  newarr   [mscorlib]System.String
0x48fba  dup
0x48fbb  ldc.i4.0
0x48fbc  ldstr    aFinishcomplete// "FinishCompleteButtonText"
0x48fc1  stelem.ref
0x48fc2  dup
0x48fc3  ldc.i4.1
0x48fc4  ldstr    aFinishcomplete_0// "FinishCompleteButtonType"
0x48fc9  stelem.ref
0x48fca  dup
0x48fcb  ldc.i4.2
0x48fcc  ldstr    aFinishcomplete_1// "FinishCompleteButtonImageUrl"
0x48fd1  stelem.ref
0x48fd2  dup
0x48fd3  ldc.i4.3
0x48fd4  ldstr    aFinishprevious// "FinishPreviousButtonText"
0x48fd9  stelem.ref
0x48fda  dup
0x48fdb  ldc.i4.4
0x48fdc  ldstr    aFinishprevious_0// "FinishPreviousButtonType"
0x48fe1  stelem.ref
0x48fe2  dup
0x48fe3  ldc.i4.5
0x48fe4  ldstr    aFinishprevious_1// "FinishPreviousButtonImageUrl"
0x48fe9  stelem.ref
0x48fea  dup
0x48feb  ldc.i4.6
0x48fec  ldstr    aFinishcomplete_2// "FinishCompleteButtonStyle"
0x48ff1  stelem.ref
0x48ff2  dup
0x48ff3  ldc.i4.7
0x48ff4  ldstr    aFinishprevious_2// "FinishPreviousButtonStyle"
0x48ff9  stelem.ref
0x48ffa  stsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_finishNavigationTemplateProperties
0x48fff  ldc.i4.6
0x49000  newarr   [mscorlib]System.String
0x49005  dup
0x49006  ldc.i4.0
0x49007  ldstr    aCancelbuttonim// "CancelButtonImageUrl"
0x4900c  stelem.ref
0x4900d  dup
0x4900e  ldc.i4.1
0x4900f  ldstr    aCancelbuttonte// "CancelButtonText"
0x49014  stelem.ref
0x49015  dup
0x49016  ldc.i4.2
0x49017  ldstr    aCancelbuttonty// "CancelButtonType"
0x4901c  stelem.ref
0x4901d  dup
0x4901e  ldc.i4.3
0x4901f  ldstr    aDisplaycancelb// "DisplayCancelButton"
0x49024  stelem.ref
0x49025  dup
0x49026  ldc.i4.4
0x49027  ldstr    aCancelbuttonst// "CancelButtonStyle"
0x4902c  stelem.ref
0x4902d  dup
0x4902e  ldc.i4.5
0x4902f  ldstr    aNavigationbutt_6// "NavigationButtonStyle"
0x49034  stelem.ref
0x49035  stsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_generalNavigationButtonProperties
0x4903a  ldc.i4.1
0x4903b  newarr   [mscorlib]System.String
0x49040  dup
0x49041  ldc.i4.0
0x49042  ldstr    aHeadertext// "HeaderText"
0x49047  stelem.ref
0x49048  stsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_headerProperties
0x4904d  ldc.i4.1
0x4904e  newarr   [mscorlib]System.String
0x49053  dup
0x49054  ldc.i4.0
0x49055  ldstr    aSidebarbuttons_4// "SideBarButtonStyle"
0x4905a  stelem.ref
0x4905b  stsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_sideBarProperties
0x49060  ldc.i4.2
0x49061  newarr   [mscorlib]System.String
0x49066  dup
0x49067  ldc.i4.0
0x49068  ldstr    aStartnextbutto_3// "StartNextButton"
0x4906d  stelem.ref
0x4906e  dup
0x4906f  ldc.i4.1
0x49070  ldstr    aCancelbutton_0// "CancelButton"
0x49075  stelem.ref
0x49076  stsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_startButtonIDs
0x4907b  ldc.i4.3
0x4907c  newarr   [mscorlib]System.String
0x49081  dup
0x49082  ldc.i4.0
0x49083  ldstr    aSteppreviousbu_0// "StepPreviousButton"
0x49088  stelem.ref
0x49089  dup
0x4908a  ldc.i4.1
0x4908b  ldstr    aStepnextbutton// "StepNextButton"
0x49090  stelem.ref
0x49091  dup
0x49092  ldc.i4.2
0x49093  ldstr    aCancelbutton_0// "CancelButton"
0x49098  stelem.ref
0x49099  stsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_stepButtonIDs
0x4909e  ldc.i4.3
0x4909f  newarr   [mscorlib]System.String
0x490a4  dup
0x490a5  ldc.i4.0
0x490a6  ldstr    aFinishprevious_3// "FinishPreviousButton"
0x490ab  stelem.ref
0x490ac  dup
0x490ad  ldc.i4.1
0x490ae  ldstr    aFinishbutton// "FinishButton"
0x490b3  stelem.ref
0x490b4  dup
0x490b5  ldc.i4.2
0x490b6  ldstr    aCancelbutton_0// "CancelButton"
0x490bb  stelem.ref
0x490bc  stsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_finishButtonIDs
0x490c1  ret
```
