# System.Xml.Serialization.XmlSerializationReaderILGen::GenerateTypeElement

- ea: `0x947e0`
- end: `0x9499f`
- name: `System.Xml.Serialization.XmlSerializationReaderILGen::GenerateTypeElement`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config`

## callers

- `0x93ad0`

## callees

- `0x63040`
- `0x630b0`
- `0x63220`
- `0x632c0`
- `0x63480`
- `0x637d0`
- `0x63bc0`
- `0x642b0`
- `0x64320`
- `0x643c0`
- `0x646c0`
- `0x68600`
- `0x68660`
- `0x68690`
- `0x68c50`
- `0x69630`
- `0x69670`
- `0x69a50`
- `0x79510`
- `0x947e0`
- `0x949a0`
- `0x981d0`
- `0x982d0`
- `0x122e60`

## string_xrefs

- `0x948b6`: `get_Reader`
- `0x9493d`: `throw CreateUnknownNodeException();`
- `0x948d8`: `MoveToContent`

## pseudocode

```c

```

## disassembly

```asm
0x947e0  ldarg.1
0x947e1  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x947e6  stloc.0
0x947e7  ldloc.0
0x947e8  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x947ed  stloc.1
0x947ee  ldarg.0
0x947ef  ldloc.0
0x947f0  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x947f5  call     instance string System.Xml.Serialization.XmlSerializationReaderILGen::NextMethodName(string name)
0x947fa  stloc.2
0x947fb  ldarg.0
0x947fc  ldarg.0
0x947fd  ldfld    class [mscorlib]System.Reflection.Emit.TypeBuilder System.Xml.Serialization.XmlSerializationILGen::typeBuilder
0x94802  newobj   instance void System.Xml.Serialization.CodeGenerator::.ctor(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder)
0x94807  stfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9480c  ldarg.0
0x9480d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94812  ldtoken  [mscorlib]System.Object
0x94817  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9481c  ldloc.2
0x9481d  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x94822  ldsfld   string[] System.Xml.Serialization.CodeGenerator::EmptyStringArray
0x94827  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PublicMethodAttributes
0x9482c  callvirt instance void System.Xml.Serialization.CodeGenerator::BeginMethod(class [mscorlib]System.Type returnType, string methodName, class [mscorlib]System.Type[] argTypes, string[] argNames, valuetype [mscorlib]System.Reflection.MethodAttributes methodAttributes)
0x94831  ldarg.0
0x94832  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94837  ldtoken  [mscorlib]System.Object
0x9483c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94841  ldstr    aO_0// "o"
0x94846  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareLocal(class [mscorlib]System.Type type, string name)
0x9484b  stloc.3
0x9484c  ldarg.0
0x9484d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94852  ldnull
0x94853  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x94858  ldarg.0
0x94859  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9485e  ldloc.3
0x9485f  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x94864  newobj   instance void System.Xml.Serialization.MemberMapping::.ctor()
0x94869  stloc.s  4
0x9486b  ldloc.s  4
0x9486d  ldloc.1
0x9486e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x94873  callvirt instance void System.Xml.Serialization.AccessorMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x94878  ldloc.s  4
0x9487a  ldc.i4.1
0x9487b  newarr   System.Xml.Serialization.ElementAccessor
0x94880  dup
0x94881  ldc.i4.0
0x94882  ldloc.0
0x94883  stelem.ref
0x94884  callvirt instance void System.Xml.Serialization.AccessorMapping::set_Elements(class System.Xml.Serialization.ElementAccessor[] value)
0x94889  ldc.i4.1
0x9488a  newarr   Member
0x9488f  dup
0x94890  ldc.i4.0
0x94891  ldarg.0
0x94892  ldstr    aO_0// "o"
0x94897  ldstr    aO_0// "o"
0x9489c  ldstr    aA_0// "a"
0x948a1  ldc.i4.0
0x948a2  ldloc.s  4
0x948a4  newobj   instance void Member::.ctor(class System.Xml.Serialization.XmlSerializationReaderILGen outerClass, string source, string arraySource, string arrayName, int32 i, class System.Xml.Serialization.MemberMapping mapping)
0x948a9  stelem.ref
0x948aa  stloc.s  5
0x948ac  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x948b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x948b6  ldstr    aGetReader// "get_Reader"
0x948bb  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x948c0  ldnull
0x948c1  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x948c6  ldnull
0x948c7  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x948cc  stloc.s  6
0x948ce  ldtoken  System.Xml.XmlReader
0x948d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x948d8  ldstr    aMovetocontent// "MoveToContent"
0x948dd  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x948e2  ldnull
0x948e3  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x948e8  ldnull
0x948e9  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x948ee  stloc.s  7
0x948f0  ldarg.0
0x948f1  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x948f6  ldc.i4.0
0x948f7  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x948fc  ldarg.0
0x948fd  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94902  ldloc.s  6
0x94904  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x94909  ldarg.0
0x9490a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9490f  ldloc.s  7
0x94911  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x94916  ldarg.0
0x94917  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9491c  callvirt instance void System.Xml.Serialization.CodeGenerator::Pop()
0x94921  ldstr    aUnknownnodeNul_0// "UnknownNode(null, "
0x94926  ldarg.0
0x94927  ldloc.s  5
0x94929  call     instance string System.Xml.Serialization.XmlSerializationReaderILGen::ExpectedElements(class Member[] members)
0x9492e  ldstr    asc_133068// ");"
0x94933  call     string [mscorlib]System.String::Concat(string, string, string)
0x94938  stloc.s  8
0x9493a  ldarg.0
0x9493b  ldloc.s  5
0x9493d  ldstr    aThrowCreateunk_0// "throw CreateUnknownNodeException();"
0x94942  ldloc.s  8
0x94944  ldloc.0
0x94945  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x9494a  brtrue.s loc_9494F
0x9494c  ldnull
0x9494d  br.s     loc_94953
0x9494f  ldloc.s  5
0x94951  ldc.i4.0
0x94952  ldelem.ref
0x94953  ldnull
0x94954  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteMemberElements(class Member[] members, string elementElseString, string elseString, class Member anyElement, class Member anyText)
0x94959  ldarg.0
0x9495a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9495f  ldloc.3
0x94960  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x94965  ldarg.0
0x94966  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9496b  ldarg.0
0x9496c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94971  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::get_ReturnLocal()
0x94976  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x9497b  ldarg.0
0x9497c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94981  ldarg.0
0x94982  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94987  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::get_ReturnLocal()
0x9498c  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x94991  ldarg.0
0x94992  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94997  callvirt instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.CodeGenerator::EndMethod()
0x9499c  pop
0x9499d  ldloc.2
0x9499e  ret
```
