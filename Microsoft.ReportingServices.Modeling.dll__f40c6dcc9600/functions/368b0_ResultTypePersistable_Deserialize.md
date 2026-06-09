# ResultTypePersistable::Deserialize

- ea: `0x368b0`
- end: `0x369e4`
- name: `ResultTypePersistable::Deserialize`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x368a0`

## callees

- `0x15d0`
- `0x1d40`
- `0x1e20`
- `0x1eb0`
- `0x3890`
- `0x3990`
- `0x6920`
- `0x97d0`
- `0x19c50`
- `0x19d40`
- `0x368b0`
- `0x36aa0`

## string_xrefs

- `0x36981`: `Can not complete ResultType deserialization: DataType is not deserialized.`
- `0x36995`: `Can not complete ResultType deserialization: Cardinality is not deserialized.`
- `0x369a9`: `Can not complete ResultType deserialization: Nullable is not deserialized.`

## pseudocode

```c

```

## disassembly

```asm
0x368b0  ldloca.s 0
0x368b2  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType>
0x368b8  ldloca.s 1
0x368ba  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.Cardinality>
0x368c0  ldloca.s 2
0x368c2  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x368c8  ldnull
0x368c9  stloc.3
0x368ca  ldarga.s 1
0x368cc  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration ResultTypePersistable::get_Declaration()
0x368d1  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::RegisterDeclaration(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration declaration)
0x368d6  br       loc_3696C
0x368db  ldarga.s 1
0x368dd  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::get_CurrentMember()
0x368e2  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_MemberName()
0x368e7  stloc.s  4
0x368e9  ldloc.s  4
0x368eb  ldc.i4.5
0x368ec  beq.s    loc_36906
0x368ee  ldloc.s  4
0x368f0  ldc.i4.s 0x26
0x368f2  sub
0x368f3  switch   loc_36916, loc_36926, loc_36936
0x36904  br.s     loc_36941
0x36906  ldloca.s 0
0x36908  ldarga.s 1
0x3690a  call     instance unsigned int8 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadByte()
0x3690f  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType>::.ctor(var<u1>)
0x36914  br.s     loc_3696C
0x36916  ldloca.s 1
0x36918  ldarga.s 1
0x3691a  call     instance unsigned int8 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadByte()
0x3691f  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.Cardinality>::.ctor(var<u1>)
0x36924  br.s     loc_3696C
0x36926  ldloca.s 2
0x36928  ldarga.s 1
0x3692a  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadBoolean()
0x3692f  call     instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x36934  br.s     loc_3696C
0x36936  ldarga.s 1
0x36938  ldarg.0
0x36939  call     class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceHelper::ReadIQueryEntityReference(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader& reader, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable refOwner)
0x3693e  stloc.3
0x3693f  br.s     loc_3696C
0x36941  ldstr    aUnexpectedMemb// "Unexpected member: "
0x36946  ldarga.s 1
0x36948  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::get_CurrentMember()
0x3694d  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_MemberName()
0x36952  stloc.s  5
0x36954  ldloca.s 5
0x36956  constrained. Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName
0x3695c  callvirt instance string [mscorlib]System.Object::ToString()
0x36961  call     string [mscorlib]System.String::Concat(string, string)
0x36966  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x3696b  throw
0x3696c  ldarga.s 1
0x3696e  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::NextMember()
0x36973  brtrue   loc_368DB
0x36978  ldloca.s 0
0x3697a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType>::get_HasValue()
0x3697f  brtrue.s loc_3698C
0x36981  ldstr    aCanNotComplete// "Can not complete ResultType deserializa"...
0x36986  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x3698b  throw
0x3698c  ldloca.s 1
0x3698e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.Cardinality>::get_HasValue()
0x36993  brtrue.s loc_369A0
0x36995  ldstr    aCanNotComplete_0// "Can not complete ResultType deserializa"...
0x3699a  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x3699f  throw
0x369a0  ldloca.s 2
0x369a2  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x369a7  brtrue.s loc_369B4
0x369a9  ldstr    aCanNotComplete_1// "Can not complete ResultType deserializa"...
0x369ae  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x369b3  throw
0x369b4  ldarg.0
0x369b5  ldloca.s 0
0x369b7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType>::get_Value()
0x369bc  ldloca.s 1
0x369be  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.Cardinality>::get_Value()
0x369c3  ldloca.s 2
0x369c5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x369ca  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x369cf  stfld    valuetype Microsoft.ReportingServices.Modeling.ResultType ResultTypePersistable::m_resultType
0x369d4  ldloc.3
0x369d5  brfalse.s loc_369E3
0x369d7  ldarg.0
0x369d8  ldflda   valuetype Microsoft.ReportingServices.Modeling.ResultType ResultTypePersistable::m_resultType
0x369dd  ldloc.3
0x369de  call     instance void Microsoft.ReportingServices.Modeling.ResultType::SetEntityKeyTarget(class Microsoft.ReportingServices.Modeling.IQueryEntity entityKeyTarget)
0x369e3  ret
```
