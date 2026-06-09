# System.Xml.Serialization.XmlSerializationReaderILGen::WriteArray

- ea: `0x99700`
- end: `0x99a56`
- name: `System.Xml.Serialization.XmlSerializationReaderILGen::WriteArray`
- size: `854`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: `registry_config`

## callers

- `0x95a80`
- `0x99a60`

## callees

- `0x63380`
- `0x63610`
- `0x63620`
- `0x636b0`
- `0x636f0`
- `0x637d0`
- `0x63bc0`
- `0x640d0`
- `0x643c0`
- `0x645a0`
- `0x645b0`
- `0x64640`
- `0x646c0`
- `0x64b40`
- `0x68c50`
- `0x68dc0`
- `0x69630`
- `0x69670`
- `0x69a50`
- `0x69b60`
- `0x69be0`
- `0x97eb0`
- `0x981d0`
- `0x982d0`
- `0x98f00`
- `0x98f10`
- `0x99700`
- `0x9a930`
- `0x9a9c0`
- `0x122ea0`
- `0x1230b0`
- `0x123110`

## string_xrefs

- `0x99813`: `get_Reader`
- `0x99987`: `MoveToContent`
- `0x99912`: `ReadStartElement`
- `0x999e2`: `ReadEndElement`
- `0x9970a`: `ReadNull`

## pseudocode

```c

```

## disassembly

