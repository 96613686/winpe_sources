# System.Xaml.Permissions.XamlLoadPermission::FromXml

- ea: `0x127a0`
- end: `0x1291f`
- name: `System.Xaml.Permissions.XamlLoadPermission::FromXml`
- size: `383`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10`
- `0x11f50`
- `0x124c0`
- `0x12730`
- `0x127a0`

## string_xrefs

- `0x127c0`: `SecurityXmlUnexpectedTag`
- `0x12811`: `SecurityXmlUnexpectedValue`
- `0x12862`: `SecurityXmlUnexpectedValue`

## pseudocode

```c

```

## disassembly

```asm
0x127a0  ldarg.1
0x127a1  brtrue.s loc_127AE
0x127a3  ldstr    aElem// "elem"
0x127a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x127ad  throw
0x127ae  ldarg.1
0x127af  callvirt instance string [mscorlib]System.Security.SecurityElement::get_Tag()
0x127b4  ldstr    aIpermission// "IPermission"
0x127b9  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x127be  brfalse.s loc_127EC
0x127c0  ldstr    aSecurityxmlune// "SecurityXmlUnexpectedTag"
0x127c5  ldc.i4.2
0x127c6  newarr   [mscorlib]System.Object
0x127cb  dup
0x127cc  ldc.i4.0
0x127cd  ldarg.1
0x127ce  callvirt instance string [mscorlib]System.Security.SecurityElement::get_Tag()
0x127d3  stelem.ref
0x127d4  dup
0x127d5  ldc.i4.1
0x127d6  ldstr    aIpermission// "IPermission"
0x127db  stelem.ref
0x127dc  call     string System.Xaml.SR::Get(string id, object[] args)
0x127e1  ldstr    aElem// "elem"
0x127e6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x127eb  throw
0x127ec  ldarg.1
0x127ed  ldstr    aClass_0// "class"
0x127f2  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x127f7  stloc.0
0x127f8  ldloc.0
0x127f9  ldarg.0
0x127fa  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x127ff  callvirt instance string [mscorlib]System.Type::get_FullName()
0x12804  ldc.i4.0
0x12805  call     class [mscorlib]System.Globalization.CultureInfo System.Xaml.TypeConverterHelper::get_InvariantEnglishUS()
0x1280a  callvirt instance bool [mscorlib]System.String::StartsWith(string, bool, class [mscorlib]System.Globalization.CultureInfo)
0x1280f  brtrue.s loc_12846
0x12811  ldstr    aSecurityxmlune_0// "SecurityXmlUnexpectedValue"
0x12816  ldc.i4.3
0x12817  newarr   [mscorlib]System.Object
0x1281c  dup
0x1281d  ldc.i4.0
0x1281e  ldloc.0
0x1281f  stelem.ref
0x12820  dup
0x12821  ldc.i4.1
0x12822  ldstr    aClass_0// "class"
0x12827  stelem.ref
0x12828  dup
0x12829  ldc.i4.2
0x1282a  ldarg.0
0x1282b  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x12830  callvirt instance string [mscorlib]System.Type::get_FullName()
0x12835  stelem.ref
0x12836  call     string System.Xaml.SR::Get(string id, object[] args)
0x1283b  ldstr    aElem// "elem"
0x12840  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x12845  throw
0x12846  ldarg.1
0x12847  ldstr    aVersion// "version"
0x1284c  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x12851  stloc.1
0x12852  ldloc.1
0x12853  brfalse.s loc_12891
0x12855  ldloc.1
0x12856  ldstr    a1// "1"
0x1285b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x12860  brfalse.s loc_12891
0x12862  ldstr    aSecurityxmlune_0// "SecurityXmlUnexpectedValue"
0x12867  ldc.i4.3
0x12868  newarr   [mscorlib]System.Object
0x1286d  dup
0x1286e  ldc.i4.0
0x1286f  ldloc.0
0x12870  stelem.ref
0x12871  dup
0x12872  ldc.i4.1
0x12873  ldstr    aVersion// "version"
0x12878  stelem.ref
0x12879  dup
0x1287a  ldc.i4.2
0x1287b  ldstr    a1// "1"
0x12880  stelem.ref
0x12881  call     string System.Xaml.SR::Get(string id, object[] args)
0x12886  ldstr    aElem// "elem"
0x1288b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x12890  throw
0x12891  ldarg.1
0x12892  ldstr    aUnrestricted// "Unrestricted"
0x12897  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x1289c  stloc.2
0x1289d  ldloc.2
0x1289e  brfalse.s loc_128B1
0x128a0  ldloc.2
0x128a1  call     bool [mscorlib]System.Boolean::Parse(string)
0x128a6  brfalse.s loc_128B1
0x128a8  ldarg.0
0x128a9  ldc.i4.1
0x128aa  ldnull
0x128ab  call     instance void System.Xaml.Permissions.XamlLoadPermission::Init(bool isUnrestricted, class [mscorlib]System.Collections.Generic.IList`1<class System.Xaml.Permissions.XamlAccessLevel> allowedAccess)
0x128b0  ret
0x128b1  ldnull
0x128b2  stloc.3
0x128b3  ldarg.1
0x128b4  callvirt instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Security.SecurityElement::get_Children()
0x128b9  brfalse.s loc_12916
0x128bb  ldarg.1
0x128bc  callvirt instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Security.SecurityElement::get_Children()
0x128c1  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x128c6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.Permissions.XamlAccessLevel>::.ctor(int32)
0x128cb  stloc.3
0x128cc  ldarg.1
0x128cd  callvirt instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Security.SecurityElement::get_Children()
0x128d2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x128d7  stloc.s  4
0x128d9  br.s     loc_128F6
0x128db  ldloc.s  4
0x128dd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x128e2  castclass [mscorlib]System.Security.SecurityElement
0x128e7  stloc.s  5
0x128e9  ldloc.3
0x128ea  ldloc.s  5
0x128ec  call     class System.Xaml.Permissions.XamlAccessLevel System.Xaml.Permissions.XamlAccessLevel::FromXml(class [mscorlib]System.Security.SecurityElement elem)
0x128f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.Permissions.XamlAccessLevel>::Add(var<u1>)
0x128f6  ldloc.s  4
0x128f8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x128fd  brtrue.s loc_128DB
0x128ff  leave.s  loc_12916
0x12901  ldloc.s  4
0x12903  isinst   [mscorlib]System.IDisposable
0x12908  stloc.s  6
0x1290a  ldloc.s  6
0x1290c  brfalse.s loc_12915
0x1290e  ldloc.s  6
0x12910  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12915  endfinally
0x12916  ldarg.0
0x12917  ldc.i4.0
0x12918  ldloc.3
0x12919  call     instance void System.Xaml.Permissions.XamlLoadPermission::Init(bool isUnrestricted, class [mscorlib]System.Collections.Generic.IList`1<class System.Xaml.Permissions.XamlAccessLevel> allowedAccess)
0x1291e  ret
```
