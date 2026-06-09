# System.Xml.Serialization.XmlSerializationReaderILGen::WriteText

- ea: `0x98590`
- end: `0x98902`
- name: `System.Xml.Serialization.XmlSerializationReaderILGen::WriteText`
- size: `882`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config`

## callers

- `0x983b0`

## callees

- `0x62370`
- `0x632b0`
- `0x637d0`
- `0x640d0`
- `0x642b0`
- `0x64320`
- `0x643c0`
- `0x68600`
- `0x68c50`
- `0x696f0`
- `0x72bf0`
- `0x72c00`
- `0x72c10`
- `0x72cf0`
- `0x871a0`
- `0x94a20`
- `0x98590`
- `0x991b0`
- `0x991c0`
- `0x99470`
- `0x123090`
- `0x1230c0`
- `0x1230e0`

## string_xrefs

- `0x986c0`: `XmlInternalError`
- `0x985ea`: `get_Reader`
- `0x98727`: `get_Reader`
- `0x988db`: `Reader.ReadString()`
- `0x9860b`: `ReadString`
- `0x98749`: `ReadString`
- `0x9882c`: `ReadString`
- `0x9864e`: `CreateTextNode`

## pseudocode

```c

```

## disassembly

```asm
0x98590  ldarg.1
0x98591  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x98596  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x9859b  stloc.0
0x9859c  ldloc.0
0x9859d  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x985a2  isinst   System.Xml.Serialization.SpecialMapping
0x985a7  brfalse  loc_986E8
0x985ac  ldloc.0
0x985ad  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x985b2  castclass System.Xml.Serialization.SpecialMapping
0x985b7  stloc.1
0x985b8  ldarg.0
0x985b9  ldarg.1
0x985ba  callvirt instance string Member::get_ArraySource()
0x985bf  ldloc.1
0x985c0  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x985c5  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBeginTyped(string source, class System.Xml.Serialization.TypeDesc typeDesc)
0x985ca  ldloc.1
0x985cb  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x985d0  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0x985d5  stloc.s  6
0x985d7  ldloc.s  6
0x985d9  ldc.i4.s 9
0x985db  bne.un   loc_986C0
0x985e0  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x985e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x985ea  ldstr    aGetReader// "get_Reader"
0x985ef  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x985f4  ldnull
0x985f5  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x985fa  ldnull
0x985fb  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x98600  stloc.2
0x98601  ldtoken  System.Xml.XmlReader
0x98606  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9860b  ldstr    aReadstring// "ReadString"
0x98610  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x98615  ldnull
0x98616  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x9861b  ldnull
0x9861c  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x98621  stloc.3
0x98622  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x98627  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9862c  ldstr    aGetDocument// "get_Document"
0x98631  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x98636  ldnull
0x98637  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x9863c  ldnull
0x9863d  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x98642  stloc.s  4
0x98644  ldtoken  System.Xml.XmlDocument
0x98649  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9864e  ldstr    aCreatetextnode// "CreateTextNode"
0x98653  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x98658  ldnull
0x98659  ldc.i4.1
0x9865a  newarr   [mscorlib]System.Type
0x9865f  dup
0x98660  ldc.i4.0
0x98661  ldtoken  [mscorlib]System.String
0x98666  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9866b  stelem.ref
0x9866c  ldnull
0x9866d  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x98672  stloc.s  5
0x98674  ldarg.0
0x98675  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9867a  ldc.i4.0
0x9867b  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x98680  ldarg.0
0x98681  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x98686  ldloc.s  4
0x98688  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x9868d  ldarg.0
0x9868e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x98693  ldc.i4.0
0x98694  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x98699  ldarg.0
0x9869a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9869f  ldloc.2
0x986a0  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x986a5  ldarg.0
0x986a6  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x986ab  ldloc.3
0x986ac  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x986b1  ldarg.0
0x986b2  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x986b7  ldloc.s  5
0x986b9  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x986be  br.s     loc_986D0
0x986c0  ldstr    aXmlinternalerr// "XmlInternalError"
0x986c5  call     string System.Xml.Res::GetString(string name)
0x986ca  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x986cf  throw
0x986d0  ldarg.0
0x986d1  ldarg.1
0x986d2  callvirt instance string Member::get_ArraySource()
0x986d7  ldloc.1
0x986d8  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x986dd  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x986e2  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceEnd(string source, class [mscorlib]System.Type elementType)
0x986e7  ret
0x986e8  ldarg.1
0x986e9  callvirt instance bool Member::get_IsArrayLike()
0x986ee  brfalse  loc_987DE
0x986f3  ldarg.0
0x986f4  ldarg.1
0x986f5  callvirt instance string Member::get_ArraySource()
0x986fa  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBegin(string source)
0x986ff  ldloc.0
0x98700  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x98705  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9870a  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CollapseWhitespace()
0x9870f  brfalse.s loc_9871D
0x98711  ldarg.0
0x98712  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x98717  ldc.i4.0
0x98718  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x9871d  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x98722  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x98727  ldstr    aGetReader// "get_Reader"
0x9872c  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x98731  ldnull
0x98732  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x98737  ldnull
0x98738  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x9873d  stloc.s  7
0x9873f  ldtoken  System.Xml.XmlReader
0x98744  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x98749  ldstr    aReadstring// "ReadString"
0x9874e  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x98753  ldnull
0x98754  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x98759  ldnull
0x9875a  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x9875f  stloc.s  8
0x98761  ldarg.0
0x98762  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x98767  ldc.i4.0
0x98768  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x9876d  ldarg.0
0x9876e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x98773  ldloc.s  7
0x98775  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x9877a  ldarg.0
0x9877b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x98780  ldloc.s  8
0x98782  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x98787  ldloc.0
0x98788  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x9878d  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x98792  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CollapseWhitespace()
0x98797  brfalse  loc_988E5
0x9879c  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x987a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x987a6  ldstr    aCollapsewhites_2// "CollapseWhitespace"
0x987ab  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x987b0  ldnull
0x987b1  ldc.i4.1
0x987b2  newarr   [mscorlib]System.Type
0x987b7  dup
0x987b8  ldc.i4.0
0x987b9  ldtoken  [mscorlib]System.String
0x987be  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x987c3  stelem.ref
0x987c4  ldnull
0x987c5  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x987ca  stloc.s  9
0x987cc  ldarg.0
0x987cd  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x987d2  ldloc.s  9
0x987d4  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x987d9  br       loc_988E5
0x987de  ldloc.0
0x987df  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x987e4  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x987e9  ldarg.0
0x987ea  call     instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.XmlSerializationILGen::get_StringTypeDesc()
0x987ef  beq.s    loc_98810
0x987f1  ldloc.0
0x987f2  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x987f7  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x987fc  callvirt instance string System.Xml.Serialization.TypeDesc::get_FormatterName()
0x98801  ldstr    aString_0// "String"
0x98806  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9880b  brfalse  loc_988C8
0x98810  ldarg.0
0x98811  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x98816  ldstr    aTmp_2// "tmp"
0x9881b  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::GetLocal(string name)
0x98820  stloc.s  0xA
0x98822  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x98827  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9882c  ldstr    aReadstring// "ReadString"
0x98831  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x98836  ldnull
0x98837  ldc.i4.2
0x98838  newarr   [mscorlib]System.Type
0x9883d  dup
0x9883e  ldc.i4.0
0x9883f  ldtoken  [mscorlib]System.String
0x98844  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x98849  stelem.ref
0x9884a  dup
0x9884b  ldc.i4.1
0x9884c  ldtoken  [mscorlib]System.Boolean
0x98851  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x98856  stelem.ref
0x98857  ldnull
0x98858  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x9885d  stloc.s  0xB
0x9885f  ldarg.0
0x98860  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x98865  ldc.i4.0
0x98866  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x9886b  ldarg.0
0x9886c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x98871  ldloc.s  0xA
0x98873  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x98878  ldarg.0
0x98879  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9887e  ldloc.0
0x9887f  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x98884  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x98889  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CollapseWhitespace()
0x9888e  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(bool boolVar)
0x98893  ldarg.0
0x98894  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x98899  ldloc.s  0xB
0x9889b  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x988a0  ldarg.0
0x988a1  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x988a6  ldloc.s  0xA
0x988a8  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x988ad  ldarg.0
0x988ae  ldarg.1
0x988af  callvirt instance string Member::get_ArraySource()
0x988b4  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBegin(string source)
0x988b9  ldarg.0
0x988ba  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x988bf  ldloc.s  0xA
0x988c1  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x988c6  br.s     loc_988E5
0x988c8  ldarg.0
0x988c9  ldarg.1
0x988ca  callvirt instance string Member::get_ArraySource()
0x988cf  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBegin(string source)
0x988d4  ldarg.0
0x988d5  ldloc.0
0x988d6  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x988db  ldstr    aReaderReadstri// "Reader.ReadString()"
0x988e0  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WritePrimitive(class System.Xml.Serialization.TypeMapping mapping, string source)
0x988e5  ldarg.0
0x988e6  ldarg.1
0x988e7  callvirt instance string Member::get_ArraySource()
0x988ec  ldloc.0
0x988ed  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x988f2  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x988f7  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x988fc  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceEnd(string source, class [mscorlib]System.Type elementType)
0x98901  ret
```
