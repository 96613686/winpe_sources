# System.Xml.Serialization.TempAssembly::GenerateAssembly

- ea: `0x66150`
- end: `0x66630`
- name: `System.Xml.Serialization.TempAssembly::GenerateAssembly`
- size: `1248`
- prototype: ``
- caller_count: `2`
- callee_count: `35`
- tags: `registry_config, broker_com_uri`

## callers

- `0x65c10`
- `0xaa7d0`

## callees

- `0x622f0`
- `0x654e0`
- `0x65990`
- `0x65ac0`
- `0x660c0`
- `0x66150`
- `0x66b60`
- `0x67090`
- `0x67210`
- `0x67230`
- `0x67240`
- `0x67370`
- `0x676c0`
- `0x68430`
- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x684e0`
- `0x74f10`
- `0x79520`
- `0x79650`
- `0x86730`
- `0x86930`
- `0x86f20`
- `0x8c2b0`
- `0x8c2e0`
- `0x8c540`
- `0x8c710`
- `0x9d4f0`
- `0x9d500`
- `0x9d710`
- `0x9d750`
- `0xa2e70`
- `0xa4360`

## string_xrefs

- `0x665e1`: `XmlSerializerContract`
- `0x662af`: `#if _DYNAMIC_XMLSERIALIZER_COMPILATION`
- `0x662bb`: `[assembly:System.Security.AllowPartiallyTrustedCallers()]`
- `0x662c7`: `[assembly:System.Security.SecurityTransparent()]`
- `0x662d3`: `[assembly:System.Security.SecurityRules(System.Security.SecurityRuleSet.Level1)]`
- `0x6635a`: `XmlPregenTypeDynamic`
- `0x66416`: `XmlSerializationWriter`
- `0x6641b`: `XmlSerializationWriter`
- `0x6649c`: `XmlSerializationWriter`
- `0x66428`: `XmlSerializationReader`
- `0x6642d`: `XmlSerializationReader`
- `0x66509`: `XmlSerializationReader`
- `0x66478`: `namespace Microsoft.Xml.Serialization.GeneratedAssembly {`
- `0x66575`: `XmlSerializer1`

## pseudocode

```c

```

## disassembly

