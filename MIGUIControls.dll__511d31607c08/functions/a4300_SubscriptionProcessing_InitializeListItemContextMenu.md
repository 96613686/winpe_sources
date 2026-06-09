# SubscriptionProcessing::InitializeListItemContextMenu

- ea: `0xa4300`
- end: `0xa4593`
- name: `SubscriptionProcessing::InitializeListItemContextMenu`
- size: `659`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0xa3780`
- `0xa4d80`
- `0xa57d0`

## callees

- `0x12ed0`
- `0x37120`
- `0x37140`
- `0x37810`
- `0xa4300`

## string_xrefs

- `0xa4424`: `MenuDisableTask`
- `0xa43c9`: `MenuDeleteTask`
- `0xa452f`: `MenuEnableTask`

## pseudocode

```c

```

## disassembly

```asm
0xa4300  ldarg.0
0xa4301  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu SubscriptionProcessing::ctxMenuForListItem
0xa4306  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0xa430b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Clear()
0xa4310  ldarg.0
0xa4311  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions SubscriptionProcessing::actions
0xa4316  callvirt instance class [mscorlib]System.Collections.ICollection Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::get_Actions()
0xa431b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xa4320  stloc.0
0xa4321  br       loc_A4571
0xa4326  ldloc.0
0xa4327  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa432c  castclass Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction
0xa4331  stloc.1
0xa4332  ldloc.1
0xa4333  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0xa4338  stloc.2
0xa4339  ldloc.2
0xa433a  ldc.i4.s 0x27
0xa433c  sub
0xa433d  switch   loc_A435F, loc_A43B5, loc_A451E, loc_A4410, loc_A446B, loc_A44C6
0xa435a  br       loc_A4571
0xa435f  ldloc.1
0xa4360  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0xa4365  brtrue   loc_A4571
0xa436a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0xa436f  stloc.3
0xa4370  ldloc.3
0xa4371  ldstr    aMenuproperties// "MenuProperties"
0xa4376  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa437b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0xa4380  ldloc.3
0xa4381  ldc.i4.0
0xa4382  box      ListItemContextMenuItemTag
0xa4387  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0xa438c  ldloc.3
0xa438d  ldarg.0
0xa438e  ldftn    instance void SubscriptionProcessing::PropertiesMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0xa4394  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa4399  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0xa439e  ldarg.0
0xa439f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu SubscriptionProcessing::ctxMenuForListItem
0xa43a4  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0xa43a9  ldloc.3
0xa43aa  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0xa43af  pop
0xa43b0  br       loc_A4571
0xa43b5  ldloc.1
0xa43b6  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0xa43bb  brtrue   loc_A4571
0xa43c0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0xa43c5  stloc.s  4
0xa43c7  ldloc.s  4
0xa43c9  ldstr    aMenudeletetask// "MenuDeleteTask"
0xa43ce  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa43d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0xa43d8  ldloc.s  4
0xa43da  ldc.i4.1
0xa43db  box      ListItemContextMenuItemTag
0xa43e0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0xa43e5  ldloc.s  4
0xa43e7  ldarg.0
0xa43e8  ldftn    instance void SubscriptionProcessing::DeleteMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0xa43ee  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa43f3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0xa43f8  ldarg.0
0xa43f9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu SubscriptionProcessing::ctxMenuForListItem
0xa43fe  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0xa4403  ldloc.s  4
0xa4405  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0xa440a  pop
0xa440b  br       loc_A4571
0xa4410  ldloc.1
0xa4411  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0xa4416  brtrue   loc_A4571
0xa441b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0xa4420  stloc.s  5
0xa4422  ldloc.s  5
0xa4424  ldstr    aMenudisabletas// "MenuDisableTask"
0xa4429  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa442e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0xa4433  ldloc.s  5
0xa4435  ldc.i4.3
0xa4436  box      ListItemContextMenuItemTag
0xa443b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0xa4440  ldloc.s  5
0xa4442  ldarg.0
0xa4443  ldftn    instance void SubscriptionProcessing::DisableMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0xa4449  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa444e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0xa4453  ldarg.0
0xa4454  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu SubscriptionProcessing::ctxMenuForListItem
0xa4459  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0xa445e  ldloc.s  5
0xa4460  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0xa4465  pop
0xa4466  br       loc_A4571
0xa446b  ldloc.1
0xa446c  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0xa4471  brtrue   loc_A4571
0xa4476  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0xa447b  stloc.s  6
0xa447d  ldloc.s  6
0xa447f  ldstr    aSubscriptionpr_6// "SubscriptionPropertiesDialogRetryButton"
0xa4484  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa4489  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0xa448e  ldloc.s  6
0xa4490  ldc.i4.6
0xa4491  box      ListItemContextMenuItemTag
0xa4496  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0xa449b  ldloc.s  6
0xa449d  ldarg.0
0xa449e  ldftn    instance void SubscriptionProcessing::RetryMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0xa44a4  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa44a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0xa44ae  ldarg.0
0xa44af  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu SubscriptionProcessing::ctxMenuForListItem
0xa44b4  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0xa44b9  ldloc.s  6
0xa44bb  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0xa44c0  pop
0xa44c1  br       loc_A4571
0xa44c6  ldloc.1
0xa44c7  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0xa44cc  brtrue   loc_A4571
0xa44d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0xa44d6  stloc.s  7
0xa44d8  ldloc.s  7
0xa44da  ldstr    aSubscriptionst_10// "SubscriptionStatus"
0xa44df  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa44e4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0xa44e9  ldloc.s  7
0xa44eb  ldc.i4.7
0xa44ec  box      ListItemContextMenuItemTag
0xa44f1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0xa44f6  ldloc.s  7
0xa44f8  ldarg.0
0xa44f9  ldftn    instance void SubscriptionProcessing::StatusMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0xa44ff  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa4504  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0xa4509  ldarg.0
0xa450a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu SubscriptionProcessing::ctxMenuForListItem
0xa450f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0xa4514  ldloc.s  7
0xa4516  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0xa451b  pop
0xa451c  br.s     loc_A4571
0xa451e  ldloc.1
0xa451f  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0xa4524  brtrue.s loc_A4571
0xa4526  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::.ctor()
0xa452b  stloc.s  8
0xa452d  ldloc.s  8
0xa452f  ldstr    aMenuenabletask// "MenuEnableTask"
0xa4534  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa4539  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::set_Text(string)
0xa453e  ldloc.s  8
0xa4540  ldc.i4.2
0xa4541  box      ListItemContextMenuItemTag
0xa4546  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Menu::set_Tag(object)
0xa454b  ldloc.s  8
0xa454d  ldarg.0
0xa454e  ldftn    instance void SubscriptionProcessing::EnableMenuHandler(object sender, class [mscorlib]System.EventArgs e)
0xa4554  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa4559  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MenuItem::add_Click(class [mscorlib]System.EventHandler)
0xa455e  ldarg.0
0xa455f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenu SubscriptionProcessing::ctxMenuForListItem
0xa4564  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection [System.Windows.Forms]System.Windows.Forms.Menu::get_MenuItems()
0xa4569  ldloc.s  8
0xa456b  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Menu/MenuItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.MenuItem)
0xa4570  pop
0xa4571  ldloc.0
0xa4572  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa4577  brtrue   loc_A4326
0xa457c  leave.s  loc_A4592
0xa457e  ldloc.0
0xa457f  isinst   [mscorlib]System.IDisposable
0xa4584  stloc.s  9
0xa4586  ldloc.s  9
0xa4588  brfalse.s loc_A4591
0xa458a  ldloc.s  9
0xa458c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa4591  endfinally
0xa4592  ret
```
