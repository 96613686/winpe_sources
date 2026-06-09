# System.Xml.Serialization.XmlSerializationWriterILGen::WriteStructMethod

- ea: `0xa62e0`
- end: `0xa6c4c`
- name: `System.Xml.Serialization.XmlSerializationWriterILGen::WriteStructMethod`
- size: `2412`
- prototype: ``
- caller_count: `1`
- callee_count: `59`
- tags: `registry_config`

## callers

- `0xa4550`

## callees

- `0x63040`
- `0x63100`
- `0x63220`
- `0x632a0`
- `0x63480`
- `0x63610`
- `0x63690`
- `0x636b0`
- `0x636f0`
- `0x637d0`
- `0x63bc0`
- `0x63c50`
- `0x63c60`
- `0x63dc0`
- `0x640d0`
- `0x64260`
- `0x64320`
- `0x64380`
- `0x643a0`
- `0x643b0`
- `0x643c0`
- `0x64b80`
- `0x65610`
- `0x68990`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x69620`
- `0x69640`
- `0x69660`
- `0x69690`
- `0x696f0`
- `0x69710`
- `0x69730`
- `0x69ae0`
- `0x69b00`
- `0x69b20`
- `0x69b50`
- `0x69b90`
- `0x72bf0`
- `0x72d60`
- `0x72e40`
- `0x72e50`
- `0x746e0`
- `0x87190`
- `0x871e0`
- `0x872b0`
- `0x88210`
- `0xa4c80`
- `0xa5c30`

## string_xrefs

- `0xa6685`: `CreateUnknownTypeException`
- `0xa688b`: `WriteStartElement`
- `0xa642c`: `WriteNullTagLiteral`
- `0xa692e`: `WriteXsiType`
- `0xa65cc`: `WriteTypedPrimitive`

## pseudocode

```c

