# System.ComponentModel.Design.UndoEngine::OnComponentAdding

- ea: `0x62c20`
- end: `0x62cc3`
- name: `System.ComponentModel.Design.UndoEngine::OnComponentAdding`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x629c0`
- `0x62af0`
- `0x62c20`
- `0x8eec0`
- `0x8ef40`
- `0x10a790`

## string_xrefs

- `0x62c45`: `UndoEngineComponentAdd1`
- `0x62c68`: `UndoEngineComponentAdd0`

## pseudocode

```c

```

## disassembly

```asm
0x62c20  ldarg.0
0x62c21  ldfld    bool System.ComponentModel.Design.UndoEngine::_enabled
0x62c26  brfalse.s loc_62C86
0x62c28  ldarg.0
0x62c29  ldfld    class UndoUnit System.ComponentModel.Design.UndoEngine::_executingUnit
0x62c2e  brtrue.s loc_62C86
0x62c30  ldarg.0
0x62c31  ldfld    class [mscorlib]System.Collections.Stack System.ComponentModel.Design.UndoEngine::_unitStack
0x62c36  callvirt instance int32 [mscorlib]System.Collections.Stack::get_Count()
0x62c3b  brtrue.s loc_62C86
0x62c3d  ldarg.2
0x62c3e  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.ComponentEventArgs::get_Component()
0x62c43  brfalse.s loc_62C68
0x62c45  ldstr    aUndoenginecomp// "UndoEngineComponentAdd1"
0x62c4a  ldc.i4.1
0x62c4b  newarr   [mscorlib]System.Object
0x62c50  dup
0x62c51  ldc.i4.0
0x62c52  ldarg.0
0x62c53  ldarg.2
0x62c54  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.ComponentEventArgs::get_Component()
0x62c59  ldc.i4.1
0x62c5a  call     instance string System.ComponentModel.Design.UndoEngine::GetName(object obj, bool generateNew)
0x62c5f  stelem.ref
0x62c60  call     string System.Design.SR::GetString(string name, object[] args)
0x62c65  stloc.0
0x62c66  br.s     loc_62C73
0x62c68  ldstr    aUndoenginecomp_0// "UndoEngineComponentAdd0"
0x62c6d  call     string System.Design.SR::GetString(string name)
0x62c72  stloc.0
0x62c73  ldarg.0
0x62c74  ldfld    class [mscorlib]System.Collections.Stack System.ComponentModel.Design.UndoEngine::_unitStack
0x62c79  ldarg.0
0x62c7a  ldloc.0
0x62c7b  ldc.i4.1
0x62c7c  callvirt instance class UndoUnit System.ComponentModel.Design.UndoEngine::CreateUndoUnit(string name, bool primary)
0x62c81  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x62c86  ldarg.0
0x62c87  ldfld    class [mscorlib]System.Collections.Stack System.ComponentModel.Design.UndoEngine::_unitStack
0x62c8c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.Stack::GetEnumerator()
0x62c91  stloc.1
0x62c92  br.s     loc_62CA7
0x62c94  ldloc.1
0x62c95  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x62c9a  castclass UndoUnit
0x62c9f  stloc.2
0x62ca0  ldloc.2
0x62ca1  ldarg.2
0x62ca2  callvirt instance void UndoUnit::ComponentAdding(class [System]System.ComponentModel.Design.ComponentEventArgs e)
0x62ca7  ldloc.1
0x62ca8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x62cad  brtrue.s loc_62C94
0x62caf  leave.s  loc_62CC2
0x62cb1  ldloc.1
0x62cb2  isinst   [mscorlib]System.IDisposable
0x62cb7  stloc.3
0x62cb8  ldloc.3
0x62cb9  brfalse.s loc_62CC1
0x62cbb  ldloc.3
0x62cbc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62cc1  endfinally
0x62cc2  ret
```
