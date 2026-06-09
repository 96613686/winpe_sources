# Microsoft.VisualStudio.Setup.Extensions::IsOnlyHotloadInstallPlanned

- ea: `0x10f60`
- end: `0x11084`
- name: `Microsoft.VisualStudio.Setup.Extensions::IsOnlyHotloadInstallPlanned`
- size: `292`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x12de0`
- `0x140b0`

## callees

- `0x10f60`
- `0x1b280`
- `0x59710`
- `0x68310`

## string_xrefs

- `0x10f64`: `Install schedule was not provided`
- `0x10f89`: `No installation activities were planned`

## pseudocode

```c

```

## disassembly

```asm
0x10f60  ldarg.0
0x10f61  brtrue.s loc_10F6F
0x10f63  ldc.i4.0
0x10f64  ldstr    aInstallSchedul// "Install schedule was not provided"
0x10f69  newobj   instance void ScheduleHotloadResult::.ctor(bool CanHotload, string BlockReason)
0x10f6e  ret
0x10f6f  ldarg.0
0x10f70  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Activities.IActivity> Microsoft.VisualStudio.Setup.Schedule::get_PackagesToInstallOrUninstall()
0x10f75  call     T0x2B0000C0
0x10f7a  call     T0x2B0000C1
0x10f7f  stloc.0
0x10f80  ldloc.0
0x10f81  call     T0x2B0000C2
0x10f86  brtrue.s loc_10F94
0x10f88  ldc.i4.0
0x10f89  ldstr    aNoInstallation// "No installation activities were planned"
0x10f8e  newobj   instance void ScheduleHotloadResult::.ctor(bool CanHotload, string BlockReason)
0x10f93  ret
0x10f94  ldloc.0
0x10f95  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Activities.Install, bool> <>c::<>9__137_0
0x10f9a  dup
0x10f9b  brtrue.s loc_10FB4
0x10f9d  pop
0x10f9e  ldsfld   class <>c <>c::<>9
0x10fa3  ldftn    instance bool <>c::<IsOnlyHotloadInstallPlanned>b__137_0(class Microsoft.VisualStudio.Setup.Activities.Install y)
0x10fa9  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Activities.Install, bool>::.ctor(object, native int)
0x10fae  dup
0x10faf  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Activities.Install, bool> <>c::<>9__137_0
0x10fb4  call     T0x2B0000C3
0x10fb9  brfalse.s loc_10FC7
0x10fbb  ldc.i4.0
0x10fbc  ldstr    aOneOrMorePacka// "One or more package removals were reque"...
0x10fc1  newobj   instance void ScheduleHotloadResult::.ctor(bool CanHotload, string BlockReason)
0x10fc6  ret
0x10fc7  ldc.i4.0
0x10fc8  stloc.1
0x10fc9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Activities.Activity>::.ctor()
0x10fce  stloc.2
0x10fcf  ldloc.0
0x10fd0  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Activities.Install>::GetEnumerator()
0x10fd5  stloc.3
0x10fd6  br.s     loc_11008
0x10fd8  ldloca.s 3
0x10fda  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.VisualStudio.Setup.Activities.Install>::get_Current()
0x10fdf  stloc.s  4
0x10fe1  ldloc.s  4
0x10fe3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x10fe8  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage
0x10fed  stloc.s  5
0x10fef  ldloc.s  5
0x10ff1  brfalse.s loc_11000
0x10ff3  ldloc.s  5
0x10ff5  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_HotLoadable()
0x10ffa  brfalse.s loc_11000
0x10ffc  ldc.i4.1
0x10ffd  stloc.1
0x10ffe  br.s     loc_11008
0x11000  ldloc.2
0x11001  ldloc.s  4
0x11003  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Activities.Activity>::Add(var<u1>)
0x11008  ldloca.s 3
0x1100a  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.VisualStudio.Setup.Activities.Install>::MoveNext()
0x1100f  brtrue.s loc_10FD8
0x11011  leave.s  loc_11021
0x11013  ldloca.s 3
0x11015  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.VisualStudio.Setup.Activities.Install>
0x1101b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11020  endfinally
0x11021  ldloc.1
0x11022  brtrue.s loc_11030
0x11024  ldc.i4.0
0x11025  ldstr    aNoHotloadableV// "No hotloadable VSIX packages were prese"...
0x1102a  newobj   instance void ScheduleHotloadResult::.ctor(bool CanHotload, string BlockReason)
0x1102f  ret
0x11030  ldloc.2
0x11031  call     T0x2B0000C4
0x11036  brfalse.s loc_11078
0x11038  ldc.i4.0
0x11039  ldstr    aTheFollowingPa// "The following packages prevented hotloa"...
0x1103e  ldstr    asc_828F4// ","
0x11043  ldloc.2
0x11044  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Activities.Activity, string> <>c::<>9__137_1
0x11049  dup
0x1104a  brtrue.s loc_11063
0x1104c  pop
0x1104d  ldsfld   class <>c <>c::<>9
0x11052  ldftn    instance string <>c::<IsOnlyHotloadInstallPlanned>b__137_1(class Microsoft.VisualStudio.Setup.Activities.Activity x)
0x11058  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Activities.Activity, string>::.ctor(object, native int)
0x1105d  dup
0x1105e  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Activities.Activity, string> <>c::<>9__137_1
0x11063  call     T0x2B0000C5
0x11068  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x1106d  call     string [mscorlib]System.String::Concat(string, string)
0x11072  newobj   instance void ScheduleHotloadResult::.ctor(bool CanHotload, string BlockReason)
0x11077  ret
0x11078  ldc.i4.1
0x11079  ldsfld   string [mscorlib]System.String::Empty
0x1107e  newobj   instance void ScheduleHotloadResult::.ctor(bool CanHotload, string BlockReason)
0x11083  ret
```