```asm
0x99700  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x99705  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9970a  ldstr    aReadnull// "ReadNull"
0x9970f  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x99714  ldnull
0x99715  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x9971a  ldnull
0x9971b  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x99720  stloc.0
0x99721  ldarg.0
0x99722  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99727  ldc.i4.0
0x99728  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x9972d  ldarg.0
0x9972e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99733  ldloc.0
0x99734  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99739  ldarg.0
0x9973a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9973f  callvirt instance void System.Xml.Serialization.CodeGenerator::IfNot()
0x99744  newobj   instance void System.Xml.Serialization.MemberMapping::.ctor()
0x99749  stloc.1
0x9974a  ldloc.1
0x9974b  ldarg.3
0x9974c  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.ArrayMapping::get_Elements()
0x99751  callvirt instance void System.Xml.Serialization.AccessorMapping::set_Elements(class System.Xml.Serialization.ElementAccessor[] value)
0x99756  ldloc.1
0x99757  ldarg.3
0x99758  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9975d  callvirt instance void System.Xml.Serialization.AccessorMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x99762  ldloc.1
0x99763  ldarg.s  4
0x99765  callvirt instance void System.Xml.Serialization.MemberMapping::set_ReadOnly(bool value)
0x9976a  ldarg.1
0x9976b  ldstr    aO// "o.@"
0x99770  ldc.i4.4
0x99771  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x99776  brfalse.s loc_99790
0x99778  ldloc.1
0x99779  ldarg.0
0x9977a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Reflection.MemberInfo> System.Xml.Serialization.XmlSerializationILGen::memberInfos
0x9977f  ldarg.1
0x99780  ldc.i4.3
0x99781  callvirt instance string [mscorlib]System.String::Substring(int32)
0x99786  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Reflection.MemberInfo>::get_Item(void)
0x9978b  callvirt instance void System.Xml.Serialization.MemberMapping::set_MemberInfo(class [mscorlib]System.Reflection.MemberInfo value)
0x99790  ldarg.0
0x99791  ldarg.1
0x99792  ldarg.2
0x99793  ldarg.s  7
0x99795  ldloc.1
0x99796  ldc.i4.0
0x99797  newobj   instance void Member::.ctor(class System.Xml.Serialization.XmlSerializationReaderILGen outerClass, string source, string arrayName, int32 i, class System.Xml.Serialization.MemberMapping mapping, bool multiRef)
0x9979c  stloc.2
0x9979d  ldloc.2
0x9979e  ldc.i4.0
0x9979f  callvirt instance void Member::set_IsNullable(bool value)
0x997a4  ldc.i4.1
0x997a5  newarr   Member
0x997aa  dup
0x997ab  ldc.i4.0
0x997ac  ldloc.2
0x997ad  stelem.ref
0x997ae  stloc.3
0x997af  ldarg.0
0x997b0  ldloc.3
0x997b1  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteMemberBegin(class Member[] members)
0x997b6  ldarg.0
0x997b7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x997bc  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::DefineLabel()
0x997c1  stloc.s  4
0x997c3  ldarg.0
0x997c4  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x997c9  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::DefineLabel()
0x997ce  stloc.s  5
0x997d0  ldarg.s  4
0x997d2  brfalse.s loc_99809
0x997d4  ldarg.0
0x997d5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x997da  ldarg.0
0x997db  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x997e0  ldloc.2
0x997e1  callvirt instance string Member::get_ArrayName()
0x997e6  callvirt instance object System.Xml.Serialization.CodeGenerator::GetVariable(string name)
0x997eb  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x997f0  ldarg.0
0x997f1  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x997f6  ldnull
0x997f7  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x997fc  ldarg.0
0x997fd  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99802  ldloc.s  4
0x99804  callvirt instance void System.Xml.Serialization.CodeGenerator::Beq(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x99809  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x9980e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99813  ldstr    aGetReader// "get_Reader"
0x99818  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x9981d  ldnull
0x9981e  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x99823  ldnull
0x99824  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x99829  stloc.s  6
0x9982b  ldtoken  System.Xml.XmlReader
0x99830  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99835  ldstr    aGetIsemptyelem// "get_IsEmptyElement"
0x9983a  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x9983f  ldnull
0x99840  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x99845  ldnull
0x99846  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x9984b  stloc.s  7
0x9984d  ldarg.0
0x9984e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99853  ldc.i4.0
0x99854  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x99859  ldarg.0
0x9985a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9985f  ldloc.s  6
0x99861  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99866  ldarg.0
0x99867  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9986c  ldloc.s  7
0x9986e  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99873  ldarg.s  4
0x99875  brfalse.s loc_998AA
0x99877  ldarg.0
0x99878  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9987d  ldloc.s  5
0x9987f  callvirt instance void System.Xml.Serialization.CodeGenerator::Br_S(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x99884  ldarg.0
0x99885  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9988a  ldloc.s  4
0x9988c  callvirt instance void System.Xml.Serialization.CodeGenerator::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x99891  ldarg.0
0x99892  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99897  ldc.i4.1
0x99898  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(bool boolVar)
0x9989d  ldarg.0
0x9989e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x998a3  ldloc.s  5
0x998a5  callvirt instance void System.Xml.Serialization.CodeGenerator::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x998aa  ldarg.0
0x998ab  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x998b0  callvirt instance void System.Xml.Serialization.CodeGenerator::If()
0x998b5  ldtoken  System.Xml.XmlReader
0x998ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x998bf  ldstr    aSkip_0// "Skip"
0x998c4  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x998c9  ldnull
0x998ca  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x998cf  ldnull
0x998d0  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x998d5  stloc.s  8
0x998d7  ldarg.0
0x998d8  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x998dd  ldc.i4.0
0x998de  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x998e3  ldarg.0
0x998e4  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x998e9  ldloc.s  6
0x998eb  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x998f0  ldarg.0
0x998f1  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x998f6  ldloc.s  8
0x998f8  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x998fd  ldarg.0
0x998fe  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99903  callvirt instance void System.Xml.Serialization.CodeGenerator::Else()
0x99908  ldtoken  System.Xml.XmlReader
0x9990d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99912  ldstr    aReadstarteleme// "ReadStartElement"
0x99917  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x9991c  ldnull
0x9991d  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x99922  ldnull
0x99923  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x99928  stloc.s  9
0x9992a  ldarg.0
0x9992b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99930  ldc.i4.0
0x99931  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x99936  ldarg.0
0x99937  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9993c  ldloc.s  6
0x9993e  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99943  ldarg.0
0x99944  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99949  ldloc.s  9
0x9994b  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99950  ldarg.0
0x99951  call     instance int32 System.Xml.Serialization.XmlSerializationReaderILGen::WriteWhileNotLoopStart()
0x99956  stloc.s  0xA
0x99958  ldstr    aUnknownnodeNul_0// "UnknownNode(null, "
0x9995d  ldarg.0
0x9995e  ldloc.3
0x9995f  call     instance string System.Xml.Serialization.XmlSerializationReaderILGen::ExpectedElements(class Member[] members)
0x99964  ldstr    asc_133068// ");"
0x99969  call     string [mscorlib]System.String::Concat(string, string, string)
0x9996e  stloc.s  0xB
0x99970  ldarg.0
0x99971  ldloc.3
0x99972  ldloc.s  0xB
0x99974  ldloc.s  0xB
0x99976  ldnull
0x99977  ldnull
0x99978  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteMemberElements(class Member[] members, string elementElseString, string elseString, class Member anyElement, class Member anyText)
0x9997d  ldtoken  System.Xml.XmlReader
0x99982  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99987  ldstr    aMovetocontent// "MoveToContent"
0x9998c  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x99991  ldnull
0x99992  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x99997  ldnull
0x99998  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x9999d  stloc.s  0xC
0x9999f  ldarg.0
0x999a0  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x999a5  ldc.i4.0
0x999a6  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x999ab  ldarg.0
0x999ac  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x999b1  ldloc.s  6
0x999b3  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x999b8  ldarg.0
0x999b9  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x999be  ldloc.s  0xC
0x999c0  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x999c5  ldarg.0
0x999c6  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x999cb  callvirt instance void System.Xml.Serialization.CodeGenerator::Pop()
0x999d0  ldarg.0
0x999d1  ldloc.s  0xA
0x999d3  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteWhileLoopEnd(int32 loopIndex)
0x999d8  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x999dd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x999e2  ldstr    aReadendelement_0// "ReadEndElement"
0x999e7  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x999ec  ldnull
0x999ed  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x999f2  ldnull
0x999f3  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x999f8  stloc.s  0xD
0x999fa  ldarg.0
0x999fb  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99a00  ldc.i4.0
0x99a01  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x99a06  ldarg.0
0x99a07  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99a0c  ldloc.s  0xD
0x99a0e  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99a13  ldarg.0
0x99a14  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99a19  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0x99a1e  ldarg.0
0x99a1f  ldloc.3
0x99a20  ldc.i4.0
0x99a21  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteMemberEnd(class Member[] members, bool soapRefs)
0x99a26  ldarg.s  5
0x99a28  brfalse.s loc_99A4A
0x99a2a  ldarg.0
0x99a2b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99a30  callvirt instance void System.Xml.Serialization.CodeGenerator::Else()
0x99a35  ldloc.2
0x99a36  ldc.i4.1
0x99a37  callvirt instance void Member::set_IsNullable(bool value)
0x99a3c  ldarg.0
0x99a3d  ldloc.3
0x99a3e  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteMemberBegin(class Member[] members)
0x99a43  ldarg.0
0x99a44  ldloc.3
0x99a45  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteMemberEnd(class Member[] members)
0x99a4a  ldarg.0
0x99a4b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99a50  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0x99a55  ret
```
