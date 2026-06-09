# System.Windows.Forms.Design.BaseContextMenuStrip::AddEditMenuItem

- ea: `0x95310`
- end: `0x953fd`
- name: `System.Windows.Forms.Design.BaseContextMenuStrip::AddEditMenuItem`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x95480`

## callees

- `0x8ef40`
- `0x9fc00`
- `0x9fc40`
- `0xb9b60`
- `0xc8650`

## string_xrefs

- `0x95350`: `ContextMenuCopy`
- `0x953c6`: `ContextMenuDelete`
- `0x953d0`: `delete`

## pseudocode

```c

```

## disassembly

```asm
0x95310  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::Cut
0x95315  ldstr    aContextmenucut// "ContextMenuCut"
0x9531a  call     string System.Design.SR::GetString(string name)
0x9531f  ldstr    aCut// "cut"
0x95324  ldarg.0
0x95325  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.BaseContextMenuStrip::serviceProvider
0x9532a  newobj   instance void System.Windows.Forms.Design.StandardCommandToolStripMenuItem::.ctor(class [System]System.ComponentModel.Design.CommandID menuID, string text, string imageName, class [mscorlib]System.IServiceProvider serviceProvider)
0x9532f  stloc.0
0x95330  ldarg.0
0x95331  call     instance class System.Windows.Forms.Design.ContextMenuStripGroupCollection System.Windows.Forms.Design.GroupedContextMenuStrip::get_Groups()
0x95336  ldstr    aEdit// "Edit"
0x9533b  callvirt instance class System.Windows.Forms.Design.ContextMenuStripGroup System.Windows.Forms.Design.ContextMenuStripGroupCollection::get_Item(string key)
0x95340  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem> System.Windows.Forms.Design.ContextMenuStripGroup::get_Items()
0x95345  ldloc.0
0x95346  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::Add(var<u1>)
0x9534b  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::Copy
0x95350  ldstr    aContextmenucop// "ContextMenuCopy"
0x95355  call     string System.Design.SR::GetString(string name)
0x9535a  ldstr    aCopy// "copy"
0x9535f  ldarg.0
0x95360  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.BaseContextMenuStrip::serviceProvider
0x95365  newobj   instance void System.Windows.Forms.Design.StandardCommandToolStripMenuItem::.ctor(class [System]System.ComponentModel.Design.CommandID menuID, string text, string imageName, class [mscorlib]System.IServiceProvider serviceProvider)
0x9536a  stloc.0
0x9536b  ldarg.0
0x9536c  call     instance class System.Windows.Forms.Design.ContextMenuStripGroupCollection System.Windows.Forms.Design.GroupedContextMenuStrip::get_Groups()
0x95371  ldstr    aEdit// "Edit"
0x95376  callvirt instance class System.Windows.Forms.Design.ContextMenuStripGroup System.Windows.Forms.Design.ContextMenuStripGroupCollection::get_Item(string key)
0x9537b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem> System.Windows.Forms.Design.ContextMenuStripGroup::get_Items()
0x95380  ldloc.0
0x95381  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::Add(var<u1>)
0x95386  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::Paste
0x9538b  ldstr    aContextmenupas// "ContextMenuPaste"
0x95390  call     string System.Design.SR::GetString(string name)
0x95395  ldstr    aPaste// "paste"
0x9539a  ldarg.0
0x9539b  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.BaseContextMenuStrip::serviceProvider
0x953a0  newobj   instance void System.Windows.Forms.Design.StandardCommandToolStripMenuItem::.ctor(class [System]System.ComponentModel.Design.CommandID menuID, string text, string imageName, class [mscorlib]System.IServiceProvider serviceProvider)
0x953a5  stloc.0
0x953a6  ldarg.0
0x953a7  call     instance class System.Windows.Forms.Design.ContextMenuStripGroupCollection System.Windows.Forms.Design.GroupedContextMenuStrip::get_Groups()
0x953ac  ldstr    aEdit// "Edit"
0x953b1  callvirt instance class System.Windows.Forms.Design.ContextMenuStripGroup System.Windows.Forms.Design.ContextMenuStripGroupCollection::get_Item(string key)
0x953b6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem> System.Windows.Forms.Design.ContextMenuStripGroup::get_Items()
0x953bb  ldloc.0
0x953bc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::Add(var<u1>)
0x953c1  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::Delete
0x953c6  ldstr    aContextmenudel// "ContextMenuDelete"
0x953cb  call     string System.Design.SR::GetString(string name)
0x953d0  ldstr    aDelete_1// "delete"
0x953d5  ldarg.0
0x953d6  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.BaseContextMenuStrip::serviceProvider
0x953db  newobj   instance void System.Windows.Forms.Design.StandardCommandToolStripMenuItem::.ctor(class [System]System.ComponentModel.Design.CommandID menuID, string text, string imageName, class [mscorlib]System.IServiceProvider serviceProvider)
0x953e0  stloc.0
0x953e1  ldarg.0
0x953e2  call     instance class System.Windows.Forms.Design.ContextMenuStripGroupCollection System.Windows.Forms.Design.GroupedContextMenuStrip::get_Groups()
0x953e7  ldstr    aEdit// "Edit"
0x953ec  callvirt instance class System.Windows.Forms.Design.ContextMenuStripGroup System.Windows.Forms.Design.ContextMenuStripGroupCollection::get_Item(string key)
0x953f1  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem> System.Windows.Forms.Design.ContextMenuStripGroup::get_Items()
0x953f6  ldloc.0
0x953f7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::Add(var<u1>)
0x953fc  ret
```
