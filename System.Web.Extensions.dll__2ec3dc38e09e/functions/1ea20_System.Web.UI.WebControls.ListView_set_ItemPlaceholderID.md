# System.Web.UI.WebControls.ListView::set_ItemPlaceholderID

- ea: `0x1ea20`
- end: `0x1ea62`
- name: `System.Web.UI.WebControls.ListView::set_ItemPlaceholderID`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1ea20`
- `0x29810`

## string_xrefs

- `0x1ea3f`: `ItemPlaceholderID`
- `0x1ea56`: `ItemPlaceholderID`

## pseudocode

```c

```

## disassembly

```asm
0x1ea20  ldarg.1
0x1ea21  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ea26  brfalse.s loc_1EA50
0x1ea28  ldstr    aValue// "value"
0x1ea2d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1ea32  call     string System.Web.Resources.AtlasWeb::get_ListView_ContainerNameMustNotBeEmpty()
0x1ea37  ldc.i4.1
0x1ea38  newarr   [mscorlib]System.Object
0x1ea3d  dup
0x1ea3e  ldc.i4.0
0x1ea3f  ldstr    aItemplaceholde// "ItemPlaceholderID"
0x1ea44  stelem.ref
0x1ea45  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1ea4a  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x1ea4f  throw
0x1ea50  ldarg.0
0x1ea51  callvirt instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.Control::get_ViewState()
0x1ea56  ldstr    aItemplaceholde// "ItemPlaceholderID"
0x1ea5b  ldarg.1
0x1ea5c  callvirt instance void [System.Web]System.Web.UI.StateBag::set_Item(string, object)
0x1ea61  ret
```
