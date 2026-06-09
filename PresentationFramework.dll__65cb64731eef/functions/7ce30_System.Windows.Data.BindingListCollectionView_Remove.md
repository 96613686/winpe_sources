# System.Windows.Data.BindingListCollectionView::Remove

- ea: `0x7ce30`
- end: `0x7ce79`
- name: `System.Windows.Data.BindingListCollectionView::Remove`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x38c70`
- `0x7cd40`
- `0x7ce30`
- `0x7ce80`
- `0x7d090`
- `0x7d9f0`
- `0x80450`

## string_xrefs

- `0x7ce40`: `MemberNotAllowedDuringAddOrEdit`
- `0x7ce4d`: `Remove`

## pseudocode

```c

```

## disassembly

```asm
0x7ce30  ldarg.0
0x7ce31  call     instance bool System.Windows.Data.BindingListCollectionView::get_IsEditingItem()
0x7ce36  brtrue.s loc_7CE40
0x7ce38  ldarg.0
0x7ce39  call     instance bool System.Windows.Data.BindingListCollectionView::get_IsAddingNew()
0x7ce3e  brfalse.s loc_7CE5E
0x7ce40  ldstr    aMembernotallow// "MemberNotAllowedDuringAddOrEdit"
0x7ce45  ldc.i4.1
0x7ce46  newarr   [mscorlib]System.Object
0x7ce4b  dup
0x7ce4c  ldc.i4.0
0x7ce4d  ldstr    aRemove// "Remove"
0x7ce52  stelem.ref
0x7ce53  call     string System.Windows.SR::Get(string id, object[] args)
0x7ce58  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7ce5d  throw
0x7ce5e  ldarg.0
0x7ce5f  call     instance void System.Windows.Data.CollectionView::VerifyRefreshNotDeferred()
0x7ce64  ldarg.0
0x7ce65  ldarg.1
0x7ce66  call     instance int32 System.Windows.Data.BindingListCollectionView::InternalIndexOf(object item)
0x7ce6b  stloc.0
0x7ce6c  ldloc.0
0x7ce6d  ldc.i4.0
0x7ce6e  blt.s    loc_7CE78
0x7ce70  ldarg.0
0x7ce71  ldarg.1
0x7ce72  ldloc.0
0x7ce73  call     instance void System.Windows.Data.BindingListCollectionView::RemoveImpl(object item, int32 index)
0x7ce78  ret
```
