# System.Web.UI.PageRequestManager::UnregisterUpdatePanel

- ea: `0x11c70`
- end: `0x11cbd`
- name: `System.Web.UI.PageRequestManager::UnregisterUpdatePanel`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x161f0`

## callees

- `0x11c70`
- `0x2af50`

## string_xrefs

- `0x11ca4`: `updatePanel`

## pseudocode

```c

```

## disassembly

```asm
0x11c70  ldarg.0
0x11c71  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.UpdatePanel> System.Web.UI.PageRequestManager::_allUpdatePanels
0x11c76  brfalse.s loc_11C86
0x11c78  ldarg.0
0x11c79  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.UpdatePanel> System.Web.UI.PageRequestManager::_allUpdatePanels
0x11c7e  ldarg.1
0x11c7f  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.UpdatePanel>::Contains(var<u1>)
0x11c84  brtrue.s loc_11CAF
0x11c86  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11c8b  call     string System.Web.Resources.AtlasWeb::get_ScriptManager_UpdatePanelNotRegistered()
0x11c90  ldc.i4.1
0x11c91  newarr   [mscorlib]System.Object
0x11c96  dup
0x11c97  ldc.i4.0
0x11c98  ldarg.1
0x11c99  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11c9e  stelem.ref
0x11c9f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11ca4  ldstr    aUpdatepanel// "updatePanel"
0x11ca9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x11cae  throw
0x11caf  ldarg.0
0x11cb0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.UpdatePanel> System.Web.UI.PageRequestManager::_allUpdatePanels
0x11cb5  ldarg.1
0x11cb6  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.UpdatePanel>::Remove(var<u1>)
0x11cbb  pop
0x11cbc  ret
```