```asm
0x66150  call     class [mscorlib]System.Security.Permissions.FileIOPermission System.Xml.Serialization.TempAssembly::get_FileIOPermission()
0x66155  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x6615a  newobj   instance void System.Xml.Serialization.Compiler::.ctor()
0x6615f  stloc.0
0x66160  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x66165  stloc.1
0x66166  ldarg.0
0x66167  stloc.s  0xF
0x66169  ldc.i4.0
0x6616a  stloc.s  0x10
0x6616c  br.s     loc_6618A
0x6616e  ldloc.s  0xF
0x66170  ldloc.s  0x10
0x66172  ldelem.ref
0x66173  stloc.s  0x11
0x66175  ldloc.1
0x66176  ldloc.s  0x11
0x66178  callvirt instance class System.Xml.Serialization.TypeScope System.Xml.Serialization.XmlMapping::get_Scope()
0x6617d  ldloc.s  0x11
0x6617f  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x66184  ldloc.s  0x10
0x66186  ldc.i4.1
0x66187  add
0x66188  stloc.s  0x10
0x6618a  ldloc.s  0x10
0x6618c  ldloc.s  0xF
0x6618e  ldlen
0x6618f  conv.i4
0x66190  blt.s    loc_6616E
0x66192  ldloc.1
0x66193  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x66198  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x6619d  newarr   System.Xml.Serialization.TypeScope
0x661a2  stloc.2
0x661a3  ldloc.1
0x661a4  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x661a9  ldloc.2
0x661aa  ldc.i4.0
0x661ab  callvirt instance void [mscorlib]System.Collections.ICollection::CopyTo(class [mscorlib]System.Array, int32)
0x661b0  ldarg.s  6
0x661b2  callvirt instance void [mscorlib]System.Collections.Hashtable::Clear()
0x661b7  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x661bc  stloc.3
0x661bd  ldloc.2
0x661be  stloc.s  0x12
0x661c0  ldc.i4.0
0x661c1  stloc.s  0x13
0x661c3  br       loc_6624D
0x661c8  ldloc.s  0x12
0x661ca  ldloc.s  0x13
0x661cc  ldelem.ref
0x661cd  stloc.s  0x14
0x661cf  ldloc.s  0x14
0x661d1  callvirt instance class [mscorlib]System.Collections.ICollection System.Xml.Serialization.TypeScope::get_Types()
0x661d6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x661db  stloc.s  0x15
0x661dd  br.s     loc_66227
0x661df  ldloc.s  0x15
0x661e1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x661e6  castclass [mscorlib]System.Type
0x661eb  stloc.s  0x16
0x661ed  ldloc.0
0x661ee  ldloc.s  0x16
0x661f0  ldloc.3
0x661f1  callvirt instance void System.Xml.Serialization.Compiler::AddImport(class [mscorlib]System.Type type, class [mscorlib]System.Collections.Hashtable types)
0x661f6  ldloc.s  0x16
0x661f8  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x661fd  stloc.s  0x17
0x661ff  ldloc.s  0x17
0x66201  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x66206  stloc.s  0x18
0x66208  ldarg.s  6
0x6620a  ldloc.s  0x18
0x6620c  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x66211  brtrue.s loc_66227
0x66213  ldloc.s  0x17
0x66215  callvirt instance bool [mscorlib]System.Reflection.Assembly::get_GlobalAssemblyCache()
0x6621a  brtrue.s loc_66227
0x6621c  ldarg.s  6
0x6621e  ldloc.s  0x18
0x66220  ldloc.s  0x17
0x66222  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x66227  ldloc.s  0x15
0x66229  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6622e  brtrue.s loc_661DF
0x66230  leave.s  loc_66247
0x66232  ldloc.s  0x15
0x66234  isinst   [mscorlib]System.IDisposable
0x66239  stloc.s  0x19
0x6623b  ldloc.s  0x19
0x6623d  brfalse.s loc_66246
0x6623f  ldloc.s  0x19
0x66241  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66246  endfinally
0x66247  ldloc.s  0x13
0x66249  ldc.i4.1
0x6624a  add
0x6624b  stloc.s  0x13
0x6624d  ldloc.s  0x13
0x6624f  ldloc.s  0x12
0x66251  ldlen
0x66252  conv.i4
0x66253  blt      loc_661C8
0x66258  ldc.i4.0
0x66259  stloc.s  0x1A
0x6625b  br.s     loc_6626E
0x6625d  ldloc.0
0x6625e  ldarg.1
0x6625f  ldloc.s  0x1A
0x66261  ldelem.ref
0x66262  ldloc.3
0x66263  callvirt instance void System.Xml.Serialization.Compiler::AddImport(class [mscorlib]System.Type type, class [mscorlib]System.Collections.Hashtable types)
0x66268  ldloc.s  0x1A
0x6626a  ldc.i4.1
0x6626b  add
0x6626c  stloc.s  0x1A
0x6626e  ldloc.s  0x1A
0x66270  ldarg.1
0x66271  ldlen
0x66272  conv.i4
0x66273  blt.s    loc_6625D
0x66275  ldloc.0
0x66276  ldtoken  [mscorlib]System.Object
0x6627b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x66280  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x66285  callvirt instance void System.Xml.Serialization.Compiler::AddImport(class [mscorlib]System.Reflection.Assembly assembly)
0x6628a  ldloc.0
0x6628b  ldtoken  System.Xml.Serialization.XmlSerializer
0x66290  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x66295  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x6629a  callvirt instance void System.Xml.Serialization.Compiler::AddImport(class [mscorlib]System.Reflection.Assembly assembly)
0x6629f  ldloc.0
0x662a0  callvirt instance class [mscorlib]System.IO.TextWriter System.Xml.Serialization.Compiler::get_Source()
0x662a5  ldc.i4.0
0x662a6  newobj   instance void System.Xml.Serialization.IndentedWriter::.ctor(class [mscorlib]System.IO.TextWriter writer, bool compact)
0x662ab  stloc.s  4
0x662ad  ldloc.s  4
0x662af  ldstr    aIfDynamicXmlse// "#if _DYNAMIC_XMLSERIALIZER_COMPILATION"
0x662b4  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x662b9  ldloc.s  4
0x662bb  ldstr    aAssemblySystem// "[assembly:System.Security.AllowPartiall"...
0x662c0  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x662c5  ldloc.s  4
0x662c7  ldstr    aAssemblySystem_0// "[assembly:System.Security.SecurityTrans"...
0x662cc  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x662d1  ldloc.s  4
0x662d3  ldstr    aAssemblySystem_1// "[assembly:System.Security.SecurityRules"...
0x662d8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x662dd  ldloc.s  4
0x662df  ldstr    aEndif// "#endif"
0x662e4  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x662e9  ldarg.1
0x662ea  brfalse.s loc_66328
0x662ec  ldarg.1
0x662ed  ldlen
0x662ee  brfalse.s loc_66328
0x662f0  ldarg.1
0x662f1  ldc.i4.0
0x662f2  ldelem.ref
0x662f3  ldnull
0x662f4  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x662f9  brfalse.s loc_66328
0x662fb  ldloc.s  4
0x662fd  ldstr    aAssemblySystem_2// "[assembly:System.Reflection.AssemblyVer"...
0x66302  ldarg.1
0x66303  ldc.i4.0
0x66304  ldelem.ref
0x66305  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x6630a  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x6630f  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x66314  callvirt instance string [mscorlib]System.Object::ToString()
0x66319  ldstr    asc_12E77C// "\")]"
0x6631e  call     string [mscorlib]System.String::Concat(string, string, string)
0x66323  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x66328  ldarg.s  5
0x6632a  ldnull
0x6632b  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x66330  brfalse  loc_6640D
0x66335  ldarg.1
0x66336  ldlen
0x66337  brfalse  loc_6640D
0x6633c  ldc.i4.0
0x6633d  stloc.s  0x1B
0x6633f  br.s     loc_66382
0x66341  ldarg.1
0x66342  ldloc.s  0x1B
0x66344  ldelem.ref
0x66345  stloc.s  0x1C
0x66347  ldloc.s  0x1C
0x66349  ldnull
0x6634a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6634f  brtrue.s loc_6637C
0x66351  ldloc.s  0x1C
0x66353  call     bool System.Xml.Serialization.DynamicAssemblies::IsTypeDynamic(class [mscorlib]System.Type type)
0x66358  brfalse.s loc_6637C
0x6635a  ldstr    aXmlpregentyped// "XmlPregenTypeDynamic"
0x6635f  ldc.i4.1
0x66360  newarr   [mscorlib]System.Object
0x66365  dup
0x66366  ldc.i4.0
0x66367  ldarg.1
0x66368  ldloc.s  0x1B
0x6636a  ldelem.ref
0x6636b  callvirt instance string [mscorlib]System.Type::get_FullName()
0x66370  stelem.ref
0x66371  call     string System.Xml.Res::GetString(string name, object[] args)
0x66376  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6637b  throw
0x6637c  ldloc.s  0x1B
0x6637e  ldc.i4.1
0x6637f  add
0x66380  stloc.s  0x1B
0x66382  ldloc.s  0x1B
0x66384  ldarg.1
0x66385  ldlen
0x66386  conv.i4
0x66387  blt.s    loc_66341
0x66389  ldloc.s  4
0x6638b  ldstr    aAssembly// "[assembly:"
0x66390  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x66395  ldloc.s  4
0x66397  ldtoken  System.Xml.Serialization.XmlSerializerVersionAttribute
0x6639c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x663a1  callvirt instance string [mscorlib]System.Type::get_FullName()
0x663a6  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x663ab  ldloc.s  4
0x663ad  ldstr    asc_12DDFC// "("
0x663b2  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x663b7  ldloc.s  4
0x663b9  ldstr    aParentassembly// "ParentAssemblyId="
0x663be  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x663c3  ldloc.s  4
0x663c5  ldarg.1
0x663c6  ldc.i4.0
0x663c7  ldelem.ref
0x663c8  call     string System.Xml.Serialization.TempAssembly::GenerateAssemblyId(class [mscorlib]System.Type type)
0x663cd  call     void System.Xml.Serialization.ReflectionAwareCodeGen::WriteQuotedCSharpString(class System.Xml.Serialization.IndentedWriter writer, string value)
0x663d2  ldloc.s  4
0x663d4  ldstr    aVersion_3// ", Version="
0x663d9  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x663de  ldloc.s  4
0x663e0  ldstr    a4000// "4.0.0.0"
0x663e5  call     void System.Xml.Serialization.ReflectionAwareCodeGen::WriteQuotedCSharpString(class System.Xml.Serialization.IndentedWriter writer, string value)
0x663ea  ldarg.2
0x663eb  brfalse.s loc_66401
0x663ed  ldloc.s  4
0x663ef  ldstr    aNamespace_1// ", Namespace="
0x663f4  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x663f9  ldloc.s  4
0x663fb  ldarg.2
0x663fc  call     void System.Xml.Serialization.ReflectionAwareCodeGen::WriteQuotedCSharpString(class System.Xml.Serialization.IndentedWriter writer, string value)
0x66401  ldloc.s  4
0x66403  ldstr    asc_12E828// ")]"
0x66408  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x6640d  newobj   instance void System.Xml.Serialization.CodeIdentifiers::.ctor()
0x66412  stloc.s  5
0x66414  ldloc.s  5
0x66416  ldstr    aXmlserializati_3// "XmlSerializationWriter"
0x6641b  ldstr    aXmlserializati_3// "XmlSerializationWriter"
0x66420  callvirt instance string System.Xml.Serialization.CodeIdentifiers::AddUnique(string identifier, object value)
0x66425  pop
0x66426  ldloc.s  5
0x66428  ldstr    aXmlserializati_4// "XmlSerializationReader"
0x6642d  ldstr    aXmlserializati_4// "XmlSerializationReader"
0x66432  callvirt instance string System.Xml.Serialization.CodeIdentifiers::AddUnique(string identifier, object value)
0x66437  pop
0x66438  ldnull
0x66439  stloc.s  6
0x6643b  ldarg.1
0x6643c  brfalse.s loc_66476
0x6643e  ldarg.1
0x6643f  ldlen
0x66440  conv.i4
0x66441  ldc.i4.1
0x66442  bne.un.s loc_66476
0x66444  ldarg.1
0x66445  ldc.i4.0
0x66446  ldelem.ref
0x66447  ldnull
0x66448  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6644d  brfalse.s loc_66476
0x6644f  ldarg.1
0x66450  ldc.i4.0
0x66451  ldelem.ref
0x66452  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x66457  call     string System.Xml.Serialization.CodeIdentifier::MakeValid(string identifier)
0x6645c  stloc.s  6
0x6645e  ldarg.1
0x6645f  ldc.i4.0
0x66460  ldelem.ref
0x66461  callvirt instance bool [mscorlib]System.Type::get_IsArray()
0x66466  brfalse.s loc_66476
0x66468  ldloc.s  6
0x6646a  ldstr    aArray_0// "Array"
0x6646f  call     string [mscorlib]System.String::Concat(string, string)
0x66474  stloc.s  6
0x66476  ldloc.s  4
0x66478  ldstr    aNamespaceMicro// "namespace Microsoft.Xml.Serialization.G"...
0x6647d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x66482  ldloc.s  4
  ... truncated ...
```
