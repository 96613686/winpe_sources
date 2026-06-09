# System.Web.UI.WebControls.TemplatePagerField::OnPagerCommand

- ea: `0x266d0`
- end: `0x26715`
- name: `System.Web.UI.WebControls.TemplatePagerField::OnPagerCommand`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x26650`

## callees

- `0x265a0`
- `0x266d0`
- `0x2b350`

## string_xrefs

- `0x26704`: `PagerCommand`

## pseudocode

```c

```

## disassembly

```asm
0x266d0  ldarg.0
0x266d1  call     instance class [System]System.ComponentModel.EventHandlerList System.Web.UI.WebControls.TemplatePagerField::get_Events()
0x266d6  ldsfld   object System.Web.UI.WebControls.TemplatePagerField::EventPagerCommand
0x266db  callvirt instance class [mscorlib]System.Delegate [System]System.ComponentModel.EventHandlerList::get_Item(object)
0x266e0  castclass class [mscorlib]System.EventHandler`1<class System.Web.UI.WebControls.DataPagerCommandEventArgs>
0x266e5  stloc.0
0x266e6  ldloc.0
0x266e7  brfalse.s loc_266F2
0x266e9  ldloc.0
0x266ea  ldarg.0
0x266eb  ldarg.1
0x266ec  callvirt instance void class [mscorlib]System.EventHandler`1<class System.Web.UI.WebControls.DataPagerCommandEventArgs>::Invoke(object, var<u1>)
0x266f1  ret
0x266f2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x266f7  call     string System.Web.Resources.AtlasWeb::get_TemplatePagerField_UnhandledEvent()
0x266fc  ldc.i4.1
0x266fd  newarr   [mscorlib]System.Object
0x26702  dup
0x26703  ldc.i4.0
0x26704  ldstr    aPagercommand// "PagerCommand"
0x26709  stelem.ref
0x2670a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2670f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x26714  throw
```
