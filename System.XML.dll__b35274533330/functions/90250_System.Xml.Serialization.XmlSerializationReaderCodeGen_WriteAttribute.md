# System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteAttribute

- ea: `0x90250`
- end: `0x90534`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteAttribute`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config`

## callers

- `0x8fd70`

## callees

- `0x62370`
- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x68600`
- `0x68a60`
- `0x68c50`
- `0x69620`
- `0x69640`
- `0x69b00`
- `0x72c10`
- `0x72c30`
- `0x86170`
- `0x8da80`
- `0x90250`
- `0x917e0`
- `0x91c90`
- `0x91ce0`
- `0x122c70`
- `0x122c90`
- `0x122ca0`
- `0x122d40`
- `0x122d60`

## string_xrefs

- `0x903af`: `XmlInternalError`
- `0x903d0`: `string listValues = Reader.Value;`
- `0x90498`: `Reader.Value`

## pseudocode

```c

```

## disassembly

```asm
0x90250  ldarg.1
0x90251  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x90256  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x9025b  stloc.0
0x9025c  ldloc.0
0x9025d  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x90262  isinst   System.Xml.Serialization.SpecialMapping
0x90267  brfalse  loc_903BF
0x9026c  ldloc.0
0x9026d  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x90272  castclass System.Xml.Serialization.SpecialMapping
0x90277  stloc.1
0x90278  ldloc.1
0x90279  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9027e  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0x90283  ldc.i4.s 0xA
0x90285  bne.un.s loc_902C4
0x90287  ldarg.0
0x90288  ldarg.1
0x90289  callvirt instance string Member::get_ArraySource()
0x9028e  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBegin(string source)
0x90293  ldarg.0
0x90294  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90299  ldstr    aAttr_0// "attr"
0x9029e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x902a3  ldarg.0
0x902a4  ldarg.1
0x902a5  callvirt instance string Member::get_ArraySource()
0x902aa  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceEnd(string source)
0x902af  ldarg.0
0x902b0  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x902b5  ldstr    asc_12B71A// ";"
0x902ba  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x902bf  br       loc_904C5
0x902c4  ldloc.1
0x902c5  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x902ca  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CanBeAttributeValue()
0x902cf  brfalse  loc_903AF
0x902d4  ldarg.0
0x902d5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x902da  ldstr    aIfAttrIs// "if (attr is "
0x902df  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x902e4  ldarg.0
0x902e5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x902ea  ldtoken  System.Xml.XmlAttribute
0x902ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x902f4  callvirt instance string [mscorlib]System.Type::get_FullName()
0x902f9  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x902fe  ldarg.0
0x902ff  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90304  ldstr    asc_134612// ") {"
0x90309  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9030e  ldarg.0
0x9030f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90314  dup
0x90315  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9031a  stloc.2
0x9031b  ldloc.2
0x9031c  ldc.i4.1
0x9031d  add
0x9031e  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x90323  ldarg.0
0x90324  ldarg.1
0x90325  callvirt instance string Member::get_ArraySource()
0x9032a  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBegin(string source)
0x9032f  ldarg.0
0x90330  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90335  ldstr    asc_12DDFC// "("
0x9033a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9033f  ldarg.0
0x90340  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90345  ldtoken  System.Xml.XmlAttribute
0x9034a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9034f  callvirt instance string [mscorlib]System.Type::get_FullName()
0x90354  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90359  ldarg.0
0x9035a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9035f  ldstr    aAttr_1// ")attr"
0x90364  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90369  ldarg.0
0x9036a  ldarg.1
0x9036b  callvirt instance string Member::get_ArraySource()
0x90370  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceEnd(string source)
0x90375  ldarg.0
0x90376  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9037b  ldstr    asc_12B71A// ";"
0x90380  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90385  ldarg.0
0x90386  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9038b  dup
0x9038c  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x90391  stloc.2
0x90392  ldloc.2
0x90393  ldc.i4.1
0x90394  sub
0x90395  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9039a  ldarg.0
0x9039b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x903a0  ldstr    asc_12E936// "}"
0x903a5  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x903aa  br       loc_904C5
0x903af  ldstr    aXmlinternalerr// "XmlInternalError"
0x903b4  call     string System.Xml.Res::GetString(string name)
0x903b9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x903be  throw
0x903bf  ldloc.0
0x903c0  callvirt instance bool System.Xml.Serialization.AttributeAccessor::get_IsList()
0x903c5  brfalse  loc_9047D
0x903ca  ldarg.0
0x903cb  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x903d0  ldstr    aStringListvalu// "string listValues = Reader.Value;"
0x903d5  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x903da  ldarg.0
0x903db  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x903e0  ldstr    aStringValsList// "string[] vals = listValues.Split(null);"
0x903e5  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x903ea  ldarg.0
0x903eb  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x903f0  ldstr    aForIntI0IValsL// "for (int i = 0; i < vals.Length; i++) {"
0x903f5  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x903fa  ldarg.0
0x903fb  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90400  dup
0x90401  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x90406  stloc.2
0x90407  ldloc.2
0x90408  ldc.i4.1
0x90409  add
0x9040a  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9040f  ldarg.0
0x90410  ldarg.1
0x90411  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x90416  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x9041b  ldarg.1
0x9041c  callvirt instance string Member::get_ArrayName()
0x90421  call     instance string System.Xml.Serialization.XmlSerializationReaderCodeGen::GetArraySource(class System.Xml.Serialization.TypeDesc typeDesc, string arrayName)
0x90426  stloc.3
0x90427  ldarg.0
0x90428  ldloc.3
0x90429  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBegin(string source)
0x9042e  ldarg.0
0x9042f  ldloc.0
0x90430  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x90435  ldstr    aValsI// "vals[i]"
0x9043a  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WritePrimitive(class System.Xml.Serialization.TypeMapping mapping, string source)
0x9043f  ldarg.0
0x90440  ldloc.3
0x90441  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceEnd(string source)
0x90446  ldarg.0
0x90447  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9044c  ldstr    asc_12B71A// ";"
0x90451  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90456  ldarg.0
0x90457  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9045c  dup
0x9045d  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x90462  stloc.2
0x90463  ldloc.2
0x90464  ldc.i4.1
0x90465  sub
0x90466  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9046b  ldarg.0
0x9046c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90471  ldstr    asc_12E936// "}"
0x90476  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9047b  br.s     loc_904C5
0x9047d  ldarg.0
0x9047e  ldarg.1
0x9047f  callvirt instance string Member::get_ArraySource()
0x90484  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceBegin(string source)
0x90489  ldarg.0
0x9048a  ldloc.0
0x9048b  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x90490  ldloc.0
0x90491  callvirt instance bool System.Xml.Serialization.AttributeAccessor::get_IsList()
0x90496  brtrue.s loc_9049F
0x90498  ldstr    aReaderValue// "Reader.Value"
0x9049d  br.s     loc_904A4
0x9049f  ldstr    aValsI// "vals[i]"
0x904a4  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WritePrimitive(class System.Xml.Serialization.TypeMapping mapping, string source)
0x904a9  ldarg.0
0x904aa  ldarg.1
0x904ab  callvirt instance string Member::get_ArraySource()
0x904b0  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteSourceEnd(string source)
0x904b5  ldarg.0
0x904b6  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x904bb  ldstr    asc_12B71A// ";"
0x904c0  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x904c5  ldarg.1
0x904c6  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x904cb  callvirt instance valuetype System.Xml.Serialization.SpecifiedAccessor System.Xml.Serialization.MemberMapping::get_CheckSpecified()
0x904d0  ldc.i4.2
0x904d1  bne.un.s loc_9050A
0x904d3  ldarg.1
0x904d4  callvirt instance string Member::get_CheckSpecifiedSource()
0x904d9  brfalse.s loc_9050A
0x904db  ldarg.1
0x904dc  callvirt instance string Member::get_CheckSpecifiedSource()
0x904e1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x904e6  ldc.i4.0
0x904e7  ble.s    loc_9050A
0x904e9  ldarg.0
0x904ea  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x904ef  ldarg.1
0x904f0  callvirt instance string Member::get_CheckSpecifiedSource()
0x904f5  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x904fa  ldarg.0
0x904fb  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90500  ldstr    aTrue_1// " = true;"
0x90505  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9050a  ldarg.1
0x9050b  callvirt instance string Member::get_ParamsReadSource()
0x90510  brfalse.s loc_90533
0x90512  ldarg.0
0x90513  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90518  ldarg.1
0x90519  callvirt instance string Member::get_ParamsReadSource()
0x9051e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x90523  ldarg.0
0x90524  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x90529  ldstr    aTrue_1// " = true;"
0x9052e  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x90533  ret
```
