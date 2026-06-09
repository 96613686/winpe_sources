# System.Web.UI.Design.ControlDesigner::InvokeTransactedChange_1

- ea: `0x32c0`
- end: `0x33ad`
- name: `System.Web.UI.Design.ControlDesigner::InvokeTransactedChange_1`
- size: `237`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x32a0`
- `0x1b540`
- `0x1b6e0`

## callees

- `0x3190`
- `0x32c0`
- `0x11690`
- `0x8ef40`

## string_xrefs

- `0x32c3`: `component`
- `0x32df`: `ControlDesigner_TransactedChangeRequiresServiceProvider`
- `0x32e9`: `serviceProvider`

## pseudocode

```c

```

## disassembly

```asm
0x32c0  ldarg.1
0x32c1  brtrue.s loc_32CE
0x32c3  ldstr    aComponent// "component"
0x32c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x32cd  throw
0x32ce  ldarg.2
0x32cf  brtrue.s loc_32DC
0x32d1  ldstr    aCallback// "callback"
0x32d6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x32db  throw
0x32dc  ldarg.0
0x32dd  brtrue.s loc_32F4
0x32df  ldstr    aControldesigne_3// "ControlDesigner_TransactedChangeRequire"...
0x32e4  call     string System.Design.SR::GetString(string name)
0x32e9  ldstr    aServiceprovide// "serviceProvider"
0x32ee  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x32f3  throw
0x32f4  ldarg.0
0x32f5  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x32fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32ff  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x3304  castclass [System]System.ComponentModel.Design.IDesignerHost
0x3309  stloc.0
0x330a  ldloc.0
0x330b  ldarg.s  4
0x330d  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0x3312  stloc.1
0x3313  ldarg.0
0x3314  ldtoken  [System]System.ComponentModel.Design.IComponentChangeService
0x3319  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x331e  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x3323  castclass [System]System.ComponentModel.Design.IComponentChangeService
0x3328  stloc.2
0x3329  ldloc.2
0x332a  brfalse.s loc_3347
0x332c  ldloc.2
0x332d  ldarg.1
0x332e  ldarg.s  5
0x3330  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0x3335  leave.s  loc_3347
0x3337  stloc.s  5
0x3339  ldloc.s  5
0x333b  ldsfld   class [System]System.ComponentModel.Design.CheckoutException [System]System.ComponentModel.Design.CheckoutException::Canceled
0x3340  bne.un.s loc_3344
0x3342  leave.s  loc_33AC
0x3344  ldloc.s  5
0x3346  throw
0x3347  ldloc.0
0x3348  ldarg.1
0x3349  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0x334e  isinst   System.Web.UI.Design.ControlDesigner
0x3353  stloc.3
0x3354  ldc.i4.0
0x3355  stloc.s  4
0x3357  ldloc.3
0x3358  brfalse.s loc_3361
0x335a  ldloc.3
0x335b  ldc.i4.1
0x335c  callvirt instance void System.Web.UI.Design.ControlDesigner::IgnoreComponentChanges(bool ignore)
0x3361  ldarg.2
0x3362  ldarg.3
0x3363  callvirt instance bool System.Web.UI.Design.TransactedChangeCallback::Invoke(object context)
0x3368  brfalse.s loc_3391
0x336a  ldloc.3
0x336b  brfalse.s loc_3377
0x336d  ldc.i4.1
0x336e  stloc.s  4
0x3370  ldloc.3
0x3371  ldc.i4.0
0x3372  callvirt instance void System.Web.UI.Design.ControlDesigner::IgnoreComponentChanges(bool ignore)
0x3377  ldloc.2
0x3378  brfalse.s loc_3385
0x337a  ldloc.2
0x337b  ldarg.1
0x337c  ldarg.s  5
0x337e  ldnull
0x337f  ldnull
0x3380  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0x3385  ldarg.1
0x3386  call     void [System]System.ComponentModel.TypeDescriptor::Refresh(object)
0x338b  ldloc.1
0x338c  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Commit()
0x3391  leave.s  loc_33AC
0x3393  ldloc.3
0x3394  brfalse.s loc_33A1
0x3396  ldloc.s  4
0x3398  brtrue.s loc_33A1
0x339a  ldloc.3
0x339b  ldc.i4.0
0x339c  callvirt instance void System.Web.UI.Design.ControlDesigner::IgnoreComponentChanges(bool ignore)
0x33a1  endfinally
0x33a2  ldloc.1
0x33a3  brfalse.s loc_33AB
0x33a5  ldloc.1
0x33a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33ab  endfinally
0x33ac  ret
```
