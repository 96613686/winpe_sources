# System.Xml.Serialization.XmlSerializationReaderILGen::WriteLiteralStructMethod

- ea: `0x96090`
- end: `0x96f4d`
- name: `System.Xml.Serialization.XmlSerializationReaderILGen::WriteLiteralStructMethod`
- size: `3773`
- prototype: ``
- caller_count: `1`
- callee_count: `85`
- tags: `registry_config`

## callers

- `0x96080`

## callees

- `0x622f0`
- `0x63040`
- `0x63100`
- `0x63220`
- `0x63290`
- `0x632b0`
- `0x632c0`
- `0x632f0`
- `0x63480`
- `0x63610`
- `0x63640`
- `0x636b0`
- `0x636f0`
- `0x637d0`
- `0x63830`
- `0x63bc0`
- `0x63d40`
- `0x63dc0`
- `0x640d0`
- `0x64100`
- `0x64260`
- `0x642b0`
- `0x642f0`
- `0x64320`
- `0x64340`
- `0x643a0`
- `0x643c0`
- `0x645a0`
- `0x645b0`
- `0x64620`
- `0x64640`
- `0x646a0`
- `0x646c0`
- `0x65610`
- `0x68600`
- `0x68660`
- `0x68690`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x691c0`
- `0x69420`
- `0x69600`
- `0x69620`
- `0x69640`
- `0x69660`
- `0x696f0`
- `0x69b00`
- `0x69b20`
- `0x69bf0`

## string_xrefs

- `0x96566`: `http://www.w3.org/2001/XMLSchema`
- `0x96c4a`: `get_Reader`
- `0x9694c`: `paramsRead[`
- `0x96a5e`: `XmlSequenceHierarchy`
- `0x96e4f`: `MoveToContent`
- `0x96c6c`: `MoveToElement`
- `0x96da6`: `ReadStartElement`
- `0x96eb2`: `ReadEndElement`
- `0x961a0`: `ReadNull`
- `0x9632c`: `ReadTypedNull`
- `0x9651e`: `ReadTypedPrimitive`
- `0x96604`: `ReadTypedPrimitive`
- `0x96685`: `CreateUnknownTypeException`
- `0x96781`: `CreateAbstractTypeException`

## pseudocode

```c

```

## disassembly

