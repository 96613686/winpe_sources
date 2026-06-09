# System.Xml.Serialization.XmlReflectionImporter::ImportMembersMapping_3

- ea: `0x7bda0`
- end: `0x7bf5a`
- name: `System.Xml.Serialization.XmlReflectionImporter::ImportMembersMapping_3`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config`

## callers

- `0x79be0`

## callees

- `0x622f0`
- `0x62370`
- `0x68c60`
- `0x69640`
- `0x696f0`
- `0x69730`
- `0x69bc0`
- `0x69bf0`
- `0x69cf0`
- `0x69d00`
- `0x69d10`
- `0x69d30`
- `0x69d80`
- `0x6b1c0`
- `0x73d90`
- `0x75c10`
- `0x7a210`
- `0x7bda0`
- `0x7bf60`
- `0x7e5d0`
- `0x7e970`
- `0x7e9b0`
- `0x7e9e0`

## string_xrefs

- `0x7be4b`: `XmlInvalidReturnPosition`
- `0x7be09`: `XmlRpcLitAttributeAttributes`
- `0x7be19`: `XmlInvalidAttributeType`
- `0x7be26`: `XmlAttribute`
- `0x7bea3`: `XmlIllegalMultipleTextMembers`
- `0x7becd`: `XmlMultipleXmlnsMembers`
- `0x7bf2c`: `XmlSequenceMembers`

## pseudocode

```c

