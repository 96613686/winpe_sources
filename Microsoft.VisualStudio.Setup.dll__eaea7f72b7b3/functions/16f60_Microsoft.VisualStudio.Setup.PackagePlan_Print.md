# Microsoft.VisualStudio.Setup.PackagePlan::Print

- ea: `0x16f60`
- end: `0x1717b`
- name: `Microsoft.VisualStudio.Setup.PackagePlan::Print`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x175e0`

## callees

- `0x16e10`
- `0x16e30`
- `0x16e50`
- `0x16e70`
- `0x16e90`
- `0x16eb0`
- `0x16ee0`
- `0x16f00`
- `0x16f20`
- `0x16f40`
- `0x16f60`

## string_xrefs

- `0x170d8`: `Plan changed after checking compatible/superseding versions - PlannedAction: {0}.`
- `0x17128`: `Remove`
- `0x1715a`: `Non-installable {0}, PlannedAction: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x16f60  ldarg.1
0x16f61  ldstr    aLogger// "logger"
0x16f66  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x16f6b  ldarg.0
0x16f6c  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState> Microsoft.VisualStudio.Setup.PackagePlan::get_SelectedState()
0x16f71  stloc.3
0x16f72  ldloca.s 3
0x16f74  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState>::get_HasValue()
0x16f79  brtrue.s loc_16F82
0x16f7b  ldstr    asc_853DA// " "
0x16f80  br.s     loc_16F9F
0x16f82  ldstr    aSelectionstate// " SelectionState: {0}, "
0x16f87  ldarg.0
0x16f88  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState> Microsoft.VisualStudio.Setup.PackagePlan::get_SelectedState()
0x16f8d  stloc.3
0x16f8e  ldloca.s 3
0x16f90  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState>::get_Value()
0x16f95  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState
0x16f9a  call     string [mscorlib]System.String::Format(string, object)
0x16f9f  stloc.0
0x16fa0  ldarg.0
0x16fa1  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState> Microsoft.VisualStudio.Setup.PackagePlan::get_DeepDetectionState()
0x16fa6  stloc.s  4
0x16fa8  ldloca.s 4
0x16faa  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState>::get_HasValue()
0x16faf  brtrue.s loc_16FC8
0x16fb1  ldstr    aDetectionstate// "DetectionState: {0}"
0x16fb6  ldarg.0
0x16fb7  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState Microsoft.VisualStudio.Setup.PackagePlan::get_SoftDetectionState()
0x16fbc  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState
0x16fc1  call     string [mscorlib]System.String::Format(string, object)
0x16fc6  br.s     loc_16FE6
0x16fc8  ldstr    aDetectionstate// "DetectionState: {0}"
0x16fcd  ldarg.0
0x16fce  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState> Microsoft.VisualStudio.Setup.PackagePlan::get_DeepDetectionState()
0x16fd3  stloc.s  4
0x16fd5  ldloca.s 4
0x16fd7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState>::get_Value()
0x16fdc  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState
0x16fe1  call     string [mscorlib]System.String::Format(string, object)
0x16fe6  stloc.1
0x16fe7  ldstr    aPackage01Curre// "Package: {0},{1}CurrentState: {2}, Requ"...
0x16fec  ldc.i4.5
0x16fed  newarr   [mscorlib]System.Object
0x16ff2  dup
0x16ff3  ldc.i4.0
0x16ff4  ldarg.0
0x16ff5  call     instance string Microsoft.VisualStudio.Setup.PackagePlan::get_Id()
0x16ffa  stelem.ref
0x16ffb  dup
0x16ffc  ldc.i4.1
0x16ffd  ldloc.0
0x16ffe  stelem.ref
0x16fff  dup
0x17000  ldc.i4.2
0x17001  ldarg.0
0x17002  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState Microsoft.VisualStudio.Setup.PackagePlan::get_SoftDetectionState()
0x17007  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState
0x1700c  stelem.ref
0x1700d  dup
0x1700e  ldc.i4.3
0x1700f  ldarg.0
0x17010  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.PackagePlan::get_RequestedState()
0x17015  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState
0x1701a  stelem.ref
0x1701b  dup
0x1701c  ldc.i4.4
0x1701d  ldloc.1
0x1701e  stelem.ref
0x1701f  call     string [mscorlib]System.String::Format(string, object[])
0x17024  stloc.2
0x17025  ldarg.0
0x17026  ldfld    bool Microsoft.VisualStudio.Setup.PackagePlan::installable
0x1702b  brfalse  loc_17159
0x17030  ldarg.1
0x17031  ldstr    a0Plannedaction// "{0}, PlannedAction: {1}."
0x17036  ldloc.2
0x17037  ldarg.0
0x17038  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionBeforeRefCount()
0x1703d  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>
0x17042  call     string [mscorlib]System.String::Format(string, object, object)
0x17047  call     T0x2B000003
0x1704c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x17051  ldarg.0
0x17052  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionAfterRefCount()
0x17057  stloc.s  5
0x17059  ldloca.s 5
0x1705b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::get_HasValue()
0x17060  brfalse.s loc_170A4
0x17062  ldarg.0
0x17063  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionAfterRefCount()
0x17068  stloc.s  5
0x1706a  ldloca.s 5
0x1706c  ldarg.0
0x1706d  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionBeforeRefCount()
0x17072  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>
0x17077  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>
0x1707d  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x17082  brtrue.s loc_170A4
0x17084  ldarg.1
0x17085  ldstr    aPlanChangedAft// "Plan changed after checking instance/le"...
0x1708a  ldarg.0
0x1708b  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionAfterRefCount()
0x17090  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>
0x17095  call     string [mscorlib]System.String::Format(string, object)
0x1709a  call     T0x2B000003
0x1709f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x170a4  ldarg.0
0x170a5  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_FinalPlannedAction()
0x170aa  stloc.s  5
0x170ac  ldloca.s 5
0x170ae  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::get_HasValue()
0x170b3  brfalse.s loc_170F7
0x170b5  ldarg.0
0x170b6  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_FinalPlannedAction()
0x170bb  stloc.s  5
0x170bd  ldloca.s 5
0x170bf  ldarg.0
0x170c0  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionAfterRefCount()
0x170c5  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>
0x170ca  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>
0x170d0  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x170d5  brtrue.s loc_170F7
0x170d7  ldarg.1
0x170d8  ldstr    aPlanChangedAft_0// "Plan changed after checking compatible/"...
0x170dd  ldarg.0
0x170de  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_FinalPlannedAction()
0x170e3  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>
0x170e8  call     string [mscorlib]System.String::Format(string, object)
0x170ed  call     T0x2B000003
0x170f2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x170f7  ldarg.0
0x170f8  ldfld    bool Microsoft.VisualStudio.Setup.PackagePlan::logDependencyAction
0x170fd  brfalse.s loc_1717A
0x170ff  ldarg.0
0x17100  call     instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.PackagePlan::get_AddOrRemoveDependencyAction()
0x17105  stloc.s  7
0x17107  ldloca.s 7
0x17109  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1710e  brtrue.s loc_17117
0x17110  ldstr    aNoaction// "NoAction"
0x17115  br.s     loc_17134
0x17117  ldarg.0
0x17118  call     instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.PackagePlan::get_AddOrRemoveDependencyAction()
0x1711d  stloc.s  7
0x1711f  ldloca.s 7
0x17121  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x17126  brtrue.s loc_1712F
0x17128  ldstr    aRemove// "Remove"
0x1712d  br.s     loc_17134
0x1712f  ldstr    aAdd_0// "Add"
0x17134  stloc.s  6
0x17136  ldarg.1
0x17137  ldstr    aDependencyActi_0// "Dependency action plan - PackageExecute"...
0x1713c  ldarg.0
0x1713d  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionAfterRefCount()
0x17142  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>
0x17147  ldloc.s  6
0x17149  call     string [mscorlib]System.String::Format(string, object, object)
0x1714e  call     T0x2B000003
0x17153  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x17158  ret
0x17159  ldarg.1
0x1715a  ldstr    aNonInstallable// "Non-installable {0}, PlannedAction: {1}"...
0x1715f  ldloc.2
0x17160  ldarg.0
0x17161  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedAction()
0x17166  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction
0x1716b  call     string [mscorlib]System.String::Format(string, object, object)
0x17170  call     T0x2B000003
0x17175  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1717a  ret
```
