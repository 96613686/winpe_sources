# System.Windows.Input.CommandManager::RegisterClassCommandBinding

- ea: `0x312c0`
- end: `0x31332`
- name: `System.Windows.Input.CommandManager::RegisterClassCommandBinding`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x30cb0`
- `0x30de0`
- `0x312c0`

## string_xrefs

- `0x312d7`: `commandBinding`

## pseudocode

```c

```

## disassembly

```asm
0x312c0  ldarg.0
0x312c1  ldnull
0x312c2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x312c7  brfalse.s loc_312D4
0x312c9  ldstr    aType// "type"
0x312ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x312d3  throw
0x312d4  ldarg.1
0x312d5  brtrue.s loc_312E2
0x312d7  ldstr    aCommandbinding// "commandBinding"
0x312dc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x312e1  throw
0x312e2  ldsfld   class [System]System.Collections.Specialized.HybridDictionary System.Windows.Input.CommandManager::_classCommandBindings
0x312e7  callvirt instance object [System]System.Collections.Specialized.HybridDictionary::get_SyncRoot()
0x312ec  stloc.1
0x312ed  ldc.i4.0
0x312ee  stloc.2
0x312ef  ldloc.1
0x312f0  ldloca.s 2
0x312f2  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x312f7  ldsfld   class [System]System.Collections.Specialized.HybridDictionary System.Windows.Input.CommandManager::_classCommandBindings
0x312fc  ldarg.0
0x312fd  callvirt instance object [System]System.Collections.Specialized.HybridDictionary::get_Item(object)
0x31302  isinst   System.Windows.Input.CommandBindingCollection
0x31307  stloc.0
0x31308  ldloc.0
0x31309  brtrue.s loc_3131D
0x3130b  newobj   instance void System.Windows.Input.CommandBindingCollection::.ctor()
0x31310  stloc.0
0x31311  ldsfld   class [System]System.Collections.Specialized.HybridDictionary System.Windows.Input.CommandManager::_classCommandBindings
0x31316  ldarg.0
0x31317  ldloc.0
0x31318  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::set_Item(object, object)
0x3131d  ldloc.0
0x3131e  ldarg.1
0x3131f  callvirt instance int32 System.Windows.Input.CommandBindingCollection::Add(class System.Windows.Input.CommandBinding commandBinding)
0x31324  pop
0x31325  leave.s  loc_31331
0x31327  ldloc.2
0x31328  brfalse.s loc_31330
0x3132a  ldloc.1
0x3132b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x31330  endfinally
0x31331  ret
```
