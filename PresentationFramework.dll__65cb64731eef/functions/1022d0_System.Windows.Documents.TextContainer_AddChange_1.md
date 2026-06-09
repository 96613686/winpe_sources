# System.Windows.Documents.TextContainer::AddChange_1

- ea: `0x1022d0`
- end: `0x102362`
- name: `System.Windows.Documents.TextContainer::AddChange_1`
- size: `146`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1022a0`
- `0x102550`
- `0x1039d0`

## callees

- `0x1022d0`
- `0x102fb0`
- `0x102fe0`
- `0x104120`
- `0x1042b0`
- `0x1042f0`
- `0x104320`
- `0x113650`

## string_xrefs

- `0x1022f4`: `Illegal to modify TextContainer structure inside Change event scope!`
- `0x102322`: `Missing call to BeforeAddChange!`

## pseudocode

```c

```

## disassembly

```asm
0x1022d0  ldarg.0
0x1022d1  ldfld    int32 System.Windows.Documents.TextContainer::_changeBlockLevel
0x1022d6  ldc.i4.0
0x1022d7  cgt
0x1022d9  ldstr    aAllPublicApisM// "All public APIs must call BeginChange!"
0x1022de  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1022e3  ldarg.0
0x1022e4  ldc.i4.1
0x1022e5  call     instance bool System.Windows.Documents.TextContainer::CheckFlags(valuetype Flags flags)
0x1022ea  brfalse.s loc_1022F3
0x1022ec  ldarg.s  6
0x1022ee  ldc.i4.2
0x1022ef  ceq
0x1022f1  br.s     loc_1022F4
0x1022f3  ldc.i4.1
0x1022f4  ldstr    aIllegalToModif_0// "Illegal to modify TextContainer structu"...
0x1022f9  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1022fe  ldarg.0
0x1022ff  call     instance bool System.Windows.Documents.TextContainer::get_HasListeners()
0x102304  brfalse.s loc_102361
0x102306  ldarg.0
0x102307  ldfld    class System.Windows.Documents.TextContainerChangedEventArgs System.Windows.Documents.TextContainer::_changes
0x10230c  brtrue.s loc_102319
0x10230e  ldarg.0
0x10230f  newobj   instance void System.Windows.Documents.TextContainerChangedEventArgs::.ctor()
0x102314  stfld    class System.Windows.Documents.TextContainerChangedEventArgs System.Windows.Documents.TextContainer::_changes
0x102319  ldarg.0
0x10231a  ldfld    class System.Windows.Documents.TextContainerChangedEventArgs System.Windows.Documents.TextContainer::_changes
0x10231f  ldnull
0x102320  cgt.un
0x102322  ldstr    aMissingCallToB// "Missing call to BeforeAddChange!"
0x102327  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x10232c  ldarg.0
0x10232d  ldfld    class System.Windows.Documents.TextContainerChangedEventArgs System.Windows.Documents.TextContainer::_changes
0x102332  ldarg.s  6
0x102334  ldarg.1
0x102335  callvirt instance int32 System.Windows.Documents.TextPointer::get_Offset()
0x10233a  ldarg.3
0x10233b  ldarg.0
0x10233c  call     instance bool System.Windows.Documents.TextContainer::get_CollectTextChanges()
0x102341  callvirt instance void System.Windows.Documents.TextContainerChangedEventArgs::AddChange(valuetype System.Windows.Documents.PrecursorTextChangeType textChange, int32 offset, int32 length, bool collectTextChanges)
0x102346  ldarg.0
0x102347  ldfld    class System.Windows.Documents.TextContainerChangeEventHandler System.Windows.Documents.TextContainer::ChangeHandler
0x10234c  brfalse.s loc_102361
0x10234e  ldarg.0
0x10234f  ldarg.1
0x102350  ldarg.2
0x102351  ldarg.3
0x102352  ldarg.s  4
0x102354  ldarg.s  5
0x102356  ldarg.s  6
0x102358  ldarg.s  7
0x10235a  ldarg.s  8
0x10235c  call     instance void System.Windows.Documents.TextContainer::FireChangeEvent(class System.Windows.Documents.TextPointer startPosition, class System.Windows.Documents.TextPointer endPosition, int32 symbolCount, int32 leftEdgeCharCount, int32 childCharCount, valuetype System.Windows.Documents.PrecursorTextChangeType precursorTextChange, class [WindowsBase]System.Windows.DependencyProperty property, bool affectsRenderOnly)
0x102361  ret
```
