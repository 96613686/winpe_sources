# System.Web.UI.Design.WebControls.CreateUserWizardDesigner::AddDesignerRegions

- ea: `0x1a840`
- end: `0x1a9eb`
- name: `System.Web.UI.Design.WebControls.CreateUserWizardDesigner::AddDesignerRegions`
- size: `427`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0xb050`
- `0xb0a0`
- `0xb100`
- `0xb240`
- `0x10250`
- `0x18be0`
- `0x1a840`
- `0x47cf0`
- `0x47ec0`
- `0x48790`
- `0x49100`
- `0x49140`
- `0x49270`
- `0x8ef40`

## string_xrefs

- `0x1a8e3`: `ContentTemplate`
- `0x1a8ee`: `ContentTemplate`
- `0x1a98f`: `Move to `

## pseudocode

```c

```

## disassembly

```asm
0x1a840  ldarg.0
0x1a841  call     instance bool System.Web.UI.Design.WebControls.WizardDesigner::get_SupportsDesignerRegions()
0x1a846  brtrue.s loc_1A849
0x1a848  ret
0x1a849  ldarg.0
0x1a84a  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1a84f  callvirt instance class [System.Web]System.Web.UI.WebControls.CreateUserWizardStep [System.Web]System.Web.UI.WebControls.CreateUserWizard::get_CreateUserStep()
0x1a854  brtrue.s loc_1A86A
0x1a856  ldarg.0
0x1a857  callvirt instance void System.Web.UI.Design.WebControls.CompositeControlDesigner::CreateChildControls()
0x1a85c  ldarg.0
0x1a85d  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1a862  callvirt instance class [System.Web]System.Web.UI.WebControls.CreateUserWizardStep [System.Web]System.Web.UI.WebControls.CreateUserWizard::get_CreateUserStep()
0x1a867  brtrue.s loc_1A86A
0x1a869  ret
0x1a86a  ldarg.0
0x1a86b  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1a870  callvirt instance class [System.Web]System.Web.UI.WebControls.CreateUserWizardStep [System.Web]System.Web.UI.WebControls.CreateUserWizard::get_CreateUserStep()
0x1a875  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.TemplatedWizardStep::get_ContentTemplate()
0x1a87a  ldnull
0x1a87b  ceq
0x1a87d  stloc.0
0x1a87e  ldarg.0
0x1a87f  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1a884  callvirt instance class [System.Web]System.Web.UI.WebControls.CompleteWizardStep [System.Web]System.Web.UI.WebControls.CreateUserWizard::get_CompleteStep()
0x1a889  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.TemplatedWizardStep::get_ContentTemplate()
0x1a88e  ldnull
0x1a88f  ceq
0x1a891  stloc.1
0x1a892  ldarg.0
0x1a893  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1a898  callvirt instance class [System.Web]System.Web.UI.WebControls.WizardStepCollection [System.Web]System.Web.UI.WebControls.Wizard::get_WizardSteps()
0x1a89d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.WebControls.WizardStepCollection::GetEnumerator()
0x1a8a2  stloc.2
0x1a8a3  br       loc_1A94B
0x1a8a8  ldloc.2
0x1a8a9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1a8ae  castclass [System.Web]System.Web.UI.WebControls.WizardStepBase
0x1a8b3  stloc.3
0x1a8b4  ldloc.0
0x1a8b5  brfalse.s loc_1A8BF
0x1a8b7  ldloc.3
0x1a8b8  isinst   [System.Web]System.Web.UI.WebControls.CreateUserWizardStep
0x1a8bd  brtrue.s loc_1A8D0
0x1a8bf  ldloc.1
0x1a8c0  brfalse.s loc_1A8CD
0x1a8c2  ldloc.3
0x1a8c3  isinst   [System.Web]System.Web.UI.WebControls.CompleteWizardStep
0x1a8c8  ldnull
0x1a8c9  cgt.un
0x1a8cb  br.s     loc_1A8D1
0x1a8cd  ldc.i4.0
0x1a8ce  br.s     loc_1A8D1
0x1a8d0  ldc.i4.1
0x1a8d1  stloc.s  4
0x1a8d3  ldnull
0x1a8d4  stloc.s  5
0x1a8d6  ldloc.s  4
0x1a8d8  brtrue.s loc_1A932
0x1a8da  ldloc.3
0x1a8db  isinst   [System.Web]System.Web.UI.WebControls.TemplatedWizardStep
0x1a8e0  brfalse.s loc_1A916
0x1a8e2  ldarg.0
0x1a8e3  ldstr    aContenttemplat// "ContentTemplate"
0x1a8e8  ldarg.0
0x1a8e9  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1a8ee  ldstr    aContenttemplat// "ContentTemplate"
0x1a8f3  ldarg.0
0x1a8f4  call     instance class [System.Web]System.Web.UI.WebControls.Style[] System.Web.UI.Design.WebControls.WizardDesigner::get_TemplateStyleArray()
0x1a8f9  ldc.i4.5
0x1a8fa  ldelem.ref
0x1a8fb  newobj   instance void System.Web.UI.Design.TemplateDefinition::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name, object templatedObject, string templatePropertyName, class [System.Web]System.Web.UI.WebControls.Style style)
0x1a900  stloc.s  6
0x1a902  ldloc.s  6
0x1a904  ldloc.3
0x1a905  newobj   instance void System.Web.UI.Design.WebControls.WizardStepTemplatedEditableRegion::.ctor(class System.Web.UI.Design.TemplateDefinition templateDefinition, class [System.Web]System.Web.UI.WebControls.WizardStepBase wizardStep)
0x1a90a  stloc.s  5
0x1a90c  ldloc.s  5
0x1a90e  ldc.i4.0
0x1a90f  callvirt instance void System.Web.UI.Design.DesignerRegion::set_EnsureSize(bool value)
0x1a914  br.s     loc_1A91F
0x1a916  ldarg.0
0x1a917  ldloc.3
0x1a918  newobj   instance void System.Web.UI.Design.WebControls.WizardStepEditableRegion::.ctor(class System.Web.UI.Design.WebControls.WizardDesigner designer, class [System.Web]System.Web.UI.WebControls.WizardStepBase wizardStep)
0x1a91d  stloc.s  5
0x1a91f  ldloc.s  5
0x1a921  ldstr    aContainercontr// "ContainerControlDesigner_RegionWatermar"...
0x1a926  call     string System.Design.SR::GetString(string name)
0x1a92b  callvirt instance void System.Web.UI.Design.DesignerRegion::set_Description(string value)
0x1a930  br.s     loc_1A942
0x1a932  ldarg.0
0x1a933  ldarg.0
0x1a934  ldloc.3
0x1a935  call     instance string System.Web.UI.Design.WebControls.WizardDesigner::GetRegionName(class [System.Web]System.Web.UI.WebControls.WizardStepBase step)
0x1a93a  ldloc.3
0x1a93b  newobj   instance void System.Web.UI.Design.WebControls.WizardSelectableRegion::.ctor(class System.Web.UI.Design.WebControls.WizardDesigner designer, string name, class [System.Web]System.Web.UI.WebControls.WizardStepBase wizardStep)
0x1a940  stloc.s  5
0x1a942  ldarg.1
0x1a943  ldloc.s  5
0x1a945  callvirt instance int32 System.Web.UI.Design.DesignerRegionCollection::Add(class System.Web.UI.Design.DesignerRegion region)
0x1a94a  pop
0x1a94b  ldloc.2
0x1a94c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a951  brtrue   loc_1A8A8
0x1a956  leave.s  loc_1A96C
0x1a958  ldloc.2
0x1a959  isinst   [mscorlib]System.IDisposable
0x1a95e  stloc.s  7
0x1a960  ldloc.s  7
0x1a962  brfalse.s loc_1A96B
0x1a964  ldloc.s  7
0x1a966  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a96b  endfinally
0x1a96c  ldarg.0
0x1a96d  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1a972  callvirt instance class [System.Web]System.Web.UI.WebControls.WizardStepCollection [System.Web]System.Web.UI.WebControls.Wizard::get_WizardSteps()
0x1a977  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.WebControls.WizardStepCollection::GetEnumerator()
0x1a97c  stloc.s  8
0x1a97e  br.s     loc_1A9CA
0x1a980  ldloc.s  8
0x1a982  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1a987  castclass [System.Web]System.Web.UI.WebControls.WizardStepBase
0x1a98c  stloc.s  9
0x1a98e  ldarg.0
0x1a98f  ldstr    aMoveTo// "Move to "
0x1a994  ldarg.0
0x1a995  ldloc.s  9
0x1a997  call     instance string System.Web.UI.Design.WebControls.WizardDesigner::GetRegionName(class [System.Web]System.Web.UI.WebControls.WizardStepBase step)
0x1a99c  call     string [mscorlib]System.String::Concat(string, string)
0x1a9a1  ldloc.s  9
0x1a9a3  newobj   instance void System.Web.UI.Design.WebControls.WizardSelectableRegion::.ctor(class System.Web.UI.Design.WebControls.WizardDesigner designer, string name, class [System.Web]System.Web.UI.WebControls.WizardStepBase wizardStep)
0x1a9a8  stloc.s  0xA
0x1a9aa  ldarg.0
0x1a9ab  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1a9b0  callvirt instance class [System.Web]System.Web.UI.WebControls.WizardStepBase [System.Web]System.Web.UI.WebControls.Wizard::get_ActiveStep()
0x1a9b5  ldloc.s  9
0x1a9b7  bne.un.s loc_1A9C1
0x1a9b9  ldloc.s  0xA
0x1a9bb  ldc.i4.1
0x1a9bc  callvirt instance void System.Web.UI.Design.DesignerRegion::set_Selected(bool value)
0x1a9c1  ldarg.1
0x1a9c2  ldloc.s  0xA
0x1a9c4  callvirt instance int32 System.Web.UI.Design.DesignerRegionCollection::Add(class System.Web.UI.Design.DesignerRegion region)
0x1a9c9  pop
0x1a9ca  ldloc.s  8
0x1a9cc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a9d1  brtrue.s loc_1A980
0x1a9d3  leave.s  loc_1A9EA
0x1a9d5  ldloc.s  8
0x1a9d7  isinst   [mscorlib]System.IDisposable
0x1a9dc  stloc.s  7
0x1a9de  ldloc.s  7
0x1a9e0  brfalse.s loc_1A9E9
0x1a9e2  ldloc.s  7
0x1a9e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a9e9  endfinally
0x1a9ea  ret
```
