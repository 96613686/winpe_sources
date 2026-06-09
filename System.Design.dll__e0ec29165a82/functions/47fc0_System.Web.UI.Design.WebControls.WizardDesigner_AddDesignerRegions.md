# System.Web.UI.Design.WebControls.WizardDesigner::AddDesignerRegions

- ea: `0x47fc0`
- end: `0x480d6`
- name: `System.Web.UI.Design.WebControls.WizardDesigner::AddDesignerRegions`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x485e0`

## callees

- `0xb050`
- `0xb240`
- `0x10250`
- `0x47cf0`
- `0x47ec0`
- `0x47fc0`
- `0x48790`
- `0x49100`
- `0x49140`
- `0x49270`
- `0x8ef40`

## string_xrefs

- `0x47ff1`: `ContentTemplate`
- `0x47ffc`: `ContentTemplate`
- `0x48096`: `Move to `

## pseudocode

```c

```

## disassembly

```asm
0x47fc0  ldarg.0
0x47fc1  call     instance bool System.Web.UI.Design.WebControls.WizardDesigner::get_SupportsDesignerRegions()
0x47fc6  brtrue.s loc_47FC9
0x47fc8  ret
0x47fc9  ldarg.0
0x47fca  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x47fcf  callvirt instance class [System.Web]System.Web.UI.WebControls.WizardStepCollection [System.Web]System.Web.UI.WebControls.Wizard::get_WizardSteps()
0x47fd4  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.WebControls.WizardStepCollection::GetEnumerator()
0x47fd9  stloc.0
0x47fda  br.s     loc_48054
0x47fdc  ldloc.0
0x47fdd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x47fe2  castclass [System.Web]System.Web.UI.WebControls.WizardStepBase
0x47fe7  stloc.1
0x47fe8  ldloc.1
0x47fe9  isinst   [System.Web]System.Web.UI.WebControls.TemplatedWizardStep
0x47fee  brfalse.s loc_48031
0x47ff0  ldarg.0
0x47ff1  ldstr    aContenttemplat// "ContentTemplate"
0x47ff6  ldarg.0
0x47ff7  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x47ffc  ldstr    aContenttemplat// "ContentTemplate"
0x48001  ldarg.0
0x48002  call     instance class [System.Web]System.Web.UI.WebControls.Style[] System.Web.UI.Design.WebControls.WizardDesigner::get_TemplateStyleArray()
0x48007  ldc.i4.5
0x48008  ldelem.ref
0x48009  newobj   instance void System.Web.UI.Design.TemplateDefinition::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name, object templatedObject, string templatePropertyName, class [System.Web]System.Web.UI.WebControls.Style style)
0x4800e  stloc.2
0x4800f  ldloc.2
0x48010  ldloc.1
0x48011  newobj   instance void System.Web.UI.Design.WebControls.WizardStepTemplatedEditableRegion::.ctor(class System.Web.UI.Design.TemplateDefinition templateDefinition, class [System.Web]System.Web.UI.WebControls.WizardStepBase wizardStep)
0x48016  stloc.3
0x48017  ldloc.3
0x48018  ldstr    aContainercontr// "ContainerControlDesigner_RegionWatermar"...
0x4801d  call     string System.Design.SR::GetString(string name)
0x48022  callvirt instance void System.Web.UI.Design.DesignerRegion::set_Description(string value)
0x48027  ldarg.1
0x48028  ldloc.3
0x48029  callvirt instance int32 System.Web.UI.Design.DesignerRegionCollection::Add(class System.Web.UI.Design.DesignerRegion region)
0x4802e  pop
0x4802f  br.s     loc_48054
0x48031  ldarg.0
0x48032  ldloc.1
0x48033  newobj   instance void System.Web.UI.Design.WebControls.WizardStepEditableRegion::.ctor(class System.Web.UI.Design.WebControls.WizardDesigner designer, class [System.Web]System.Web.UI.WebControls.WizardStepBase wizardStep)
0x48038  stloc.s  4
0x4803a  ldloc.s  4
0x4803c  ldstr    aContainercontr// "ContainerControlDesigner_RegionWatermar"...
0x48041  call     string System.Design.SR::GetString(string name)
0x48046  callvirt instance void System.Web.UI.Design.DesignerRegion::set_Description(string value)
0x4804b  ldarg.1
0x4804c  ldloc.s  4
0x4804e  callvirt instance int32 System.Web.UI.Design.DesignerRegionCollection::Add(class System.Web.UI.Design.DesignerRegion region)
0x48053  pop
0x48054  ldloc.0
0x48055  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4805a  brtrue.s loc_47FDC
0x4805c  leave.s  loc_48072
0x4805e  ldloc.0
0x4805f  isinst   [mscorlib]System.IDisposable
0x48064  stloc.s  5
0x48066  ldloc.s  5
0x48068  brfalse.s loc_48071
0x4806a  ldloc.s  5
0x4806c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x48071  endfinally
0x48072  ldarg.0
0x48073  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x48078  callvirt instance class [System.Web]System.Web.UI.WebControls.WizardStepCollection [System.Web]System.Web.UI.WebControls.Wizard::get_WizardSteps()
0x4807d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.WebControls.WizardStepCollection::GetEnumerator()
0x48082  stloc.s  6
0x48084  br.s     loc_480B5
0x48086  ldloc.s  6
0x48088  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4808d  castclass [System.Web]System.Web.UI.WebControls.WizardStepBase
0x48092  stloc.s  7
0x48094  ldarg.1
0x48095  ldarg.0
0x48096  ldstr    aMoveTo// "Move to "
0x4809b  ldarg.0
0x4809c  ldloc.s  7
0x4809e  call     instance string System.Web.UI.Design.WebControls.WizardDesigner::GetRegionName(class [System.Web]System.Web.UI.WebControls.WizardStepBase step)
0x480a3  call     string [mscorlib]System.String::Concat(string, string)
0x480a8  ldloc.s  7
0x480aa  newobj   instance void System.Web.UI.Design.WebControls.WizardSelectableRegion::.ctor(class System.Web.UI.Design.WebControls.WizardDesigner designer, string name, class [System.Web]System.Web.UI.WebControls.WizardStepBase wizardStep)
0x480af  callvirt instance int32 System.Web.UI.Design.DesignerRegionCollection::Add(class System.Web.UI.Design.DesignerRegion region)
0x480b4  pop
0x480b5  ldloc.s  6
0x480b7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x480bc  brtrue.s loc_48086
0x480be  leave.s  loc_480D5
0x480c0  ldloc.s  6
0x480c2  isinst   [mscorlib]System.IDisposable
0x480c7  stloc.s  5
0x480c9  ldloc.s  5
0x480cb  brfalse.s loc_480D4
0x480cd  ldloc.s  5
0x480cf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x480d4  endfinally
0x480d5  ret
```
