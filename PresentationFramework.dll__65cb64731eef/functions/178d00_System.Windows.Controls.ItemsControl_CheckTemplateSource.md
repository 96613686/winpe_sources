# System.Windows.Controls.ItemsControl::CheckTemplateSource

- ea: `0x178d00`
- end: `0x178d5e`
- name: `System.Windows.Controls.ItemsControl::CheckTemplateSource`
- size: `94`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x178b70`
- `0x178bf0`

## callees

- `0x38c40`
- `0x178a00`
- `0x178b90`
- `0x178d00`
- `0x1d9e30`
- `0x1d9e90`

## string_xrefs

- `0x178d30`: `ItemTemplateSelectorBreaksDisplayMemberPath`
- `0x178d4d`: `DisplayMemberPathAndItemTemplateDefined`

## pseudocode

```c

```

## disassembly

```asm
0x178d00  ldarg.0
0x178d01  call     instance string System.Windows.Controls.ItemsControl::get_DisplayMemberPath()
0x178d06  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x178d0b  brfalse.s loc_178D23
0x178d0d  ldstr    aItem_1// "Item"
0x178d12  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ItemsControl::ItemTemplateProperty
0x178d17  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ItemsControl::ItemTemplateSelectorProperty
0x178d1c  ldarg.0
0x178d1d  call     void MS.Internal.Helper::CheckTemplateAndTemplateSelector(string name, class [WindowsBase]System.Windows.DependencyProperty templateProperty, class [WindowsBase]System.Windows.DependencyProperty templateSelectorProperty, class [WindowsBase]System.Windows.DependencyObject d)
0x178d22  ret
0x178d23  ldarg.0
0x178d24  call     instance class System.Windows.Controls.DataTemplateSelector System.Windows.Controls.ItemsControl::get_ItemTemplateSelector()
0x178d29  isinst   MS.Internal.Data.DisplayMemberTemplateSelector
0x178d2e  brtrue.s loc_178D40
0x178d30  ldstr    aItemtemplatese_0// "ItemTemplateSelectorBreaksDisplayMember"...
0x178d35  call     string System.Windows.SR::Get(string id)
0x178d3a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x178d3f  throw
0x178d40  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ItemsControl::ItemTemplateProperty
0x178d45  ldarg.0
0x178d46  call     bool MS.Internal.Helper::IsTemplateDefined(class [WindowsBase]System.Windows.DependencyProperty templateProperty, class [WindowsBase]System.Windows.DependencyObject d)
0x178d4b  brfalse.s loc_178D5D
0x178d4d  ldstr    aDisplaymemberp_1// "DisplayMemberPathAndItemTemplateDefined"
0x178d52  call     string System.Windows.SR::Get(string id)
0x178d57  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x178d5c  throw
0x178d5d  ret
```
