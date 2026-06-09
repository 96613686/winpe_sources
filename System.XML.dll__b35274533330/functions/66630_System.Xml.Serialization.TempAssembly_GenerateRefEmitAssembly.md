# System.Xml.Serialization.TempAssembly::GenerateRefEmitAssembly

- ea: `0x66630`
- end: `0x669d0`
- name: `System.Xml.Serialization.TempAssembly::GenerateRefEmitAssembly`
- size: `928`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x65c10`

## callees

- `0xdaf0`
- `0x64880`
- `0x64920`
- `0x654e0`
- `0x65990`
- `0x65ac0`
- `0x66630`
- `0x66b60`
- `0x79520`
- `0x79650`
- `0x87210`
- `0x87740`
- `0x87870`
- `0x87f30`
- `0x937d0`
- `0x937f0`
- `0x93930`
- `0x93ad0`
- `0xa4470`
- `0xa4480`
- `0xa45a0`
- `0xa45d0`

## string_xrefs

- `0x6698b`: `XmlSerializerContract`
- `0x667bf`: `XmlSerializationWriter`
- `0x667c4`: `XmlSerializationWriter`
- `0x66828`: `XmlSerializationWriter`
- `0x667d1`: `XmlSerializationReader`
- `0x667d6`: `XmlSerializationReader`
- `0x66897`: `XmlSerializationReader`
- `0x6691f`: `XmlSerializer1`

## pseudocode

```c

