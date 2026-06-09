# System.Windows.Data.BindingListCollectionView::RemoveAt

- ea: `0x7cde0`
- end: `0x7ce23`
- name: `System.Windows.Data.BindingListCollectionView::RemoveAt`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x38c70`
- `0x7cd40`
- `0x7cde0`
- `0x7ce80`
- `0x7d090`
- `0x7fb60`
- `0x80450`

## string_xrefs

- `0x7cdf0`: `MemberNotAllowedDuringAddOrEdit`
- `0x7cdfd`: `RemoveAt`

## pseudocode

```c

```

## disassembly

```asm
0x7cde0  ldarg.0
0x7cde1  call     instance bool System.Windows.Data.BindingListCollectionView::get_IsEditingItem()
0x7cde6  brtrue.s loc_7CDF0
0x7cde8  ldarg.0
0x7cde9  call     instance bool System.Windows.Data.BindingListCollectionView::get_IsAddingNew()
0x7cdee  brfalse.s loc_7CE0E
0x7cdf0  ldstr    aMembernotallow// "MemberNotAllowedDuringAddOrEdit"
0x7cdf5  ldc.i4.1
0x7cdf6  newarr   [mscorlib]System.Object
0x7cdfb  dup
0x7cdfc  ldc.i4.0
0x7cdfd  ldstr    aRemoveat// "RemoveAt"
0x7ce02  stelem.ref
0x7ce03  call     string System.Windows.SR::Get(string id, object[] args)
0x7ce08  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7ce0d  throw
0x7ce0e  ldarg.0
0x7ce0f  call     instance void System.Windows.Data.CollectionView::VerifyRefreshNotDeferred()
0x7ce14  ldarg.0
0x7ce15  ldarg.0
0x7ce16  ldarg.1
0x7ce17  callvirt instance object System.Windows.Data.CollectionView::GetItemAt(int32 index)
0x7ce1c  ldarg.1
0x7ce1d  call     instance void System.Windows.Data.BindingListCollectionView::RemoveImpl(object item, int32 index)
0x7ce22  ret
```
