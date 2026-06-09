# System.Windows.Controls.ItemContainerGenerator::Remove

- ea: `0x175bc0`
- end: `0x175f07`
- name: `System.Windows.Controls.ItemContainerGenerator::Remove`
- size: `839`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x175bb0`
- `0x176020`

## callees

- `0x38c40`
- `0x38c70`
- `0x175bc0`
- `0x177070`
- `0x1770f0`
- `0x1777d0`
- `0x1bbc10`
- `0x1bbc30`
- `0x273cf0`
- `0x273d10`
- `0x273d30`
- `0x273d50`
- `0x273d60`
- `0x273d70`
- `0x273d80`
- `0x273dc0`
- `0x274000`
- `0x2741a0`

## string_xrefs

- `0x175bc9`: `RemoveRequiresOffsetZero`
- `0x175c06`: `RemoveRequiresPositiveCount`
- `0x175c85`: `CannotRemoveUnrealizedItems`

## pseudocode

```c

```

## disassembly

```asm
0x175bc0  ldarga.s 1
0x175bc2  call     instance int32 System.Windows.Controls.Primitives.GeneratorPosition::get_Offset()
0x175bc7  brfalse.s loc_175C02
0x175bc9  ldstr    aRemoverequires// "RemoveRequiresOffsetZero"
0x175bce  ldc.i4.2
0x175bcf  newarr   [mscorlib]System.Object
0x175bd4  dup
0x175bd5  ldc.i4.0
0x175bd6  ldarga.s 1
0x175bd8  call     instance int32 System.Windows.Controls.Primitives.GeneratorPosition::get_Index()
0x175bdd  box      [mscorlib]System.Int32
0x175be2  stelem.ref
0x175be3  dup
0x175be4  ldc.i4.1
0x175be5  ldarga.s 1
0x175be7  call     instance int32 System.Windows.Controls.Primitives.GeneratorPosition::get_Offset()
0x175bec  box      [mscorlib]System.Int32
0x175bf1  stelem.ref
0x175bf2  call     string System.Windows.SR::Get(string id, object[] args)
0x175bf7  ldstr    aPosition// "position"
0x175bfc  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x175c01  throw
0x175c02  ldarg.2
0x175c03  ldc.i4.0
0x175c04  bgt.s    loc_175C2A
0x175c06  ldstr    aRemoverequires_0// "RemoveRequiresPositiveCount"
0x175c0b  ldc.i4.1
0x175c0c  newarr   [mscorlib]System.Object
0x175c11  dup
0x175c12  ldc.i4.0
0x175c13  ldarg.2
0x175c14  box      [mscorlib]System.Int32
0x175c19  stelem.ref
0x175c1a  call     string System.Windows.SR::Get(string id, object[] args)
0x175c1f  ldstr    aCount// "count"
0x175c24  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x175c29  throw
0x175c2a  ldarg.0
0x175c2b  ldfld    class ItemBlock System.Windows.Controls.ItemContainerGenerator::_itemMap
0x175c30  brtrue.s loc_175C33
0x175c32  ret
0x175c33  ldarga.s 1
0x175c35  call     instance int32 System.Windows.Controls.Primitives.GeneratorPosition::get_Index()
0x175c3a  stloc.0
0x175c3b  ldloc.0
0x175c3c  stloc.2
0x175c3d  ldarg.0
0x175c3e  ldfld    class ItemBlock System.Windows.Controls.ItemContainerGenerator::_itemMap
0x175c43  callvirt instance class ItemBlock ItemBlock::get_Next()
0x175c48  stloc.1
0x175c49  br.s     loc_175C64
0x175c4b  ldloc.2
0x175c4c  ldloc.1
0x175c4d  callvirt instance int32 ItemBlock::get_ContainerCount()
0x175c52  blt.s    loc_175C6D
0x175c54  ldloc.2
0x175c55  ldloc.1
0x175c56  callvirt instance int32 ItemBlock::get_ContainerCount()
0x175c5b  sub
0x175c5c  stloc.2
0x175c5d  ldloc.1
0x175c5e  callvirt instance class ItemBlock ItemBlock::get_Next()
0x175c63  stloc.1
0x175c64  ldloc.1
0x175c65  ldarg.0
0x175c66  ldfld    class ItemBlock System.Windows.Controls.ItemContainerGenerator::_itemMap
0x175c6b  bne.un.s loc_175C4B
0x175c6d  ldloc.1
0x175c6e  isinst   RealizedItemBlock
0x175c73  stloc.3
0x175c74  ldloc.2
0x175c75  ldarg.2
0x175c76  add
0x175c77  ldc.i4.1
0x175c78  sub
0x175c79  stloc.s  4
0x175c7b  br.s     loc_175CC9
0x175c7d  ldloc.1
0x175c7e  isinst   RealizedItemBlock
0x175c83  brtrue.s loc_175CAD
0x175c85  ldstr    aCannotremoveun// "CannotRemoveUnrealizedItems"
0x175c8a  ldc.i4.2
0x175c8b  newarr   [mscorlib]System.Object
0x175c90  dup
0x175c91  ldc.i4.0
0x175c92  ldloc.0
0x175c93  box      [mscorlib]System.Int32
0x175c98  stelem.ref
0x175c99  dup
0x175c9a  ldc.i4.1
0x175c9b  ldarg.2
0x175c9c  box      [mscorlib]System.Int32
0x175ca1  stelem.ref
0x175ca2  call     string System.Windows.SR::Get(string id, object[] args)
0x175ca7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x175cac  throw
0x175cad  ldloc.s  4
0x175caf  ldloc.1
0x175cb0  callvirt instance int32 ItemBlock::get_ContainerCount()
0x175cb5  blt.s    loc_175CD2
0x175cb7  ldloc.s  4
0x175cb9  ldloc.1
0x175cba  callvirt instance int32 ItemBlock::get_ContainerCount()
0x175cbf  sub
0x175cc0  stloc.s  4
0x175cc2  ldloc.1
0x175cc3  callvirt instance class ItemBlock ItemBlock::get_Next()
0x175cc8  stloc.1
0x175cc9  ldloc.1
0x175cca  ldarg.0
0x175ccb  ldfld    class ItemBlock System.Windows.Controls.ItemContainerGenerator::_itemMap
0x175cd0  bne.un.s loc_175C7D
0x175cd2  ldloc.1
0x175cd3  isinst   RealizedItemBlock
0x175cd8  stloc.s  5
0x175cda  ldloc.3
0x175cdb  stloc.s  6
0x175cdd  ldloc.2
0x175cde  stloc.s  7
0x175ce0  br       loc_175D97
0x175ce5  ldloc.s  6
0x175ce7  ldloc.s  7
0x175ce9  callvirt instance class [WindowsBase]System.Windows.DependencyObject ItemBlock::ContainerAt(int32 index)
0x175cee  stloc.s  0x12
0x175cf0  ldarg.0
0x175cf1  ldloc.s  0x12
0x175cf3  ldloc.s  6
0x175cf5  ldloc.s  7
0x175cf7  callvirt instance object ItemBlock::ItemAt(int32 index)
0x175cfc  call     instance void System.Windows.Controls.ItemContainerGenerator::UnlinkContainerFromItem(class [WindowsBase]System.Windows.DependencyObject container, object item)
0x175d01  ldarg.0
0x175d02  ldfld    bool System.Windows.Controls.ItemContainerGenerator::_generatesGroupItems
0x175d07  brfalse.s loc_175D18
0x175d09  ldloc.s  0x12
0x175d0b  isinst   System.Windows.Controls.GroupItem
0x175d10  ldnull
0x175d11  cgt.un
0x175d13  ldc.i4.0
0x175d14  ceq
0x175d16  br.s     loc_175D19
0x175d18  ldc.i4.0
0x175d19  stloc.s  0x13
0x175d1b  ldarg.3
0x175d1c  brfalse.s loc_175D70
0x175d1e  ldloc.s  0x13
0x175d20  brtrue.s loc_175D70
0x175d22  ldarg.0
0x175d23  ldfld    class [mscorlib]System.Type System.Windows.Controls.ItemContainerGenerator::_containerType
0x175d28  ldnull
0x175d29  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x175d2e  brfalse.s loc_175D3F
0x175d30  ldarg.0
0x175d31  ldloc.s  0x12
0x175d33  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x175d38  stfld    class [mscorlib]System.Type System.Windows.Controls.ItemContainerGenerator::_containerType
0x175d3d  br.s     loc_175D63
0x175d3f  ldarg.0
0x175d40  ldfld    class [mscorlib]System.Type System.Windows.Controls.ItemContainerGenerator::_containerType
0x175d45  ldloc.s  0x12
0x175d47  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x175d4c  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x175d51  brfalse.s loc_175D63
0x175d53  ldstr    aCannotrecylehe// "CannotRecyleHeterogeneousTypes"
0x175d58  call     string System.Windows.SR::Get(string id)
0x175d5d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x175d62  throw
0x175d63  ldarg.0
0x175d64  ldfld    class [System]System.Collections.Generic.Queue`1<class [WindowsBase]System.Windows.DependencyObject> System.Windows.Controls.ItemContainerGenerator::_recyclableContainers
0x175d69  ldloc.s  0x12
0x175d6b  callvirt instance void class [System]System.Collections.Generic.Queue`1<class [WindowsBase]System.Windows.DependencyObject>::Enqueue(var<u1>)
0x175d70  ldloc.s  7
0x175d72  ldc.i4.1
0x175d73  add
0x175d74  dup
0x175d75  stloc.s  7
0x175d77  ldloc.s  6
0x175d79  callvirt instance int32 ItemBlock::get_ContainerCount()
0x175d7e  blt.s    loc_175D97
0x175d80  ldloc.s  6
0x175d82  ldloc.s  5
0x175d84  beq.s    loc_175D97
0x175d86  ldloc.s  6
0x175d88  callvirt instance class ItemBlock ItemBlock::get_Next()
0x175d8d  isinst   RealizedItemBlock
0x175d92  stloc.s  6
0x175d94  ldc.i4.0
0x175d95  stloc.s  7
0x175d97  ldloc.s  6
0x175d99  ldloc.s  5
0x175d9b  bne.un   loc_175CE5
0x175da0  ldloc.s  7
0x175da2  ldloc.s  4
0x175da4  ble      loc_175CE5
0x175da9  ldloc.2
0x175daa  ldc.i4.0
0x175dab  ceq
0x175dad  stloc.s  8
0x175daf  ldloc.s  4
0x175db1  ldloc.s  5
0x175db3  callvirt instance int32 ItemBlock::get_ItemCount()
0x175db8  ldc.i4.1
0x175db9  sub
0x175dba  ceq
0x175dbc  stloc.s  9
0x175dbe  ldloc.s  8
0x175dc0  brfalse.s loc_175DD2
0x175dc2  ldloc.3
0x175dc3  callvirt instance class ItemBlock ItemBlock::get_Prev()
0x175dc8  isinst   UnrealizedItemBlock
0x175dcd  ldnull
0x175dce  cgt.un
0x175dd0  br.s     loc_175DD3
0x175dd2  ldc.i4.0
0x175dd3  stloc.s  0xA
0x175dd5  ldloc.s  9
0x175dd7  brfalse.s loc_175DEA
0x175dd9  ldloc.s  5
0x175ddb  callvirt instance class ItemBlock ItemBlock::get_Next()
0x175de0  isinst   UnrealizedItemBlock
0x175de5  ldnull
0x175de6  cgt.un
0x175de8  br.s     loc_175DEB
0x175dea  ldc.i4.0
0x175deb  stloc.s  0xB
0x175ded  ldnull
0x175dee  stloc.s  0xD
0x175df0  ldloc.s  0xA
0x175df2  brfalse.s loc_175E16
0x175df4  ldloc.3
0x175df5  callvirt instance class ItemBlock ItemBlock::get_Prev()
0x175dfa  castclass UnrealizedItemBlock
0x175dff  stloc.s  0xC
0x175e01  ldloc.s  0xC
0x175e03  callvirt instance int32 ItemBlock::get_ItemCount()
0x175e08  stloc.s  0xE
0x175e0a  ldloc.s  0xC
0x175e0c  callvirt instance int32 ItemBlock::get_ItemCount()
0x175e11  neg
0x175e12  stloc.s  0xF
0x175e14  br.s     loc_175E4C
0x175e16  ldloc.s  0xB
0x175e18  brfalse.s loc_175E30
0x175e1a  ldloc.s  5
0x175e1c  callvirt instance class ItemBlock ItemBlock::get_Next()
0x175e21  castclass UnrealizedItemBlock
0x175e26  stloc.s  0xC
0x175e28  ldc.i4.0
0x175e29  stloc.s  0xE
0x175e2b  ldloc.2
0x175e2c  stloc.s  0xF
0x175e2e  br.s     loc_175E4C
0x175e30  newobj   instance void UnrealizedItemBlock::.ctor()
0x175e35  stloc.s  0xC
0x175e37  ldc.i4.0
0x175e38  stloc.s  0xE
0x175e3a  ldloc.2
0x175e3b  stloc.s  0xF
0x175e3d  ldloc.s  8
0x175e3f  brtrue.s loc_175E44
0x175e41  ldloc.3
0x175e42  br.s     loc_175E4A
0x175e44  ldloc.3
0x175e45  callvirt instance class ItemBlock ItemBlock::get_Prev()
0x175e4a  stloc.s  0xD
0x175e4c  ldloc.3
0x175e4d  stloc.1
0x175e4e  br.s     loc_175E91
0x175e50  ldloc.1
0x175e51  callvirt instance int32 ItemBlock::get_ItemCount()
0x175e56  stloc.s  0x14
0x175e58  ldarg.0
0x175e59  ldloc.1
0x175e5a  ldloc.2
0x175e5b  ldloc.s  0x14
0x175e5d  ldloc.2
0x175e5e  sub
0x175e5f  ldloc.s  0xC
0x175e61  ldloc.s  0xE
0x175e63  ldloc.s  0xF
0x175e65  call     instance void System.Windows.Controls.ItemContainerGenerator::MoveItems(class ItemBlock block, int32 offset, int32 count, class ItemBlock newBlock, int32 newOffset, int32 deltaCount)
0x175e6a  ldloc.s  0xE
0x175e6c  ldloc.s  0x14
0x175e6e  ldloc.2
0x175e6f  sub
0x175e70  add
0x175e71  stloc.s  0xE
0x175e73  ldc.i4.0
0x175e74  stloc.2
0x175e75  ldloc.s  0xF
0x175e77  ldloc.s  0x14
0x175e79  sub
0x175e7a  stloc.s  0xF
0x175e7c  ldloc.1
0x175e7d  callvirt instance int32 ItemBlock::get_ItemCount()
0x175e82  brtrue.s loc_175E8A
0x175e84  ldloc.1
0x175e85  callvirt instance void ItemBlock::Remove()
0x175e8a  ldloc.1
0x175e8b  callvirt instance class ItemBlock ItemBlock::get_Next()
0x175e90  stloc.1
  ... truncated ...
```
