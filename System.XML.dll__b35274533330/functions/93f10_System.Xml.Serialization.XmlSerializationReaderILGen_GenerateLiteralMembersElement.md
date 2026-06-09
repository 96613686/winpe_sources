# System.Xml.Serialization.XmlSerializationReaderILGen::GenerateLiteralMembersElement

- ea: `0x93f10`
- end: `0x9472a`
- name: `System.Xml.Serialization.XmlSerializationReaderILGen::GenerateLiteralMembersElement`
- size: `2074`
- prototype: ``
- caller_count: `1`
- callee_count: `58`
- tags: `registry_config`

## callers

- `0x93e60`

## callees

- `0x63040`
- `0x630b0`
- `0x63220`
- `0x632b0`
- `0x632c0`
- `0x63480`
- `0x63610`
- `0x636f0`
- `0x637d0`
- `0x63870`
- `0x63bc0`
- `0x640d0`
- `0x64100`
- `0x642b0`
- `0x642f0`
- `0x64320`
- `0x643c0`
- `0x646c0`
- `0x64c00`
- `0x68600`
- `0x68660`
- `0x68690`
- `0x686d0`
- `0x686f0`
- `0x69620`
- `0x69640`
- `0x69660`
- `0x696f0`
- `0x69730`
- `0x69b00`
- `0x69b20`
- `0x69bb0`
- `0x69bf0`
- `0x69ce0`
- `0x69d20`
- `0x72ba0`
- `0x72dd0`
- `0x72e10`
- `0x79510`
- `0x93b40`
- `0x93c40`
- `0x93e70`
- `0x93f10`
- `0x94730`
- `0x949a0`
- `0x972b0`
- `0x97eb0`
- `0x981d0`
- `0x982d0`
- `0x98990`

## string_xrefs

- `0x93fa8`: `get_Reader`
- `0x94167`: `paramsRead[`
- `0x93fca`: `MoveToContent`
- `0x94452`: `MoveToElement`
- `0x94595`: `ReadStartElement`
- `0x94685`: `ReadEndElement`

## pseudocode

```c

```

## disassembly

