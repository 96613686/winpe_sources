# System.Windows.DependencyObject::ClearValueCommon

- ea: `0x304c0`
- end: `0x30557`
- name: `System.Windows.DependencyObject::ClearValueCommon`
- size: `151`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x300d0`
- `0x30460`
- `0x30490`

## callees

- `0x2c130`
- `0x2fb80`
- `0x2fbf0`
- `0x304c0`
- `0x30760`
- `0x315e0`
- `0x31cd0`
- `0x32e40`
- `0x34270`
- `0x345a0`
- `0x34840`
- `0x34b90`
- `0x34bd0`
- `0x34ce0`

## string_xrefs

- `0x304c8`: `ClearOnReadOnlyObjectNotAllowed`

## pseudocode

```c

```

## disassembly

```asm
0x304c0  ldarg.0
0x304c1  call     instance bool System.Windows.DependencyObject::get_IsSealed()
0x304c6  brfalse.s loc_304E2
0x304c8  ldstr    aClearonreadonl// "ClearOnReadOnlyObjectNotAllowed"
0x304cd  ldc.i4.1
0x304ce  newarr   [mscorlib]System.Object
0x304d3  dup
0x304d4  ldc.i4.0
0x304d5  ldarg.0
0x304d6  stelem.ref
0x304d7  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x304dc  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x304e1  throw
0x304e2  ldarg.0
0x304e3  ldarg.1
0x304e4  ldarg.2
0x304e5  ldarg.3
0x304e6  ldc.i4.s 0x10
0x304e8  call     instance valuetype System.Windows.EffectiveValueEntry System.Windows.DependencyObject::GetValueEntry(valuetype System.Windows.EntryIndex entryIndex, class System.Windows.DependencyProperty dp, class System.Windows.PropertyMetadata metadata, valuetype System.Windows.RequestFlags requests)
0x304ed  stloc.0
0x304ee  ldloca.s 0
0x304f0  call     instance object System.Windows.EffectiveValueEntry::get_LocalValue()
0x304f5  stloc.1
0x304f6  ldloca.s 0
0x304f8  call     instance bool System.Windows.EffectiveValueEntry::get_IsExpression()
0x304fd  brtrue.s loc_30502
0x304ff  ldnull
0x30500  br.s     loc_30508
0x30502  ldloc.1
0x30503  isinst   System.Windows.Expression
0x30508  stloc.2
0x30509  ldloc.2
0x3050a  brfalse.s loc_3053C
0x3050c  ldloc.2
0x3050d  callvirt instance class System.Windows.DependencySource[] System.Windows.Expression::GetSources()
0x30512  stloc.s  4
0x30514  ldarg.0
0x30515  ldarg.2
0x30516  ldloc.s  4
0x30518  ldloc.2
0x30519  ldc.i4.0
0x3051a  call     void System.Windows.DependencyObject::UpdateSourceDependentLists(class System.Windows.DependencyObject d, class System.Windows.DependencyProperty dp, class System.Windows.DependencySource[] sources, class System.Windows.Expression expr, bool add)
0x3051f  ldloc.2
0x30520  ldarg.0
0x30521  ldarg.2
0x30522  callvirt instance void System.Windows.Expression::OnDetach(class System.Windows.DependencyObject d, class System.Windows.DependencyProperty dp)
0x30527  ldloc.2
0x30528  callvirt instance void System.Windows.Expression::MarkDetached()
0x3052d  ldarg.0
0x3052e  ldarg.1
0x3052f  ldarg.2
0x30530  callvirt instance int32 System.Windows.DependencyProperty::get_GlobalIndex()
0x30535  call     instance valuetype System.Windows.EntryIndex System.Windows.DependencyObject::CheckEntryIndex(valuetype System.Windows.EntryIndex entryIndex, int32 targetIndex)
0x3053a  starg.s  1
0x3053c  ldloca.s 3
0x3053e  ldarg.2
0x3053f  ldc.i4.s 0xB
0x30541  call     instance void System.Windows.EffectiveValueEntry::.ctor(class System.Windows.DependencyProperty dp, valuetype System.Windows.BaseValueSourceInternal valueSource)
0x30546  ldarg.0
0x30547  ldarg.1
0x30548  ldarg.2
0x30549  ldarg.3
0x3054a  ldloc.0
0x3054b  ldloca.s 3
0x3054d  ldc.i4.0
0x3054e  ldc.i4.0
0x3054f  ldc.i4.0
0x30550  call     instance valuetype System.Windows.UpdateResult System.Windows.DependencyObject::UpdateEffectiveValue(valuetype System.Windows.EntryIndex entryIndex, class System.Windows.DependencyProperty dp, class System.Windows.PropertyMetadata metadata, valuetype System.Windows.EffectiveValueEntry oldEntry, valuetype System.Windows.EffectiveValueEntry& newEntry, bool coerceWithDeferredReference, bool coerceWithCurrentValue, valuetype System.Windows.OperationType operationType)
0x30555  pop
0x30556  ret
```
