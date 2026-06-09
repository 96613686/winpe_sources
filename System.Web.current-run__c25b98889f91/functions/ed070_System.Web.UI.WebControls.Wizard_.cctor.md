# System.Web.UI.WebControls.Wizard::.cctor

- ea: `0xed070`
- end: `0xed175`
- name: `System.Web.UI.WebControls.Wizard::.cctor`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## string_xrefs

- `0xed0c0`: `sideBarPlaceholder`
- `0xed0de`: `MoveNext`
- `0xed0e8`: `MovePrevious`
- `0xed0fc`: `MoveComplete`
- `0xed160`: `SideBarList`
- `0xed16a`: `SideBarButton`

## pseudocode

```c

```

## disassembly

```asm
0xed070  newobj   instance void [mscorlib]System.Object::.ctor()
0xed075  stsfld   object System.Web.UI.WebControls.Wizard::_eventActiveStepChanged
0xed07a  newobj   instance void [mscorlib]System.Object::.ctor()
0xed07f  stsfld   object System.Web.UI.WebControls.Wizard::_eventFinishButtonClick
0xed084  newobj   instance void [mscorlib]System.Object::.ctor()
0xed089  stsfld   object System.Web.UI.WebControls.Wizard::_eventNextButtonClick
0xed08e  newobj   instance void [mscorlib]System.Object::.ctor()
0xed093  stsfld   object System.Web.UI.WebControls.Wizard::_eventPreviousButtonClick
0xed098  newobj   instance void [mscorlib]System.Object::.ctor()
0xed09d  stsfld   object System.Web.UI.WebControls.Wizard::_eventSideBarButtonClick
0xed0a2  newobj   instance void [mscorlib]System.Object::.ctor()
0xed0a7  stsfld   object System.Web.UI.WebControls.Wizard::_eventCancelButtonClick
0xed0ac  ldstr    aHeaderplacehol// "headerPlaceholder"
0xed0b1  stsfld   string System.Web.UI.WebControls.Wizard::HeaderPlaceholderId
0xed0b6  ldstr    aNavigationplac// "navigationPlaceholder"
0xed0bb  stsfld   string System.Web.UI.WebControls.Wizard::NavigationPlaceholderId
0xed0c0  ldstr    aSidebarplaceho// "sideBarPlaceholder"
0xed0c5  stsfld   string System.Web.UI.WebControls.Wizard::SideBarPlaceholderId
0xed0ca  ldstr    aWizardstepplac// "wizardStepPlaceholder"
0xed0cf  stsfld   string System.Web.UI.WebControls.Wizard::WizardStepPlaceholderId
0xed0d4  ldstr    aCancel// "Cancel"
0xed0d9  stsfld   string System.Web.UI.WebControls.Wizard::CancelCommandName
0xed0de  ldstr    aMovenext// "MoveNext"
0xed0e3  stsfld   string System.Web.UI.WebControls.Wizard::MoveNextCommandName
0xed0e8  ldstr    aMoveprevious// "MovePrevious"
0xed0ed  stsfld   string System.Web.UI.WebControls.Wizard::MovePreviousCommandName
0xed0f2  ldstr    aMove// "Move"
0xed0f7  stsfld   string System.Web.UI.WebControls.Wizard::MoveToCommandName
0xed0fc  ldstr    aMovecomplete// "MoveComplete"
0xed101  stsfld   string System.Web.UI.WebControls.Wizard::MoveCompleteCommandName
0xed106  ldstr    aCancelbutton// "CancelButton"
0xed10b  stsfld   string System.Web.UI.WebControls.Wizard::CancelButtonID
0xed110  ldstr    aStartnextbutto_2// "StartNextButton"
0xed115  stsfld   string System.Web.UI.WebControls.Wizard::StartNextButtonID
0xed11a  ldstr    aSteppreviousbu_2// "StepPreviousButton"
0xed11f  stsfld   string System.Web.UI.WebControls.Wizard::StepPreviousButtonID
0xed124  ldstr    aStepnextbutton_2// "StepNextButton"
0xed129  stsfld   string System.Web.UI.WebControls.Wizard::StepNextButtonID
0xed12e  ldstr    aFinishbutton// "FinishButton"
0xed133  stsfld   string System.Web.UI.WebControls.Wizard::FinishButtonID
0xed138  ldstr    aFinishprevious_2// "FinishPreviousButton"
0xed13d  stsfld   string System.Web.UI.WebControls.Wizard::FinishPreviousButtonID
0xed142  ldstr    aCustomprevious// "CustomPreviousButton"
0xed147  stsfld   string System.Web.UI.WebControls.Wizard::CustomPreviousButtonID
0xed14c  ldstr    aCustomnextbutt// "CustomNextButton"
0xed151  stsfld   string System.Web.UI.WebControls.Wizard::CustomNextButtonID
0xed156  ldstr    aCustomfinishbu// "CustomFinishButton"
0xed15b  stsfld   string System.Web.UI.WebControls.Wizard::CustomFinishButtonID
0xed160  ldstr    aSidebarlist// "SideBarList"
0xed165  stsfld   string System.Web.UI.WebControls.Wizard::DataListID
0xed16a  ldstr    aSidebarbutton// "SideBarButton"
0xed16f  stsfld   string System.Web.UI.WebControls.Wizard::SideBarButtonID
0xed174  ret
```
