# System.Web.UI.WebControls.CreateUserWizard::InstantiateStepContentTemplates

- ea: `0xa03f0`
- end: `0xa0571`
- name: `System.Web.UI.WebControls.CreateUserWizard::InstantiateStepContentTemplates`
- size: `385`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x5f1e0`
- `0x611a0`
- `0x66310`
- `0x664f0`
- `0x6e390`
- `0x9daa0`
- `0x9dde0`
- `0xa03f0`
- `0xded90`
- `0xdede0`
- `0xeb680`
- `0xebb80`
- `0xec5e0`
- `0xed360`
- `0x19dcb0`
- `0x19ded0`
- `0x19eb40`
- `0x19f0d0`
- `0x1a7090`
- `0x1a7210`

## string_xrefs

- `0xa0441`: `CreateUserStepContainer`
- `0xa04d0`: `CompleteStepContainer`

## pseudocode

```c

```

## disassembly

```asm
0xa03f0  ldarg.0
0xa03f1  callvirt instance class System.Web.UI.ITemplate System.Web.UI.WebControls.Wizard::get_LayoutTemplate()
0xa03f6  ldnull
0xa03f7  ceq
0xa03f9  stloc.0
0xa03fa  ldarg.0
0xa03fb  callvirt instance class System.Web.UI.WebControls.WizardStepCollection System.Web.UI.WebControls.Wizard::get_WizardSteps()
0xa0400  callvirt instance class [mscorlib]System.Collections.IEnumerator System.Web.UI.WebControls.WizardStepCollection::GetEnumerator()
0xa0405  stloc.1
0xa0406  br       loc_A054F
0xa040b  ldloc.1
0xa040c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa0411  castclass System.Web.UI.WebControls.WizardStepBase
0xa0416  stloc.2
0xa0417  ldloc.2
0xa0418  ldarg.0
0xa0419  call     instance class System.Web.UI.WebControls.CreateUserWizardStep System.Web.UI.WebControls.CreateUserWizard::get_CreateUserStep()
0xa041e  bne.un   loc_A04A6
0xa0423  ldloc.2
0xa0424  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0xa0429  callvirt instance void System.Web.UI.ControlCollection::Clear()
0xa042e  ldarg.0
0xa042f  ldarg.0
0xa0430  ldloc.0
0xa0431  newobj   instance void CreateUserStepContainer::.ctor(class System.Web.UI.WebControls.CreateUserWizard wizard, bool useInnerTable)
0xa0436  stfld    class CreateUserStepContainer System.Web.UI.WebControls.CreateUserWizard::_createUserStepContainer
0xa043b  ldarg.0
0xa043c  ldfld    class CreateUserStepContainer System.Web.UI.WebControls.CreateUserWizard::_createUserStepContainer
0xa0441  ldstr    aCreateuserstep// "CreateUserStepContainer"
0xa0446  callvirt instance void System.Web.UI.Control::set_ID(string value)
0xa044b  ldarg.0
0xa044c  call     instance class System.Web.UI.WebControls.CreateUserWizardStep System.Web.UI.WebControls.CreateUserWizard::get_CreateUserStep()
0xa0451  callvirt instance class System.Web.UI.ITemplate System.Web.UI.WebControls.TemplatedWizardStep::get_ContentTemplate()
0xa0456  stloc.3
0xa0457  ldloc.3
0xa0458  brtrue.s loc_A0463
0xa045a  ldarg.0
0xa045b  newobj   instance void DefaultCreateUserContentTemplate::.ctor(class System.Web.UI.WebControls.CreateUserWizard wizard)
0xa0460  stloc.3
0xa0461  br.s     loc_A046E
0xa0463  ldarg.0
0xa0464  ldfld    class CreateUserStepContainer System.Web.UI.WebControls.CreateUserWizard::_createUserStepContainer
0xa0469  callvirt instance void BlockControl::SetEnableTheming()
0xa046e  ldloc.3
0xa046f  ldarg.0
0xa0470  ldfld    class CreateUserStepContainer System.Web.UI.WebControls.CreateUserWizard::_createUserStepContainer
0xa0475  callvirt instance class System.Web.UI.Control BaseContentTemplateContainer::get_Container()
0xa047a  callvirt instance void System.Web.UI.ITemplate::InstantiateIn(class System.Web.UI.Control container)
0xa047f  ldarg.0
0xa0480  call     instance class System.Web.UI.WebControls.CreateUserWizardStep System.Web.UI.WebControls.CreateUserWizard::get_CreateUserStep()
0xa0485  ldarg.0
0xa0486  ldfld    class CreateUserStepContainer System.Web.UI.WebControls.CreateUserWizard::_createUserStepContainer
0xa048b  callvirt instance void System.Web.UI.WebControls.TemplatedWizardStep::set_ContentTemplateContainer(class System.Web.UI.Control value)
0xa0490  ldloc.2
0xa0491  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0xa0496  ldarg.0
0xa0497  ldfld    class CreateUserStepContainer System.Web.UI.WebControls.CreateUserWizard::_createUserStepContainer
0xa049c  callvirt instance void System.Web.UI.ControlCollection::Add(class System.Web.UI.Control child)
0xa04a1  br       loc_A054F
0xa04a6  ldloc.2
0xa04a7  ldarg.0
0xa04a8  call     instance class System.Web.UI.WebControls.CompleteWizardStep System.Web.UI.WebControls.CreateUserWizard::get_CompleteStep()
0xa04ad  bne.un   loc_A053B
0xa04b2  ldloc.2
0xa04b3  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0xa04b8  callvirt instance void System.Web.UI.ControlCollection::Clear()
0xa04bd  ldarg.0
0xa04be  ldarg.0
0xa04bf  ldloc.0
0xa04c0  newobj   instance void CompleteStepContainer::.ctor(class System.Web.UI.WebControls.CreateUserWizard wizard, bool useInnerTable)
0xa04c5  stfld    class CompleteStepContainer System.Web.UI.WebControls.CreateUserWizard::_completeStepContainer
0xa04ca  ldarg.0
0xa04cb  ldfld    class CompleteStepContainer System.Web.UI.WebControls.CreateUserWizard::_completeStepContainer
0xa04d0  ldstr    aCompletestepco// "CompleteStepContainer"
0xa04d5  callvirt instance void System.Web.UI.Control::set_ID(string value)
0xa04da  ldarg.0
0xa04db  call     instance class System.Web.UI.WebControls.CompleteWizardStep System.Web.UI.WebControls.CreateUserWizard::get_CompleteStep()
0xa04e0  callvirt instance class System.Web.UI.ITemplate System.Web.UI.WebControls.TemplatedWizardStep::get_ContentTemplate()
0xa04e5  stloc.s  4
0xa04e7  ldloc.s  4
0xa04e9  brtrue.s loc_A04FA
0xa04eb  ldarg.0
0xa04ec  ldfld    class CompleteStepContainer System.Web.UI.WebControls.CreateUserWizard::_completeStepContainer
0xa04f1  newobj   instance void DefaultCompleteStepContentTemplate::.ctor(class CompleteStepContainer container)
0xa04f6  stloc.s  4
0xa04f8  br.s     loc_A0505
0xa04fa  ldarg.0
0xa04fb  ldfld    class CompleteStepContainer System.Web.UI.WebControls.CreateUserWizard::_completeStepContainer
0xa0500  callvirt instance void BlockControl::SetEnableTheming()
0xa0505  ldloc.s  4
0xa0507  ldarg.0
0xa0508  ldfld    class CompleteStepContainer System.Web.UI.WebControls.CreateUserWizard::_completeStepContainer
0xa050d  callvirt instance class System.Web.UI.Control BaseContentTemplateContainer::get_Container()
0xa0512  callvirt instance void System.Web.UI.ITemplate::InstantiateIn(class System.Web.UI.Control container)
0xa0517  ldarg.0
0xa0518  call     instance class System.Web.UI.WebControls.CompleteWizardStep System.Web.UI.WebControls.CreateUserWizard::get_CompleteStep()
0xa051d  ldarg.0
0xa051e  ldfld    class CompleteStepContainer System.Web.UI.WebControls.CreateUserWizard::_completeStepContainer
0xa0523  callvirt instance void System.Web.UI.WebControls.TemplatedWizardStep::set_ContentTemplateContainer(class System.Web.UI.Control value)
0xa0528  ldloc.2
0xa0529  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0xa052e  ldarg.0
0xa052f  ldfld    class CompleteStepContainer System.Web.UI.WebControls.CreateUserWizard::_completeStepContainer
0xa0534  callvirt instance void System.Web.UI.ControlCollection::Add(class System.Web.UI.Control child)
0xa0539  br.s     loc_A054F
0xa053b  ldloc.2
0xa053c  isinst   System.Web.UI.WebControls.TemplatedWizardStep
0xa0541  stloc.s  5
0xa0543  ldloc.s  5
0xa0545  brfalse.s loc_A054F
0xa0547  ldarg.0
0xa0548  ldloc.s  5
0xa054a  call     instance void System.Web.UI.WebControls.Wizard::InstantiateStepContentTemplate(class System.Web.UI.WebControls.TemplatedWizardStep step)
0xa054f  ldloc.1
0xa0550  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa0555  brtrue   loc_A040B
0xa055a  leave.s  loc_A0570
0xa055c  ldloc.1
0xa055d  isinst   [mscorlib]System.IDisposable
0xa0562  stloc.s  6
0xa0564  ldloc.s  6
0xa0566  brfalse.s loc_A056F
0xa0568  ldloc.s  6
0xa056a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa056f  endfinally
0xa0570  ret
```
