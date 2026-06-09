# System.Xml.Serialization.XmlSerializationReaderILGen::WriteAttributes

- ea: `0x972b0`
- end: `0x97a87`
- name: `System.Xml.Serialization.XmlSerializationReaderILGen::WriteAttributes`
- size: `2007`
- prototype: ``
- caller_count: `2`
- callee_count: `47`
- tags: `registry_config`

## callers

- `0x93f10`
- `0x96090`

## callees

- `0x634c0`
- `0x63640`
- `0x636b0`
- `0x636f0`
- `0x637d0`
- `0x63830`
- `0x63bc0`
- `0x63c60`
- `0x640d0`
- `0x64100`
- `0x64260`
- `0x642b0`
- `0x64320`
- `0x643c0`
- `0x645a0`
- `0x645b0`
- `0x64620`
- `0x64970`
- `0x649c0`
- `0x649e0`
- `0x64b40`
- `0x64b90`
- `0x64bc0`
- `0x64c20`
- `0x64c50`
- `0x68660`
- `0x68690`
- `0x686d0`
- `0x686f0`
- `0x68a50`
- `0x69620`
- `0x69640`
- `0x69730`
- `0x69750`
- `0x72bf0`
- `0x88210`
- `0x88220`
- `0x970a0`
- `0x972b0`
- `0x97a90`
- `0x991c0`
- `0x99470`
- `0x9b340`
- `0x123090`
- `0x1230a0`
- `0x1230c0`
- `0x123160`

## string_xrefs

- `0x973cb`: `http://www.w3.org/XML/1998/namespace`
- `0x979ce`: `http://www.w3.org/XML/1998/namespace`
- `0x973bf`: `Reader`
- `0x973d8`: `Reader`
- `0x972c4`: `get_Reader`
- `0x972e5`: `MoveToNextAttribute`
- `0x97445`: `IsXmlnsAttribute`
- `0x9773c`: `IsXmlnsAttribute`
- `0x97828`: `ReadNode`

## pseudocode

```c

```

## disassembly

