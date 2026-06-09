# System.Windows.Data.CompositeCollection::RemoveAt

- ea: `0x82010`
- end: `0x82061`
- name: `System.Windows.Data.CompositeCollection::RemoveAt`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x81ff0`

## callees

- `0x38c40`
- `0x82010`
- `0x82080`
- `0x82090`
- `0x82260`
- `0x822b0`
- `0x822f0`

## string_xrefs

- `0x8204c`: `removeIndex`
- `0x82051`: `ItemCollectionRemoveArgumentOutOfRange`

## pseudocode

```c

```

## disassembly

```asm
0x82010  ldc.i4.0
0x82011  ldarg.1
0x82012  bgt.s    loc_8204C
0x82014  ldarg.1
0x82015  ldarg.0
0x82016  call     instance int32 System.Windows.Data.CompositeCollection::get_Count()
0x8201b  bge.s    loc_8204C
0x8201d  ldarg.0
0x8201e  ldarg.1
0x8201f  call     instance object System.Windows.Data.CompositeCollection::get_Item(int32 itemIndex)
0x82024  stloc.0
0x82025  ldloc.0
0x82026  isinst   System.Windows.Data.CollectionContainer
0x8202b  stloc.1
0x8202c  ldloc.1
0x8202d  brfalse.s loc_82036
0x8202f  ldarg.0
0x82030  ldloc.1
0x82031  call     instance void System.Windows.Data.CompositeCollection::RemoveCollectionContainer(class System.Windows.Data.CollectionContainer cc)
0x82036  ldarg.0
0x82037  call     instance class [mscorlib]System.Collections.ArrayList System.Windows.Data.CompositeCollection::get_InternalList()
0x8203c  ldarg.1
0x8203d  callvirt instance void [mscorlib]System.Collections.ArrayList::RemoveAt(int32)
0x82042  ldarg.0
0x82043  ldc.i4.1
0x82044  ldloc.0
0x82045  ldarg.1
0x82046  call     instance void System.Windows.Data.CompositeCollection::OnCollectionChanged(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction action, object item, int32 index)
0x8204b  ret
0x8204c  ldstr    aRemoveindex// "removeIndex"
0x82051  ldstr    aItemcollection_0// "ItemCollectionRemoveArgumentOutOfRange"
0x82056  call     string System.Windows.SR::Get(string id)
0x8205b  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x82060  throw
```
