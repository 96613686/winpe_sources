# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadVariant_0

- ea: `0x1468a0`
- end: `0x146aa8`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadVariant_0`
- size: `520`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1467f0`
- `0x146880`

## callees

- `0x1458e0`
- `0x1468a0`
- `0x14a7a0`
- `0x14a8c0`
- `0x14a970`
- `0x14a990`
- `0x14a9a0`
- `0x14a9c0`
- `0x14a9e0`
- `0x14ab40`
- `0x14ab50`

## string_xrefs

- `0x146a86`: `IntermediateFormatReader does not support {0}.{1}.`

## pseudocode

```c

```

## disassembly

```asm
0x1468a0  ldarg.1
0x1468a1  brfalse.s loc_146913
0x1468a3  ldarg.1
0x1468a4  ldc.i4.1
0x1468a5  beq      loc_146A78
0x1468aa  ldarg.1
0x1468ab  ldc.i4   0xEA
0x1468b0  sub
0x1468b1  switch   loc_146A6C, loc_146A60, loc_146A10, loc_146A21, loc_146A54, loc_146A43, loc_146915, loc_1469FF, loc_146A32, loc_146922, loc_146933, loc_146944, loc_146955, loc_146966, loc_146977, loc_146988, loc_146999, loc_1469AA, loc_1469BB, loc_1469CC, loc_1469DD, loc_1469EE
0x14690e  br       loc_146A80
0x146913  ldnull
0x146914  ret
0x146915  ldarg.0
0x146916  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x14691b  ldc.i4.0
0x14691c  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadString(bool checkforNull)
0x146921  ret
0x146922  ldarg.0
0x146923  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x146928  callvirt instance char [mscorlib]System.IO.BinaryReader::ReadChar()
0x14692d  box      [mscorlib]System.Char
0x146932  ret
0x146933  ldarg.0
0x146934  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x146939  callvirt instance bool [mscorlib]System.IO.BinaryReader::ReadBoolean()
0x14693e  box      [mscorlib]System.Boolean
0x146943  ret
0x146944  ldarg.0
0x146945  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x14694a  callvirt instance int16 [mscorlib]System.IO.BinaryReader::ReadInt16()
0x14694f  box      [mscorlib]System.Int16
0x146954  ret
0x146955  ldarg.0
0x146956  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x14695b  callvirt instance int32 [mscorlib]System.IO.BinaryReader::ReadInt32()
0x146960  box      [mscorlib]System.Int32
0x146965  ret
0x146966  ldarg.0
0x146967  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x14696c  callvirt instance int64 [mscorlib]System.IO.BinaryReader::ReadInt64()
0x146971  box      [mscorlib]System.Int64
0x146976  ret
0x146977  ldarg.0
0x146978  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x14697d  callvirt instance unsigned int16 [mscorlib]System.IO.BinaryReader::ReadUInt16()
0x146982  box      [mscorlib]System.UInt16
0x146987  ret
0x146988  ldarg.0
0x146989  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x14698e  callvirt instance unsigned int32 [mscorlib]System.IO.BinaryReader::ReadUInt32()
0x146993  box      [mscorlib]System.UInt32
0x146998  ret
0x146999  ldarg.0
0x14699a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x14699f  callvirt instance unsigned int64 [mscorlib]System.IO.BinaryReader::ReadUInt64()
0x1469a4  box      [mscorlib]System.UInt64
0x1469a9  ret
0x1469aa  ldarg.0
0x1469ab  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x1469b0  callvirt instance unsigned int8 [mscorlib]System.IO.BinaryReader::ReadByte()
0x1469b5  box      [mscorlib]System.Byte
0x1469ba  ret
0x1469bb  ldarg.0
0x1469bc  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x1469c1  callvirt instance int8 [mscorlib]System.IO.BinaryReader::ReadSByte()
0x1469c6  box      [mscorlib]System.SByte
0x1469cb  ret
0x1469cc  ldarg.0
0x1469cd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x1469d2  callvirt instance float32 [mscorlib]System.IO.BinaryReader::ReadSingle()
0x1469d7  box      [mscorlib]System.Single
0x1469dc  ret
0x1469dd  ldarg.0
0x1469de  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x1469e3  callvirt instance float64 [mscorlib]System.IO.BinaryReader::ReadDouble()
0x1469e8  box      [mscorlib]System.Double
0x1469ed  ret
0x1469ee  ldarg.0
0x1469ef  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x1469f4  callvirt instance valuetype [mscorlib]System.Decimal [mscorlib]System.IO.BinaryReader::ReadDecimal()
0x1469f9  box      [mscorlib]System.Decimal
0x1469fe  ret
0x1469ff  ldarg.0
0x146a00  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x146a05  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadDateTime()
0x146a0a  box      [mscorlib]System.DateTime
0x146a0f  ret
0x146a10  ldarg.0
0x146a11  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x146a16  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadDateTimeWithKind()
0x146a1b  box      [mscorlib]System.DateTime
0x146a20  ret
0x146a21  ldarg.0
0x146a22  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x146a27  callvirt instance valuetype [mscorlib]System.DateTimeOffset Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadDateTimeOffset()
0x146a2c  box      [mscorlib]System.DateTimeOffset
0x146a31  ret
0x146a32  ldarg.0
0x146a33  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x146a38  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadTimeSpan()
0x146a3d  box      [mscorlib]System.TimeSpan
0x146a42  ret
0x146a43  ldarg.0
0x146a44  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x146a49  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadGuid()
0x146a4e  box      [mscorlib]System.Guid
0x146a53  ret
0x146a54  ldarg.0
0x146a55  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x146a5a  callvirt instance unsigned int8[] Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadByteArray()
0x146a5f  ret
0x146a60  ldarg.0
0x146a61  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x146a66  callvirt instance class [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeography Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadSqlGeography()
0x146a6b  ret
0x146a6c  ldarg.0
0x146a6d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x146a72  callvirt instance class [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeometry Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadSqlGeometry()
0x146a77  ret
0x146a78  ldarg.0
0x146a79  ldc.i4.0
0x146a7a  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadRIFObject(bool verify)
0x146a7f  ret
0x146a80  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x146a85  ldc.i4.0
0x146a86  ldstr    aIntermediatefo// "IntermediateFormatReader does not suppo"...
0x146a8b  ldarg.1
0x146a8c  box      Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token
0x146a91  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x146a96  ldarg.1
0x146a97  box      Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token
0x146a9c  call     string [mscorlib]System.String::Format(string, object, object)
0x146aa1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x146aa6  ldnull
0x146aa7  ret
```
