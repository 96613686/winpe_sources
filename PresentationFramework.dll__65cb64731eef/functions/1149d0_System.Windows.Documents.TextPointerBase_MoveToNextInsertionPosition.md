# System.Windows.Documents.TextPointerBase::MoveToNextInsertionPosition

- ea: `0x1149d0`
- end: `0x114b02`
- name: `System.Windows.Documents.TextPointerBase::MoveToNextInsertionPosition`
- size: `306`
- prototype: ``
- caller_count: `8`
- callee_count: `11`
- tags: ``

## callers

- `0xcf680`
- `0xdb360`
- `0xe5f50`
- `0x112470`
- `0x1846d0`
- `0x1df0e0`
- `0x1df560`
- `0x1df990`

## callees

- `0xe4150`
- `0xe41b0`
- `0xe41e0`
- `0xe4240`
- `0xe4250`
- `0xe4340`
- `0xe43f0`
- `0x113dc0`
- `0x1149c0`
- `0x1149d0`
- `0x11f390`

## string_xrefs

- `0x114aca`: `thisNavigator is expected to be moved from initialPosition - 1`
- `0x114ae0`: `thisNavigator is expected to be moved from initialPosition - 2`

## pseudocode

```c

```

## disassembly

```asm
0x1149d0  ldarg.0
0x1149d1  callvirt instance bool System.Windows.Documents.ITextPointer::get_IsFrozen()
0x1149d6  ldc.i4.0
0x1149d7  ceq
0x1149d9  ldstr    aCanTReposition// "Can't reposition a frozen pointer!"
0x1149de  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1149e3  ldc.i4.1
0x1149e4  stloc.0
0x1149e5  ldarg.1
0x1149e6  ldc.i4.1
0x1149e7  beq.s    loc_1149EC
0x1149e9  ldc.i4.m1
0x1149ea  br.s     loc_1149ED
0x1149ec  ldc.i4.1
0x1149ed  stloc.1
0x1149ee  ldarg.0
0x1149ef  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextPointer::CreatePointer()
0x1149f4  stloc.2
0x1149f5  ldarg.0
0x1149f6  call     bool System.Windows.Documents.TextPointerBase::IsAtInsertionPosition(class System.Windows.Documents.ITextPointer position)
0x1149fb  brtrue.s loc_114A38
0x1149fd  ldarg.0
0x1149fe  ldarg.1
0x1149ff  call     bool System.Windows.Documents.TextPointerBase::MoveToInsertionPosition(class System.Windows.Documents.ITextPointer thisNavigator, valuetype System.Windows.Documents.LogicalDirection direction)
0x114a04  brtrue.s loc_114A0D
0x114a06  ldc.i4.0
0x114a07  stloc.0
0x114a08  br       loc_114AB9
0x114a0d  ldarg.1
0x114a0e  ldc.i4.1
0x114a0f  bne.un.s loc_114A1E
0x114a11  ldloc.2
0x114a12  ldarg.0
0x114a13  callvirt instance int32 System.Windows.Documents.ITextPointer::CompareTo(class System.Windows.Documents.ITextPointer position)
0x114a18  ldc.i4.0
0x114a19  blt      loc_114AB9
0x114a1e  ldarg.1
0x114a1f  brtrue.s loc_114A38
0x114a21  ldarg.0
0x114a22  ldloc.2
0x114a23  callvirt instance int32 System.Windows.Documents.ITextPointer::CompareTo(class System.Windows.Documents.ITextPointer position)
0x114a28  ldc.i4.0
0x114a29  bge.s    loc_114A38
0x114a2b  br       loc_114AB9
0x114a30  ldarg.0
0x114a31  ldloc.1
0x114a32  callvirt instance int32 System.Windows.Documents.ITextPointer::MoveByOffset(int32 offset)
0x114a37  pop
0x114a38  ldarg.0
0x114a39  ldarg.1
0x114a3a  callvirt instance class [mscorlib]System.Type System.Windows.Documents.ITextPointer::GetElementType(valuetype System.Windows.Documents.LogicalDirection direction)
0x114a3f  call     bool System.Windows.Documents.TextSchema::IsFormattingType(class [mscorlib]System.Type elementType)
0x114a44  brtrue.s loc_114A30
0x114a46  ldarg.0
0x114a47  ldarg.1
0x114a48  callvirt instance valuetype System.Windows.Documents.TextPointerContext System.Windows.Documents.ITextPointer::GetPointerContext(valuetype System.Windows.Documents.LogicalDirection direction)
0x114a4d  brfalse.s loc_114A59
0x114a4f  ldarg.0
0x114a50  ldloc.1
0x114a51  callvirt instance int32 System.Windows.Documents.ITextPointer::MoveByOffset(int32 offset)
0x114a56  pop
0x114a57  br.s     loc_114A64
0x114a59  ldarg.0
0x114a5a  ldloc.2
0x114a5b  callvirt instance void System.Windows.Documents.ITextPointer::MoveToPosition(class System.Windows.Documents.ITextPointer position)
0x114a60  ldc.i4.0
0x114a61  stloc.0
0x114a62  br.s     loc_114AB9
0x114a64  ldarg.0
0x114a65  call     bool System.Windows.Documents.TextPointerBase::IsAtInsertionPosition(class System.Windows.Documents.ITextPointer position)
0x114a6a  brfalse.s loc_114A46
0x114a6c  ldarg.1
0x114a6d  brtrue.s loc_114AB9
0x114a6f  br.s     loc_114A79
0x114a71  ldarg.0
0x114a72  ldloc.1
0x114a73  callvirt instance int32 System.Windows.Documents.ITextPointer::MoveByOffset(int32 offset)
0x114a78  pop
0x114a79  ldarg.0
0x114a7a  ldarg.1
0x114a7b  callvirt instance class [mscorlib]System.Type System.Windows.Documents.ITextPointer::GetElementType(valuetype System.Windows.Documents.LogicalDirection direction)
0x114a80  call     bool System.Windows.Documents.TextSchema::IsFormattingType(class [mscorlib]System.Type elementType)
0x114a85  brtrue.s loc_114A71
0x114a87  ldarg.0
0x114a88  ldarg.1
0x114a89  callvirt instance valuetype System.Windows.Documents.TextPointerContext System.Windows.Documents.ITextPointer::GetPointerContext(valuetype System.Windows.Documents.LogicalDirection direction)
0x114a8e  stloc.3
0x114a8f  ldloc.3
0x114a90  ldc.i4.3
0x114a91  beq.s    loc_114A96
0x114a93  ldloc.3
0x114a94  brtrue.s loc_114AB9
0x114a96  ldloc.1
0x114a97  neg
0x114a98  stloc.1
0x114a99  br.s     loc_114AA3
0x114a9b  ldarg.0
0x114a9c  ldloc.1
0x114a9d  callvirt instance int32 System.Windows.Documents.ITextPointer::MoveByOffset(int32 offset)
0x114aa2  pop
0x114aa3  ldarg.0
0x114aa4  ldc.i4.1
0x114aa5  callvirt instance class [mscorlib]System.Type System.Windows.Documents.ITextPointer::GetElementType(valuetype System.Windows.Documents.LogicalDirection direction)
0x114aaa  call     bool System.Windows.Documents.TextSchema::IsFormattingType(class [mscorlib]System.Type elementType)
0x114aaf  brfalse.s loc_114AB9
0x114ab1  ldarg.0
0x114ab2  call     bool System.Windows.Documents.TextPointerBase::IsAtInsertionPosition(class System.Windows.Documents.ITextPointer position)
0x114ab7  brfalse.s loc_114A9B
0x114ab9  ldloc.0
0x114aba  brfalse.s loc_114AEC
0x114abc  ldarg.1
0x114abd  ldc.i4.1
0x114abe  bne.un.s loc_114AD6
0x114ac0  ldarg.0
0x114ac1  ldloc.2
0x114ac2  callvirt instance int32 System.Windows.Documents.ITextPointer::CompareTo(class System.Windows.Documents.ITextPointer position)
0x114ac7  ldc.i4.0
0x114ac8  cgt
0x114aca  ldstr    aThisnavigatorI// "thisNavigator is expected to be moved f"...
0x114acf  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x114ad4  br.s     loc_114B00
0x114ad6  ldarg.0
0x114ad7  ldloc.2
0x114ad8  callvirt instance int32 System.Windows.Documents.ITextPointer::CompareTo(class System.Windows.Documents.ITextPointer position)
0x114add  ldc.i4.0
0x114ade  clt
0x114ae0  ldstr    aThisnavigatorI_0// "thisNavigator is expected to be moved f"...
0x114ae5  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x114aea  br.s     loc_114B00
0x114aec  ldarg.0
0x114aed  ldloc.2
0x114aee  callvirt instance int32 System.Windows.Documents.ITextPointer::CompareTo(class System.Windows.Documents.ITextPointer position)
0x114af3  ldc.i4.0
0x114af4  ceq
0x114af6  ldstr    aThisnavigatorM// "thisNavigator must stay at initial posi"...
0x114afb  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x114b00  ldloc.0
0x114b01  ret
```
