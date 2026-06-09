# System.Xml.Serialization.XmlSerializationILGen::GenerateSerializerContract

- ea: `0x87f30`
- end: `0x881ed`
- name: `System.Xml.Serialization.XmlSerializationILGen::GenerateSerializerContract`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x66630`

## callees

- `0x63040`
- `0x630b0`
- `0x63220`
- `0x63280`
- `0x63810`
- `0x63830`
- `0x63b50`
- `0x63bc0`
- `0x643c0`
- `0x64950`
- `0x87550`
- `0x87620`
- `0x87c60`
- `0x87d60`

## string_xrefs

- `0x87f36`: `XmlSerializerContract`
- `0x88098`: `readMethods`
- `0x8809d`: `ReadMethods`
- `0x880ad`: `writeMethods`
- `0x880b2`: `WriteMethods`
- `0x87f62`: `Reader`
- `0x87f8f`: `get_Reader`
- `0x88003`: `Writer`
- `0x88030`: `get_Writer`

## pseudocode

```c

```

## disassembly

```asm
0x87f30  ldarg.0
0x87f31  ldfld    class [mscorlib]System.Reflection.Emit.ModuleBuilder System.Xml.Serialization.XmlSerializationILGen::moduleBuilder
0x87f36  ldstr    aXmlserializerc// "XmlSerializerContract"
0x87f3b  ldc.i4   0x100001
0x87f40  ldtoken  System.Xml.Serialization.XmlSerializerImplementation
0x87f45  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87f4a  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x87f4f  call     class [mscorlib]System.Reflection.Emit.TypeBuilder System.Xml.Serialization.CodeGenerator::CreateTypeBuilder(class [mscorlib]System.Reflection.Emit.ModuleBuilder moduleBuilder, string name, valuetype [mscorlib]System.Reflection.TypeAttributes attributes, class [mscorlib]System.Type parent, class [mscorlib]System.Type[] interfaces)
0x87f54  stloc.0
0x87f55  ldarg.0
0x87f56  ldloc.0
0x87f57  newobj   instance void System.Xml.Serialization.CodeGenerator::.ctor(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder)
0x87f5c  stfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87f61  ldloc.0
0x87f62  ldstr    aReader_2// "Reader"
0x87f67  ldc.i4.0
0x87f68  ldc.i4.s 0x20
0x87f6a  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x87f6f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87f74  ldnull
0x87f75  ldnull
0x87f76  ldnull
0x87f77  ldnull
0x87f78  ldnull
0x87f79  callvirt instance class [mscorlib]System.Reflection.Emit.PropertyBuilder [mscorlib]System.Reflection.Emit.TypeBuilder::DefineProperty(string, valuetype [mscorlib]System.Reflection.PropertyAttributes, valuetype [mscorlib]System.Reflection.CallingConventions, class [mscorlib]System.Type, class [mscorlib]System.Type[], class [mscorlib]System.Type[], class [mscorlib]System.Type[], class [mscorlib]System.Type[][], class [mscorlib]System.Type[][])
0x87f7e  stloc.1
0x87f7f  ldarg.0
0x87f80  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87f85  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x87f8a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87f8f  ldstr    aGetReader// "get_Reader"
0x87f94  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x87f99  ldsfld   string[] System.Xml.Serialization.CodeGenerator::EmptyStringArray
0x87f9e  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PublicOverrideMethodAttributes
0x87fa3  ldc.i4   0x800
0x87fa8  or
0x87fa9  callvirt instance void System.Xml.Serialization.CodeGenerator::BeginMethod(class [mscorlib]System.Type returnType, string methodName, class [mscorlib]System.Type[] argTypes, string[] argNames, valuetype [mscorlib]System.Reflection.MethodAttributes methodAttributes)
0x87fae  ldloc.1
0x87faf  ldarg.0
0x87fb0  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87fb5  callvirt instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.CodeGenerator::get_MethodBuilder()
0x87fba  callvirt instance void [mscorlib]System.Reflection.Emit.PropertyBuilder::SetGetMethod(class [mscorlib]System.Reflection.Emit.MethodBuilder)
0x87fbf  ldarg.0
0x87fc0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Serialization.XmlSerializationILGen::CreatedTypes
0x87fc5  ldarg.s  4
0x87fc7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::get_Item(void)
0x87fcc  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x87fd1  ldnull
0x87fd2  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x87fd7  ldnull
0x87fd8  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x87fdd  stloc.2
0x87fde  ldarg.0
0x87fdf  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87fe4  ldloc.2
0x87fe5  callvirt instance void System.Xml.Serialization.CodeGenerator::New(class [mscorlib]System.Reflection.ConstructorInfo constructorInfo)
0x87fea  ldarg.0
0x87feb  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87ff0  callvirt instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.CodeGenerator::EndMethod()
0x87ff5  pop
0x87ff6  ldarg.0
0x87ff7  ldloc.0
0x87ff8  newobj   instance void System.Xml.Serialization.CodeGenerator::.ctor(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder)
0x87ffd  stfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x88002  ldloc.0
0x88003  ldstr    aWriter_2// "Writer"
0x88008  ldc.i4.0
0x88009  ldc.i4.s 0x20
0x8800b  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0x88010  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x88015  ldnull
0x88016  ldnull
0x88017  ldnull
0x88018  ldnull
0x88019  ldnull
0x8801a  callvirt instance class [mscorlib]System.Reflection.Emit.PropertyBuilder [mscorlib]System.Reflection.Emit.TypeBuilder::DefineProperty(string, valuetype [mscorlib]System.Reflection.PropertyAttributes, valuetype [mscorlib]System.Reflection.CallingConventions, class [mscorlib]System.Type, class [mscorlib]System.Type[], class [mscorlib]System.Type[], class [mscorlib]System.Type[], class [mscorlib]System.Type[][], class [mscorlib]System.Type[][])
0x8801f  stloc.1
0x88020  ldarg.0
0x88021  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x88026  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0x8802b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x88030  ldstr    aGetWriter// "get_Writer"
0x88035  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x8803a  ldsfld   string[] System.Xml.Serialization.CodeGenerator::EmptyStringArray
0x8803f  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PublicOverrideMethodAttributes
0x88044  ldc.i4   0x800
0x88049  or
0x8804a  callvirt instance void System.Xml.Serialization.CodeGenerator::BeginMethod(class [mscorlib]System.Type returnType, string methodName, class [mscorlib]System.Type[] argTypes, string[] argNames, valuetype [mscorlib]System.Reflection.MethodAttributes methodAttributes)
0x8804f  ldloc.1
0x88050  ldarg.0
0x88051  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x88056  callvirt instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.CodeGenerator::get_MethodBuilder()
0x8805b  callvirt instance void [mscorlib]System.Reflection.Emit.PropertyBuilder::SetGetMethod(class [mscorlib]System.Reflection.Emit.MethodBuilder)
0x88060  ldarg.0
0x88061  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Serialization.XmlSerializationILGen::CreatedTypes
0x88066  ldarg.s  6
0x88068  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::get_Item(void)
0x8806d  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x88072  ldnull
0x88073  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x88078  ldnull
0x88079  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x8807e  stloc.2
0x8807f  ldarg.0
0x88080  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x88085  ldloc.2
0x88086  callvirt instance void System.Xml.Serialization.CodeGenerator::New(class [mscorlib]System.Reflection.ConstructorInfo constructorInfo)
0x8808b  ldarg.0
0x8808c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x88091  callvirt instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.CodeGenerator::EndMethod()
0x88096  pop
0x88097  ldarg.0
0x88098  ldstr    aReadmethods// "readMethods"
0x8809d  ldstr    aReadmethods_0// "ReadMethods"
0x880a2  ldarg.s  5
0x880a4  ldarg.2
0x880a5  ldloc.0
0x880a6  call     instance class [mscorlib]System.Reflection.Emit.FieldBuilder System.Xml.Serialization.XmlSerializationILGen::GeneratePublicMethods(string privateName, string publicName, string[] methods, class System.Xml.Serialization.XmlMapping[] xmlMappings, class [mscorlib]System.Reflection.Emit.TypeBuilder serializerContractTypeBuilder)
0x880ab  stloc.3
0x880ac  ldarg.0
0x880ad  ldstr    aWritemethods// "writeMethods"
0x880b2  ldstr    aWritemethods_0// "WriteMethods"
0x880b7  ldarg.s  7
0x880b9  ldarg.2
0x880ba  ldloc.0
0x880bb  call     instance class [mscorlib]System.Reflection.Emit.FieldBuilder System.Xml.Serialization.XmlSerializationILGen::GeneratePublicMethods(string privateName, string publicName, string[] methods, class System.Xml.Serialization.XmlMapping[] xmlMappings, class [mscorlib]System.Reflection.Emit.TypeBuilder serializerContractTypeBuilder)
0x880c0  stloc.s  4
0x880c2  ldarg.0
0x880c3  ldarg.s  8
0x880c5  ldloc.0
0x880c6  call     instance class [mscorlib]System.Reflection.Emit.FieldBuilder System.Xml.Serialization.XmlSerializationILGen::GenerateTypedSerializers(class [mscorlib]System.Collections.Hashtable serializers, class [mscorlib]System.Reflection.Emit.TypeBuilder serializerContractTypeBuilder)
0x880cb  stloc.s  5
0x880cd  ldarg.0
0x880ce  ldarg.3
0x880cf  ldloc.0
0x880d0  call     instance void System.Xml.Serialization.XmlSerializationILGen::GenerateSupportedTypes(class [mscorlib]System.Type[] types, class [mscorlib]System.Reflection.Emit.TypeBuilder serializerContractTypeBuilder)
0x880d5  ldarg.0
0x880d6  ldarg.s  8
0x880d8  ldarg.2
0x880d9  ldloc.0
0x880da  call     instance void System.Xml.Serialization.XmlSerializationILGen::GenerateGetSerializer(class [mscorlib]System.Collections.Hashtable serializers, class System.Xml.Serialization.XmlMapping[] xmlMappings, class [mscorlib]System.Reflection.Emit.TypeBuilder serializerContractTypeBuilder)
0x880df  ldtoken  System.Xml.Serialization.XmlSerializerImplementation
0x880e4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x880e9  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x880ee  ldnull
0x880ef  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x880f4  ldnull
0x880f5  call     instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x880fa  stloc.s  6
0x880fc  ldarg.0
0x880fd  ldloc.0
0x880fe  newobj   instance void System.Xml.Serialization.CodeGenerator::.ctor(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder)
0x88103  stfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x88108  ldarg.0
0x88109  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x8810e  ldtoken  [mscorlib]System.Void
0x88113  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x88118  ldstr    aCtor// ".ctor"
0x8811d  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x88122  ldsfld   string[] System.Xml.Serialization.CodeGenerator::EmptyStringArray
0x88127  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PublicMethodAttributes
0x8812c  ldc.i4   0x1000
0x88131  or
0x88132  ldc.i4   0x800
0x88137  or
0x88138  callvirt instance void System.Xml.Serialization.CodeGenerator::BeginMethod(class [mscorlib]System.Type returnType, string methodName, class [mscorlib]System.Type[] argTypes, string[] argNames, valuetype [mscorlib]System.Reflection.MethodAttributes methodAttributes)
0x8813d  ldarg.0
0x8813e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x88143  ldc.i4.0
0x88144  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x88149  ldarg.0
0x8814a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x8814f  ldnull
0x88150  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x88155  ldarg.0
0x88156  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x8815b  ldloc.3
0x8815c  callvirt instance void System.Xml.Serialization.CodeGenerator::StoreMember(class [mscorlib]System.Reflection.MemberInfo memberInfo)
0x88161  ldarg.0
0x88162  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x88167  ldc.i4.0
0x88168  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x8816d  ldarg.0
0x8816e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x88173  ldnull
0x88174  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x88179  ldarg.0
0x8817a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x8817f  ldloc.s  4
0x88181  callvirt instance void System.Xml.Serialization.CodeGenerator::StoreMember(class [mscorlib]System.Reflection.MemberInfo memberInfo)
0x88186  ldarg.0
0x88187  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x8818c  ldc.i4.0
0x8818d  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x88192  ldarg.0
0x88193  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x88198  ldnull
0x88199  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x8819e  ldarg.0
0x8819f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x881a4  ldloc.s  5
0x881a6  callvirt instance void System.Xml.Serialization.CodeGenerator::StoreMember(class [mscorlib]System.Reflection.MemberInfo memberInfo)
0x881ab  ldarg.0
0x881ac  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x881b1  ldc.i4.0
0x881b2  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x881b7  ldarg.0
0x881b8  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x881bd  ldloc.s  6
0x881bf  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.ConstructorInfo ctor)
0x881c4  ldarg.0
0x881c5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x881ca  callvirt instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.CodeGenerator::EndMethod()
0x881cf  pop
0x881d0  ldloc.0
0x881d1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Emit.TypeBuilder::CreateType()
0x881d6  stloc.s  7
0x881d8  ldarg.0
0x881d9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Serialization.XmlSerializationILGen::CreatedTypes
0x881de  ldloc.s  7
0x881e0  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x881e5  ldloc.s  7
0x881e7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::Add(var<u1>, !!T0)
0x881ec  ret
```
