# NGenTask.ParsedLogsInfo::AppendParsedLog

- ea: `0x3620`
- end: `0x3700`
- name: `NGenTask.ParsedLogsInfo::AppendParsedLog`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x11c0`
- `0x3790`

## callees

- `0x3590`
- `0x35d0`
- `0x35e0`
- `0x3620`
- `0x3700`
- `0x3710`

## pseudocode

```c

```

## disassembly

```asm
0x3620  ldarg.1
0x3621  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [mscorlib]System.DateTime> NGenTask.ParsedLogsInfo::get_NativeImages()
0x3626  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [mscorlib]System.DateTime>>::GetEnumerator()
0x362b  stloc.0
0x362c  br.s     loc_3649
0x362e  ldloc.0
0x362f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [mscorlib]System.DateTime>>::get_Current()
0x3634  stloc.1
0x3635  ldarg.0
0x3636  ldloca.s 1
0x3638  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [mscorlib]System.DateTime>::get_Key()
0x363d  ldloca.s 1
0x363f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [mscorlib]System.DateTime>::get_Value()
0x3644  call     instance void NGenTask.ParsedLogsInfo::AddNewNativeImage(string nativeImageName, valuetype [mscorlib]System.DateTime nativeImageAccessTime)
0x3649  ldloc.0
0x364a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x364f  brtrue.s loc_362E
0x3651  leave.s  loc_365D
0x3653  ldloc.0
0x3654  brfalse.s loc_365C
0x3656  ldloc.0
0x3657  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x365c  endfinally
0x365d  ldarg.1
0x365e  callvirt instance class [System]System.Collections.Generic.ISet`1<class NGenTask.ILAssembly> NGenTask.ParsedLogsInfo::get_ILAssemblies()
0x3663  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ILAssembly>::GetEnumerator()
0x3668  stloc.2
0x3669  br.s     loc_3679
0x366b  ldloc.2
0x366c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ILAssembly>::get_Current()
0x3671  stloc.3
0x3672  ldarg.0
0x3673  ldloc.3
0x3674  call     instance void NGenTask.ParsedLogsInfo::AddNewILAssembly(class NGenTask.ILAssembly newILAssembly)
0x3679  ldloc.2
0x367a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x367f  brtrue.s loc_366B
0x3681  leave.s  loc_368D
0x3683  ldloc.2
0x3684  brfalse.s loc_368C
0x3686  ldloc.2
0x3687  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x368c  endfinally
0x368d  ldarg.1
0x368e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>> NGenTask.ParsedLogsInfo::m_containerAssociations
0x3693  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>>::GetEnumerator()
0x3698  stloc.s  4
0x369a  br.s     loc_36E6
0x369c  ldloca.s 4
0x369e  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>>::get_Current()
0x36a3  stloc.s  5
0x36a5  ldloca.s 5
0x36a7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>>::get_Value()
0x36ac  callvirt instance valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<var<u1>> class [System.Core]System.Collections.Generic.HashSet`1<string>::GetEnumerator()
0x36b1  stloc.s  6
0x36b3  br.s     loc_36CD
0x36b5  ldloca.s 6
0x36b7  call     instance var<u1> valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<string>::get_Current()
0x36bc  stloc.s  7
0x36be  ldarg.0
0x36bf  ldloca.s 5
0x36c1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>>::get_Key()
0x36c6  ldloc.s  7
0x36c8  call     instance void NGenTask.ParsedLogsInfo::AddNewContainerAssociation(class NGenTask.ContainerRootDirectoryInfo rootDirectory, string containerMoniker)
0x36cd  ldloca.s 6
0x36cf  call     instance bool valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<string>::MoveNext()
0x36d4  brtrue.s loc_36B5
0x36d6  leave.s  loc_36E6
0x36d8  ldloca.s 6
0x36da  constrained. valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<string>
0x36e0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36e5  endfinally
0x36e6  ldloca.s 4
0x36e8  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>>::MoveNext()
0x36ed  brtrue.s loc_369C
0x36ef  leave.s  loc_36FF
0x36f1  ldloca.s 4
0x36f3  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>>
0x36f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36fe  endfinally
0x36ff  ret
```
