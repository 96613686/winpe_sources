# Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::InitializeGeneraltItemContextMenu

- ea: `0x81d90`
- end: `0x81ed9`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::InitializeGeneraltItemContextMenu`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x80490`

## callees

- `0x12ed0`

## string_xrefs

- `0x81ddb`: `MenuCreateNewTask`
- `0x81e0f`: `TaskSchedulerContextMenuImportTask`

## pseudocode

```c

```

## disassembly

```asm
0x81d90  ldarg.0
0x81d91  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuGeneralItems
0x81d96  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81d9b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Clear()
0x81da0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x81da5  stloc.0
0x81da6  ldloc.0
0x81da7  ldstr    aMenurunwizard// "MenuRunWizard"
0x81dac  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81db1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81db6  ldloc.0
0x81db7  ldc.i4.0
0x81db8  box      GeneralItemContextMenuItemTag
0x81dbd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81dc2  ldloc.0
0x81dc3  ldarg.0
0x81dc4  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::RunWizardMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81dca  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81dcf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81dd4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x81dd9  stloc.1
0x81dda  ldloc.1
0x81ddb  ldstr    aMenucreatenewt// "MenuCreateNewTask"
0x81de0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81de5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81dea  ldloc.1
0x81deb  ldc.i4.1
0x81dec  box      GeneralItemContextMenuItemTag
0x81df1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81df6  ldloc.1
0x81df7  ldarg.0
0x81df8  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::CreateNewTaskMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81dfe  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81e03  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81e08  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x81e0d  stloc.2
0x81e0e  ldloc.2
0x81e0f  ldstr    aTaskschedulerc// "TaskSchedulerContextMenuImportTask"
0x81e14  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81e19  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81e1e  ldloc.2
0x81e1f  ldc.i4.2
0x81e20  box      GeneralItemContextMenuItemTag
0x81e25  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81e2a  ldloc.2
0x81e2b  ldarg.0
0x81e2c  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ImportTaskMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81e32  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81e37  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81e3c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0x81e41  stloc.3
0x81e42  ldloc.3
0x81e43  ldstr    aMenurefresh// "MenuRefresh"
0x81e48  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81e4d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0x81e52  ldloc.3
0x81e53  ldc.i4.3
0x81e54  box      GeneralItemContextMenuItemTag
0x81e59  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0x81e5e  ldloc.3
0x81e5f  ldarg.0
0x81e60  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::RefreshTaskMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0x81e66  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81e6b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0x81e70  ldarg.0
0x81e71  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuGeneralItems
0x81e76  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81e7b  ldloc.0
0x81e7c  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81e81  pop
0x81e82  ldarg.0
0x81e83  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuGeneralItems
0x81e88  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81e8d  ldloc.1
0x81e8e  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81e93  pop
0x81e94  ldarg.0
0x81e95  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuGeneralItems
0x81e9a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81e9f  ldloc.2
0x81ea0  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81ea5  pop
0x81ea6  ldarg.0
0x81ea7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuGeneralItems
0x81eac  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81eb1  ldstr    aDashcharacter// "DashCharacter"
0x81eb6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x81ebb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor(string)
0x81ec0  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81ec5  pop
0x81ec6  ldarg.0
0x81ec7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ctxMenuGeneralItems
0x81ecc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0x81ed1  ldloc.3
0x81ed2  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0x81ed7  pop
0x81ed8  ret
```