```

## disassembly

```asm
0x7bda0  newobj   instance void System.Xml.Serialization.MembersMapping::.ctor()
0x7bda5  stloc.0
0x7bda6  ldloc.0
0x7bda7  ldarg.0
0x7bda8  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.XmlReflectionImporter::typeScope
0x7bdad  ldtoken  object[]
0x7bdb2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7bdb7  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(class [mscorlib]System.Type type)
0x7bdbc  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x7bdc1  ldarg.1
0x7bdc2  ldlen
0x7bdc3  conv.i4
0x7bdc4  newarr   System.Xml.Serialization.MemberMapping
0x7bdc9  stloc.1
0x7bdca  newobj   instance void System.Xml.Serialization.NameTable::.ctor()
0x7bdcf  stloc.2
0x7bdd0  newobj   instance void System.Xml.Serialization.NameTable::.ctor()
0x7bdd5  stloc.3
0x7bdd6  ldnull
0x7bdd7  stloc.s  4
0x7bdd9  ldc.i4.0
0x7bdda  stloc.s  5
0x7bddc  ldc.i4.0
0x7bddd  stloc.s  6
0x7bddf  br       loc_7BF1E
0x7bde4  nop
0x7bde5  ldarg.0
0x7bde6  ldarg.1
0x7bde7  ldloc.s  6
0x7bde9  ldelem.ref
0x7bdea  ldarg.2
0x7bdeb  ldarg.1
0x7bdec  ldarg.s  4
0x7bdee  ldarg.s  5
0x7bdf0  ldarg.s  6
0x7bdf2  call     instance class System.Xml.Serialization.MemberMapping System.Xml.Serialization.XmlReflectionImporter::ImportMemberMapping(class System.Xml.Serialization.XmlReflectionMember xmlReflectionMember, string ns, class System.Xml.Serialization.XmlReflectionMember[] xmlReflectionMembers, bool rpc, bool openModel, class System.Xml.Serialization.RecursionLimiter limiter)
0x7bdf7  stloc.s  7
0x7bdf9  ldarg.3
0x7bdfa  brtrue.s loc_7BE37
0x7bdfc  ldloc.s  7
0x7bdfe  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x7be03  brfalse.s loc_7BE37
0x7be05  ldarg.s  4
0x7be07  brfalse.s loc_7BE19
0x7be09  ldstr    aXmlrpclitattri// "XmlRpcLitAttributeAttributes"
0x7be0e  call     string System.Xml.Res::GetString(string name)
0x7be13  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7be18  throw
0x7be19  ldstr    aXmlinvalidattr_0// "XmlInvalidAttributeType"
0x7be1e  ldc.i4.1
0x7be1f  newarr   [mscorlib]System.Object
0x7be24  dup
0x7be25  ldc.i4.0
0x7be26  ldstr    aXmlattribute// "XmlAttribute"
0x7be2b  stelem.ref
0x7be2c  call     string System.Xml.Res::GetString(string name, object[] args)
0x7be31  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7be36  throw
0x7be37  ldarg.s  4
0x7be39  brfalse.s loc_7BE63
0x7be3b  ldarg.1
0x7be3c  ldloc.s  6
0x7be3e  ldelem.ref
0x7be3f  callvirt instance bool System.Xml.Serialization.XmlReflectionMember::get_IsReturnValue()
0x7be44  brfalse.s loc_7BE63
0x7be46  ldloc.s  6
0x7be48  ldc.i4.0
0x7be49  ble.s    loc_7BE5B
0x7be4b  ldstr    aXmlinvalidretu// "XmlInvalidReturnPosition"
0x7be50  call     string System.Xml.Res::GetString(string name)
0x7be55  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7be5a  throw
0x7be5b  ldloc.s  7
0x7be5d  ldc.i4.1
0x7be5e  callvirt instance void System.Xml.Serialization.MemberMapping::set_IsReturnValue(bool value)
0x7be63  ldloc.1
0x7be64  ldloc.s  6
0x7be66  ldloc.s  7
0x7be68  stelem.ref
0x7be69  ldloc.s  5
0x7be6b  ldloc.s  7
0x7be6d  callvirt instance bool System.Xml.Serialization.MemberMapping::get_IsSequence()
0x7be72  or
0x7be73  stloc.s  5
0x7be75  ldarg.1
0x7be76  ldloc.s  6
0x7be78  ldelem.ref
0x7be79  callvirt instance class System.Xml.Serialization.XmlAttributes System.Xml.Serialization.XmlReflectionMember::get_XmlAttributes()
0x7be7e  callvirt instance bool System.Xml.Serialization.XmlAttributes::get_XmlIgnore()
0x7be83  brtrue.s loc_7BE90
0x7be85  ldloc.s  7
0x7be87  ldloc.2
0x7be88  ldloc.3
0x7be89  ldloc.s  5
0x7be8b  call     void System.Xml.Serialization.XmlReflectionImporter::AddUniqueAccessor(class System.Xml.Serialization.MemberMapping member, class System.Xml.Serialization.INameScope elements, class System.Xml.Serialization.INameScope attributes, bool isSequence)
0x7be90  ldloc.1
0x7be91  ldloc.s  6
0x7be93  ldloc.s  7
0x7be95  stelem.ref
0x7be96  ldloc.s  7
0x7be98  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x7be9d  brfalse.s loc_7BEBC
0x7be9f  ldloc.s  4
0x7bea1  brfalse.s loc_7BEB3
0x7bea3  ldstr    aXmlillegalmult_0// "XmlIllegalMultipleTextMembers"
0x7bea8  call     string System.Xml.Res::GetString(string name)
0x7bead  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7beb2  throw
0x7beb3  ldloc.s  7
0x7beb5  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x7beba  stloc.s  4
0x7bebc  ldloc.s  7
0x7bebe  callvirt instance class System.Xml.Serialization.XmlnsAccessor System.Xml.Serialization.AccessorMapping::get_Xmlns()
0x7bec3  brfalse.s loc_7BEE5
0x7bec5  ldloc.0
0x7bec6  callvirt instance class System.Xml.Serialization.MemberMapping System.Xml.Serialization.MembersMapping::get_XmlnsMember()
0x7becb  brfalse.s loc_7BEDD
0x7becd  ldstr    aXmlmultiplexml_0// "XmlMultipleXmlnsMembers"
0x7bed2  call     string System.Xml.Res::GetString(string name)
0x7bed7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7bedc  throw
0x7bedd  ldloc.0
0x7bede  ldloc.s  7
0x7bee0  callvirt instance void System.Xml.Serialization.MembersMapping::set_XmlnsMember(class System.Xml.Serialization.MemberMapping value)
0x7bee5  leave.s  loc_7BF18
0x7bee7  stloc.s  8
0x7bee9  ldloc.s  8
0x7beeb  isinst   [mscorlib]System.Threading.ThreadAbortException
0x7bef0  brtrue.s loc_7BF04
0x7bef2  ldloc.s  8
0x7bef4  isinst   [mscorlib]System.StackOverflowException
0x7bef9  brtrue.s loc_7BF04
0x7befb  ldloc.s  8
0x7befd  isinst   [mscorlib]System.OutOfMemoryException
0x7bf02  brfalse.s loc_7BF06
0x7bf04  rethrow
0x7bf06  ldarg.0
0x7bf07  ldarg.1
0x7bf08  ldloc.s  6
0x7bf0a  ldelem.ref
0x7bf0b  callvirt instance string System.Xml.Serialization.XmlReflectionMember::get_MemberName()
0x7bf10  ldloc.s  8
0x7bf12  call     instance class [mscorlib]System.Exception System.Xml.Serialization.XmlReflectionImporter::CreateReflectionException(string context, class [mscorlib]System.Exception e)
0x7bf17  throw
0x7bf18  ldloc.s  6
0x7bf1a  ldc.i4.1
0x7bf1b  add
0x7bf1c  stloc.s  6
0x7bf1e  ldloc.s  6
0x7bf20  ldloc.1
0x7bf21  ldlen
0x7bf22  conv.i4
0x7bf23  blt      loc_7BDE4
0x7bf28  ldloc.s  5
0x7bf2a  brfalse.s loc_7BF4A
0x7bf2c  ldstr    aXmlsequencemem// "XmlSequenceMembers"
0x7bf31  ldc.i4.1
0x7bf32  newarr   [mscorlib]System.Object
0x7bf37  dup
0x7bf38  ldc.i4.0
0x7bf39  ldstr    aOrder// "Order"
0x7bf3e  stelem.ref
0x7bf3f  call     string System.Xml.Res::GetString(string name, object[] args)
0x7bf44  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7bf49  throw
0x7bf4a  ldloc.0
0x7bf4b  ldloc.1
0x7bf4c  callvirt instance void System.Xml.Serialization.MembersMapping::set_Members(class System.Xml.Serialization.MemberMapping[] value)
0x7bf51  ldloc.0
0x7bf52  ldarg.3
0x7bf53  callvirt instance void System.Xml.Serialization.MembersMapping::set_HasWrapperElement(bool value)
0x7bf58  ldloc.0
0x7bf59  ret
```
