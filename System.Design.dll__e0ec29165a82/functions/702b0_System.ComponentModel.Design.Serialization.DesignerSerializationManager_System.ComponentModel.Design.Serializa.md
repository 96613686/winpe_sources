# System.ComponentModel.Design.Serialization.DesignerSerializationManager::System.ComponentModel.Design.Serialization.IDesignerSerializationManager.CreateInstance

- ea: `0x702b0`
- end: `0x70354`
- name: `System.ComponentModel.Design.Serialization.DesignerSerializationManager::System.ComponentModel.Design.Serialization.IDesignerSerializationManager.CreateInstance`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x6f8e0`
- `0x6f9c0`
- `0x6f9e0`
- `0x702b0`
- `0x8eec0`
- `0x10d3a0`

## string_xrefs

- `0x702cf`: `SerializationManagerDuplicateComponentDecl`
- `0x702ea`: `SerializationManagerDuplicateComponentDecl`

## pseudocode

```c

```

## disassembly

```asm
0x702b0  ldarg.0
0x702b1  call     instance void System.ComponentModel.Design.Serialization.DesignerSerializationManager::CheckSession()
0x702b6  ldarg.3
0x702b7  brfalse.s loc_702F6
0x702b9  ldarg.0
0x702ba  ldfld    class [mscorlib]System.Collections.Hashtable System.ComponentModel.Design.Serialization.DesignerSerializationManager::instancesByName
0x702bf  brfalse.s loc_702F6
0x702c1  ldarg.0
0x702c2  ldfld    class [mscorlib]System.Collections.Hashtable System.ComponentModel.Design.Serialization.DesignerSerializationManager::instancesByName
0x702c7  ldarg.3
0x702c8  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x702cd  brfalse.s loc_702F6
0x702cf  ldstr    aSerializationm_3// "SerializationManagerDuplicateComponentD"...
0x702d4  ldc.i4.1
0x702d5  newarr   [mscorlib]System.Object
0x702da  dup
0x702db  ldc.i4.0
0x702dc  ldarg.3
0x702dd  stelem.ref
0x702de  call     string System.Design.SR::GetString(string name, object[] args)
0x702e3  newobj   instance void [mscorlib]System.Runtime.Serialization.SerializationException::.ctor(string)
0x702e8  stloc.1
0x702e9  ldloc.1
0x702ea  ldstr    aSerializationm_3// "SerializationManagerDuplicateComponentD"...
0x702ef  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x702f4  ldloc.1
0x702f5  throw
0x702f6  ldarg.0
0x702f7  ldarg.1
0x702f8  ldarg.2
0x702f9  ldarg.3
0x702fa  ldarg.s  4
0x702fc  callvirt instance object System.ComponentModel.Design.Serialization.DesignerSerializationManager::CreateInstance(class [mscorlib]System.Type type, class [mscorlib]System.Collections.ICollection arguments, string name, bool addToContainer)
0x70301  stloc.0
0x70302  ldarg.3
0x70303  brfalse.s loc_70352
0x70305  ldloc.0
0x70306  isinst   [System]System.ComponentModel.IComponent
0x7030b  brfalse.s loc_70315
0x7030d  ldarg.0
0x7030e  call     instance bool System.ComponentModel.Design.Serialization.DesignerSerializationManager::get_RecycleInstances()
0x70313  brtrue.s loc_70352
0x70315  ldarg.0
0x70316  ldfld    class [mscorlib]System.Collections.Hashtable System.ComponentModel.Design.Serialization.DesignerSerializationManager::instancesByName
0x7031b  brtrue.s loc_70338
0x7031d  ldarg.0
0x7031e  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x70323  stfld    class [mscorlib]System.Collections.Hashtable System.ComponentModel.Design.Serialization.DesignerSerializationManager::instancesByName
0x70328  ldarg.0
0x70329  newobj   instance void ReferenceComparer::.ctor()
0x7032e  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0x70333  stfld    class [mscorlib]System.Collections.Hashtable System.ComponentModel.Design.Serialization.DesignerSerializationManager::namesByInstance
0x70338  ldarg.0
0x70339  ldfld    class [mscorlib]System.Collections.Hashtable System.ComponentModel.Design.Serialization.DesignerSerializationManager::instancesByName
0x7033e  ldarg.3
0x7033f  ldloc.0
0x70340  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x70345  ldarg.0
0x70346  ldfld    class [mscorlib]System.Collections.Hashtable System.ComponentModel.Design.Serialization.DesignerSerializationManager::namesByInstance
0x7034b  ldloc.0
0x7034c  ldarg.3
0x7034d  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x70352  ldloc.0
0x70353  ret
```