```asm
0x93f10  ldarg.1
0x93f11  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x93f16  stloc.0
0x93f17  ldloc.0
0x93f18  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x93f1d  castclass System.Xml.Serialization.MembersMapping
0x93f22  callvirt instance class System.Xml.Serialization.MemberMapping[] System.Xml.Serialization.MembersMapping::get_Members()
0x93f27  stloc.1
0x93f28  ldloc.0
0x93f29  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x93f2e  castclass System.Xml.Serialization.MembersMapping
0x93f33  callvirt instance bool System.Xml.Serialization.MembersMapping::get_HasWrapperElement()
0x93f38  stloc.2
0x93f39  ldarg.0
0x93f3a  ldloc.0
0x93f3b  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x93f40  call     instance string System.Xml.Serialization.XmlSerializationReaderILGen::NextMethodName(string name)
0x93f45  stloc.3
0x93f46  ldarg.0
0x93f47  ldarg.0
0x93f48  ldfld    class [mscorlib]System.Reflection.Emit.TypeBuilder System.Xml.Serialization.XmlSerializationILGen::typeBuilder
0x93f4d  newobj   instance void System.Xml.Serialization.CodeGenerator::.ctor(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder)
0x93f52  stfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x93f57  ldarg.0
0x93f58  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x93f5d  ldtoken  object[]
0x93f62  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93f67  ldloc.3
0x93f68  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x93f6d  ldsfld   string[] System.Xml.Serialization.CodeGenerator::EmptyStringArray
0x93f72  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PublicMethodAttributes
0x93f77  callvirt instance void System.Xml.Serialization.CodeGenerator::BeginMethod(class [mscorlib]System.Type returnType, string methodName, class [mscorlib]System.Type[] argTypes, string[] argNames, valuetype [mscorlib]System.Reflection.MethodAttributes methodAttributes)
0x93f7c  ldarg.0
0x93f7d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x93f82  ldnull
0x93f83  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x93f88  ldarg.0
0x93f89  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x93f8e  ldarg.0
0x93f8f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x93f94  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::get_ReturnLocal()
0x93f99  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x93f9e  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x93fa3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93fa8  ldstr    aGetReader// "get_Reader"
0x93fad  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x93fb2  ldnull
0x93fb3  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x93fb8  ldnull
0x93fb9  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x93fbe  stloc.s  4
0x93fc0  ldtoken  System.Xml.XmlReader
0x93fc5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93fca  ldstr    aMovetocontent// "MoveToContent"
0x93fcf  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x93fd4  ldnull
0x93fd5  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x93fda  ldnull
0x93fdb  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x93fe0  stloc.s  5
0x93fe2  ldarg.0
0x93fe3  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x93fe8  ldc.i4.0
0x93fe9  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x93fee  ldarg.0
0x93fef  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x93ff4  ldloc.s  4
0x93ff6  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x93ffb  ldarg.0
0x93ffc  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94001  ldloc.s  5
0x94003  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x94008  ldarg.0
0x94009  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9400e  callvirt instance void System.Xml.Serialization.CodeGenerator::Pop()
0x94013  ldarg.0
0x94014  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94019  ldtoken  object[]
0x9401e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94023  ldstr    aP// "p"
0x94028  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareLocal(class [mscorlib]System.Type type, string name)
0x9402d  stloc.s  6
0x9402f  ldarg.0
0x94030  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94035  ldtoken  [mscorlib]System.Object
0x9403a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9403f  ldloc.1
0x94040  ldlen
0x94041  conv.i4
0x94042  box      [mscorlib]System.Int32
0x94047  callvirt instance void System.Xml.Serialization.CodeGenerator::NewArray(class [mscorlib]System.Type elementType, object len)
0x9404c  ldarg.0
0x9404d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94052  ldloc.s  6
0x94054  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x94059  ldarg.0
0x9405a  ldstr    aP// "p"
0x9405f  ldloc.1
0x94060  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::InitializeValueTypes(string arrayName, class System.Xml.Serialization.MemberMapping[] mappings)
0x94065  ldc.i4.0
0x94066  stloc.s  7
0x94068  ldloc.2
0x94069  brfalse.s loc_94095
0x9406b  ldarg.0
0x9406c  call     instance int32 System.Xml.Serialization.XmlSerializationReaderILGen::WriteWhileNotLoopStart()
0x94071  stloc.s  7
0x94073  ldarg.0
0x94074  ldloc.0
0x94075  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x9407a  ldloc.0
0x9407b  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x94080  ldc.i4.1
0x94081  beq.s    loc_9408A
0x94083  ldstr    asc_1284AE// ""
0x94088  br.s     loc_94090
0x9408a  ldloc.0
0x9408b  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x94090  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteIsStartTag(string name, string ns)
0x94095  ldnull
0x94096  stloc.s  8
0x94098  ldnull
0x94099  stloc.s  9
0x9409b  ldnull
0x9409c  stloc.s  0xA
0x9409e  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x940a3  stloc.s  0xB
0x940a5  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x940aa  stloc.s  0xC
0x940ac  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x940b1  stloc.s  0xD
0x940b3  ldc.i4.0
0x940b4  stloc.s  0x12
0x940b6  br       loc_94355
0x940bb  ldloc.1
0x940bc  ldloc.s  0x12
0x940be  ldelem.ref
0x940bf  stloc.s  0x13
0x940c1  ldstr    aP_0// "p["
0x940c6  ldloca.s 0x12
0x940c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x940cd  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x940d2  ldstr    asc_12BE9E// "]"
0x940d7  call     string [mscorlib]System.String::Concat(string, string, string)
0x940dc  stloc.s  0x14
0x940de  ldloc.s  0x14
0x940e0  stloc.s  0x15
0x940e2  ldloc.s  0x13
0x940e4  callvirt instance class System.Xml.Serialization.XmlnsAccessor System.Xml.Serialization.AccessorMapping::get_Xmlns()
0x940e9  brfalse.s loc_94124
0x940eb  ldc.i4.5
0x940ec  newarr   [mscorlib]System.String
0x940f1  dup
0x940f2  ldc.i4.0
0x940f3  ldstr    asc_12FF58// "(("
0x940f8  stelem.ref
0x940f9  dup
0x940fa  ldc.i4.1
0x940fb  ldloc.s  0x13
0x940fd  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x94102  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x94107  stelem.ref
0x94108  dup
0x94109  ldc.i4.2
0x9410a  ldstr    asc_129CD8// ")"
0x9410f  stelem.ref
0x94110  dup
0x94111  ldc.i4.3
0x94112  ldloc.s  0x14
0x94114  stelem.ref
0x94115  dup
0x94116  ldc.i4.4
0x94117  ldstr    asc_129CD8// ")"
0x9411c  stelem.ref
0x9411d  call     string [mscorlib]System.String::Concat(string[])
0x94122  stloc.s  0x15
0x94124  ldarg.0
0x94125  ldloc.1
0x94126  ldloc.s  0x13
0x94128  call     instance string System.Xml.Serialization.XmlSerializationReaderILGen::GetChoiceIdentifierSource(class System.Xml.Serialization.MemberMapping[] mappings, class System.Xml.Serialization.MemberMapping member)
0x9412d  stloc.s  0x16
0x9412f  ldarg.0
0x94130  ldloc.s  0x14
0x94132  ldloc.s  0x15
0x94134  ldstr    aA_0// "a"
0x94139  ldloc.s  0x12
0x9413b  ldloc.s  0x13
0x9413d  ldloc.s  0x16
0x9413f  newobj   instance void Member::.ctor(class System.Xml.Serialization.XmlSerializationReaderILGen outerClass, string source, string arraySource, string arrayName, int32 i, class System.Xml.Serialization.MemberMapping mapping, string choiceSource)
0x94144  stloc.s  0x17
0x94146  ldarg.0
0x94147  ldloc.s  0x14
0x94149  ldnull
0x9414a  ldstr    aA_0// "a"
0x9414f  ldloc.s  0x12
0x94151  ldloc.s  0x13
0x94153  ldloc.s  0x16
0x94155  newobj   instance void Member::.ctor(class System.Xml.Serialization.XmlSerializationReaderILGen outerClass, string source, string arraySource, string arrayName, int32 i, class System.Xml.Serialization.MemberMapping mapping, string choiceSource)
0x9415a  stloc.s  0x18
0x9415c  ldloc.s  0x13
0x9415e  callvirt instance bool System.Xml.Serialization.MemberMapping::get_IsSequence()
0x94163  brtrue.s loc_94187
0x94165  ldloc.s  0x17
0x94167  ldstr    aParamsread// "paramsRead["
0x9416c  ldloca.s 0x12
0x9416e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x94173  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x94178  ldstr    asc_12BE9E// "]"
0x9417d  call     string [mscorlib]System.String::Concat(string, string, string)
0x94182  callvirt instance void Member::set_ParamsReadSource(string value)
0x94187  ldloc.s  0x13
0x94189  callvirt instance valuetype System.Xml.Serialization.SpecifiedAccessor System.Xml.Serialization.MemberMapping::get_CheckSpecified()
0x9418e  ldc.i4.2
0x9418f  bne.un.s loc_941EC
0x94191  ldloc.s  0x13
0x94193  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x94198  ldstr    aSpecified// "Specified"
0x9419d  call     string [mscorlib]System.String::Concat(string, string)
0x941a2  stloc.s  0x1A
0x941a4  ldc.i4.0
0x941a5  stloc.s  0x1B
0x941a7  br.s     loc_941E5
0x941a9  ldloc.1
0x941aa  ldloc.s  0x1B
0x941ac  ldelem.ref
0x941ad  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x941b2  ldloc.s  0x1A
0x941b4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x941b9  brfalse.s loc_941DF
0x941bb  ldloc.s  0x17
0x941bd  ldstr    aP_0// "p["
0x941c2  ldloca.s 0x1B
0x941c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x941c9  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x941ce  ldstr    asc_12BE9E// "]"
0x941d3  call     string [mscorlib]System.String::Concat(string, string, string)
0x941d8  callvirt instance void Member::set_CheckSpecifiedSource(string value)
0x941dd  br.s     loc_941EC
0x941df  ldloc.s  0x1B
0x941e1  ldc.i4.1
0x941e2  add
0x941e3  stloc.s  0x1B
0x941e5  ldloc.s  0x1B
0x941e7  ldloc.1
0x941e8  ldlen
0x941e9  conv.i4
0x941ea  blt.s    loc_941A9
0x941ec  ldc.i4.0
0x941ed  stloc.s  0x19
0x941ef  ldloc.s  0x13
0x941f1  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x941f6  brfalse.s loc_941FC
0x941f8  ldloc.s  0x18
0x941fa  stloc.s  8
0x941fc  ldloc.s  0x13
0x941fe  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x94203  brfalse.s loc_94217
0x94205  ldloc.s  0x13
0x94207  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x9420c  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x94211  brfalse.s loc_94217
0x94213  ldloc.s  0x18
0x94215  stloc.s  0xA
0x94217  ldloc.s  0x13
0x94219  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x9421e  brtrue.s loc_94229
0x94220  ldloc.s  0x13
0x94222  callvirt instance class System.Xml.Serialization.XmlnsAccessor System.Xml.Serialization.AccessorMapping::get_Xmlns()
0x94227  brfalse.s loc_94235
0x94229  ldloc.s  0xD
0x9422b  ldloc.s  0x17
0x9422d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x94232  pop
0x94233  br.s     loc_94248
0x94235  ldloc.s  0x13
0x94237  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x9423c  brfalse.s loc_94248
0x9423e  ldloc.s  0xC
0x94240  ldloc.s  0x17
0x94242  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x94247  pop
0x94248  ldloc.s  0x13
0x9424a  callvirt instance bool System.Xml.Serialization.MemberMapping::get_IsSequence()
0x9424f  brtrue.s loc_942B5
0x94251  ldc.i4.0
0x94252  stloc.s  0x1C
0x94254  br.s     loc_942A8
0x94256  ldloc.s  0x13
0x94258  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x9425d  ldloc.s  0x1C
0x9425f  ldelem.ref
0x94260  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x94265  brfalse.s loc_942A2
0x94267  ldloc.s  0x13
0x94269  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x9426e  ldloc.s  0x1C
0x94270  ldelem.ref
0x94271  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x94276  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9427b  brtrue.s loc_942A2
0x9427d  ldloc.s  0x18
  ... truncated ...
```