```

## disassembly

```asm
0xa62e0  ldarg.0
0xa62e1  call     instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationILGen::get_MethodNames()
0xa62e6  ldarg.1
0xa62e7  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xa62ec  castclass [mscorlib]System.String
0xa62f1  stloc.0
0xa62f2  ldarg.0
0xa62f3  ldarg.0
0xa62f4  ldfld    class [mscorlib]System.Reflection.Emit.TypeBuilder System.Xml.Serialization.XmlSerializationILGen::typeBuilder
0xa62f9  newobj   instance void System.Xml.Serialization.CodeGenerator::.ctor(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder)
0xa62fe  stfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6303  ldc.i4.5
0xa6304  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::.ctor(int32)
0xa6309  stloc.1
0xa630a  ldc.i4.5
0xa630b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(int32)
0xa6310  stloc.2
0xa6311  ldloc.1
0xa6312  ldtoken  [mscorlib]System.String
0xa6317  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa631c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0xa6321  ldloc.2
0xa6322  ldstr    aN_0// "n"
0xa6327  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xa632c  ldloc.1
0xa632d  ldtoken  [mscorlib]System.String
0xa6332  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6337  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0xa633c  ldloc.2
0xa633d  ldstr    aNs// "ns"
0xa6342  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xa6347  ldloc.1
0xa6348  ldarg.1
0xa6349  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa634e  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa6353  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0xa6358  ldloc.2
0xa6359  ldstr    aO_0// "o"
0xa635e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xa6363  ldarg.1
0xa6364  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa6369  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0xa636e  brfalse.s loc_A638B
0xa6370  ldloc.1
0xa6371  ldtoken  [mscorlib]System.Boolean
0xa6376  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa637b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0xa6380  ldloc.2
0xa6381  ldstr    aIsnullable_1// "isNullable"
0xa6386  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xa638b  ldloc.1
0xa638c  ldtoken  [mscorlib]System.Boolean
0xa6391  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6396  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0xa639b  ldloc.2
0xa639c  ldstr    aNeedtype// "needType"
0xa63a1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xa63a6  ldarg.0
0xa63a7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa63ac  ldtoken  [mscorlib]System.Void
0xa63b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa63b6  ldarg.0
0xa63b7  ldloc.0
0xa63b8  call     instance class System.Xml.Serialization.MethodBuilderInfo System.Xml.Serialization.XmlSerializationILGen::GetMethodBuilder(string methodName)
0xa63bd  ldloc.1
0xa63be  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::ToArray()
0xa63c3  ldloc.2
0xa63c4  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0xa63c9  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PrivateMethodAttributes
0xa63ce  callvirt instance void System.Xml.Serialization.CodeGenerator::BeginMethod(class [mscorlib]System.Type returnType, class System.Xml.Serialization.MethodBuilderInfo methodBuilderInfo, class [mscorlib]System.Type[] argTypes, string[] argNames, valuetype [mscorlib]System.Reflection.MethodAttributes methodAttributes)
0xa63d3  ldarg.1
0xa63d4  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa63d9  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0xa63de  brfalse  loc_A64B9
0xa63e3  ldarg.0
0xa63e4  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa63e9  ldarg.0
0xa63ea  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa63ef  ldstr    aO_0// "o"
0xa63f4  callvirt instance class System.Xml.Serialization.ArgBuilder System.Xml.Serialization.CodeGenerator::GetArg(string name)
0xa63f9  ldc.i4.1
0xa63fa  ldnull
0xa63fb  callvirt instance void System.Xml.Serialization.CodeGenerator::If(object value1, valuetype System.Xml.Serialization.Cmp cmpOp, object value2)
0xa6400  ldarg.0
0xa6401  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6406  ldarg.0
0xa6407  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa640c  ldstr    aIsnullable_1// "isNullable"
0xa6411  callvirt instance class System.Xml.Serialization.ArgBuilder System.Xml.Serialization.CodeGenerator::GetArg(string name)
0xa6416  ldc.i4.1
0xa6417  ldc.i4.1
0xa6418  box      [mscorlib]System.Boolean
0xa641d  callvirt instance void System.Xml.Serialization.CodeGenerator::If(object value1, valuetype System.Xml.Serialization.Cmp cmpOp, object value2)
0xa6422  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa6427  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa642c  ldstr    aWritenulltagli// "WriteNullTagLiteral"
0xa6431  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa6436  ldnull
0xa6437  ldc.i4.2
0xa6438  newarr   [mscorlib]System.Type
0xa643d  dup
0xa643e  ldc.i4.0
0xa643f  ldtoken  [mscorlib]System.String
0xa6444  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6449  stelem.ref
0xa644a  dup
0xa644b  ldc.i4.1
0xa644c  ldtoken  [mscorlib]System.String
0xa6451  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6456  stelem.ref
0xa6457  ldnull
0xa6458  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa645d  stloc.s  6
0xa645f  ldarg.0
0xa6460  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6465  ldc.i4.0
0xa6466  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa646b  ldarg.0
0xa646c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6471  ldstr    aN_0// "n"
0xa6476  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0xa647b  ldarg.0
0xa647c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6481  ldstr    aNs// "ns"
0xa6486  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0xa648b  ldarg.0
0xa648c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6491  ldloc.s  6
0xa6493  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa6498  ldarg.0
0xa6499  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa649e  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0xa64a3  ldarg.0
0xa64a4  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa64a9  callvirt instance void System.Xml.Serialization.CodeGenerator::GotoMethodEnd()
0xa64ae  ldarg.0
0xa64af  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa64b4  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0xa64b9  ldarg.0
0xa64ba  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa64bf  ldarg.0
0xa64c0  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa64c5  ldstr    aNeedtype// "needType"
0xa64ca  callvirt instance class System.Xml.Serialization.ArgBuilder System.Xml.Serialization.CodeGenerator::GetArg(string name)
0xa64cf  ldc.i4.4
0xa64d0  ldc.i4.1
0xa64d1  box      [mscorlib]System.Boolean
0xa64d6  callvirt instance void System.Xml.Serialization.CodeGenerator::If(object value1, valuetype System.Xml.Serialization.Cmp cmpOp, object value2)
0xa64db  ldarg.0
0xa64dc  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa64e1  ldtoken  [mscorlib]System.Type
0xa64e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa64eb  ldstr    aT_0// "t"
0xa64f0  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareLocal(class [mscorlib]System.Type type, string name)
0xa64f5  stloc.3
0xa64f6  ldtoken  [mscorlib]System.Object
0xa64fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6500  ldstr    aGettype_1// "GetType"
0xa6505  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa650a  ldnull
0xa650b  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0xa6510  ldnull
0xa6511  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa6516  stloc.s  4
0xa6518  ldarg.0
0xa6519  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa651e  ldstr    aO_0// "o"
0xa6523  callvirt instance class System.Xml.Serialization.ArgBuilder System.Xml.Serialization.CodeGenerator::GetArg(string name)
0xa6528  stloc.s  5
0xa652a  ldarg.0
0xa652b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6530  ldloc.s  5
0xa6532  callvirt instance void System.Xml.Serialization.CodeGenerator::LdargAddress(class System.Xml.Serialization.ArgBuilder argBuilder)
0xa6537  ldarg.0
0xa6538  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa653d  ldloc.s  5
0xa653f  ldfld    class [mscorlib]System.Type System.Xml.Serialization.ArgBuilder::ArgType
0xa6544  ldtoken  [mscorlib]System.Object
0xa6549  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa654e  callvirt instance void System.Xml.Serialization.CodeGenerator::ConvertAddress(class [mscorlib]System.Type source, class [mscorlib]System.Type target)
0xa6553  ldarg.0
0xa6554  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6559  ldloc.s  4
0xa655b  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa6560  ldarg.0
0xa6561  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6566  ldloc.3
0xa6567  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0xa656c  ldarg.0
0xa656d  ldstr    aT_0// "t"
0xa6572  ldarg.1
0xa6573  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa6578  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa657d  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteTypeCompare(string variable, class [mscorlib]System.Type type)
0xa6582  ldarg.0
0xa6583  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6588  callvirt instance void System.Xml.Serialization.CodeGenerator::If()
0xa658d  ldarg.0
0xa658e  ldarg.1
0xa658f  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteDerivedTypes(class System.Xml.Serialization.StructMapping mapping)
0xa6594  ldarg.1
0xa6595  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa659a  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0xa659f  brfalse.s loc_A65A7
0xa65a1  ldarg.0
0xa65a2  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteEnumAndArrayTypes()
0xa65a7  ldarg.0
0xa65a8  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa65ad  callvirt instance void System.Xml.Serialization.CodeGenerator::Else()
0xa65b2  ldarg.1
0xa65b3  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa65b8  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0xa65bd  brfalse  loc_A667B
0xa65c2  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa65c7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa65cc  ldstr    aWritetypedprim_0// "WriteTypedPrimitive"
0xa65d1  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa65d6  ldnull
0xa65d7  ldc.i4.4
0xa65d8  newarr   [mscorlib]System.Type
0xa65dd  dup
0xa65de  ldc.i4.0
0xa65df  ldtoken  [mscorlib]System.String
0xa65e4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa65e9  stelem.ref
0xa65ea  dup
0xa65eb  ldc.i4.1
0xa65ec  ldtoken  [mscorlib]System.String
0xa65f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa65f6  stelem.ref
0xa65f7  dup
0xa65f8  ldc.i4.2
0xa65f9  ldtoken  [mscorlib]System.Object
0xa65fe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6603  stelem.ref
0xa6604  dup
0xa6605  ldc.i4.3
0xa6606  ldtoken  [mscorlib]System.Boolean
0xa660b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6610  stelem.ref
0xa6611  ldnull
0xa6612  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa6617  stloc.s  7
0xa6619  ldarg.0
0xa661a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa661f  ldc.i4.0
0xa6620  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa6625  ldarg.0
0xa6626  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa662b  ldstr    aN_0// "n"
0xa6630  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0xa6635  ldarg.0
0xa6636  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa663b  ldstr    aNs// "ns"
0xa6640  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0xa6645  ldarg.0
0xa6646  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa664b  ldstr    aO_0// "o"
0xa6650  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0xa6655  ldarg.0
0xa6656  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa665b  ldc.i4.1
0xa665c  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(bool boolVar)
0xa6661  ldarg.0
0xa6662  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6667  ldloc.s  7
0xa6669  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa666e  ldarg.0
0xa666f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6674  callvirt instance void System.Xml.Serialization.CodeGenerator::GotoMethodEnd()
0xa6679  br.s     loc_A66F8
0xa667b  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa6680  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6685  ldstr    aCreateunknownt// "CreateUnknownTypeException"
0xa668a  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa668f  ldnull
0xa6690  ldc.i4.1
0xa6691  newarr   [mscorlib]System.Type
0xa6696  dup
0xa6697  ldc.i4.0
0xa6698  ldtoken  [mscorlib]System.Object
0xa669d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa66a2  stelem.ref
0xa66a3  ldnull
0xa66a4  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa66a9  stloc.s  8
0xa66ab  ldarg.0
0xa66ac  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa66b1  ldc.i4.0
0xa66b2  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa66b7  ldarg.0
0xa66b8  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa66bd  ldloc.s  5
0xa66bf  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(class System.Xml.Serialization.ArgBuilder arg)
0xa66c4  ldarg.0
0xa66c5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa66ca  ldloc.s  5
0xa66cc  ldfld    class [mscorlib]System.Type System.Xml.Serialization.ArgBuilder::ArgType
0xa66d1  ldtoken  [mscorlib]System.Object
0xa66d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
  ... truncated ...
```
