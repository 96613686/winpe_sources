# Microsoft.VisualStudio.Setup.Extensions::MarkVitalFailure

- ea: `0x5d40`
- end: `0x5d90`
- name: `Microsoft.VisualStudio.Setup.Extensions::MarkVitalFailure`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5d40`

## callees

- `0x5d40`
- `0x7fe0`
- `0x8010`
- `0x8020`
- `0xc1a0`

## pseudocode

```c

```

## disassembly

```asm
0x5d40  ldarg.0
0x5d41  ldstr    aPackage// "package"
0x5d46  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x5d4b  ldarg.0
0x5d4c  ldc.i4.1
0x5d4d  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_HasVitalFailure(bool value)
0x5d52  ldarg.0
0x5d53  callvirt instance class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.IPackage::get_SelectedParents()
0x5d58  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x5d5d  stloc.0
0x5d5e  br.s     loc_5D7B
0x5d60  ldloc.0
0x5d61  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x5d66  stloc.1
0x5d67  ldloc.1
0x5d68  callvirt instance class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.IPackage::get_SelectedRequiredChildren()
0x5d6d  ldarg.0
0x5d6e  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.IPackage>::Contains(var<u1>)
0x5d73  brfalse.s loc_5D7B
0x5d75  ldloc.1
0x5d76  call     void Microsoft.VisualStudio.Setup.Extensions::MarkVitalFailure(class Microsoft.VisualStudio.Setup.IPackage package)
0x5d7b  ldloc.0
0x5d7c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5d81  brtrue.s loc_5D60
0x5d83  leave.s  loc_5D8F
0x5d85  ldloc.0
0x5d86  brfalse.s loc_5D8E
0x5d88  ldloc.0
0x5d89  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d8e  endfinally
0x5d8f  ret
```