```asm
0x96090  ldarg.0
0x96091  call     instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationILGen::get_MethodNames()
0x96096  ldarg.1
0x96097  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x9609c  castclass [mscorlib]System.String
0x960a1  stloc.0
0x960a2  ldarg.1
0x960a3  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x960a8  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x960ad  stloc.1
0x960ae  ldarg.0
0x960af  ldarg.0
0x960b0  ldfld    class [mscorlib]System.Reflection.Emit.TypeBuilder System.Xml.Serialization.XmlSerializationILGen::typeBuilder
0x960b5  newobj   instance void System.Xml.Serialization.CodeGenerator::.ctor(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder)
0x960ba  stfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x960bf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::.ctor()
0x960c4  stloc.2
0x960c5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x960ca  stloc.3
0x960cb  ldarg.1
0x960cc  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x960d1  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0x960d6  brfalse.s loc_960F3
0x960d8  ldloc.2
0x960d9  ldtoken  [mscorlib]System.Boolean
0x960de  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x960e3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x960e8  ldloc.3
0x960e9  ldstr    aIsnullable_1// "isNullable"
0x960ee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x960f3  ldloc.2
0x960f4  ldtoken  [mscorlib]System.Boolean
0x960f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x960fe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x96103  ldloc.3
0x96104  ldstr    aChecktype// "checkType"
0x96109  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9610e  ldarg.0
0x9610f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96114  ldarg.1
0x96115  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9611a  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x9611f  ldarg.0
0x96120  ldloc.0
0x96121  call     instance class System.Xml.Serialization.MethodBuilderInfo System.Xml.Serialization.XmlSerializationILGen::GetMethodBuilder(string methodName)
0x96126  ldloc.2
0x96127  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::ToArray()
0x9612c  ldloc.3
0x9612d  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x96132  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PrivateMethodAttributes
0x96137  callvirt instance void System.Xml.Serialization.CodeGenerator::BeginMethod(class [mscorlib]System.Type returnType, class System.Xml.Serialization.MethodBuilderInfo methodBuilderInfo, class [mscorlib]System.Type[] argTypes, string[] argNames, valuetype [mscorlib]System.Reflection.MethodAttributes methodAttributes)
0x9613c  ldarg.0
0x9613d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96142  ldtoken  System.Xml.XmlQualifiedName
0x96147  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9614c  ldstr    aXsitype// "xsiType"
0x96151  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareLocal(class [mscorlib]System.Type type, string name)
0x96156  stloc.s  4
0x96158  ldarg.0
0x96159  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9615e  ldtoken  [mscorlib]System.Boolean
0x96163  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x96168  ldstr    aIsnull// "isNull"
0x9616d  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareLocal(class [mscorlib]System.Type type, string name)
0x96172  stloc.s  5
0x96174  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x96179  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9617e  ldstr    aGetxsitype// "GetXsiType"
0x96183  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x96188  ldnull
0x96189  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x9618e  ldnull
0x9618f  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x96194  stloc.s  6
0x96196  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x9619b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x961a0  ldstr    aReadnull// "ReadNull"
0x961a5  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x961aa  ldnull
0x961ab  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x961b0  ldnull
0x961b1  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x961b6  stloc.s  7
0x961b8  ldarg.0
0x961b9  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x961be  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::DefineLabel()
0x961c3  stloc.s  8
0x961c5  ldarg.0
0x961c6  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x961cb  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::DefineLabel()
0x961d0  stloc.s  9
0x961d2  ldarg.0
0x961d3  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x961d8  ldstr    aChecktype// "checkType"
0x961dd  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0x961e2  ldarg.0
0x961e3  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x961e8  ldloc.s  8
0x961ea  callvirt instance void System.Xml.Serialization.CodeGenerator::Brtrue(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x961ef  ldarg.0
0x961f0  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x961f5  ldnull
0x961f6  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x961fb  ldarg.0
0x961fc  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96201  ldloc.s  9
0x96203  callvirt instance void System.Xml.Serialization.CodeGenerator::Br_S(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x96208  ldarg.0
0x96209  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9620e  ldloc.s  8
0x96210  callvirt instance void System.Xml.Serialization.CodeGenerator::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x96215  ldarg.0
0x96216  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9621b  ldc.i4.0
0x9621c  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x96221  ldarg.0
0x96222  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96227  ldloc.s  6
0x96229  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x9622e  ldarg.0
0x9622f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96234  ldloc.s  9
0x96236  callvirt instance void System.Xml.Serialization.CodeGenerator::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x9623b  ldarg.0
0x9623c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96241  ldloc.s  4
0x96243  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x96248  ldarg.0
0x96249  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9624e  ldc.i4.0
0x9624f  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(bool boolVar)
0x96254  ldarg.0
0x96255  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9625a  ldloc.s  5
0x9625c  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x96261  ldarg.1
0x96262  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x96267  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0x9626c  brfalse.s loc_962BA
0x9626e  ldarg.0
0x9626f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96274  ldstr    aIsnullable_1// "isNullable"
0x96279  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0x9627e  ldarg.0
0x9627f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96284  callvirt instance void System.Xml.Serialization.CodeGenerator::If()
0x96289  ldarg.0
0x9628a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9628f  ldc.i4.0
0x96290  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x96295  ldarg.0
0x96296  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9629b  ldloc.s  7
0x9629d  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x962a2  ldarg.0
0x962a3  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x962a8  ldloc.s  5
0x962aa  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x962af  ldarg.0
0x962b0  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x962b5  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0x962ba  ldarg.0
0x962bb  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x962c0  ldstr    aChecktype// "checkType"
0x962c5  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0x962ca  ldarg.0
0x962cb  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x962d0  callvirt instance void System.Xml.Serialization.CodeGenerator::If()
0x962d5  ldarg.1
0x962d6  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x962db  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x962e0  brfalse  loc_96412
0x962e5  ldarg.0
0x962e6  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x962eb  ldloc.s  5
0x962ed  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x962f2  ldarg.0
0x962f3  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x962f8  callvirt instance void System.Xml.Serialization.CodeGenerator::If()
0x962fd  ldarg.0
0x962fe  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96303  ldloc.s  4
0x96305  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x9630a  ldarg.0
0x9630b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96310  ldnull
0x96311  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x96316  ldarg.0
0x96317  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9631c  ldc.i4.4
0x9631d  callvirt instance void System.Xml.Serialization.CodeGenerator::If(valuetype System.Xml.Serialization.Cmp cmpOp)
0x96322  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x96327  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9632c  ldstr    aReadtypednull// "ReadTypedNull"
0x96331  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x96336  ldnull
0x96337  ldc.i4.1
0x96338  newarr   [mscorlib]System.Type
0x9633d  dup
0x9633e  ldc.i4.0
0x9633f  ldloc.s  4
0x96341  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.LocalVariableInfo::get_LocalType()
0x96346  stelem.ref
0x96347  ldnull
0x96348  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x9634d  stloc.s  0xA
0x9634f  ldarg.0
0x96350  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96355  ldc.i4.0
0x96356  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x9635b  ldarg.0
0x9635c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96361  ldloc.s  4
0x96363  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x96368  ldarg.0
0x96369  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9636e  ldloc.s  0xA
0x96370  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x96375  ldarg.0
0x96376  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9637b  ldarg.0
0x9637c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96381  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::get_ReturnLocal()
0x96386  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x9638b  ldarg.0
0x9638c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96391  ldarg.0
0x96392  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96397  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::get_ReturnLabel()
0x9639c  callvirt instance void System.Xml.Serialization.CodeGenerator::Br(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x963a1  ldarg.0
0x963a2  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x963a7  callvirt instance void System.Xml.Serialization.CodeGenerator::Else()
0x963ac  ldarg.1
0x963ad  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x963b2  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsValueType()
0x963b7  brfalse.s loc_963C4
0x963b9  ldstr    aArgNevervaluet// "Arg_NeverValueType"
0x963be  call     class [mscorlib]System.Exception System.Xml.Serialization.CodeGenerator::NotSupported(string msg)
0x963c3  throw
0x963c4  ldarg.0
0x963c5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x963ca  ldnull
0x963cb  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x963d0  ldarg.0
0x963d1  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x963d6  ldarg.0
0x963d7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x963dc  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::get_ReturnLocal()
0x963e1  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x963e6  ldarg.0
0x963e7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x963ec  ldarg.0
0x963ed  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x963f2  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::get_ReturnLabel()
0x963f7  callvirt instance void System.Xml.Serialization.CodeGenerator::Br(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x963fc  ldarg.0
0x963fd  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96402  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0x96407  ldarg.0
0x96408  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9640d  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0x96412  ldarg.0
0x96413  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96418  ldtoken  System.Xml.XmlQualifiedName
0x9641d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x96422  ldstr    aXsitype// "xsiType"
0x96427  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Type type, string name)
0x9642c  ldarg.0
0x9642d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96432  ldnull
0x96433  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x96438  ldarg.0
0x96439  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9643e  callvirt instance void System.Xml.Serialization.CodeGenerator::Ceq()
0x96443  ldarg.1
0x96444  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x96449  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x9644e  brtrue.s loc_964C1
0x96450  ldarg.0
0x96451  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96456  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::DefineLabel()
0x9645b  stloc.s  8
0x9645d  ldarg.0
0x9645e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96463  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::DefineLabel()
0x96468  stloc.s  9
0x9646a  ldarg.0
0x9646b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x96470  ldloc.s  8
0x96472  callvirt instance void System.Xml.Serialization.CodeGenerator::Brtrue(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x96477  ldarg.0
0x96478  ldstr    aXsitype// "xsiType"
0x9647d  ldarg.1
0x9647e  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x96483  ldarg.1
0x96484  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x96489  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteQNameEqual(string source, string name, string ns)
0x9648e  ldarg.0
0x9648f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
  ... truncated ...
```
