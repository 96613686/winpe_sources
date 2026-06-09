# Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::SetListItemContextMenu

- ea: `0x818a0`
- end: `0x81d84`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::SetListItemContextMenu`
- size: `1252`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x81ee0`

## callees

- `0x12ed0`
- `0x65450`
- `0x818a0`

## string_xrefs

- `0x818d9`: `MenuRunTask`
- `0x81c0f`: `MenuRunTask`
- `0x8191f`: `MenuEndTask`
- `0x81c5a`: `MenuEndTask`
- `0x81965`: `MenuDisableTask`
- `0x81ca9`: `MenuDisableTask`
- `0x819ab`: `MenuExportTask`
- `0x81ad5`: `MenuExportTask`
- `0x81a3e`: `MenuDeleteTask`
- `0x81b6b`: `MenuDeleteTask`
- `0x81d41`: `MenuDeleteTask`
- `0x81a8a`: `MenuEnableTask`
- `0x81cf6`: `MenuEnableTask`

## pseudocode

```c

```

## disassembly

```asm
0x818a0  ldarg.0
0x818a1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x818a6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x818ab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Clear()
0x818b0  ldarg.1
0x818b1  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x818b6  ldc.i4.1
0x818b7  bne.un   loc_81BAE
0x818bc  ldarg.1
0x818bd  ldc.i4.0
0x818be  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x818c3  castclass Microsoft.Windows.ManagementUI.CombinedControls.UITask
0x818c8  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_IsEnabled()
0x818cd  brfalse  loc_81A81
0x818d2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x818d7  stloc.0
0x818d8  ldloc.0
0x818d9  ldstr    aMenuruntask// "MenuRunTask"
0x818de  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x818e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x818e8  ldloc.0
0x818e9  ldc.i4.0
0x818ea  box      ListItemContextMenuItemTag
0x818ef  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x818f4  ldloc.0
0x818f5  ldarg.0
0x818f6  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::RunMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x818fc  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81901  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81906  ldarg.0
0x81907  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x8190c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81911  ldloc.0
0x81912  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81917  pop
0x81918  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x8191d  stloc.1
0x8191e  ldloc.1
0x8191f  ldstr    aMenuendtask// "MenuEndTask"
0x81924  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81929  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x8192e  ldloc.1
0x8192f  ldc.i4.0
0x81930  box      ListItemContextMenuItemTag
0x81935  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x8193a  ldloc.1
0x8193b  ldarg.0
0x8193c  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::EndMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81942  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81947  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x8194c  ldarg.0
0x8194d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x81952  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81957  ldloc.1
0x81958  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x8195d  pop
0x8195e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x81963  stloc.2
0x81964  ldloc.2
0x81965  ldstr    aMenudisabletas// "MenuDisableTask"
0x8196a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x8196f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81974  ldloc.2
0x81975  ldc.i4.3
0x81976  box      ListItemContextMenuItemTag
0x8197b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81980  ldloc.2
0x81981  ldarg.0
0x81982  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::DisableMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81988  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8198d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81992  ldarg.0
0x81993  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x81998  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x8199d  ldloc.2
0x8199e  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x819a3  pop
0x819a4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x819a9  stloc.3
0x819aa  ldloc.3
0x819ab  ldstr    aMenuexporttask// "MenuExportTask"
0x819b0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x819b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x819ba  ldloc.3
0x819bb  ldc.i4.1
0x819bc  box      ListItemContextMenuItemTag
0x819c1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x819c6  ldloc.3
0x819c7  ldarg.0
0x819c8  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ExportMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x819ce  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x819d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x819d8  ldarg.0
0x819d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x819de  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x819e3  ldloc.3
0x819e4  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x819e9  pop
0x819ea  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x819ef  stloc.s  4
0x819f1  ldloc.s  4
0x819f3  ldstr    aMenuproperties// "MenuProperties"
0x819f8  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x819fd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81a02  ldloc.s  4
0x81a04  ldc.i4.0
0x81a05  box      ListItemContextMenuItemTag
0x81a0a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81a0f  ldloc.s  4
0x81a11  ldarg.0
0x81a12  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::PropertiesMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81a18  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81a1d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81a22  ldarg.0
0x81a23  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x81a28  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81a2d  ldloc.s  4
0x81a2f  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81a34  pop
0x81a35  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x81a3a  stloc.s  5
0x81a3c  ldloc.s  5
0x81a3e  ldstr    aMenudeletetask// "MenuDeleteTask"
0x81a43  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81a48  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81a4d  ldloc.s  5
0x81a4f  ldc.i4.1
0x81a50  box      ListItemContextMenuItemTag
0x81a55  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81a5a  ldloc.s  5
0x81a5c  ldarg.0
0x81a5d  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::DeleteMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81a63  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81a68  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81a6d  ldarg.0
0x81a6e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x81a73  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81a78  ldloc.s  5
0x81a7a  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81a7f  pop
0x81a80  ret
0x81a81  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x81a86  stloc.s  6
0x81a88  ldloc.s  6
0x81a8a  ldstr    aMenuenabletask// "MenuEnableTask"
0x81a8f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81a94  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81a99  ldloc.s  6
0x81a9b  ldc.i4.2
0x81a9c  box      ListItemContextMenuItemTag
0x81aa1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81aa6  ldloc.s  6
0x81aa8  ldarg.0
0x81aa9  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::EnableMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81aaf  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81ab4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81ab9  ldarg.0
0x81aba  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x81abf  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81ac4  ldloc.s  6
0x81ac6  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81acb  pop
0x81acc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x81ad1  stloc.s  7
0x81ad3  ldloc.s  7
0x81ad5  ldstr    aMenuexporttask// "MenuExportTask"
0x81ada  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81adf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81ae4  ldloc.s  7
0x81ae6  ldc.i4.1
0x81ae7  box      ListItemContextMenuItemTag
0x81aec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81af1  ldloc.s  7
0x81af3  ldarg.0
0x81af4  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ExportMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81afa  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81aff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81b04  ldarg.0
0x81b05  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x81b0a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81b0f  ldloc.s  7
0x81b11  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81b16  pop
0x81b17  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x81b1c  stloc.s  8
0x81b1e  ldloc.s  8
0x81b20  ldstr    aMenuproperties// "MenuProperties"
0x81b25  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81b2a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81b2f  ldloc.s  8
0x81b31  ldc.i4.0
0x81b32  box      ListItemContextMenuItemTag
0x81b37  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81b3c  ldloc.s  8
0x81b3e  ldarg.0
0x81b3f  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::PropertiesMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81b45  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81b4a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81b4f  ldarg.0
0x81b50  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x81b55  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81b5a  ldloc.s  8
0x81b5c  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81b61  pop
0x81b62  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x81b67  stloc.s  9
0x81b69  ldloc.s  9
0x81b6b  ldstr    aMenudeletetask// "MenuDeleteTask"
0x81b70  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81b75  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81b7a  ldloc.s  9
0x81b7c  ldc.i4.1
0x81b7d  box      ListItemContextMenuItemTag
0x81b82  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81b87  ldloc.s  9
0x81b89  ldarg.0
0x81b8a  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::DeleteMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81b90  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81b95  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81b9a  ldarg.0
0x81b9b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x81ba0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81ba5  ldloc.s  9
0x81ba7  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81bac  pop
0x81bad  ret
0x81bae  ldarg.1
0x81baf  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x81bb4  ldc.i4.1
0x81bb5  ble      loc_81D83
0x81bba  ldc.i4.1
0x81bbb  stloc.s  0xA
0x81bbd  ldarg.1
0x81bbe  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x81bc3  stloc.s  0xC
0x81bc5  br.s     loc_81BDF
0x81bc7  ldloc.s  0xC
0x81bc9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x81bce  castclass Microsoft.Windows.ManagementUI.CombinedControls.UITask
0x81bd3  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_IsEnabled()
0x81bd8  brtrue.s loc_81BDF
0x81bda  ldc.i4.0
0x81bdb  stloc.s  0xA
0x81bdd  leave.s  loc_81BFF
0x81bdf  ldloc.s  0xC
0x81be1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x81be6  brtrue.s loc_81BC7
0x81be8  leave.s  loc_81BFF
0x81bea  ldloc.s  0xC
0x81bec  isinst   [mscorlib]System.IDisposable
0x81bf1  stloc.s  0xD
0x81bf3  ldloc.s  0xD
0x81bf5  brfalse.s loc_81BFE
0x81bf7  ldloc.s  0xD
0x81bf9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x81bfe  endfinally
0x81bff  ldloc.s  0xA
0x81c01  brfalse  loc_81C9C
0x81c06  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x81c0b  stloc.s  0xE
0x81c0d  ldloc.s  0xE
0x81c0f  ldstr    aMenuruntask// "MenuRunTask"
0x81c14  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81c19  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81c1e  ldloc.s  0xE
0x81c20  ldc.i4.0
0x81c21  box      ListItemContextMenuItemTag
0x81c26  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81c2b  ldloc.s  0xE
0x81c2d  ldarg.0
0x81c2e  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::RunMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81c34  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81c39  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81c3e  ldarg.0
0x81c3f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x81c44  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81c49  ldloc.s  0xE
0x81c4b  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81c50  pop
0x81c51  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x81c56  stloc.s  0xF
0x81c58  ldloc.s  0xF
0x81c5a  ldstr    aMenuendtask// "MenuEndTask"
0x81c5f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81c64  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81c69  ldloc.s  0xF
0x81c6b  ldc.i4.0
0x81c6c  box      ListItemContextMenuItemTag
0x81c71  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81c76  ldloc.s  0xF
0x81c78  ldarg.0
0x81c79  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::EndMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81c7f  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81c84  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81c89  ldarg.0
0x81c8a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuForListItem
0x81c8f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81c94  ldloc.s  0xF
0x81c96  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81c9b  pop
  ... truncated ...
```
