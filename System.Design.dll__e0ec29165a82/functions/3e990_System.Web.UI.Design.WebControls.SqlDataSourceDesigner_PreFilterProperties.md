# System.Web.UI.Design.WebControls.SqlDataSourceDesigner::PreFilterProperties

- ea: `0x3e990`
- end: `0x3eb1f`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceDesigner::PreFilterProperties`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x13fb0`

## callees

- `0x33d0`
- `0x3e990`

## string_xrefs

- `0x3e9e1`: `DeleteQuery`
- `0x3e9ec`: `DeleteQuery`
- `0x3ea62`: `UpdateQuery`
- `0x3ea6d`: `UpdateQuery`
- `0x3eae9`: `SelectCommand`
- `0x3eafa`: `SelectCommand`

## pseudocode

```c

```

## disassembly

```asm
0x3e990  ldarg.0
0x3e991  ldarg.1
0x3e992  call     instance void System.Web.UI.Design.ControlDesigner::PreFilterProperties(class [mscorlib]System.Collections.IDictionary properties)
0x3e997  ldsfld   string[] System.Web.UI.Design.WebControls.SqlDataSourceDesigner::_hiddenProperties
0x3e99c  stloc.1
0x3e99d  ldc.i4.0
0x3e99e  stloc.2
0x3e99f  br.s     loc_3E9DA
0x3e9a1  ldloc.1
0x3e9a2  ldloc.2
0x3e9a3  ldelem.ref
0x3e9a4  stloc.3
0x3e9a5  ldarg.1
0x3e9a6  ldloc.3
0x3e9a7  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x3e9ac  castclass [System]System.ComponentModel.PropertyDescriptor
0x3e9b1  stloc.0
0x3e9b2  ldloc.0
0x3e9b3  brfalse.s loc_3E9D6
0x3e9b5  ldarg.1
0x3e9b6  ldloc.3
0x3e9b7  ldloc.0
0x3e9b8  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.PropertyDescriptor::get_ComponentType()
0x3e9bd  ldloc.0
0x3e9be  ldc.i4.1
0x3e9bf  newarr   [mscorlib]System.Attribute
0x3e9c4  dup
0x3e9c5  ldc.i4.0
0x3e9c6  ldsfld   class [System]System.ComponentModel.BrowsableAttribute [System]System.ComponentModel.BrowsableAttribute::No
0x3e9cb  stelem.ref
0x3e9cc  call     class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.TypeDescriptor::CreateProperty(class [mscorlib]System.Type, class [System]System.ComponentModel.PropertyDescriptor, class [mscorlib]System.Attribute[])
0x3e9d1  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3e9d6  ldloc.2
0x3e9d7  ldc.i4.1
0x3e9d8  add
0x3e9d9  stloc.2
0x3e9da  ldloc.2
0x3e9db  ldloc.1
0x3e9dc  ldlen
0x3e9dd  conv.i4
0x3e9de  blt.s    loc_3E9A1
0x3e9e0  ldarg.1
0x3e9e1  ldstr    aDeletequery// "DeleteQuery"
0x3e9e6  ldarg.0
0x3e9e7  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e9ec  ldstr    aDeletequery// "DeleteQuery"
0x3e9f1  ldtoken  [System.Web]System.Web.UI.DataSourceOperation
0x3e9f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e9fb  ldc.i4.0
0x3e9fc  newarr   [mscorlib]System.Attribute
0x3ea01  call     class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.TypeDescriptor::CreateProperty(class [mscorlib]System.Type, string, class [mscorlib]System.Type, class [mscorlib]System.Attribute[])
0x3ea06  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3ea0b  ldarg.1
0x3ea0c  ldstr    aInsertquery// "InsertQuery"
0x3ea11  ldarg.0
0x3ea12  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ea17  ldstr    aInsertquery// "InsertQuery"
0x3ea1c  ldtoken  [System.Web]System.Web.UI.DataSourceOperation
0x3ea21  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3ea26  ldc.i4.0
0x3ea27  newarr   [mscorlib]System.Attribute
0x3ea2c  call     class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.TypeDescriptor::CreateProperty(class [mscorlib]System.Type, string, class [mscorlib]System.Type, class [mscorlib]System.Attribute[])
0x3ea31  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3ea36  ldarg.1
0x3ea37  ldstr    aSelectquery// "SelectQuery"
0x3ea3c  ldarg.0
0x3ea3d  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ea42  ldstr    aSelectquery// "SelectQuery"
0x3ea47  ldtoken  [System.Web]System.Web.UI.DataSourceOperation
0x3ea4c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3ea51  ldc.i4.0
0x3ea52  newarr   [mscorlib]System.Attribute
0x3ea57  call     class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.TypeDescriptor::CreateProperty(class [mscorlib]System.Type, string, class [mscorlib]System.Type, class [mscorlib]System.Attribute[])
0x3ea5c  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3ea61  ldarg.1
0x3ea62  ldstr    aUpdatequery// "UpdateQuery"
0x3ea67  ldarg.0
0x3ea68  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ea6d  ldstr    aUpdatequery// "UpdateQuery"
0x3ea72  ldtoken  [System.Web]System.Web.UI.DataSourceOperation
0x3ea77  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3ea7c  ldc.i4.0
0x3ea7d  newarr   [mscorlib]System.Attribute
0x3ea82  call     class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.TypeDescriptor::CreateProperty(class [mscorlib]System.Type, string, class [mscorlib]System.Type, class [mscorlib]System.Attribute[])
0x3ea87  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3ea8c  ldarg.1
0x3ea8d  ldstr    aConnectionstri// "ConnectionString"
0x3ea92  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x3ea97  castclass [System]System.ComponentModel.PropertyDescriptor
0x3ea9c  stloc.0
0x3ea9d  ldarg.1
0x3ea9e  ldstr    aConnectionstri// "ConnectionString"
0x3eaa3  ldarg.0
0x3eaa4  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3eaa9  ldloc.0
0x3eaaa  ldc.i4.0
0x3eaab  newarr   [mscorlib]System.Attribute
0x3eab0  call     class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.TypeDescriptor::CreateProperty(class [mscorlib]System.Type, class [System]System.ComponentModel.PropertyDescriptor, class [mscorlib]System.Attribute[])
0x3eab5  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3eaba  ldarg.1
0x3eabb  ldstr    aProvidername_0// "ProviderName"
0x3eac0  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x3eac5  castclass [System]System.ComponentModel.PropertyDescriptor
0x3eaca  stloc.0
0x3eacb  ldarg.1
0x3eacc  ldstr    aProvidername_0// "ProviderName"
0x3ead1  ldarg.0
0x3ead2  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ead7  ldloc.0
0x3ead8  ldc.i4.0
0x3ead9  newarr   [mscorlib]System.Attribute
0x3eade  call     class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.TypeDescriptor::CreateProperty(class [mscorlib]System.Type, class [System]System.ComponentModel.PropertyDescriptor, class [mscorlib]System.Attribute[])
0x3eae3  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3eae8  ldarg.1
0x3eae9  ldstr    aSelectcommand// "SelectCommand"
0x3eaee  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x3eaf3  castclass [System]System.ComponentModel.PropertyDescriptor
0x3eaf8  stloc.0
0x3eaf9  ldarg.1
0x3eafa  ldstr    aSelectcommand// "SelectCommand"
0x3eaff  ldarg.0
0x3eb00  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3eb05  ldloc.0
0x3eb06  ldc.i4.1
0x3eb07  newarr   [mscorlib]System.Attribute
0x3eb0c  dup
0x3eb0d  ldc.i4.0
0x3eb0e  ldsfld   class [System]System.ComponentModel.BrowsableAttribute [System]System.ComponentModel.BrowsableAttribute::No
0x3eb13  stelem.ref
0x3eb14  call     class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.TypeDescriptor::CreateProperty(class [mscorlib]System.Type, class [System]System.ComponentModel.PropertyDescriptor, class [mscorlib]System.Attribute[])
0x3eb19  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3eb1e  ret
```
