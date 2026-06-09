# UserControlDesignerHost::System.ComponentModel.IContainer.Add_0

- ea: `0xf1160`
- end: `0xf1262`
- name: `UserControlDesignerHost::System.ComponentModel.IContainer.Add_0`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x8ef40`
- `0xf0f30`
- `0xf0f40`
- `0xf1160`
- `0xf1890`

## string_xrefs

- `0xf1163`: `component`
- `0xf11f2`: `UserControlDesignerHost_ComponentAlreadyExists`

## pseudocode

```c

```

## disassembly

```asm
0xf1160  ldarg.1
0xf1161  brtrue.s loc_F116E
0xf1163  ldstr    aComponent// "component"
0xf1168  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf116d  throw
0xf116e  ldarg.1
0xf116f  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xf1174  brtrue.s loc_F11CF
0xf1176  ldarg.1
0xf1177  ldarg.1
0xf1178  ldarg.0
0xf1179  newobj   instance void DummySite::.ctor(class [System]System.ComponentModel.IComponent component, class UserControlDesignerHost designerHost)
0xf117e  callvirt instance void [System]System.ComponentModel.IComponent::set_Site(class [System]System.ComponentModel.ISite)
0xf1183  ldarg.1
0xf1184  isinst   [System.Web]System.Web.UI.Control
0xf1189  brfalse.s loc_F11A3
0xf118b  ldarg.1
0xf118c  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xf1191  ldarg.1
0xf1192  castclass [System.Web]System.Web.UI.Control
0xf1197  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xf119c  callvirt instance void [System]System.ComponentModel.ISite::set_Name(string)
0xf11a1  br.s     loc_F11CF
0xf11a3  ldarg.1
0xf11a4  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xf11a9  ldstr    aTemp_0// "Temp"
0xf11ae  ldarg.0
0xf11af  ldarg.0
0xf11b0  ldfld    int32 UserControlDesignerHost::_nameCounter
0xf11b5  stloc.1
0xf11b6  ldloc.1
0xf11b7  ldc.i4.1
0xf11b8  add
0xf11b9  stfld    int32 UserControlDesignerHost::_nameCounter
0xf11be  ldloca.s 1
0xf11c0  call     instance string [mscorlib]System.Int32::ToString()
0xf11c5  call     string [mscorlib]System.String::Concat(string, string)
0xf11ca  callvirt instance void [System]System.ComponentModel.ISite::set_Name(string)
0xf11cf  ldarg.2
0xf11d0  brtrue.s loc_F11DF
0xf11d2  ldarg.1
0xf11d3  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xf11d8  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0xf11dd  starg.s  2
0xf11df  ldarg.0
0xf11e0  call     instance class [mscorlib]System.Collections.Hashtable UserControlDesignerHost::get_ComponentTable()
0xf11e5  ldarg.2
0xf11e6  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xf11eb  brfalse.s loc_F1211
0xf11ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf11f2  ldstr    aUsercontroldes_5// "UserControlDesignerHost_ComponentAlread"...
0xf11f7  call     string System.Design.SR::GetString(string name)
0xf11fc  ldc.i4.1
0xf11fd  newarr   [mscorlib]System.Object
0xf1202  dup
0xf1203  ldc.i4.0
0xf1204  ldarg.2
0xf1205  stelem.ref
0xf1206  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf120b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xf1210  throw
0xf1211  ldarg.0
0xf1212  call     instance class [mscorlib]System.Collections.Hashtable UserControlDesignerHost::get_ComponentTable()
0xf1217  ldarg.2
0xf1218  ldarg.1
0xf1219  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0xf121e  ldarg.1
0xf121f  ldtoken  [System]System.ComponentModel.Design.IDesigner
0xf1224  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf1229  call     class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.TypeDescriptor::CreateDesigner(class [System]System.ComponentModel.IComponent, class [mscorlib]System.Type)
0xf122e  stloc.0
0xf122f  ldloc.0
0xf1230  ldarg.1
0xf1231  callvirt instance void [System]System.ComponentModel.Design.IDesigner::Initialize(class [System]System.ComponentModel.IComponent)
0xf1236  ldarg.0
0xf1237  call     instance class [mscorlib]System.Collections.Hashtable UserControlDesignerHost::get_DesignerTable()
0xf123c  ldarg.1
0xf123d  ldloc.0
0xf123e  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0xf1243  ldarg.1
0xf1244  isinst   [System.Web]System.Web.UI.Control
0xf1249  brfalse.s loc_F1261
0xf124b  ldarg.1
0xf124c  castclass [System.Web]System.Web.UI.Control
0xf1251  ldarg.0
0xf1252  ldfld    class [System]System.ComponentModel.IComponent UserControlDesignerHost::_rootComponent
0xf1257  castclass [System.Web]System.Web.UI.Page
0xf125c  callvirt instance void [System.Web]System.Web.UI.Control::set_Page(class [System.Web]System.Web.UI.Page)
0xf1261  ret
```
