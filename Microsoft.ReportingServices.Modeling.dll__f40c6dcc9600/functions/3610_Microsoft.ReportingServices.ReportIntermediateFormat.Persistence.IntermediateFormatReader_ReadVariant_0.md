# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadVariant_0

- ea: `0x3610`
- end: `0x3818`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadVariant_0`
- size: `520`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x3560`
- `0x35f0`

## callees

- `0xf60`
- `0x2650`
- `0x3610`
- `0x6e80`
- `0x6fa0`
- `0x7050`
- `0x7070`
- `0x7080`
- `0x70a0`
- `0x70c0`
- `0x7220`
- `0x7230`

## string_xrefs

- `0x37f6`: `IntermediateFormatReader does not support {0}.{1}.`

## pseudocode

```c

```

## disassembly

```asm
0x3610  ldarg.1
0x3611  brfalse.s loc_3683
0x3613  ldarg.1
0x3614  ldc.i4.1
0x3615  beq      loc_37E8
0x361a  ldarg.1
0x361b  ldc.i4   0xEA
0x3620  sub
0x3621  switch   loc_37DC, loc_37D0, loc_3780, loc_3791, loc_37C4, loc_37B3, loc_3685, loc_376F, loc_37A2, loc_3692, loc_36A3, loc_36B4, loc_36C5, loc_36D6, loc_36E7, loc_36F8, loc_3709, loc_371A, loc_372B, loc_373C, loc_374D, loc_375E
0x367e  br       loc_37F0
0x3683  ldnull
0x3684  ret
0x3685  ldarg.0
0x3686  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x368b  ldc.i4.0
0x368c  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadString(bool checkforNull)
0x3691  ret
0x3692  ldarg.0
0x3693  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x3698  callvirt instance char [mscorlib]System.IO.BinaryReader::ReadChar()
0x369d  box      [mscorlib]System.Char
0x36a2  ret
0x36a3  ldarg.0
0x36a4  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x36a9  callvirt instance bool [mscorlib]System.IO.BinaryReader::ReadBoolean()
0x36ae  box      [mscorlib]System.Boolean
0x36b3  ret
0x36b4  ldarg.0
0x36b5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x36ba  callvirt instance int16 [mscorlib]System.IO.BinaryReader::ReadInt16()
0x36bf  box      [mscorlib]System.Int16
0x36c4  ret
0x36c5  ldarg.0
0x36c6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x36cb  callvirt instance int32 [mscorlib]System.IO.BinaryReader::ReadInt32()
0x36d0  box      [mscorlib]System.Int32
0x36d5  ret
0x36d6  ldarg.0
0x36d7  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x36dc  callvirt instance int64 [mscorlib]System.IO.BinaryReader::ReadInt64()
0x36e1  box      [mscorlib]System.Int64
0x36e6  ret
0x36e7  ldarg.0
0x36e8  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x36ed  callvirt instance unsigned int16 [mscorlib]System.IO.BinaryReader::ReadUInt16()
0x36f2  box      [mscorlib]System.UInt16
0x36f7  ret
0x36f8  ldarg.0
0x36f9  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x36fe  callvirt instance unsigned int32 [mscorlib]System.IO.BinaryReader::ReadUInt32()
0x3703  box      [mscorlib]System.UInt32
0x3708  ret
0x3709  ldarg.0
0x370a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x370f  callvirt instance unsigned int64 [mscorlib]System.IO.BinaryReader::ReadUInt64()
0x3714  box      [mscorlib]System.UInt64
0x3719  ret
0x371a  ldarg.0
0x371b  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x3720  callvirt instance unsigned int8 [mscorlib]System.IO.BinaryReader::ReadByte()
0x3725  box      [mscorlib]System.Byte
0x372a  ret
0x372b  ldarg.0
0x372c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x3731  callvirt instance int8 [mscorlib]System.IO.BinaryReader::ReadSByte()
0x3736  box      [mscorlib]System.SByte
0x373b  ret
0x373c  ldarg.0
0x373d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x3742  callvirt instance float32 [mscorlib]System.IO.BinaryReader::ReadSingle()
0x3747  box      [mscorlib]System.Single
0x374c  ret
0x374d  ldarg.0
0x374e  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x3753  callvirt instance float64 [mscorlib]System.IO.BinaryReader::ReadDouble()
0x3758  box      [mscorlib]System.Double
0x375d  ret
0x375e  ldarg.0
0x375f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x3764  callvirt instance valuetype [mscorlib]System.Decimal [mscorlib]System.IO.BinaryReader::ReadDecimal()
0x3769  box      [mscorlib]System.Decimal
0x376e  ret
0x376f  ldarg.0
0x3770  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x3775  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadDateTime()
0x377a  box      [mscorlib]System.DateTime
0x377f  ret
0x3780  ldarg.0
0x3781  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x3786  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadDateTimeWithKind()
0x378b  box      [mscorlib]System.DateTime
0x3790  ret
0x3791  ldarg.0
0x3792  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x3797  callvirt instance valuetype [mscorlib]System.DateTimeOffset Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadDateTimeOffset()
0x379c  box      [mscorlib]System.DateTimeOffset
0x37a1  ret
0x37a2  ldarg.0
0x37a3  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x37a8  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadTimeSpan()
0x37ad  box      [mscorlib]System.TimeSpan
0x37b2  ret
0x37b3  ldarg.0
0x37b4  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x37b9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadGuid()
0x37be  box      [mscorlib]System.Guid
0x37c3  ret
0x37c4  ldarg.0
0x37c5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x37ca  callvirt instance unsigned int8[] Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadByteArray()
0x37cf  ret
0x37d0  ldarg.0
0x37d1  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x37d6  callvirt instance class [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeography Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadSqlGeography()
0x37db  ret
0x37dc  ldarg.0
0x37dd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x37e2  callvirt instance class [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeometry Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadSqlGeometry()
0x37e7  ret
0x37e8  ldarg.0
0x37e9  ldc.i4.0
0x37ea  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadRIFObject(bool verify)
0x37ef  ret
0x37f0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::get_Tracer()
0x37f5  ldc.i4.0
0x37f6  ldstr    aIntermediatefo// "IntermediateFormatReader does not suppo"...
0x37fb  ldarg.1
0x37fc  box      Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token
0x3801  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3806  ldarg.1
0x3807  box      Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token
0x380c  call     string [mscorlib]System.String::Format(string, object, object)
0x3811  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x3816  ldnull
0x3817  ret
```
