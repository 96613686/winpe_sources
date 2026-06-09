# DefaultComparer::GetStringToCompare

- ea: `0xccc0`
- end: `0xcd00`
- name: `DefaultComparer::GetStringToCompare`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xcc60`

## callees

- `0x560`
- `0x5b0`
- `0x5d20`
- `0xccc0`

## pseudocode

```c

```

## disassembly

```asm
0xccc0  ldsfld   string [mscorlib]System.String::Empty
0xccc5  stloc.0
0xccc6  ldarg.0
0xccc7  ldfld    int32 DefaultComparer::_columnIndex
0xcccc  brtrue.s loc_CCD7
0xccce  ldarg.1
0xcccf  callvirt instance string Microsoft.ManagementConsole.Node::get_DisplayName()
0xccd4  stloc.0
0xccd5  br.s     loc_CCFE
0xccd7  ldarg.0
0xccd8  ldfld    int32 DefaultComparer::_columnIndex
0xccdd  ldarg.1
0xccde  callvirt instance class Microsoft.ManagementConsole.NodeSubItemDisplayNameCollection Microsoft.ManagementConsole.Node::get_SubItemDisplayNames()
0xcce3  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xcce8  bgt.s    loc_CCFE
0xccea  ldarg.1
0xcceb  callvirt instance class Microsoft.ManagementConsole.NodeSubItemDisplayNameCollection Microsoft.ManagementConsole.Node::get_SubItemDisplayNames()
0xccf0  ldarg.0
0xccf1  ldfld    int32 DefaultComparer::_columnIndex
0xccf6  ldc.i4.1
0xccf7  sub
0xccf8  callvirt instance string Microsoft.ManagementConsole.NodeSubItemDisplayNameCollection::get_Item(int32 index)
0xccfd  stloc.0
0xccfe  ldloc.0
0xccff  ret
```
