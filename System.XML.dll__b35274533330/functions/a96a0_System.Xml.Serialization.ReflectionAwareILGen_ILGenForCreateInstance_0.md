# System.Xml.Serialization.ReflectionAwareILGen::ILGenForCreateInstance_0

- ea: `0xa96a0`
- end: `0xa983b`
- name: `System.Xml.Serialization.ReflectionAwareILGen::ILGenForCreateInstance_0`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0xa9640`

## callees

- `0x637d0`
- `0x63830`
- `0x63870`
- `0x63a30`
- `0x63bc0`
- `0x63c60`
- `0x63e00`
- `0x64260`
- `0xa96a0`

## string_xrefs

- `0xa96db`: `System.Xml.Linq.XElement`
- `0xa96f0`: `System.Xml.Linq.XName`
- `0xa978d`: `CreateInstance`

## pseudocode

```c

```

## disassembly

```asm
0xa96a0  ldarg.2
0xa96a1  ldtoken  [mscorlib]System.DBNull
0xa96a6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa96ab  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xa96b0  brfalse.s loc_A96D5
0xa96b2  ldtoken  [mscorlib]System.DBNull
0xa96b7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa96bc  ldstr    aValue_2// "Value"
0xa96c1  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::StaticBindingFlags
0xa96c6  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xa96cb  stloc.2
0xa96cc  ldarg.1
0xa96cd  ldloc.2
0xa96ce  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.CodeGenerator::LoadMember(class [mscorlib]System.Reflection.MemberInfo memberInfo)
0xa96d3  pop
0xa96d4  ret
0xa96d5  ldarg.2
0xa96d6  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa96db  ldstr    aSystemXmlLinqX// "System.Xml.Linq.XElement"
0xa96e0  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa96e5  brfalse  loc_A9774
0xa96ea  ldarg.2
0xa96eb  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xa96f0  ldstr    aSystemXmlLinqX_0// "System.Xml.Linq.XName"
0xa96f5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0xa96fa  stloc.3
0xa96fb  ldloc.3
0xa96fc  ldnull
0xa96fd  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xa9702  brfalse.s loc_A9774
0xa9704  ldloc.3
0xa9705  ldstr    aOpImplicit// "op_Implicit"
0xa970a  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::StaticBindingFlags
0xa970f  ldnull
0xa9710  ldc.i4.1
0xa9711  newarr   [mscorlib]System.Type
0xa9716  dup
0xa9717  ldc.i4.0
0xa9718  ldtoken  [mscorlib]System.String
0xa971d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa9722  stelem.ref
0xa9723  ldnull
0xa9724  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa9729  stloc.s  4
0xa972b  ldarg.2
0xa972c  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa9731  ldnull
0xa9732  ldc.i4.1
0xa9733  newarr   [mscorlib]System.Type
0xa9738  dup
0xa9739  ldc.i4.0
0xa973a  ldloc.3
0xa973b  stelem.ref
0xa973c  ldnull
0xa973d  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa9742  stloc.s  5
0xa9744  ldloc.s  4
0xa9746  ldnull
0xa9747  call     bool [mscorlib]System.Reflection.MethodInfo::op_Inequality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0xa974c  brfalse.s loc_A9774
0xa974e  ldloc.s  5
0xa9750  ldnull
0xa9751  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Inequality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0xa9756  brfalse.s loc_A9774
0xa9758  ldarg.1
0xa9759  ldstr    aDefault// "default"
0xa975e  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0xa9763  ldarg.1
0xa9764  ldloc.s  4
0xa9766  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa976b  ldarg.1
0xa976c  ldloc.s  5
0xa976e  callvirt instance void System.Xml.Serialization.CodeGenerator::New(class [mscorlib]System.Reflection.ConstructorInfo constructorInfo)
0xa9773  ret
0xa9774  ldc.i4   0x214
0xa9779  stloc.0
0xa977a  ldarg.s  4
0xa977c  brfalse.s loc_A9783
0xa977e  ldloc.0
0xa977f  ldc.i4.s 0x20
0xa9781  or
0xa9782  stloc.0
0xa9783  ldtoken  [mscorlib]System.Activator
0xa9788  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa978d  ldstr    aCreateinstance_1// "CreateInstance"
0xa9792  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::StaticBindingFlags
0xa9797  ldnull
0xa9798  ldc.i4.5
0xa9799  newarr   [mscorlib]System.Type
0xa979e  dup
0xa979f  ldc.i4.0
0xa97a0  ldtoken  [mscorlib]System.Type
0xa97a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa97aa  stelem.ref
0xa97ab  dup
0xa97ac  ldc.i4.1
0xa97ad  ldtoken  [mscorlib]System.Reflection.BindingFlags
0xa97b2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa97b7  stelem.ref
0xa97b8  dup
0xa97b9  ldc.i4.2
0xa97ba  ldtoken  [mscorlib]System.Reflection.Binder
0xa97bf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa97c4  stelem.ref
0xa97c5  dup
0xa97c6  ldc.i4.3
0xa97c7  ldtoken  object[]
0xa97cc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa97d1  stelem.ref
0xa97d2  dup
0xa97d3  ldc.i4.4
0xa97d4  ldtoken  [mscorlib]System.Globalization.CultureInfo
0xa97d9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa97de  stelem.ref
0xa97df  ldnull
0xa97e0  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa97e5  stloc.1
0xa97e6  ldarg.1
0xa97e7  ldarg.2
0xa97e8  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(object o)
0xa97ed  ldarg.1
0xa97ee  ldloc.0
0xa97ef  box      [mscorlib]System.Int32
0xa97f4  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0xa97f9  ldarg.1
0xa97fa  ldnull
0xa97fb  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0xa9800  ldarg.1
0xa9801  ldtoken  [mscorlib]System.Object
0xa9806  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa980b  ldc.i4.0
0xa980c  box      [mscorlib]System.Int32
0xa9811  callvirt instance void System.Xml.Serialization.CodeGenerator::NewArray(class [mscorlib]System.Type elementType, object len)
0xa9816  ldarg.1
0xa9817  ldnull
0xa9818  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0xa981d  ldarg.1
0xa981e  ldloc.1
0xa981f  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa9824  ldarg.3
0xa9825  ldnull
0xa9826  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xa982b  brfalse.s loc_A983A
0xa982d  ldarg.1
0xa982e  ldloc.1
0xa982f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MethodInfo::get_ReturnType()
0xa9834  ldarg.3
0xa9835  callvirt instance void System.Xml.Serialization.CodeGenerator::ConvertValue(class [mscorlib]System.Type source, class [mscorlib]System.Type target)
0xa983a  ret
```
