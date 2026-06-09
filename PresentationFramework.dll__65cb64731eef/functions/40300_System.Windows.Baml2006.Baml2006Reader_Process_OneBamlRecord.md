# System.Windows.Baml2006.Baml2006Reader::Process_OneBamlRecord

- ea: `0x40300`
- end: `0x4066c`
- name: `System.Windows.Baml2006.Baml2006Reader::Process_OneBamlRecord`
- size: `876`
- prototype: ``
- caller_count: `3`
- callee_count: `53`
- tags: `registry_config`

## callers

- `0x3ff70`
- `0x40130`
- `0x402d0`

## callees

- `0x38c70`
- `0x40300`
- `0x40670`
- `0x40680`
- `0x40690`
- `0x406a0`
- `0x406b0`
- `0x40720`
- `0x40730`
- `0x40850`
- `0x408c0`
- `0x40910`
- `0x409b0`
- `0x40a40`
- `0x40a50`
- `0x40a60`
- `0x40a70`
- `0x40b30`
- `0x40c10`
- `0x40ca0`
- `0x40d30`
- `0x40e10`
- `0x40e30`
- `0x40f70`
- `0x40f90`
- `0x40fc0`
- `0x41090`
- `0x41350`
- `0x41520`
- `0x41630`
- `0x416b0`
- `0x419a0`
- `0x41bd0`
- `0x41cf0`
- `0x42130`
- `0x421f0`
- `0x42490`
- `0x424e0`
- `0x42530`
- `0x42580`
- `0x425b0`
- `0x428d0`
- `0x42920`
- `0x42980`
- `0x429b0`
- `0x429e0`
- `0x42a30`
- `0x42a90`
- `0x42ae0`
- `0x42b10`

## string_xrefs

- `0x40462`: `Found unexpected Xmlns BAML record`

## pseudocode

```c

```

## disassembly

