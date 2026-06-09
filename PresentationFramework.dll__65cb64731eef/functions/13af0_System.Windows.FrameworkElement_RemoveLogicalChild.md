# System.Windows.FrameworkElement::RemoveLogicalChild

- ea: `0x13af0`
- end: `0x13b49`
- name: `System.Windows.FrameworkElement::RemoveLogicalChild`
- size: `89`
- prototype: ``
- caller_count: `22`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18050`
- `0x18080`
- `0xca050`
- `0x13bbb0`
- `0x1435b0`
- `0x15e020`
- `0x162340`
- `0x164830`
- `0x16fa50`
- `0x16fea0`
- `0x181950`
- `0x189340`
- `0x19e0b0`
- `0x19f040`
- `0x1b0c80`
- `0x1b1740`
- `0x1b1b70`
- `0x1bad50`
- `0x1bd2d0`
- `0x275ba0`
- `0x275c00`
- `0x275c40`

## callees

- `0x13620`
- `0x136f0`
- `0x13a50`
- `0x13af0`
- `0x38c40`
- `0x1d8e20`
- `0x1d8fd0`
- `0x1d9690`

## string_xrefs

- `0x13afb`: `CannotModifyLogicalChildrenDuringTreeWalk`

## pseudocode

```c

```

## disassembly

```asm
0x13af0  ldarg.1
0x13af1  brfalse.s loc_13B48
0x13af3  ldarg.0
0x13af4  call     instance bool System.Windows.FrameworkElement::get_IsLogicalChildrenIterationInProgress()
0x13af9  brfalse.s loc_13B0B
0x13afb  ldstr    aCannotmodifylo// "CannotModifyLogicalChildrenDuringTreeWa"...
0x13b00  call     string System.Windows.SR::Get(string id)
0x13b05  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x13b0a  throw
0x13b0b  ldloca.s 0
0x13b0d  ldarg.1
0x13b0e  isinst   [WindowsBase]System.Windows.DependencyObject
0x13b13  call     instance void MS.Internal.FrameworkObject::.ctor(class [WindowsBase]System.Windows.DependencyObject d)
0x13b18  ldloca.s 0
0x13b1a  call     instance class [WindowsBase]System.Windows.DependencyObject MS.Internal.FrameworkObject::get_Parent()
0x13b1f  ldarg.0
0x13b20  bne.un.s loc_13B2A
0x13b22  ldloca.s 0
0x13b24  ldnull
0x13b25  call     instance void MS.Internal.FrameworkObject::ChangeLogicalParent(class [WindowsBase]System.Windows.DependencyObject newParent)
0x13b2a  ldarg.0
0x13b2b  callvirt instance class [mscorlib]System.Collections.IEnumerator System.Windows.FrameworkElement::get_LogicalChildren()
0x13b30  stloc.1
0x13b31  ldloc.1
0x13b32  brtrue.s loc_13B3C
0x13b34  ldarg.0
0x13b35  ldc.i4.0
0x13b36  call     instance void System.Windows.FrameworkElement::set_HasLogicalChildren(bool value)
0x13b3b  ret
0x13b3c  ldarg.0
0x13b3d  ldloc.1
0x13b3e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13b43  call     instance void System.Windows.FrameworkElement::set_HasLogicalChildren(bool value)
0x13b48  ret
```