```asm
0x972b0  ldc.i4.0
0x972b1  stloc.0
0x972b2  ldnull
0x972b3  stloc.1
0x972b4  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x972b9  stloc.2
0x972ba  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x972bf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x972c4  ldstr    aGetReader// "get_Reader"
0x972c9  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x972ce  ldnull
0x972cf  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x972d4  ldnull
0x972d5  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x972da  stloc.3
0x972db  ldtoken  System.Xml.XmlReader
0x972e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x972e5  ldstr    aMovetonextattr// "MoveToNextAttribute"
0x972ea  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x972ef  ldnull
0x972f0  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x972f5  ldnull
0x972f6  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x972fb  stloc.s  4
0x972fd  ldarg.0
0x972fe  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97303  callvirt instance void System.Xml.Serialization.CodeGenerator::WhileBegin()
0x97308  ldc.i4.0
0x97309  stloc.s  5
0x9730b  br       loc_9740F
0x97310  ldarg.1
0x97311  ldloc.s  5
0x97313  ldelem.ref
0x97314  stloc.s  6
0x97316  ldloc.s  6
0x97318  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x9731d  callvirt instance class System.Xml.Serialization.XmlnsAccessor System.Xml.Serialization.AccessorMapping::get_Xmlns()
0x97322  brfalse.s loc_9732C
0x97324  ldloc.s  6
0x97326  stloc.1
0x97327  br       loc_97409
0x9732c  ldloc.s  6
0x9732e  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97333  callvirt instance bool System.Xml.Serialization.AccessorMapping::get_Ignore()
0x97338  brtrue   loc_97409
0x9733d  ldloc.s  6
0x9733f  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97344  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x97349  stloc.s  7
0x9734b  ldloc.s  7
0x9734d  brfalse  loc_97409
0x97352  ldloc.s  7
0x97354  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x97359  brtrue   loc_97409
0x9735e  ldloc.2
0x9735f  ldloc.s  7
0x97361  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x97366  pop
0x97367  ldloc.0
0x97368  dup
0x97369  ldc.i4.1
0x9736a  add
0x9736b  stloc.0
0x9736c  ldc.i4.0
0x9736d  ble.s    loc_9737C
0x9736f  ldarg.0
0x97370  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97375  callvirt instance void System.Xml.Serialization.CodeGenerator::InitElseIf()
0x9737a  br.s     loc_97387
0x9737c  ldarg.0
0x9737d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97382  callvirt instance void System.Xml.Serialization.CodeGenerator::InitIf()
0x97387  ldloc.s  6
0x97389  callvirt instance string Member::get_ParamsReadSource()
0x9738e  brfalse.s loc_973B5
0x97390  ldarg.0
0x97391  ldloc.s  6
0x97393  callvirt instance string Member::get_ParamsReadSource()
0x97398  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::ILGenParamsReadSource(string paramsReadSource)
0x9739d  ldarg.0
0x9739e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x973a3  ldc.i4.0
0x973a4  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(bool boolVar)
0x973a9  ldarg.0
0x973aa  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x973af  ldc.i4.1
0x973b0  callvirt instance void System.Xml.Serialization.CodeGenerator::AndIf(valuetype System.Xml.Serialization.Cmp cmpOp)
0x973b5  ldloc.s  7
0x973b7  callvirt instance bool System.Xml.Serialization.AttributeAccessor::get_IsSpecialXmlNamespace()
0x973bc  brfalse.s loc_973D7
0x973be  ldarg.0
0x973bf  ldstr    aReader_2// "Reader"
0x973c4  ldloc.s  7
0x973c6  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x973cb  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x973d0  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteXmlNodeEqual(string source, string name, string ns)
0x973d5  br.s     loc_97401
0x973d7  ldarg.0
0x973d8  ldstr    aReader_2// "Reader"
0x973dd  ldloc.s  7
0x973df  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x973e4  ldloc.s  7
0x973e6  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x973eb  ldc.i4.1
0x973ec  beq.s    loc_973F5
0x973ee  ldstr    asc_1284AE// ""
0x973f3  br.s     loc_973FC
0x973f5  ldloc.s  7
0x973f7  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x973fc  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteXmlNodeEqual(string source, string name, string ns)
0x97401  ldarg.0
0x97402  ldloc.s  6
0x97404  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteAttribute(class Member member)
0x97409  ldloc.s  5
0x9740b  ldc.i4.1
0x9740c  add
0x9740d  stloc.s  5
0x9740f  ldloc.s  5
0x97411  ldarg.1
0x97412  ldlen
0x97413  conv.i4
0x97414  blt      loc_97310
0x97419  ldloc.0
0x9741a  ldc.i4.0
0x9741b  ble.s    loc_9742A
0x9741d  ldarg.0
0x9741e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97423  callvirt instance void System.Xml.Serialization.CodeGenerator::InitElseIf()
0x97428  br.s     loc_97435
0x9742a  ldarg.0
0x9742b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97430  callvirt instance void System.Xml.Serialization.CodeGenerator::InitIf()
0x97435  ldloc.1
0x97436  brfalse  loc_97732
0x9743b  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x97440  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97445  ldstr    aIsxmlnsattribu// "IsXmlnsAttribute"
0x9744a  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x9744f  ldnull
0x97450  ldc.i4.1
0x97451  newarr   [mscorlib]System.Type
0x97456  dup
0x97457  ldc.i4.0
0x97458  ldtoken  [mscorlib]System.String
0x9745d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97462  stelem.ref
0x97463  ldnull
0x97464  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x97469  stloc.s  8
0x9746b  ldtoken  System.Xml.XmlReader
0x97470  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97475  ldstr    aGetName// "get_Name"
0x9747a  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x9747f  ldnull
0x97480  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x97485  ldnull
0x97486  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x9748b  stloc.s  9
0x9748d  ldtoken  System.Xml.XmlReader
0x97492  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97497  ldstr    aGetLocalname// "get_LocalName"
0x9749c  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x974a1  ldnull
0x974a2  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x974a7  ldnull
0x974a8  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x974ad  stloc.s  0xA
0x974af  ldtoken  System.Xml.XmlReader
0x974b4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x974b9  ldstr    aGetValue// "get_Value"
0x974be  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x974c3  ldnull
0x974c4  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x974c9  ldnull
0x974ca  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x974cf  stloc.s  0xB
0x974d1  ldarg.0
0x974d2  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x974d7  ldc.i4.0
0x974d8  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x974dd  ldarg.0
0x974de  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x974e3  ldc.i4.0
0x974e4  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x974e9  ldarg.0
0x974ea  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x974ef  ldloc.3
0x974f0  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x974f5  ldarg.0
0x974f6  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x974fb  ldloc.s  9
0x974fd  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x97502  ldarg.0
0x97503  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97508  ldloc.s  8
0x9750a  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x9750f  ldarg.0
0x97510  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97515  ldc.i4.1
0x97516  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(bool boolVar)
0x9751b  ldarg.0
0x9751c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97521  ldc.i4.1
0x97522  callvirt instance void System.Xml.Serialization.CodeGenerator::AndIf(valuetype System.Xml.Serialization.Cmp cmpOp)
0x97527  ldarg.0
0x97528  ldloc.1
0x97529  callvirt instance string Member::get_Source()
0x9752e  call     instance void System.Xml.Serialization.XmlSerializationILGen::ILGenLoad(string source)
0x97533  ldarg.0
0x97534  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97539  ldnull
0x9753a  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x9753f  ldarg.0
0x97540  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97545  ldc.i4.1
0x97546  callvirt instance void System.Xml.Serialization.CodeGenerator::If(valuetype System.Xml.Serialization.Cmp cmpOp)
0x9754b  ldarg.0
0x9754c  ldloc.1
0x9754d  callvirt instance string Member::get_Source()
0x97552  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBegin(string source)
0x97557  ldloc.1
0x97558  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x9755d  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97562  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x97567  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x9756c  ldnull
0x9756d  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x97572  ldnull
0x97573  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x97578  stloc.s  0xC
0x9757a  ldarg.0
0x9757b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97580  ldloc.s  0xC
0x97582  callvirt instance void System.Xml.Serialization.CodeGenerator::New(class [mscorlib]System.Reflection.ConstructorInfo constructorInfo)
0x97587  ldarg.0
0x97588  ldloc.1
0x97589  callvirt instance string Member::get_Source()
0x9758e  ldloc.1
0x9758f  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97594  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97599  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x9759e  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceEnd(string source, class [mscorlib]System.Type elementType)
0x975a3  ldarg.0
0x975a4  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x975a9  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0x975ae  ldarg.0
0x975af  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x975b4  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::DefineLabel()
0x975b9  stloc.s  0xD
0x975bb  ldarg.0
0x975bc  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x975c1  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::DefineLabel()
0x975c6  stloc.s  0xE
0x975c8  ldloc.1
0x975c9  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x975ce  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x975d3  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x975d8  ldstr    aAdd// "Add"
0x975dd  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x975e2  ldnull
0x975e3  ldc.i4.2
0x975e4  newarr   [mscorlib]System.Type
0x975e9  dup
0x975ea  ldc.i4.0
0x975eb  ldtoken  [mscorlib]System.String
0x975f0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x975f5  stelem.ref
0x975f6  dup
0x975f7  ldc.i4.1
0x975f8  ldtoken  [mscorlib]System.String
0x975fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97602  stelem.ref
0x97603  ldnull
0x97604  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x97609  stloc.s  0xF
0x9760b  ldtoken  [mscorlib]System.String
0x97610  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97615  ldstr    aGetLength// "get_Length"
0x9761a  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x9761f  ldnull
0x97620  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x97625  ldnull
0x97626  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x9762b  stloc.s  0x10
0x9762d  ldarg.0
0x9762e  ldloc.1
0x9762f  callvirt instance string Member::get_ArraySource()
0x97634  ldloc.1
0x97635  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x9763a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x9763f  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x97644  call     instance void System.Xml.Serialization.XmlSerializationILGen::ILGenLoad(string source, class [mscorlib]System.Type type)
0x97649  ldarg.0
0x9764a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9764f  ldc.i4.0
0x97650  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x97655  ldarg.0
0x97656  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9765b  ldloc.3
0x9765c  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
  ... truncated ...
```
