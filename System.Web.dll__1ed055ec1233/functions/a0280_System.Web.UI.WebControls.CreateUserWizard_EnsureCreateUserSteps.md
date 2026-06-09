# System.Web.UI.WebControls.CreateUserWizard::EnsureCreateUserSteps

- ea: `0xa0280`
- end: `0xa038e`
- name: `System.Web.UI.WebControls.CreateUserWizard::EnsureCreateUserSteps`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0xa0a80`
- `0x19db90`
- `0x19dc70`

## callees

- `0x18990`
- `0x34fa0`
- `0x5f680`
- `0x5fec0`
- `0x9cb10`
- `0xa0280`
- `0xa11a0`
- `0xe9e70`
- `0xeb070`
- `0xeb080`
- `0xebb80`
- `0xed240`
- `0xed280`
- `0xed360`

## string_xrefs

- `0xa02ad`: `CreateUserWizard_DuplicateCreateUserWizardStep`
- `0xa02d8`: `CreateUserWizard_DuplicateCompleteWizardStep`

## pseudocode

```c

```

## disassembly

```asm
0xa0280  ldc.i4.0
0xa0281  stloc.0
0xa0282  ldc.i4.0
0xa0283  stloc.1
0xa0284  ldarg.0
0xa0285  callvirt instance class System.Web.UI.WebControls.WizardStepCollection System.Web.UI.WebControls.Wizard::get_WizardSteps()
0xa028a  callvirt instance class [mscorlib]System.Collections.IEnumerator System.Web.UI.WebControls.WizardStepCollection::GetEnumerator()
0xa028f  stloc.2
0xa0290  br.s     loc_A02F2
0xa0292  ldloc.2
0xa0293  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa0298  castclass System.Web.UI.WebControls.WizardStepBase
0xa029d  stloc.3
0xa029e  ldloc.3
0xa029f  isinst   System.Web.UI.WebControls.CreateUserWizardStep
0xa02a4  stloc.s  4
0xa02a6  ldloc.s  4
0xa02a8  brfalse.s loc_A02C9
0xa02aa  ldloc.0
0xa02ab  brfalse.s loc_A02BD
0xa02ad  ldstr    aCreateuserwiza_25// "CreateUserWizard_DuplicateCreateUserWiz"...
0xa02b2  call     string System.Web.SR::GetString(string name)
0xa02b7  newobj   instance void System.Web.HttpException::.ctor(string message)
0xa02bc  throw
0xa02bd  ldc.i4.1
0xa02be  stloc.0
0xa02bf  ldarg.0
0xa02c0  ldloc.s  4
0xa02c2  stfld    class System.Web.UI.WebControls.CreateUserWizardStep System.Web.UI.WebControls.CreateUserWizard::_createUserStep
0xa02c7  br.s     loc_A02F2
0xa02c9  ldloc.3
0xa02ca  isinst   System.Web.UI.WebControls.CompleteWizardStep
0xa02cf  stloc.s  5
0xa02d1  ldloc.s  5
0xa02d3  brfalse.s loc_A02F2
0xa02d5  ldloc.1
0xa02d6  brfalse.s loc_A02E8
0xa02d8  ldstr    aCreateuserwiza_26// "CreateUserWizard_DuplicateCompleteWizar"...
0xa02dd  call     string System.Web.SR::GetString(string name)
0xa02e2  newobj   instance void System.Web.HttpException::.ctor(string message)
0xa02e7  throw
0xa02e8  ldc.i4.1
0xa02e9  stloc.1
0xa02ea  ldarg.0
0xa02eb  ldloc.s  5
0xa02ed  stfld    class System.Web.UI.WebControls.CompleteWizardStep System.Web.UI.WebControls.CreateUserWizard::_completeStep
0xa02f2  ldloc.2
0xa02f3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa02f8  brtrue.s loc_A0292
0xa02fa  leave.s  loc_A0310
0xa02fc  ldloc.2
0xa02fd  isinst   [mscorlib]System.IDisposable
0xa0302  stloc.s  6
0xa0304  ldloc.s  6
0xa0306  brfalse.s loc_A030F
0xa0308  ldloc.s  6
0xa030a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa030f  endfinally
0xa0310  ldloc.0
0xa0311  brtrue.s loc_A034D
0xa0313  ldarg.0
0xa0314  newobj   instance void System.Web.UI.WebControls.CreateUserWizardStep::.ctor()
0xa0319  stfld    class System.Web.UI.WebControls.CreateUserWizardStep System.Web.UI.WebControls.CreateUserWizard::_createUserStep
0xa031e  ldarg.0
0xa031f  ldfld    class System.Web.UI.WebControls.CreateUserWizardStep System.Web.UI.WebControls.CreateUserWizard::_createUserStep
0xa0324  ldarg.0
0xa0325  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0xa032a  callvirt instance void System.Web.UI.Control::ApplyStyleSheetSkin(class System.Web.UI.Page page)
0xa032f  ldarg.0
0xa0330  callvirt instance class System.Web.UI.WebControls.WizardStepCollection System.Web.UI.WebControls.Wizard::get_WizardSteps()
0xa0335  ldc.i4.0
0xa0336  ldarg.0
0xa0337  ldfld    class System.Web.UI.WebControls.CreateUserWizardStep System.Web.UI.WebControls.CreateUserWizard::_createUserStep
0xa033c  callvirt instance void System.Web.UI.WebControls.WizardStepCollection::AddAt(int32 index, class System.Web.UI.WebControls.WizardStepBase wizardStep)
0xa0341  ldarg.0
0xa0342  ldfld    class System.Web.UI.WebControls.CreateUserWizardStep System.Web.UI.WebControls.CreateUserWizard::_createUserStep
0xa0347  ldc.i4.1
0xa0348  callvirt instance void System.Web.UI.WebControls.View::set_Active(bool value)
0xa034d  ldloc.1
0xa034e  brtrue.s loc_A037D
0xa0350  ldarg.0
0xa0351  newobj   instance void System.Web.UI.WebControls.CompleteWizardStep::.ctor()
0xa0356  stfld    class System.Web.UI.WebControls.CompleteWizardStep System.Web.UI.WebControls.CreateUserWizard::_completeStep
0xa035b  ldarg.0
0xa035c  ldfld    class System.Web.UI.WebControls.CompleteWizardStep System.Web.UI.WebControls.CreateUserWizard::_completeStep
0xa0361  ldarg.0
0xa0362  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0xa0367  callvirt instance void System.Web.UI.Control::ApplyStyleSheetSkin(class System.Web.UI.Page page)
0xa036c  ldarg.0
0xa036d  callvirt instance class System.Web.UI.WebControls.WizardStepCollection System.Web.UI.WebControls.Wizard::get_WizardSteps()
0xa0372  ldarg.0
0xa0373  ldfld    class System.Web.UI.WebControls.CompleteWizardStep System.Web.UI.WebControls.CreateUserWizard::_completeStep
0xa0378  callvirt instance void System.Web.UI.WebControls.WizardStepCollection::Add(class System.Web.UI.WebControls.WizardStepBase wizardStep)
0xa037d  ldarg.0
0xa037e  callvirt instance int32 System.Web.UI.WebControls.Wizard::get_ActiveStepIndex()
0xa0383  ldc.i4.m1
0xa0384  bne.un.s loc_A038D
0xa0386  ldarg.0
0xa0387  ldc.i4.0
0xa0388  callvirt instance void System.Web.UI.WebControls.Wizard::set_ActiveStepIndex(int32 value)
0xa038d  ret
```
