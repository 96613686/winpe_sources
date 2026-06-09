# Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable.Deserialize

- ea: `0x81b0`
- end: `0x8299`
- name: `Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable.Deserialize`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1d40`
- `0x1e20`
- `0x1eb0`
- `0x34a0`
- `0x3990`
- `0x6920`
- `0x81b0`
- `0x82c0`
- `0x97d0`
- `0xa0a0`

## string_xrefs

- `0x8245`: `Failed to deserialize collection contents.`

## pseudocode

```c

```

## disassembly

```asm
0x81b0  ldnull
0x81b1  stloc.0
0x81b2  ldnull
0x81b3  stloc.1
0x81b4  ldarga.s 1
0x81b6  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::get_Declaration()
0x81bb  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::RegisterDeclaration(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration declaration)
0x81c0  br.s     loc_822E
0x81c2  ldarga.s 1
0x81c4  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::get_CurrentMember()
0x81c9  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_MemberName()
0x81ce  stloc.3
0x81cf  ldloc.3
0x81d0  ldc.i4.s 0x34
0x81d2  beq.s    loc_81E0
0x81d4  ldloc.3
0x81d5  ldc.i4.s 0x65
0x81d7  beq.s    loc_81EF
0x81d9  ldloc.3
0x81da  ldc.i4.s 0x66
0x81dc  beq.s    loc_81F9
0x81de  br.s     loc_8203
0x81e0  ldarg.0
0x81e1  ldarga.s 1
0x81e3  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadBoolean()
0x81e8  stfld    bool Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::m_readOnly
0x81ed  br.s     loc_822E
0x81ef  ldarga.s 1
0x81f1  call     instance string[] Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadStringArray()
0x81f6  stloc.0
0x81f7  br.s     loc_822E
0x81f9  ldarga.s 1
0x81fb  call     instance string[] Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadStringArray()
0x8200  stloc.1
0x8201  br.s     loc_822E
0x8203  ldstr    aUnexpectedMemb// "Unexpected member: "
0x8208  ldarga.s 1
0x820a  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::get_CurrentMember()
0x820f  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_MemberName()
0x8214  stloc.s  4
0x8216  ldloca.s 4
0x8218  constrained. Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName
0x821e  callvirt instance string [mscorlib]System.Object::ToString()
0x8223  call     string [mscorlib]System.String::Concat(string, string)
0x8228  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x822d  throw
0x822e  ldarga.s 1
0x8230  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::NextMember()
0x8235  brtrue.s loc_81C2
0x8237  ldloc.0
0x8238  brfalse.s loc_8245
0x823a  ldloc.1
0x823b  brfalse.s loc_8245
0x823d  ldloc.0
0x823e  ldlen
0x823f  conv.i4
0x8240  ldloc.1
0x8241  ldlen
0x8242  conv.i4
0x8243  beq.s    loc_8250
0x8245  ldstr    aFailedToDeseri// "Failed to deserialize collection conten"...
0x824a  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x824f  throw
0x8250  ldarg.0
0x8251  ldfld    bool Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::m_readOnly
0x8256  stloc.2
0x8257  ldarg.0
0x8258  ldc.i4.0
0x8259  stfld    bool Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::m_readOnly
0x825e  ldc.i4.0
0x825f  stloc.s  5
0x8261  br.s     loc_828A
0x8263  ldloca.s 6
0x8265  ldloc.0
0x8266  ldloc.s  5
0x8268  ldelem.ref
0x8269  ldloc.1
0x826a  ldloc.s  5
0x826c  ldelem.ref
0x826d  call     instance void Microsoft.ReportingServices.Modeling.QName::.ctor(string name, string ns)
0x8272  ldarg.0
0x8273  ldloc.s  6
0x8275  call     instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype Microsoft.ReportingServices.Modeling.QName>::Contains(var<u1>)
0x827a  brtrue.s loc_8284
0x827c  ldarg.0
0x827d  ldloc.s  6
0x827f  call     instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype Microsoft.ReportingServices.Modeling.QName>::Add(var<u1>)
0x8284  ldloc.s  5
0x8286  ldc.i4.1
0x8287  add
0x8288  stloc.s  5
0x828a  ldloc.s  5
0x828c  ldloc.0
0x828d  ldlen
0x828e  conv.i4
0x828f  blt.s    loc_8263
0x8291  ldarg.0
0x8292  ldloc.2
0x8293  stfld    bool Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::m_readOnly
0x8298  ret
```
