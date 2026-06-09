# System.ComponentModel.Design.UndoEngine::OnComponentChanging

- ea: `0x62d20`
- end: `0x62e0d`
- name: `System.ComponentModel.Design.UndoEngine::OnComponentChanging`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x629c0`
- `0x62af0`
- `0x62d20`
- `0x8eec0`
- `0x8ef40`
- `0x10a930`

## string_xrefs

- `0x62d56`: `UndoEngineComponentChange2`
- `0x62d8f`: `UndoEngineComponentChange1`
- `0x62db2`: `UndoEngineComponentChange0`

## pseudocode

```c

```

## disassembly

```asm
0x62d20  ldarg.0
0x62d21  ldfld    bool System.ComponentModel.Design.UndoEngine::_enabled
0x62d26  brfalse  loc_62DD0
0x62d2b  ldarg.0
0x62d2c  ldfld    class UndoUnit System.ComponentModel.Design.UndoEngine::_executingUnit
0x62d31  brtrue   loc_62DD0
0x62d36  ldarg.0
0x62d37  ldfld    class [mscorlib]System.Collections.Stack System.ComponentModel.Design.UndoEngine::_unitStack
0x62d3c  callvirt instance int32 [mscorlib]System.Collections.Stack::get_Count()
0x62d41  brtrue   loc_62DD0
0x62d46  ldarg.2
0x62d47  callvirt instance class [System]System.ComponentModel.MemberDescriptor [System]System.ComponentModel.Design.ComponentChangingEventArgs::get_Member()
0x62d4c  brfalse.s loc_62D87
0x62d4e  ldarg.2
0x62d4f  callvirt instance object [System]System.ComponentModel.Design.ComponentChangingEventArgs::get_Component()
0x62d54  brfalse.s loc_62D87
0x62d56  ldstr    aUndoenginecomp_1// "UndoEngineComponentChange2"
0x62d5b  ldc.i4.2
0x62d5c  newarr   [mscorlib]System.Object
0x62d61  dup
0x62d62  ldc.i4.0
0x62d63  ldarg.0
0x62d64  ldarg.2
0x62d65  callvirt instance object [System]System.ComponentModel.Design.ComponentChangingEventArgs::get_Component()
0x62d6a  ldc.i4.1
0x62d6b  call     instance string System.ComponentModel.Design.UndoEngine::GetName(object obj, bool generateNew)
0x62d70  stelem.ref
0x62d71  dup
0x62d72  ldc.i4.1
0x62d73  ldarg.2
0x62d74  callvirt instance class [System]System.ComponentModel.MemberDescriptor [System]System.ComponentModel.Design.ComponentChangingEventArgs::get_Member()
0x62d79  callvirt instance string [System]System.ComponentModel.MemberDescriptor::get_Name()
0x62d7e  stelem.ref
0x62d7f  call     string System.Design.SR::GetString(string name, object[] args)
0x62d84  stloc.0
0x62d85  br.s     loc_62DBD
0x62d87  ldarg.2
0x62d88  callvirt instance object [System]System.ComponentModel.Design.ComponentChangingEventArgs::get_Component()
0x62d8d  brfalse.s loc_62DB2
0x62d8f  ldstr    aUndoenginecomp_2// "UndoEngineComponentChange1"
0x62d94  ldc.i4.1
0x62d95  newarr   [mscorlib]System.Object
0x62d9a  dup
0x62d9b  ldc.i4.0
0x62d9c  ldarg.0
0x62d9d  ldarg.2
0x62d9e  callvirt instance object [System]System.ComponentModel.Design.ComponentChangingEventArgs::get_Component()
0x62da3  ldc.i4.1
0x62da4  call     instance string System.ComponentModel.Design.UndoEngine::GetName(object obj, bool generateNew)
0x62da9  stelem.ref
0x62daa  call     string System.Design.SR::GetString(string name, object[] args)
0x62daf  stloc.0
0x62db0  br.s     loc_62DBD
0x62db2  ldstr    aUndoenginecomp_3// "UndoEngineComponentChange0"
0x62db7  call     string System.Design.SR::GetString(string name)
0x62dbc  stloc.0
0x62dbd  ldarg.0
0x62dbe  ldfld    class [mscorlib]System.Collections.Stack System.ComponentModel.Design.UndoEngine::_unitStack
0x62dc3  ldarg.0
0x62dc4  ldloc.0
0x62dc5  ldc.i4.1
0x62dc6  callvirt instance class UndoUnit System.ComponentModel.Design.UndoEngine::CreateUndoUnit(string name, bool primary)
0x62dcb  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x62dd0  ldarg.0
0x62dd1  ldfld    class [mscorlib]System.Collections.Stack System.ComponentModel.Design.UndoEngine::_unitStack
0x62dd6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.Stack::GetEnumerator()
0x62ddb  stloc.1
0x62ddc  br.s     loc_62DF1
0x62dde  ldloc.1
0x62ddf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x62de4  castclass UndoUnit
0x62de9  stloc.2
0x62dea  ldloc.2
0x62deb  ldarg.2
0x62dec  callvirt instance void UndoUnit::ComponentChanging(class [System]System.ComponentModel.Design.ComponentChangingEventArgs e)
0x62df1  ldloc.1
0x62df2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x62df7  brtrue.s loc_62DDE
0x62df9  leave.s  loc_62E0C
0x62dfb  ldloc.1
0x62dfc  isinst   [mscorlib]System.IDisposable
0x62e01  stloc.3
0x62e02  ldloc.3
0x62e03  brfalse.s loc_62E0B
0x62e05  ldloc.3
0x62e06  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62e0b  endfinally
0x62e0c  ret
```
