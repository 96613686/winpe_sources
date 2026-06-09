# ExpandPositionalParameters::ExpandPositionalParametersIntoProperties

- ea: `0x2e4d0`
- end: `0x2e658`
- name: `ExpandPositionalParameters::ExpandPositionalParametersIntoProperties`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x2ea40`

## callees

- `0x20e0`
- `0x2100`
- `0x8860`
- `0xa4c0`
- `0xa590`
- `0xa6a0`
- `0xb280`
- `0xd0b0`
- `0xd430`
- `0xd8d0`
- `0xf2c0`
- `0x11f20`
- `0x11f50`
- `0x2cb10`
- `0x2e4d0`
- `0x2e660`
- `0x2e710`
- `0x2eb70`

## string_xrefs

- `0x2e5f9`: `ExpandPositionalParametersWithReadOnlyProperties`

## pseudocode

```c

```

## disassembly

```asm
0x2e4d0  ldarg.1
0x2e4d1  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2e4d6  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2e4db  stloc.0
0x2e4dc  ldloc.0
0x2e4dd  callvirt instance class System.Xaml.XamlType Frame::get_Type()
0x2e4e2  stloc.1
0x2e4e3  ldloc.1
0x2e4e4  callvirt instance class [mscorlib]System.Type System.Xaml.XamlType::get_UnderlyingType()
0x2e4e9  stloc.2
0x2e4ea  ldloc.2
0x2e4eb  ldnull
0x2e4ec  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2e4f1  brfalse.s loc_2E512
0x2e4f3  ldstr    aExpandposition_0// "ExpandPositionalParametersWithoutUnderl"...
0x2e4f8  ldc.i4.1
0x2e4f9  newarr   [mscorlib]System.Object
0x2e4fe  dup
0x2e4ff  ldc.i4.0
0x2e500  ldloc.1
0x2e501  callvirt instance string System.Xaml.XamlType::GetQualifiedName()
0x2e506  stelem.ref
0x2e507  call     string System.Xaml.SR::Get(string id, object[] args)
0x2e50c  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2e511  throw
0x2e512  ldarg.1
0x2e513  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e518  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2e51d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::get_Count()
0x2e522  stloc.3
0x2e523  ldarg.0
0x2e524  ldloc.1
0x2e525  ldloc.3
0x2e526  call     instance class [mscorlib]System.Reflection.ParameterInfo[] ExpandPositionalParameters::GetParametersInfo(class System.Xaml.XamlType objectXamlType, int32 numOfParameters)
0x2e52b  stloc.s  4
0x2e52d  ldarg.0
0x2e52e  ldloc.1
0x2e52f  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.XamlMember> ExpandPositionalParameters::GetAllPropertiesWithCAA(class System.Xaml.XamlType objectXamlType)
0x2e534  stloc.s  5
0x2e536  ldloc.s  4
0x2e538  ldlen
0x2e539  conv.i4
0x2e53a  ldloc.s  5
0x2e53c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.XamlMember>::get_Count()
0x2e541  beq.s    loc_2E553
0x2e543  ldstr    aConstructornot// "ConstructorNotFoundForGivenPositionalPa"...
0x2e548  call     string System.Xaml.SR::Get(string id)
0x2e54d  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2e552  throw
0x2e553  ldc.i4.0
0x2e554  stloc.s  6
0x2e556  br       loc_2E64C
0x2e55b  ldloc.s  4
0x2e55d  ldloc.s  6
0x2e55f  ldelem.ref
0x2e560  stloc.s  7
0x2e562  ldnull
0x2e563  stloc.s  8
0x2e565  ldloc.s  5
0x2e567  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.XamlMember>::GetEnumerator()
0x2e56c  stloc.s  0xA
0x2e56e  br.s     loc_2E5AE
0x2e570  ldloca.s 0xA
0x2e572  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xaml.XamlMember>::get_Current()
0x2e577  stloc.s  0xB
0x2e579  ldloc.s  0xB
0x2e57b  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x2e580  callvirt instance class [mscorlib]System.Type System.Xaml.XamlType::get_UnderlyingType()
0x2e585  ldloc.s  7
0x2e587  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x2e58c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2e591  brfalse.s loc_2E5AE
0x2e593  ldloc.s  0xB
0x2e595  call     string System.Xaml.XamlObjectReader::GetConstructorArgument(class System.Xaml.XamlMember member)
0x2e59a  ldloc.s  7
0x2e59c  callvirt instance string [mscorlib]System.Reflection.ParameterInfo::get_Name()
0x2e5a1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e5a6  brfalse.s loc_2E5AE
0x2e5a8  ldloc.s  0xB
0x2e5aa  stloc.s  8
0x2e5ac  leave.s  loc_2E5C7
0x2e5ae  ldloca.s 0xA
0x2e5b0  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xaml.XamlMember>::MoveNext()
0x2e5b5  brtrue.s loc_2E570
0x2e5b7  leave.s  loc_2E5C7
0x2e5b9  ldloca.s 0xA
0x2e5bb  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xaml.XamlMember>
0x2e5c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e5c6  endfinally
0x2e5c7  ldloc.s  8
0x2e5c9  ldnull
0x2e5ca  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2e5cf  brfalse.s loc_2E5E1
0x2e5d1  ldstr    aConstructornot// "ConstructorNotFoundForGivenPositionalPa"...
0x2e5d6  call     string System.Xaml.SR::Get(string id)
0x2e5db  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2e5e0  throw
0x2e5e1  ldloc.1
0x2e5e2  ldloc.s  8
0x2e5e4  callvirt instance string System.Xaml.XamlMember::get_Name()
0x2e5e9  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::GetMember(string name)
0x2e5ee  stloc.s  9
0x2e5f0  ldloc.s  9
0x2e5f2  callvirt instance bool System.Xaml.XamlMember::get_IsReadOnly()
0x2e5f7  brfalse.s loc_2E609
0x2e5f9  ldstr    aExpandposition_1// "ExpandPositionalParametersWithReadOnlyP"...
0x2e5fe  call     string System.Xaml.SR::Get(string id)
0x2e603  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2e608  throw
0x2e609  ldarg.1
0x2e60a  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e60f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2e614  ldloc.s  6
0x2e616  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::get_Item(!!T0)
0x2e61b  ldc.i4.0
0x2e61c  ldc.i4.4
0x2e61d  ldloc.s  9
0x2e61f  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2e624  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Insert(int32, var<u1>)
0x2e629  ldarg.1
0x2e62a  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e62f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2e634  ldloc.s  6
0x2e636  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::get_Item(!!T0)
0x2e63b  ldc.i4.5
0x2e63c  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType)
0x2e641  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x2e646  ldloc.s  6
0x2e648  ldc.i4.1
0x2e649  add
0x2e64a  stloc.s  6
0x2e64c  ldloc.s  6
0x2e64e  ldloc.s  4
0x2e650  ldlen
0x2e651  conv.i4
0x2e652  blt      loc_2E55B
0x2e657  ret
```
