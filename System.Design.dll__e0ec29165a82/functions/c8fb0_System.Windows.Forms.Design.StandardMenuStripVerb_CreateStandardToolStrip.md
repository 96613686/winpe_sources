# System.Windows.Forms.Design.StandardMenuStripVerb::CreateStandardToolStrip

- ea: `0xc8fb0`
- end: `0xc93bf`
- name: `System.Windows.Forms.Design.StandardMenuStripVerb::CreateStandardToolStrip`
- size: `1039`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0xc8860`

## callees

- `0x584f0`
- `0x58af0`
- `0x5b990`
- `0x8ef40`
- `0xc8fb0`
- `0xc93c0`
- `0xc9520`
- `0xec590`

## string_xrefs

- `0xc9002`: `StandardMenuCopy`
- `0xc8fc6`: `StandardMenuOpen`
- `0xc90a0`: `StandardMenuCreateDesc`

## pseudocode

```c

```

## disassembly

```asm
0xc8fb0  ldc.i4.s 0xA
0xc8fb2  newarr   [mscorlib]System.String
0xc8fb7  dup
0xc8fb8  ldc.i4.0
0xc8fb9  ldstr    aStandardmenune// "StandardMenuNew"
0xc8fbe  call     string System.Design.SR::GetString(string name)
0xc8fc3  stelem.ref
0xc8fc4  dup
0xc8fc5  ldc.i4.1
0xc8fc6  ldstr    aStandardmenuop// "StandardMenuOpen"
0xc8fcb  call     string System.Design.SR::GetString(string name)
0xc8fd0  stelem.ref
0xc8fd1  dup
0xc8fd2  ldc.i4.2
0xc8fd3  ldstr    aStandardmenusa// "StandardMenuSave"
0xc8fd8  call     string System.Design.SR::GetString(string name)
0xc8fdd  stelem.ref
0xc8fde  dup
0xc8fdf  ldc.i4.3
0xc8fe0  ldstr    aStandardmenupr// "StandardMenuPrint"
0xc8fe5  call     string System.Design.SR::GetString(string name)
0xc8fea  stelem.ref
0xc8feb  dup
0xc8fec  ldc.i4.4
0xc8fed  ldstr    asc_12DF04// "-"
0xc8ff2  stelem.ref
0xc8ff3  dup
0xc8ff4  ldc.i4.5
0xc8ff5  ldstr    aStandardtoolcu// "StandardToolCut"
0xc8ffa  call     string System.Design.SR::GetString(string name)
0xc8fff  stelem.ref
0xc9000  dup
0xc9001  ldc.i4.6
0xc9002  ldstr    aStandardmenuco// "StandardMenuCopy"
0xc9007  call     string System.Design.SR::GetString(string name)
0xc900c  stelem.ref
0xc900d  dup
0xc900e  ldc.i4.7
0xc900f  ldstr    aStandardmenupa// "StandardMenuPaste"
0xc9014  call     string System.Design.SR::GetString(string name)
0xc9019  stelem.ref
0xc901a  dup
0xc901b  ldc.i4.8
0xc901c  ldstr    asc_12DF04// "-"
0xc9021  stelem.ref
0xc9022  dup
0xc9023  ldc.i4.s 9
0xc9025  ldstr    aStandardtoolhe// "StandardToolHelp"
0xc902a  call     string System.Design.SR::GetString(string name)
0xc902f  stelem.ref
0xc9030  stloc.0
0xc9031  ldc.i4.s 0xA
0xc9033  newarr   [mscorlib]System.String
0xc9038  dup
0xc9039  ldc.i4.0
0xc903a  ldstr    aNew_0// "new"
0xc903f  stelem.ref
0xc9040  dup
0xc9041  ldc.i4.1
0xc9042  ldstr    aOpen_0// "open"
0xc9047  stelem.ref
0xc9048  dup
0xc9049  ldc.i4.2
0xc904a  ldstr    aSave// "save"
0xc904f  stelem.ref
0xc9050  dup
0xc9051  ldc.i4.3
0xc9052  ldstr    aPrint// "print"
0xc9057  stelem.ref
0xc9058  dup
0xc9059  ldc.i4.4
0xc905a  ldstr    asc_12DF04// "-"
0xc905f  stelem.ref
0xc9060  dup
0xc9061  ldc.i4.5
0xc9062  ldstr    aCut// "cut"
0xc9067  stelem.ref
0xc9068  dup
0xc9069  ldc.i4.6
0xc906a  ldstr    aCopy// "copy"
0xc906f  stelem.ref
0xc9070  dup
0xc9071  ldc.i4.7
0xc9072  ldstr    aPaste// "paste"
0xc9077  stelem.ref
0xc9078  dup
0xc9079  ldc.i4.8
0xc907a  ldstr    asc_12DF04// "-"
0xc907f  stelem.ref
0xc9080  dup
0xc9081  ldc.i4.s 9
0xc9083  ldstr    aHelp// "help"
0xc9088  stelem.ref
0xc9089  stloc.1
0xc908a  ldarg.1
0xc908b  brtrue.s loc_C908E
0xc908d  ret
0xc908e  ldarg.2
0xc908f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xc9094  ldc.i4.0
0xc9095  stsfld   bool System.Windows.Forms.Design.ToolStripDesigner::_autoAddNewItems
0xc909a  ldarg.0
0xc909b  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.StandardMenuStripVerb::_host
0xc90a0  ldstr    aStandardmenucr// "StandardMenuCreateDesc"
0xc90a5  call     string System.Design.SR::GetString(string name)
0xc90aa  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xc90af  stloc.2
0xc90b0  ldarg.0
0xc90b1  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.StandardMenuStripVerb::_provider
0xc90b6  ldtoken  [System]System.ComponentModel.Design.Serialization.INameCreationService
0xc90bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc90c0  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xc90c5  castclass [System]System.ComponentModel.Design.Serialization.INameCreationService
0xc90ca  stloc.3
0xc90cb  ldstr    aStandardmainto// "standardMainToolStrip"
0xc90d0  stloc.s  4
0xc90d2  ldloc.s  4
0xc90d4  stloc.s  5
0xc90d6  ldc.i4.1
0xc90d7  stloc.s  6
0xc90d9  ldarg.1
0xc90da  brfalse.s loc_C9115
0xc90dc  br.s     loc_C90FC
0xc90de  ldloc.s  4
0xc90e0  ldloc.s  6
0xc90e2  dup
0xc90e3  ldc.i4.1
0xc90e4  add
0xc90e5  stloc.s  6
0xc90e7  stloc.s  9
0xc90e9  ldloca.s 9
0xc90eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc90f0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc90f5  call     string [mscorlib]System.String::Concat(string, string)
0xc90fa  stloc.s  5
0xc90fc  ldarg.0
0xc90fd  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.StandardMenuStripVerb::_host
0xc9102  callvirt instance class [System]System.ComponentModel.IContainer [System]System.ComponentModel.Design.IDesignerHost::get_Container()
0xc9107  callvirt instance class [System]System.ComponentModel.ComponentCollection [System]System.ComponentModel.IContainer::get_Components()
0xc910c  ldloc.s  5
0xc910e  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.ComponentCollection::get_Item(string)
0xc9113  brtrue.s loc_C90DE
0xc9115  ldc.i4.0
0xc9116  stloc.s  7
0xc9118  ldloc.0
0xc9119  stloc.s  0xA
0xc911b  ldc.i4.0
0xc911c  stloc.s  0xB
0xc911e  br       loc_C9291
0xc9123  ldloc.s  0xA
0xc9125  ldloc.s  0xB
0xc9127  ldelem.ref
0xc9128  stloc.s  0xC
0xc912a  ldnull
0xc912b  stloc.s  5
0xc912d  ldstr    aToolstripbutto// "ToolStripButton"
0xc9132  stloc.s  4
0xc9134  ldarg.0
0xc9135  ldloc.s  0xC
0xc9137  ldtoken  [System.Windows.Forms]System.Windows.Forms.ToolStripButton
0xc913c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc9141  ldloc.3
0xc9142  ldc.i4.1
0xc9143  call     instance string System.Windows.Forms.Design.StandardMenuStripVerb::NameFromText(string text, class [mscorlib]System.Type itemType, class [System]System.ComponentModel.Design.Serialization.INameCreationService nameCreationService, bool adjustCapitalization)
0xc9148  stloc.s  5
0xc914a  ldnull
0xc914b  stloc.s  0xD
0xc914d  ldloc.s  5
0xc914f  ldstr    aSeparator// "Separator"
0xc9154  callvirt instance bool [mscorlib]System.String::Contains(string)
0xc9159  brfalse.s loc_C91A6
0xc915b  ldarg.0
0xc915c  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.StandardMenuStripVerb::_host
0xc9161  ldtoken  [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator
0xc9166  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc916b  ldloc.s  5
0xc916d  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.IDesignerHost::CreateComponent(class [mscorlib]System.Type, string)
0xc9172  castclass [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator
0xc9177  stloc.s  0xD
0xc9179  ldarg.0
0xc917a  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.StandardMenuStripVerb::_host
0xc917f  ldloc.s  0xD
0xc9181  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0xc9186  stloc.s  0xE
0xc9188  ldloc.s  0xE
0xc918a  isinst   System.ComponentModel.Design.ComponentDesigner
0xc918f  brfalse  loc_C9277
0xc9194  ldloc.s  0xE
0xc9196  castclass System.ComponentModel.Design.ComponentDesigner
0xc919b  ldnull
0xc919c  callvirt instance void System.ComponentModel.Design.ComponentDesigner::InitializeNewComponent(class [mscorlib]System.Collections.IDictionary defaultValues)
0xc91a1  br       loc_C9277
0xc91a6  ldarg.0
0xc91a7  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.StandardMenuStripVerb::_host
0xc91ac  ldtoken  [System.Windows.Forms]System.Windows.Forms.ToolStripButton
0xc91b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc91b6  ldloc.s  5
0xc91b8  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.IDesignerHost::CreateComponent(class [mscorlib]System.Type, string)
0xc91bd  castclass [System.Windows.Forms]System.Windows.Forms.ToolStripButton
0xc91c2  stloc.s  0xD
0xc91c4  ldarg.0
0xc91c5  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.StandardMenuStripVerb::_host
0xc91ca  ldloc.s  0xD
0xc91cc  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0xc91d1  stloc.s  0xF
0xc91d3  ldloc.s  0xF
0xc91d5  isinst   System.ComponentModel.Design.ComponentDesigner
0xc91da  brfalse.s loc_C91E9
0xc91dc  ldloc.s  0xF
0xc91de  castclass System.ComponentModel.Design.ComponentDesigner
0xc91e3  ldnull
0xc91e4  callvirt instance void System.ComponentModel.Design.ComponentDesigner::InitializeNewComponent(class [mscorlib]System.Collections.IDictionary defaultValues)
0xc91e9  ldloc.s  0xD
0xc91eb  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xc91f0  ldstr    aDisplaystyle// "DisplayStyle"
0xc91f5  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xc91fa  stloc.s  0x10
0xc91fc  ldloc.s  0x10
0xc91fe  brfalse.s loc_C920F
0xc9200  ldloc.s  0x10
0xc9202  ldloc.s  0xD
0xc9204  ldc.i4.2
0xc9205  box      [System.Windows.Forms]System.Windows.Forms.ToolStripItemDisplayStyle
0xc920a  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0xc920f  ldloc.s  0xD
0xc9211  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xc9216  ldstr    aText_0// "Text"
0xc921b  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xc9220  stloc.s  0x11
0xc9222  ldloc.s  0x11
0xc9224  brfalse.s loc_C9231
0xc9226  ldloc.s  0x11
0xc9228  ldloc.s  0xD
0xc922a  ldloc.s  0xC
0xc922c  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0xc9231  ldnull
0xc9232  stloc.s  0x12
0xc9234  ldarg.0
0xc9235  ldloc.1
0xc9236  ldloc.s  7
0xc9238  ldelem.ref
0xc9239  call     instance class [System.Drawing]System.Drawing.Bitmap System.Windows.Forms.Design.StandardMenuStripVerb::GetImage(string name)
0xc923e  stloc.s  0x12
0xc9240  leave.s  loc_C9245
0xc9242  pop
0xc9243  leave.s  loc_C9245
0xc9245  ldloc.s  0x12
0xc9247  brfalse.s loc_C9277
0xc9249  ldloc.s  0xD
0xc924b  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xc9250  ldstr    aImage// "Image"
0xc9255  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xc925a  stloc.s  0x13
0xc925c  ldloc.s  0x13
0xc925e  brfalse.s loc_C926B
0xc9260  ldloc.s  0x13
0xc9262  ldloc.s  0xD
0xc9264  ldloc.s  0x12
0xc9266  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0xc926b  ldloc.s  0xD
0xc926d  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::get_Magenta()
0xc9272  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_ImageTransparentColor(valuetype [System.Drawing]System.Drawing.Color)
0xc9277  ldarg.2
0xc9278  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xc927d  ldloc.s  0xD
0xc927f  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem)
0xc9284  pop
0xc9285  ldloc.s  7
0xc9287  ldc.i4.1
0xc9288  add
0xc9289  stloc.s  7
0xc928b  ldloc.s  0xB
0xc928d  ldc.i4.1
0xc928e  add
0xc928f  stloc.s  0xB
0xc9291  ldloc.s  0xB
0xc9293  ldloc.s  0xA
0xc9295  ldlen
0xc9296  conv.i4
0xc9297  blt      loc_C9123
0xc929c  ldarg.2
0xc929d  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xc92a2  ldstr    aItems// "Items"
0xc92a7  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xc92ac  stloc.s  8
0xc92ae  ldarg.0
0xc92af  ldfld    class [System]System.ComponentModel.Design.IComponentChangeService System.Windows.Forms.Design.StandardMenuStripVerb::componentChangeSvc
0xc92b4  ldarg.2
0xc92b5  ldloc.s  8
0xc92b7  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0xc92bc  ldarg.0
0xc92bd  ldfld    class [System]System.ComponentModel.Design.IComponentChangeService System.Windows.Forms.Design.StandardMenuStripVerb::componentChangeSvc
0xc92c2  ldarg.2
0xc92c3  ldloc.s  8
0xc92c5  ldnull
0xc92c6  ldnull
0xc92c7  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0xc92cc  leave    loc_C93BE
0xc92d1  stloc.s  0x14
0xc92d3  ldloc.s  0x14
  ... truncated ...
```
