# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadNLevelVariantHashtable

- ea: `0x2be0`
- end: `0x2c72`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadNLevelVariantHashtable`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x2be0`

## callees

- `0xf60`
- `0x2be0`
- `0x35f0`
- `0x6940`
- `0x6de0`
- `0x70e0`

## string_xrefs

- `0x2c40`: `Invalid token: {0} while reading NLevelVariantHashtable`

## pseudocode

```c

```

## disassembly

```asm
0x2be0  ldarg.0
0x2be1  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x2be6  ldarg.0
0x2be7  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMember
0x2bec  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_ObjectType()
0x2bf1  ldloca.s 0
0x2bf3  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadDictionaryStart(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType objectType, [out] int32& dictionarySize)
0x2bf8  brfalse.s loc_2C70
0x2bfa  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x2bff  stloc.1
0x2c00  ldc.i4.0
0x2c01  stloc.2
0x2c02  br.s     loc_2C6A
0x2c04  ldarg.0
0x2c05  call     instance object Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadVariant()
0x2c0a  stloc.3
0x2c0b  ldarg.0
0x2c0c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x2c11  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadToken()
0x2c16  stloc.s  5
0x2c18  ldloc.s  5
0x2c1a  ldc.i4.1
0x2c1b  beq.s    loc_2C30
0x2c1d  ldloc.s  5
0x2c1f  ldc.i4   0xE8
0x2c24  bne.un.s loc_2C3A
0x2c26  ldarg.0
0x2c27  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadNLevelVariantHashtable()
0x2c2c  stloc.s  4
0x2c2e  br.s     loc_2C5D
0x2c30  ldarg.0
0x2c31  call     instance object Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadVariant()
0x2c36  stloc.s  4
0x2c38  br.s     loc_2C5D
0x2c3a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::get_Tracer()
0x2c3f  ldc.i4.0
0x2c40  ldstr    aInvalidToken0W// "Invalid token: {0} while reading NLevel"...
0x2c45  ldc.i4.1
0x2c46  newarr   [mscorlib]System.Object
0x2c4b  dup
0x2c4c  ldc.i4.0
0x2c4d  ldloc.s  5
0x2c4f  box      Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token
0x2c54  stelem.ref
0x2c55  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string, object[])
0x2c5a  ldnull
0x2c5b  stloc.s  4
0x2c5d  ldloc.1
0x2c5e  ldloc.3
0x2c5f  ldloc.s  4
0x2c61  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x2c66  ldloc.2
0x2c67  ldc.i4.1
0x2c68  add
0x2c69  stloc.2
0x2c6a  ldloc.2
0x2c6b  ldloc.0
0x2c6c  blt.s    loc_2C04
0x2c6e  ldloc.1
0x2c6f  ret
0x2c70  ldnull
0x2c71  ret
```
