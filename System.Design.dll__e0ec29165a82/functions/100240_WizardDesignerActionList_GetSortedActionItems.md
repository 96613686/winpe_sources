# WizardDesignerActionList::GetSortedActionItems

- ea: `0x100240`
- end: `0x100594`
- name: `WizardDesignerActionList::GetSortedActionItems`
- size: `852`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x2660`
- `0x47c00`
- `0x47c30`
- `0x598e0`
- `0x5af90`
- `0x5d870`
- `0x5d8b0`
- `0x8eec0`
- `0x8ef40`
- `0x100240`

## string_xrefs

- `0x10055f`: `Wizard_ConvertToCustomNavigationTemplate`
- `0x10033f`: `Wizard_ConvertToStartNavigationTemplate`
- `0x1003bd`: `Wizard_ConvertToStepNavigationTemplate`
- `0x10043b`: `Wizard_ConvertToFinishNavigationTemplate`
- `0x1004c1`: `Wizard_ConvertToSideBarTemplate`
- `0x100523`: `Wizard_ResetCustomNavigationTemplate`
- `0x100303`: `Wizard_ResetStartNavigationTemplate`
- `0x100381`: `Wizard_ResetStepNavigationTemplate`
- `0x1003ff`: `Wizard_ResetFinishNavigationTemplate`
- `0x100485`: `Wizard_ResetSideBarTemplate`
- `0x1002fe`: `ResetStartNavigationTemplate`
- `0x10033a`: `ConvertToStartNavigationTemplate`
- `0x10034e`: `Wizard_ConvertToTemplateDescription`
- `0x1003cc`: `Wizard_ConvertToTemplateDescription`
- `0x10044a`: `Wizard_ConvertToTemplateDescription`
- `0x1004d0`: `Wizard_ConvertToTemplateDescription`
- `0x10056e`: `Wizard_ConvertToTemplateDescription`
- `0x10037c`: `ResetStepNavigationTemplate`
- `0x1003b8`: `ConvertToStepNavigationTemplate`
- `0x1003fa`: `ResetFinishNavigationTemplate`
- `0x100436`: `ConvertToFinishNavigationTemplate`
- `0x100480`: `ResetSideBarTemplate`
- `0x1004a1`: `SideBar`
- `0x1004dd`: `SideBar`
- `0x1004bc`: `ConvertToSideBarTemplate`
- `0x10051e`: `ResetCustomNavigationTemplate`
- `0x10055a`: `ConvertToCustomNavigationTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x100240  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0x100245  stloc.0
0x100246  ldarg.0
0x100247  ldfld    class System.Web.UI.Design.WebControls.WizardDesigner WizardDesignerActionList::_designer
0x10024c  callvirt instance bool System.Web.UI.Design.ControlDesigner::get_InTemplateMode()
0x100251  brtrue   loc_100592
0x100256  ldarg.0
0x100257  ldfld    class System.Web.UI.Design.WebControls.WizardDesigner WizardDesignerActionList::_designer
0x10025c  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x100261  callvirt instance class [System.Web]System.Web.UI.WebControls.WizardStepCollection [System.Web]System.Web.UI.WebControls.Wizard::get_WizardSteps()
0x100266  callvirt instance int32 [System.Web]System.Web.UI.WebControls.WizardStepCollection::get_Count()
0x10026b  ldc.i4.0
0x10026c  ble.s    loc_100298
0x10026e  ldloc.0
0x10026f  ldstr    aView// "View"
0x100274  ldstr    aWizardStepsvie// "Wizard_StepsView"
0x100279  call     string System.Design.SR::GetString(string name)
0x10027e  ldsfld   string [mscorlib]System.String::Empty
0x100283  ldstr    aWizardStepsvie_0// "Wizard_StepsViewDescription"
0x100288  call     string System.Design.SR::GetString(string name)
0x10028d  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x100292  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x100297  pop
0x100298  ldloc.0
0x100299  ldarg.0
0x10029a  ldstr    aStartwizardste// "StartWizardStepCollectionEditor"
0x10029f  ldstr    aWizardStartwiz// "Wizard_StartWizardStepCollectionEditor"
0x1002a4  call     string System.Design.SR::GetString(string name)
0x1002a9  ldsfld   string [mscorlib]System.String::Empty
0x1002ae  ldstr    aWizardStartwiz_0// "Wizard_StartWizardStepCollectionEditorD"...
0x1002b3  call     string System.Design.SR::GetString(string name)
0x1002b8  ldc.i4.1
0x1002b9  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0x1002be  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x1002c3  pop
0x1002c4  ldarg.0
0x1002c5  ldfld    class System.Web.UI.Design.WebControls.WizardDesigner WizardDesignerActionList::_designer
0x1002ca  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x1002cf  stloc.1
0x1002d0  ldarg.0
0x1002d1  ldfld    class System.Web.UI.Design.WebControls.WizardDesigner WizardDesignerActionList::_designer
0x1002d6  callvirt instance int32 System.Web.UI.Design.WebControls.WizardDesigner::get_ActiveStepIndex()
0x1002db  stloc.2
0x1002dc  ldloc.2
0x1002dd  ldc.i4.0
0x1002de  blt      loc_100592
0x1002e3  ldloc.2
0x1002e4  ldloc.1
0x1002e5  callvirt instance class [System.Web]System.Web.UI.WebControls.WizardStepCollection [System.Web]System.Web.UI.WebControls.Wizard::get_WizardSteps()
0x1002ea  callvirt instance int32 [System.Web]System.Web.UI.WebControls.WizardStepCollection::get_Count()
0x1002ef  bge      loc_100592
0x1002f4  ldloc.1
0x1002f5  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.Wizard::get_StartNavigationTemplate()
0x1002fa  brfalse.s loc_100338
0x1002fc  ldloc.0
0x1002fd  ldarg.0
0x1002fe  ldstr    aResetstartnavi// "ResetStartNavigationTemplate"
0x100303  ldstr    aWizardResetsta// "Wizard_ResetStartNavigationTemplate"
0x100308  call     string System.Design.SR::GetString(string name)
0x10030d  ldsfld   string [mscorlib]System.String::Empty
0x100312  ldstr    aWizardResetdes// "Wizard_ResetDescription"
0x100317  ldc.i4.1
0x100318  newarr   [mscorlib]System.Object
0x10031d  dup
0x10031e  ldc.i4.0
0x10031f  ldstr    aStartnavigatio_0// "StartNavigation"
0x100324  stelem.ref
0x100325  call     string System.Design.SR::GetString(string name, object[] args)
0x10032a  ldc.i4.1
0x10032b  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0x100330  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x100335  pop
0x100336  br.s     loc_100372
0x100338  ldloc.0
0x100339  ldarg.0
0x10033a  ldstr    aConverttostart// "ConvertToStartNavigationTemplate"
0x10033f  ldstr    aWizardConvertt_0// "Wizard_ConvertToStartNavigationTemplate"
0x100344  call     string System.Design.SR::GetString(string name)
0x100349  ldsfld   string [mscorlib]System.String::Empty
0x10034e  ldstr    aWizardConvertt_4// "Wizard_ConvertToTemplateDescription"
0x100353  ldc.i4.1
0x100354  newarr   [mscorlib]System.Object
0x100359  dup
0x10035a  ldc.i4.0
0x10035b  ldstr    aStartnavigatio_0// "StartNavigation"
0x100360  stelem.ref
0x100361  call     string System.Design.SR::GetString(string name, object[] args)
0x100366  ldc.i4.1
0x100367  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0x10036c  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x100371  pop
0x100372  ldloc.1
0x100373  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.Wizard::get_StepNavigationTemplate()
0x100378  brfalse.s loc_1003B6
0x10037a  ldloc.0
0x10037b  ldarg.0
0x10037c  ldstr    aResetstepnavig// "ResetStepNavigationTemplate"
0x100381  ldstr    aWizardResetste// "Wizard_ResetStepNavigationTemplate"
0x100386  call     string System.Design.SR::GetString(string name)
0x10038b  ldsfld   string [mscorlib]System.String::Empty
0x100390  ldstr    aWizardResetdes// "Wizard_ResetDescription"
0x100395  ldc.i4.1
0x100396  newarr   [mscorlib]System.Object
0x10039b  dup
0x10039c  ldc.i4.0
0x10039d  ldstr    aStepnavigation_0// "StepNavigation"
0x1003a2  stelem.ref
0x1003a3  call     string System.Design.SR::GetString(string name, object[] args)
0x1003a8  ldc.i4.1
0x1003a9  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0x1003ae  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x1003b3  pop
0x1003b4  br.s     loc_1003F0
0x1003b6  ldloc.0
0x1003b7  ldarg.0
0x1003b8  ldstr    aConverttostepn// "ConvertToStepNavigationTemplate"
0x1003bd  ldstr    aWizardConvertt_1// "Wizard_ConvertToStepNavigationTemplate"
0x1003c2  call     string System.Design.SR::GetString(string name)
0x1003c7  ldsfld   string [mscorlib]System.String::Empty
0x1003cc  ldstr    aWizardConvertt_4// "Wizard_ConvertToTemplateDescription"
0x1003d1  ldc.i4.1
0x1003d2  newarr   [mscorlib]System.Object
0x1003d7  dup
0x1003d8  ldc.i4.0
0x1003d9  ldstr    aStepnavigation_0// "StepNavigation"
0x1003de  stelem.ref
0x1003df  call     string System.Design.SR::GetString(string name, object[] args)
0x1003e4  ldc.i4.1
0x1003e5  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0x1003ea  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x1003ef  pop
0x1003f0  ldloc.1
0x1003f1  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.Wizard::get_FinishNavigationTemplate()
0x1003f6  brfalse.s loc_100434
0x1003f8  ldloc.0
0x1003f9  ldarg.0
0x1003fa  ldstr    aResetfinishnav// "ResetFinishNavigationTemplate"
0x1003ff  ldstr    aWizardResetfin// "Wizard_ResetFinishNavigationTemplate"
0x100404  call     string System.Design.SR::GetString(string name)
0x100409  ldsfld   string [mscorlib]System.String::Empty
0x10040e  ldstr    aWizardResetdes// "Wizard_ResetDescription"
0x100413  ldc.i4.1
0x100414  newarr   [mscorlib]System.Object
0x100419  dup
0x10041a  ldc.i4.0
0x10041b  ldstr    aFinishnavigati_0// "FinishNavigation"
0x100420  stelem.ref
0x100421  call     string System.Design.SR::GetString(string name, object[] args)
0x100426  ldc.i4.1
0x100427  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0x10042c  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x100431  pop
0x100432  br.s     loc_10046E
0x100434  ldloc.0
0x100435  ldarg.0
0x100436  ldstr    aConverttofinis// "ConvertToFinishNavigationTemplate"
0x10043b  ldstr    aWizardConvertt_2// "Wizard_ConvertToFinishNavigationTemplat"...
0x100440  call     string System.Design.SR::GetString(string name)
0x100445  ldsfld   string [mscorlib]System.String::Empty
0x10044a  ldstr    aWizardConvertt_4// "Wizard_ConvertToTemplateDescription"
0x10044f  ldc.i4.1
0x100450  newarr   [mscorlib]System.Object
0x100455  dup
0x100456  ldc.i4.0
0x100457  ldstr    aFinishnavigati_0// "FinishNavigation"
0x10045c  stelem.ref
0x10045d  call     string System.Design.SR::GetString(string name, object[] args)
0x100462  ldc.i4.1
0x100463  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0x100468  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x10046d  pop
0x10046e  ldloc.1
0x10046f  callvirt instance bool [System.Web]System.Web.UI.WebControls.Wizard::get_DisplaySideBar()
0x100474  brfalse.s loc_1004F4
0x100476  ldloc.1
0x100477  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.Wizard::get_SideBarTemplate()
0x10047c  brfalse.s loc_1004BA
0x10047e  ldloc.0
0x10047f  ldarg.0
0x100480  ldstr    aResetsidebarte// "ResetSideBarTemplate"
0x100485  ldstr    aWizardResetsid// "Wizard_ResetSideBarTemplate"
0x10048a  call     string System.Design.SR::GetString(string name)
0x10048f  ldsfld   string [mscorlib]System.String::Empty
0x100494  ldstr    aWizardResetdes// "Wizard_ResetDescription"
0x100499  ldc.i4.1
0x10049a  newarr   [mscorlib]System.Object
0x10049f  dup
0x1004a0  ldc.i4.0
0x1004a1  ldstr    aSidebar// "SideBar"
0x1004a6  stelem.ref
0x1004a7  call     string System.Design.SR::GetString(string name, object[] args)
0x1004ac  ldc.i4.1
0x1004ad  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0x1004b2  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x1004b7  pop
0x1004b8  br.s     loc_1004F4
0x1004ba  ldloc.0
0x1004bb  ldarg.0
0x1004bc  ldstr    aConverttosideb// "ConvertToSideBarTemplate"
0x1004c1  ldstr    aWizardConvertt_3// "Wizard_ConvertToSideBarTemplate"
0x1004c6  call     string System.Design.SR::GetString(string name)
0x1004cb  ldsfld   string [mscorlib]System.String::Empty
0x1004d0  ldstr    aWizardConvertt_4// "Wizard_ConvertToTemplateDescription"
0x1004d5  ldc.i4.1
0x1004d6  newarr   [mscorlib]System.Object
0x1004db  dup
0x1004dc  ldc.i4.0
0x1004dd  ldstr    aSidebar// "SideBar"
0x1004e2  stelem.ref
0x1004e3  call     string System.Design.SR::GetString(string name, object[] args)
0x1004e8  ldc.i4.1
0x1004e9  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0x1004ee  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x1004f3  pop
0x1004f4  ldarg.0
0x1004f5  ldfld    class System.Web.UI.Design.WebControls.WizardDesigner WizardDesignerActionList::_designer
0x1004fa  callvirt instance class [System.Web]System.Web.UI.WebControls.WizardStepBase System.Web.UI.Design.WebControls.WizardDesigner::get_ActiveStep()
0x1004ff  isinst   [System.Web]System.Web.UI.WebControls.TemplatedWizardStep
0x100504  stloc.3
0x100505  ldloc.3
0x100506  brfalse  loc_100592
0x10050b  ldloc.3
0x10050c  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.WizardStepType [System.Web]System.Web.UI.WebControls.WizardStepBase::get_StepType()
0x100511  ldc.i4.1
0x100512  beq.s    loc_100592
0x100514  ldloc.3
0x100515  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.TemplatedWizardStep::get_CustomNavigationTemplate()
0x10051a  brfalse.s loc_100558
0x10051c  ldloc.0
0x10051d  ldarg.0
0x10051e  ldstr    aResetcustomnav// "ResetCustomNavigationTemplate"
0x100523  ldstr    aWizardResetcus// "Wizard_ResetCustomNavigationTemplate"
0x100528  call     string System.Design.SR::GetString(string name)
0x10052d  ldsfld   string [mscorlib]System.String::Empty
0x100532  ldstr    aWizardResetdes// "Wizard_ResetDescription"
0x100537  ldc.i4.1
0x100538  newarr   [mscorlib]System.Object
0x10053d  dup
0x10053e  ldc.i4.0
0x10053f  ldstr    aCustomnavigati_1// "CustomNavigation"
0x100544  stelem.ref
0x100545  call     string System.Design.SR::GetString(string name, object[] args)
0x10054a  ldc.i4.1
0x10054b  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0x100550  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x100555  pop
0x100556  br.s     loc_100592
0x100558  ldloc.0
0x100559  ldarg.0
0x10055a  ldstr    aConverttocusto// "ConvertToCustomNavigationTemplate"
0x10055f  ldstr    aWizardConvertt// "Wizard_ConvertToCustomNavigationTemplat"...
0x100564  call     string System.Design.SR::GetString(string name)
0x100569  ldsfld   string [mscorlib]System.String::Empty
0x10056e  ldstr    aWizardConvertt_4// "Wizard_ConvertToTemplateDescription"
0x100573  ldc.i4.1
0x100574  newarr   [mscorlib]System.Object
0x100579  dup
0x10057a  ldc.i4.0
0x10057b  ldstr    aCustomnavigati_1// "CustomNavigation"
0x100580  stelem.ref
0x100581  call     string System.Design.SR::GetString(string name, object[] args)
0x100586  ldc.i4.1
0x100587  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0x10058c  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x100591  pop
0x100592  ldloc.0
0x100593  ret
```
