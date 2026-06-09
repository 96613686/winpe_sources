# System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteAttribute

- ea: `0xa04b0`
- end: `0xa05bf`
- name: `System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteAttribute`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x9fe70`

## callees

- `0x62370`
- `0x68470`
- `0x684b0`
- `0x68600`
- `0x68620`
- `0x68660`
- `0x686d0`
- `0x686f0`
- `0x68c50`
- `0x72ba0`
- `0x72c10`
- `0x72c30`
- `0x72d80`
- `0x86170`
- `0x9dc20`
- `0xa04b0`

## string_xrefs

- `0xa0531`: `XmlInternalError`
- `0xa04ee`: `WriteXmlAttribute(`
- `0xa0588`: `WriteAttribute`

## pseudocode

```c

```

## disassembly

```asm
0xa04b0  ldarg.2
0xa04b1  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa04b6  isinst   System.Xml.Serialization.SpecialMapping
0xa04bb  brfalse  loc_A0541
0xa04c0  ldarg.2
0xa04c1  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa04c6  castclass System.Xml.Serialization.SpecialMapping
0xa04cb  stloc.0
0xa04cc  ldloc.0
0xa04cd  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa04d2  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0xa04d7  ldc.i4.s 0xA
0xa04d9  beq.s    loc_A04E8
0xa04db  ldloc.0
0xa04dc  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa04e1  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CanBeAttributeValue()
0xa04e6  brfalse.s loc_A0531
0xa04e8  ldarg.0
0xa04e9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa04ee  ldstr    aWritexmlattrib// "WriteXmlAttribute("
0xa04f3  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa04f8  ldarg.0
0xa04f9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa04fe  ldarg.1
0xa04ff  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0504  ldarg.0
0xa0505  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa050a  ldstr    asc_128826// ", "
0xa050f  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0514  ldarg.0
0xa0515  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa051a  ldarg.3
0xa051b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0520  ldarg.0
0xa0521  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0526  ldstr    asc_133068// ");"
0xa052b  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa0530  ret
0xa0531  ldstr    aXmlinternalerr// "XmlInternalError"
0xa0536  call     string System.Xml.Res::GetString(string name)
0xa053b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xa0540  throw
0xa0541  ldarg.2
0xa0542  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa0547  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa054c  stloc.1
0xa054d  ldloc.1
0xa054e  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0xa0553  brtrue.s loc_A0587
0xa0555  ldc.i4.5
0xa0556  newarr   [mscorlib]System.String
0xa055b  dup
0xa055c  ldc.i4.0
0xa055d  ldstr    asc_12FF58// "(("
0xa0562  stelem.ref
0xa0563  dup
0xa0564  ldc.i4.1
0xa0565  ldloc.1
0xa0566  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa056b  stelem.ref
0xa056c  dup
0xa056d  ldc.i4.2
0xa056e  ldstr    asc_129CD8// ")"
0xa0573  stelem.ref
0xa0574  dup
0xa0575  ldc.i4.3
0xa0576  ldarg.1
0xa0577  stelem.ref
0xa0578  dup
0xa0579  ldc.i4.4
0xa057a  ldstr    asc_129CD8// ")"
0xa057f  stelem.ref
0xa0580  call     string [mscorlib]System.String::Concat(string[])
0xa0585  starg.s  1
0xa0587  ldarg.0
0xa0588  ldstr    aWriteattribute_0// "WriteAttribute"
0xa058d  ldarg.2
0xa058e  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa0593  ldarg.2
0xa0594  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0xa0599  ldc.i4.1
0xa059a  beq.s    loc_A05A3
0xa059c  ldstr    asc_1284AE// ""
0xa05a1  br.s     loc_A05A9
0xa05a3  ldarg.2
0xa05a4  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0xa05a9  ldarg.2
0xa05aa  callvirt instance object System.Xml.Serialization.Accessor::get_Default()
0xa05af  ldarg.1
0xa05b0  ldarg.2
0xa05b1  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa05b6  ldc.i4.0
0xa05b7  ldc.i4.0
0xa05b8  ldc.i4.0
0xa05b9  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WritePrimitive(string method, string name, string ns, object defaultValue, string source, class System.Xml.Serialization.TypeMapping mapping, bool writeXsiType, bool isElement, bool isNullable)
0xa05be  ret
```
