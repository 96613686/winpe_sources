# System.Xaml.Permissions.XamlAccessLevel::FromXml

- ea: `0x124c0`
- end: `0x12565`
- name: `System.Xaml.Permissions.XamlAccessLevel::FromXml`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x127a0`

## callees

- `0x11f50`
- `0x12330`
- `0x124c0`
- `0x125f0`

## string_xrefs

- `0x124c6`: `XamlAccessLevel`
- `0x124e8`: `XamlAccessLevel`
- `0x124d2`: `SecurityXmlUnexpectedTag`
- `0x1250d`: `SecurityXmlMissingAttribute`

## pseudocode

```c

```

## disassembly

```asm
0x124c0  ldarg.0
0x124c1  callvirt instance string [mscorlib]System.Security.SecurityElement::get_Tag()
0x124c6  ldstr    aXamlaccessleve// "XamlAccessLevel"
0x124cb  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x124d0  brfalse.s loc_124FE
0x124d2  ldstr    aSecurityxmlune// "SecurityXmlUnexpectedTag"
0x124d7  ldc.i4.2
0x124d8  newarr   [mscorlib]System.Object
0x124dd  dup
0x124de  ldc.i4.0
0x124df  ldarg.0
0x124e0  callvirt instance string [mscorlib]System.Security.SecurityElement::get_Tag()
0x124e5  stelem.ref
0x124e6  dup
0x124e7  ldc.i4.1
0x124e8  ldstr    aXamlaccessleve// "XamlAccessLevel"
0x124ed  stelem.ref
0x124ee  call     string System.Xaml.SR::Get(string id, object[] args)
0x124f3  ldstr    aElem// "elem"
0x124f8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x124fd  throw
0x124fe  ldarg.0
0x124ff  ldstr    aAssemblyname_0// "AssemblyName"
0x12504  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x12509  stloc.0
0x1250a  ldloc.0
0x1250b  brtrue.s loc_12530
0x1250d  ldstr    aSecurityxmlmis// "SecurityXmlMissingAttribute"
0x12512  ldc.i4.1
0x12513  newarr   [mscorlib]System.Object
0x12518  dup
0x12519  ldc.i4.0
0x1251a  ldstr    aAssemblyname_0// "AssemblyName"
0x1251f  stelem.ref
0x12520  call     string System.Xaml.SR::Get(string id, object[] args)
0x12525  ldstr    aElem// "elem"
0x1252a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1252f  throw
0x12530  ldloc.0
0x12531  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x12536  stloc.1
0x12537  ldloc.1
0x12538  ldstr    aElem// "elem"
0x1253d  call     void System.Xaml.Permissions.XamlAccessLevel::ValidateAssemblyName(class [mscorlib]System.Reflection.AssemblyName assemblyName, string argName)
0x12542  ldarg.0
0x12543  ldstr    aTypename_0// "TypeName"
0x12548  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x1254d  stloc.2
0x1254e  ldloc.2
0x1254f  brfalse.s loc_12558
0x12551  ldloc.2
0x12552  callvirt instance string [mscorlib]System.String::Trim()
0x12557  stloc.2
0x12558  ldloc.1
0x12559  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_FullName()
0x1255e  ldloc.2
0x1255f  newobj   instance void System.Xaml.Permissions.XamlAccessLevel::.ctor(string assemblyName, string typeName)
0x12564  ret
```