```asm
0x40300  ldarg.0
0x40301  ldfld    class System.Windows.Baml2006.BamlBinaryReader System.Windows.Baml2006.Baml2006Reader::_binaryReader
0x40306  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.IO.BinaryReader::get_BaseStream()
0x4030b  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x40310  ldarg.0
0x40311  ldfld    class System.Windows.Baml2006.BamlBinaryReader System.Windows.Baml2006.Baml2006Reader::_binaryReader
0x40316  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.IO.BinaryReader::get_BaseStream()
0x4031b  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x40320  bne.un.s loc_4032B
0x40322  ldarg.0
0x40323  ldc.i4.1
0x40324  stfld    bool System.Windows.Baml2006.Baml2006Reader::_isEof
0x40329  ldc.i4.0
0x4032a  ret
0x4032b  ldarg.0
0x4032c  call     instance valuetype System.Windows.Baml2006.Baml2006RecordType System.Windows.Baml2006.Baml2006Reader::Read_RecordType()
0x40331  stloc.0
0x40332  ldloc.0
0x40333  switch   loc_4063B, loc_40421, loc_4042E, loc_40430, loc_4043B, loc_4046D, loc_40478, loc_404FC, loc_4051D, loc_40507, loc_4051D, loc_40507, loc_4051D, loc_40512, loc_40528, loc_40580, loc_4055F, loc_4056A, loc_404C5, loc_404D0, loc_40462, loc_405CD, loc_405E3, loc_4062B, loc_405AC, loc_4058B, loc_405C2, loc_405EB, loc_405F3, loc_405FB, loc_40603, loc_4060B, loc_40613, loc_404A4, loc_40499, loc_4048E, loc_40483, loc_405B7, loc_40596, loc_405A1, loc_4044C, loc_40457, loc_404DB, loc_404F1, loc_404E6, loc_40633, loc_404BA, loc_40446, loc_4053E, loc_40549, loc_40533, loc_40575, loc_405D8, loc_40623, loc_4061B \
0x4041c  br       loc_4063B
0x40421  ldarg.0
0x40422  ldc.i4.6
0x40423  conv.i8
0x40424  call     instance void System.Windows.Baml2006.Baml2006Reader::SkipBytes(int64 offset)
0x40429  br       loc_4066A
0x4042e  ldc.i4.0
0x4042f  ret
0x40430  ldarg.0
0x40431  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_ElementStart()
0x40436  br       loc_4066A
0x4043b  ldarg.0
0x4043c  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_ElementEnd()
0x40441  br       loc_4066A
0x40446  newobj   instance void [System.Xaml]System.Xaml.XamlParseException::.ctor()
0x4044b  throw
0x4044c  ldarg.0
0x4044d  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_KeyElementStart()
0x40452  br       loc_4066A
0x40457  ldarg.0
0x40458  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_KeyElementEnd()
0x4045d  br       loc_4066A
0x40462  ldstr    aFoundUnexpecte// "Found unexpected Xmlns BAML record"
0x40467  newobj   instance void [System.Xaml]System.Xaml.XamlParseException::.ctor(string)
0x4046c  throw
0x4046d  ldarg.0
0x4046e  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_Property()
0x40473  br       loc_4066A
0x40478  ldarg.0
0x40479  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PropertyCustom()
0x4047e  br       loc_4066A
0x40483  ldarg.0
0x40484  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PropertyWithConverter()
0x40489  br       loc_4066A
0x4048e  ldarg.0
0x4048f  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PropertyWithExtension()
0x40494  br       loc_4066A
0x40499  ldarg.0
0x4049a  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PropertyTypeReference()
0x4049f  br       loc_4066A
0x404a4  ldarg.0
0x404a5  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PropertyStringReference()
0x404aa  br       loc_4066A
0x404af  ldarg.0
0x404b0  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PropertyWithStaticResourceId()
0x404b5  br       loc_4066A
0x404ba  ldarg.0
0x404bb  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_ContentProperty()
0x404c0  br       loc_4066A
0x404c5  ldarg.0
0x404c6  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_RoutedEvent()
0x404cb  br       loc_4066A
0x404d0  ldarg.0
0x404d1  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_ClrEvent()
0x404d6  br       loc_4066A
0x404db  ldarg.0
0x404dc  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_ConstructorParametersStart()
0x404e1  br       loc_4066A
0x404e6  ldarg.0
0x404e7  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_ConstructorParameterType()
0x404ec  br       loc_4066A
0x404f1  ldarg.0
0x404f2  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_ConstructorParametersEnd()
0x404f7  br       loc_4066A
0x404fc  ldarg.0
0x404fd  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PropertyComplexStart()
0x40502  br       loc_4066A
0x40507  ldarg.0
0x40508  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PropertyArrayStart()
0x4050d  br       loc_4066A
0x40512  ldarg.0
0x40513  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PropertyIDictionaryStart()
0x40518  br       loc_4066A
0x4051d  ldarg.0
0x4051e  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PropertyEnd()
0x40523  br       loc_4066A
0x40528  ldarg.0
0x40529  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PropertyIDictionaryEnd()
0x4052e  br       loc_4066A
0x40533  ldarg.0
0x40534  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_StaticResourceId()
0x40539  br       loc_4066A
0x4053e  ldarg.0
0x4053f  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_StaticResourceStart()
0x40544  br       loc_4066A
0x40549  ldarg.0
0x4054a  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_StaticResourceEnd()
0x4054f  br       loc_4066A
0x40554  ldarg.0
0x40555  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_OptimizedStaticResource()
0x4055a  br       loc_4066A
0x4055f  ldarg.0
0x40560  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_Text()
0x40565  br       loc_4066A
0x4056a  ldarg.0
0x4056b  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_TextWithConverter()
0x40570  br       loc_4066A
0x40575  ldarg.0
0x40576  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_TextWithId()
0x4057b  br       loc_4066A
0x40580  ldarg.0
0x40581  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_LiteralContent()
0x40586  br       loc_4066A
0x4058b  ldarg.0
0x4058c  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_DefAttribute()
0x40591  br       loc_4066A
0x40596  ldarg.0
0x40597  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_DefAttributeKeyString()
0x4059c  br       loc_4066A
0x405a1  ldarg.0
0x405a2  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_DefAttributeKeyType()
0x405a7  br       loc_4066A
0x405ac  ldarg.0
0x405ad  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_DefTag()
0x405b2  br       loc_4066A
0x405b7  ldarg.0
0x405b8  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_DeferableContentStart()
0x405bd  br       loc_4066A
0x405c2  ldarg.0
0x405c3  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_EndAttributes()
0x405c8  br       loc_4066A
0x405cd  ldarg.0
0x405ce  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_XmlAttribute()
0x405d3  br       loc_4066A
0x405d8  ldarg.0
0x405d9  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PresentationOptionsAttribute()
0x405de  br       loc_4066A
0x405e3  ldarg.0
0x405e4  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_ProcessingInstruction()
0x405e9  br.s     loc_4066A
0x405eb  ldarg.0
0x405ec  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_PIMapping()
0x405f1  br.s     loc_4066A
0x405f3  ldarg.0
0x405f4  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_AssemblyInfo()
0x405f9  br.s     loc_4066A
0x405fb  ldarg.0
0x405fc  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_TypeInfo()
0x40601  br.s     loc_4066A
0x40603  ldarg.0
0x40604  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_TypeSerializerInfo()
0x40609  br.s     loc_4066A
0x4060b  ldarg.0
0x4060c  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_AttributeInfo()
0x40611  br.s     loc_4066A
0x40613  ldarg.0
0x40614  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_StringInfo()
0x40619  br.s     loc_4066A
0x4061b  ldarg.0
0x4061c  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_LinePosition()
0x40621  br.s     loc_4066A
0x40623  ldarg.0
0x40624  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_LineNumberAndPosition()
0x40629  br.s     loc_4066A
0x4062b  ldarg.0
0x4062c  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_Comment()
0x40631  br.s     loc_4066A
0x40633  ldarg.0
0x40634  call     instance void System.Windows.Baml2006.Baml2006Reader::Process_ConnectionId()
0x40639  br.s     loc_4066A
0x4063b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x40640  ldstr    aUnknownbamlrec// "UnknownBamlRecord"
0x40645  ldc.i4.1
0x40646  newarr   [mscorlib]System.Object
0x4064b  dup
0x4064c  ldc.i4.0
0x4064d  ldloc.0
0x4064e  box      System.Windows.Baml2006.Baml2006RecordType
0x40653  stelem.ref
0x40654  call     string System.Windows.SR::Get(string id, object[] args)
0x40659  ldc.i4.0
0x4065a  newarr   [mscorlib]System.Object
0x4065f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x40664  newobj   instance void [System.Xaml]System.Xaml.XamlParseException::.ctor(string)
0x40669  throw
0x4066a  ldc.i4.1
0x4066b  ret
```