```

## disassembly

```asm
0x66630  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x66635  stloc.0
0x66636  ldarg.0
0x66637  stloc.s  0x13
0x66639  ldc.i4.0
0x6663a  stloc.s  0x14
0x6663c  br.s     loc_6665A
0x6663e  ldloc.s  0x13
0x66640  ldloc.s  0x14
0x66642  ldelem.ref
0x66643  stloc.s  0x15
0x66645  ldloc.0
0x66646  ldloc.s  0x15
0x66648  callvirt instance class System.Xml.Serialization.TypeScope System.Xml.Serialization.XmlMapping::get_Scope()
0x6664d  ldloc.s  0x15
0x6664f  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x66654  ldloc.s  0x14
0x66656  ldc.i4.1
0x66657  add
0x66658  stloc.s  0x14
0x6665a  ldloc.s  0x14
0x6665c  ldloc.s  0x13
0x6665e  ldlen
0x6665f  conv.i4
0x66660  blt.s    loc_6663E
0x66662  ldloc.0
0x66663  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x66668  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x6666d  newarr   System.Xml.Serialization.TypeScope
0x66672  stloc.1
0x66673  ldloc.0
0x66674  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x66679  ldloc.1
0x6667a  ldc.i4.0
0x6667b  callvirt instance void [mscorlib]System.Collections.ICollection::CopyTo(class [mscorlib]System.Array, int32)
0x66680  ldstr    aMicrosoftGener// "Microsoft.GeneratedCode"
0x66685  stloc.2
0x66686  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x6668b  ldloc.2
0x6668c  call     class [mscorlib]System.Reflection.Emit.AssemblyBuilder System.Xml.Serialization.CodeGenerator::CreateAssemblyBuilder(class [mscorlib]System.AppDomain appDomain, string name)
0x66691  stloc.3
0x66692  ldtoken  [mscorlib]System.Security.SecurityTransparentAttribute
0x66697  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6669c  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x666a1  ldnull
0x666a2  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x666a7  ldnull
0x666a8  call     instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x666ad  stloc.s  4
0x666af  ldloc.3
0x666b0  ldloc.s  4
0x666b2  ldc.i4.0
0x666b3  newarr   [mscorlib]System.Object
0x666b8  newobj   instance void [mscorlib]System.Reflection.Emit.CustomAttributeBuilder::.ctor(class [mscorlib]System.Reflection.ConstructorInfo, object[])
0x666bd  callvirt instance void [mscorlib]System.Reflection.Emit.AssemblyBuilder::SetCustomAttribute(class [mscorlib]System.Reflection.Emit.CustomAttributeBuilder)
0x666c2  ldtoken  [mscorlib]System.Security.AllowPartiallyTrustedCallersAttribute
0x666c7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x666cc  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x666d1  ldnull
0x666d2  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x666d7  ldnull
0x666d8  call     instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x666dd  stloc.s  5
0x666df  ldloc.3
0x666e0  ldloc.s  5
0x666e2  ldc.i4.0
0x666e3  newarr   [mscorlib]System.Object
0x666e8  newobj   instance void [mscorlib]System.Reflection.Emit.CustomAttributeBuilder::.ctor(class [mscorlib]System.Reflection.ConstructorInfo, object[])
0x666ed  callvirt instance void [mscorlib]System.Reflection.Emit.AssemblyBuilder::SetCustomAttribute(class [mscorlib]System.Reflection.Emit.CustomAttributeBuilder)
0x666f2  ldtoken  [mscorlib]System.Security.SecurityRulesAttribute
0x666f7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x666fc  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x66701  ldnull
0x66702  ldc.i4.1
0x66703  newarr   [mscorlib]System.Type
0x66708  dup
0x66709  ldc.i4.0
0x6670a  ldtoken  [mscorlib]System.Security.SecurityRuleSet
0x6670f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x66714  stelem.ref
0x66715  ldnull
0x66716  call     instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x6671b  stloc.s  6
0x6671d  ldloc.3
0x6671e  ldloc.s  6
0x66720  ldc.i4.1
0x66721  newarr   [mscorlib]System.Object
0x66726  dup
0x66727  ldc.i4.0
0x66728  ldc.i4.1
0x66729  box      [mscorlib]System.Security.SecurityRuleSet
0x6672e  stelem.ref
0x6672f  newobj   instance void [mscorlib]System.Reflection.Emit.CustomAttributeBuilder::.ctor(class [mscorlib]System.Reflection.ConstructorInfo, object[])
0x66734  callvirt instance void [mscorlib]System.Reflection.Emit.AssemblyBuilder::SetCustomAttribute(class [mscorlib]System.Reflection.Emit.CustomAttributeBuilder)
0x66739  ldarg.1
0x6673a  brfalse.s loc_667B6
0x6673c  ldarg.1
0x6673d  ldlen
0x6673e  brfalse.s loc_667B6
0x66740  ldarg.1
0x66741  ldc.i4.0
0x66742  ldelem.ref
0x66743  ldnull
0x66744  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x66749  brfalse.s loc_667B6
0x6674b  ldtoken  [mscorlib]System.Reflection.AssemblyVersionAttribute
0x66750  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x66755  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x6675a  ldnull
0x6675b  ldc.i4.1
0x6675c  newarr   [mscorlib]System.Type
0x66761  dup
0x66762  ldc.i4.0
0x66763  ldtoken  [mscorlib]System.String
0x66768  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6676d  stelem.ref
0x6676e  ldnull
0x6676f  call     instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x66774  stloc.s  0x16
0x66776  call     class [mscorlib]System.Security.Permissions.FileIOPermission System.Xml.Serialization.TempAssembly::get_FileIOPermission()
0x6677b  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x66780  ldarg.1
0x66781  ldc.i4.0
0x66782  ldelem.ref
0x66783  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x66788  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x6678d  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x66792  callvirt instance string [mscorlib]System.Object::ToString()
0x66797  stloc.s  0x17
0x66799  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x6679e  ldloc.3
0x6679f  ldloc.s  0x16
0x667a1  ldc.i4.1
0x667a2  newarr   [mscorlib]System.Object
0x667a7  dup
0x667a8  ldc.i4.0
0x667a9  ldloc.s  0x17
0x667ab  stelem.ref
0x667ac  newobj   instance void [mscorlib]System.Reflection.Emit.CustomAttributeBuilder::.ctor(class [mscorlib]System.Reflection.ConstructorInfo, object[])
0x667b1  callvirt instance void [mscorlib]System.Reflection.Emit.AssemblyBuilder::SetCustomAttribute(class [mscorlib]System.Reflection.Emit.CustomAttributeBuilder)
0x667b6  newobj   instance void System.Xml.Serialization.CodeIdentifiers::.ctor()
0x667bb  stloc.s  7
0x667bd  ldloc.s  7
0x667bf  ldstr    aXmlserializati_3// "XmlSerializationWriter"
0x667c4  ldstr    aXmlserializati_3// "XmlSerializationWriter"
0x667c9  callvirt instance string System.Xml.Serialization.CodeIdentifiers::AddUnique(string identifier, object value)
0x667ce  pop
0x667cf  ldloc.s  7
0x667d1  ldstr    aXmlserializati_4// "XmlSerializationReader"
0x667d6  ldstr    aXmlserializati_4// "XmlSerializationReader"
0x667db  callvirt instance string System.Xml.Serialization.CodeIdentifiers::AddUnique(string identifier, object value)
0x667e0  pop
0x667e1  ldnull
0x667e2  stloc.s  8
0x667e4  ldarg.1
0x667e5  brfalse.s loc_6681F
0x667e7  ldarg.1
0x667e8  ldlen
0x667e9  conv.i4
0x667ea  ldc.i4.1
0x667eb  bne.un.s loc_6681F
0x667ed  ldarg.1
0x667ee  ldc.i4.0
0x667ef  ldelem.ref
0x667f0  ldnull
0x667f1  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x667f6  brfalse.s loc_6681F
0x667f8  ldarg.1
0x667f9  ldc.i4.0
0x667fa  ldelem.ref
0x667fb  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x66800  call     string System.Xml.Serialization.CodeIdentifier::MakeValid(string identifier)
0x66805  stloc.s  8
0x66807  ldarg.1
0x66808  ldc.i4.0
0x66809  ldelem.ref
0x6680a  callvirt instance bool [mscorlib]System.Type::get_IsArray()
0x6680f  brfalse.s loc_6681F
0x66811  ldloc.s  8
0x66813  ldstr    aArray_0// "Array"
0x66818  call     string [mscorlib]System.String::Concat(string, string)
0x6681d  stloc.s  8
0x6681f  ldloc.3
0x66820  ldloc.2
0x66821  call     class [mscorlib]System.Reflection.Emit.ModuleBuilder System.Xml.Serialization.CodeGenerator::CreateModuleBuilder(class [mscorlib]System.Reflection.Emit.AssemblyBuilder assemblyBuilder, string name)
0x66826  stloc.s  9
0x66828  ldstr    aXmlserializati_3// "XmlSerializationWriter"
0x6682d  ldloc.s  8
0x6682f  call     string [mscorlib]System.String::Concat(string, string)
0x66834  stloc.s  0xA
0x66836  ldloc.s  7
0x66838  ldloc.s  0xA
0x6683a  ldloc.s  0xA
0x6683c  callvirt instance string System.Xml.Serialization.CodeIdentifiers::AddUnique(string identifier, object value)
0x66841  stloc.s  0xA
0x66843  ldloc.1
0x66844  ldstr    aPublic_3// "public"
0x66849  ldloc.s  0xA
0x6684b  newobj   instance void System.Xml.Serialization.XmlSerializationWriterILGen::.ctor(class System.Xml.Serialization.TypeScope[] scopes, string access, string className)
0x66850  stloc.s  0xB
0x66852  ldloc.s  0xB
0x66854  ldloc.s  9
0x66856  callvirt instance void System.Xml.Serialization.XmlSerializationILGen::set_ModuleBuilder(class [mscorlib]System.Reflection.Emit.ModuleBuilder value)
0x6685b  ldloc.s  0xB
0x6685d  callvirt instance void System.Xml.Serialization.XmlSerializationWriterILGen::GenerateBegin()
0x66862  ldarg.0
0x66863  ldlen
0x66864  conv.i4
0x66865  newarr   [mscorlib]System.String
0x6686a  stloc.s  0xC
0x6686c  ldc.i4.0
0x6686d  stloc.s  0x18
0x6686f  br.s     loc_66887
0x66871  ldloc.s  0xC
0x66873  ldloc.s  0x18
0x66875  ldloc.s  0xB
0x66877  ldarg.0
0x66878  ldloc.s  0x18
0x6687a  ldelem.ref
0x6687b  callvirt instance string System.Xml.Serialization.XmlSerializationWriterILGen::GenerateElement(class System.Xml.Serialization.XmlMapping xmlMapping)
0x66880  stelem.ref
0x66881  ldloc.s  0x18
0x66883  ldc.i4.1
0x66884  add
0x66885  stloc.s  0x18
0x66887  ldloc.s  0x18
0x66889  ldarg.0
0x6688a  ldlen
0x6688b  conv.i4
0x6688c  blt.s    loc_66871
0x6688e  ldloc.s  0xB
0x66890  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.XmlSerializationWriterILGen::GenerateEnd()
0x66895  stloc.s  0xD
0x66897  ldstr    aXmlserializati_4// "XmlSerializationReader"
0x6689c  ldloc.s  8
0x6689e  call     string [mscorlib]System.String::Concat(string, string)
0x668a3  stloc.s  0xE
0x668a5  ldloc.s  7
0x668a7  ldloc.s  0xE
0x668a9  ldloc.s  0xE
0x668ab  callvirt instance string System.Xml.Serialization.CodeIdentifiers::AddUnique(string identifier, object value)
0x668b0  stloc.s  0xE
0x668b2  ldloc.1
0x668b3  ldstr    aPublic_3// "public"
0x668b8  ldloc.s  0xE
0x668ba  newobj   instance void System.Xml.Serialization.XmlSerializationReaderILGen::.ctor(class System.Xml.Serialization.TypeScope[] scopes, string access, string className)
0x668bf  stloc.s  0xF
0x668c1  ldloc.s  0xF
0x668c3  ldloc.s  9
0x668c5  callvirt instance void System.Xml.Serialization.XmlSerializationILGen::set_ModuleBuilder(class [mscorlib]System.Reflection.Emit.ModuleBuilder value)
0x668ca  ldloc.s  0xF
0x668cc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Serialization.XmlSerializationILGen::CreatedTypes
0x668d1  ldloc.s  0xD
0x668d3  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x668d8  ldloc.s  0xD
0x668da  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::Add(var<u1>, !!T0)
0x668df  ldloc.s  0xF
0x668e1  callvirt instance void System.Xml.Serialization.XmlSerializationReaderILGen::GenerateBegin()
0x668e6  ldarg.0
0x668e7  ldlen
0x668e8  conv.i4
0x668e9  newarr   [mscorlib]System.String
0x668ee  stloc.s  0x10
0x668f0  ldc.i4.0
0x668f1  stloc.s  0x19
0x668f3  br.s     loc_6690B
0x668f5  ldloc.s  0x10
0x668f7  ldloc.s  0x19
0x668f9  ldloc.s  0xF
0x668fb  ldarg.0
0x668fc  ldloc.s  0x19
0x668fe  ldelem.ref
0x668ff  callvirt instance string System.Xml.Serialization.XmlSerializationReaderILGen::GenerateElement(class System.Xml.Serialization.XmlMapping xmlMapping)
0x66904  stelem.ref
0x66905  ldloc.s  0x19
0x66907  ldc.i4.1
0x66908  add
0x66909  stloc.s  0x19
0x6690b  ldloc.s  0x19
0x6690d  ldarg.0
0x6690e  ldlen
0x6690f  conv.i4
0x66910  blt.s    loc_668F5
0x66912  ldloc.s  0xF
0x66914  ldloc.s  0x10
0x66916  ldarg.0
0x66917  ldarg.1
0x66918  callvirt instance void System.Xml.Serialization.XmlSerializationReaderILGen::GenerateEnd(string[] methods, class System.Xml.Serialization.XmlMapping[] xmlMappings, class [mscorlib]System.Type[] types)
0x6691d  ldloc.s  0xF
0x6691f  ldstr    aXmlserializer1// "XmlSerializer1"
0x66924  ldloc.s  0xE
0x66926  ldloc.s  0xA
0x66928  ldloc.s  7
0x6692a  callvirt instance string System.Xml.Serialization.XmlSerializationILGen::GenerateBaseSerializer(string baseSerializer, string readerClass, string writerClass, class System.Xml.Serialization.CodeIdentifiers classes)
0x6692f  stloc.s  0x11
0x66931  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x66936  stloc.s  0x12
0x66938  ldc.i4.0
0x66939  stloc.s  0x1A
0x6693b  br.s     loc_66982
  ... truncated ...
```
