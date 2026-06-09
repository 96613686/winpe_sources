# System.Web.UI.ObjectTagBuilder::Init

- ea: `0x70c50`
- end: `0x70e6b`
- name: `System.Web.UI.ObjectTagBuilder::Init`
- size: `539`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18990`
- `0x34f20`
- `0x34fa0`
- `0x58d50`
- `0x626f0`
- `0x70c50`
- `0x835e0`
- `0x83ef0`
- `0x857d0`
- `0x85d30`

## string_xrefs

- `0x70d44`: `classid`
- `0x70d79`: `Invalid_clsid`
- `0x70e5a`: `Object_tag_must_have_class_classid_or_progid`

## pseudocode

```c

```

## disassembly

```asm
0x70c50  ldarg.s  5
0x70c52  brtrue.s loc_70C64
0x70c54  ldstr    aObjectTagMustH// "Object_tag_must_have_id"
0x70c59  call     string System.Web.SR::GetString(string name)
0x70c5e  newobj   instance void System.Web.HttpException::.ctor(string message)
0x70c63  throw
0x70c64  ldarg.0
0x70c65  ldarg.s  5
0x70c67  call     instance void System.Web.UI.ControlBuilder::set_ID(string value)
0x70c6c  ldarg.s  6
0x70c6e  ldstr    aScope// "scope"
0x70c73  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x70c78  castclass [mscorlib]System.String
0x70c7d  stloc.0
0x70c7e  ldloc.0
0x70c7f  brtrue.s loc_70C8A
0x70c81  ldarg.0
0x70c82  ldc.i4.0
0x70c83  stfld    valuetype System.Web.UI.ObjectTagScope System.Web.UI.ObjectTagBuilder::_scope
0x70c88  br.s     loc_70CFC
0x70c8a  ldloc.0
0x70c8b  ldstr    aPage_0// "page"
0x70c90  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x70c95  brfalse.s loc_70CA0
0x70c97  ldarg.0
0x70c98  ldc.i4.1
0x70c99  stfld    valuetype System.Web.UI.ObjectTagScope System.Web.UI.ObjectTagBuilder::_scope
0x70c9e  br.s     loc_70CFC
0x70ca0  ldloc.0
0x70ca1  ldstr    aSession// "session"
0x70ca6  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x70cab  brfalse.s loc_70CB6
0x70cad  ldarg.0
0x70cae  ldc.i4.2
0x70caf  stfld    valuetype System.Web.UI.ObjectTagScope System.Web.UI.ObjectTagBuilder::_scope
0x70cb4  br.s     loc_70CFC
0x70cb6  ldloc.0
0x70cb7  ldstr    aApplication_0// "application"
0x70cbc  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x70cc1  brfalse.s loc_70CCC
0x70cc3  ldarg.0
0x70cc4  ldc.i4.3
0x70cc5  stfld    valuetype System.Web.UI.ObjectTagScope System.Web.UI.ObjectTagBuilder::_scope
0x70cca  br.s     loc_70CFC
0x70ccc  ldloc.0
0x70ccd  ldstr    aAppinstance// "appinstance"
0x70cd2  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x70cd7  brfalse.s loc_70CE2
0x70cd9  ldarg.0
0x70cda  ldc.i4.4
0x70cdb  stfld    valuetype System.Web.UI.ObjectTagScope System.Web.UI.ObjectTagBuilder::_scope
0x70ce0  br.s     loc_70CFC
0x70ce2  ldstr    aInvalidScope// "Invalid_scope"
0x70ce7  ldc.i4.1
0x70ce8  newarr   [mscorlib]System.Object
0x70ced  dup
0x70cee  ldc.i4.0
0x70cef  ldloc.0
0x70cf0  stelem.ref
0x70cf1  call     string System.Web.SR::GetString(string name, object[] args)
0x70cf6  newobj   instance void System.Web.HttpException::.ctor(string message)
0x70cfb  throw
0x70cfc  ldarg.s  6
0x70cfe  ldstr    aLatebinding// "latebinding"
0x70d03  ldarg.0
0x70d04  ldflda   bool System.Web.UI.ObjectTagBuilder::_fLateBinding
0x70d09  call     bool System.Web.UI.Util::GetAndRemoveBooleanAttribute(class [mscorlib]System.Collections.IDictionary directives, string key, bool& val)
0x70d0e  pop
0x70d0f  ldarg.s  6
0x70d11  ldstr    aClass// "class"
0x70d16  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x70d1b  castclass [mscorlib]System.String
0x70d20  stloc.1
0x70d21  ldloc.1
0x70d22  brfalse.s loc_70D31
0x70d24  ldarg.0
0x70d25  ldarg.1
0x70d26  ldloc.1
0x70d27  callvirt instance class [mscorlib]System.Type System.Web.UI.TemplateParser::GetType(string typeName)
0x70d2c  stfld    class [mscorlib]System.Type System.Web.UI.ObjectTagBuilder::_type
0x70d31  ldarg.0
0x70d32  ldfld    class [mscorlib]System.Type System.Web.UI.ObjectTagBuilder::_type
0x70d37  ldnull
0x70d38  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x70d3d  brfalse  loc_70DC4
0x70d42  ldarg.s  6
0x70d44  ldstr    aClassid// "classid"
0x70d49  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x70d4e  castclass [mscorlib]System.String
0x70d53  stloc.1
0x70d54  ldloc.1
0x70d55  brfalse.s loc_70DC4
0x70d57  ldloca.s 2
0x70d59  ldloc.1
0x70d5a  call     instance void [mscorlib]System.Guid::.ctor(string)
0x70d5f  ldarg.0
0x70d60  ldloc.2
0x70d61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromCLSID(valuetype [mscorlib]System.Guid)
0x70d66  stfld    class [mscorlib]System.Type System.Web.UI.ObjectTagBuilder::_type
0x70d6b  ldarg.0
0x70d6c  ldfld    class [mscorlib]System.Type System.Web.UI.ObjectTagBuilder::_type
0x70d71  ldnull
0x70d72  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x70d77  brfalse.s loc_70D93
0x70d79  ldstr    aInvalidClsid// "Invalid_clsid"
0x70d7e  ldc.i4.1
0x70d7f  newarr   [mscorlib]System.Object
0x70d84  dup
0x70d85  ldc.i4.0
0x70d86  ldloc.1
0x70d87  stelem.ref
0x70d88  call     string System.Web.SR::GetString(string name, object[] args)
0x70d8d  newobj   instance void System.Web.HttpException::.ctor(string message)
0x70d92  throw
0x70d93  ldarg.0
0x70d94  ldfld    bool System.Web.UI.ObjectTagBuilder::_fLateBinding
0x70d99  brtrue.s loc_70DA8
0x70d9b  ldarg.0
0x70d9c  ldfld    class [mscorlib]System.Type System.Web.UI.ObjectTagBuilder::_type
0x70da1  call     bool System.Web.UI.Util::IsLateBoundComClassicType(class [mscorlib]System.Type t)
0x70da6  brfalse.s loc_70DB8
0x70da8  ldarg.0
0x70da9  ldc.i4.1
0x70daa  stfld    bool System.Web.UI.ObjectTagBuilder::_lateBound
0x70daf  ldarg.0
0x70db0  ldloc.1
0x70db1  stfld    string System.Web.UI.ObjectTagBuilder::_clsid
0x70db6  br.s     loc_70DC4
0x70db8  ldarg.1
0x70db9  ldarg.0
0x70dba  ldfld    class [mscorlib]System.Type System.Web.UI.ObjectTagBuilder::_type
0x70dbf  callvirt instance void System.Web.UI.TemplateParser::AddTypeDependency(class [mscorlib]System.Type type)
0x70dc4  ldarg.0
0x70dc5  ldfld    class [mscorlib]System.Type System.Web.UI.ObjectTagBuilder::_type
0x70dca  ldnull
0x70dcb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x70dd0  brfalse.s loc_70E4C
0x70dd2  ldarg.s  6
0x70dd4  ldstr    aProgid// "progid"
0x70dd9  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x70dde  castclass [mscorlib]System.String
0x70de3  stloc.1
0x70de4  ldloc.1
0x70de5  brfalse.s loc_70E4C
0x70de7  ldarg.0
0x70de8  ldloc.1
0x70de9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromProgID(string)
0x70dee  stfld    class [mscorlib]System.Type System.Web.UI.ObjectTagBuilder::_type
0x70df3  ldarg.0
0x70df4  ldfld    class [mscorlib]System.Type System.Web.UI.ObjectTagBuilder::_type
0x70df9  ldnull
0x70dfa  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x70dff  brfalse.s loc_70E1B
0x70e01  ldstr    aInvalidProgid// "Invalid_progid"
0x70e06  ldc.i4.1
0x70e07  newarr   [mscorlib]System.Object
0x70e0c  dup
0x70e0d  ldc.i4.0
0x70e0e  ldloc.1
0x70e0f  stelem.ref
0x70e10  call     string System.Web.SR::GetString(string name, object[] args)
0x70e15  newobj   instance void System.Web.HttpException::.ctor(string message)
0x70e1a  throw
0x70e1b  ldarg.0
0x70e1c  ldfld    bool System.Web.UI.ObjectTagBuilder::_fLateBinding
0x70e21  brtrue.s loc_70E30
0x70e23  ldarg.0
0x70e24  ldfld    class [mscorlib]System.Type System.Web.UI.ObjectTagBuilder::_type
0x70e29  call     bool System.Web.UI.Util::IsLateBoundComClassicType(class [mscorlib]System.Type t)
0x70e2e  brfalse.s loc_70E40
0x70e30  ldarg.0
0x70e31  ldc.i4.1
0x70e32  stfld    bool System.Web.UI.ObjectTagBuilder::_lateBound
0x70e37  ldarg.0
0x70e38  ldloc.1
0x70e39  stfld    string System.Web.UI.ObjectTagBuilder::_progid
0x70e3e  br.s     loc_70E4C
0x70e40  ldarg.1
0x70e41  ldarg.0
0x70e42  ldfld    class [mscorlib]System.Type System.Web.UI.ObjectTagBuilder::_type
0x70e47  callvirt instance void System.Web.UI.TemplateParser::AddTypeDependency(class [mscorlib]System.Type type)
0x70e4c  ldarg.0
0x70e4d  ldfld    class [mscorlib]System.Type System.Web.UI.ObjectTagBuilder::_type
0x70e52  ldnull
0x70e53  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x70e58  brfalse.s loc_70E6A
0x70e5a  ldstr    aObjectTagMustH_0// "Object_tag_must_have_class_classid_or_p"...
0x70e5f  call     string System.Web.SR::GetString(string name)
0x70e64  newobj   instance void System.Web.HttpException::.ctor(string message)
0x70e69  throw
0x70e6a  ret
```
