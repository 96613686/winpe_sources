# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write_39

- ea: `0x57d0`
- end: `0x5c21`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write_39`
- size: `1105`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x4780`
- `0x4f20`
- `0x4f70`
- `0x4fd0`
- `0x57b0`
- `0x57c0`

## callees

- `0xf60`
- `0x57d0`
- `0x6930`
- `0x7280`
- `0x72b0`
- `0x72d0`
- `0x7300`
- `0x73e0`
- `0x7470`
- `0x7650`
- `0x7660`

## string_xrefs

- `0x5b60`: `You must call WriteEnum for enums`

## pseudocode

```c

```

## disassembly

```asm
0x57d0  ldarg.1
0x57d1  brfalse.s loc_57DB
0x57d3  ldarg.1
0x57d4  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x57d9  bne.un.s loc_57EC
0x57db  ldarg.0
0x57dc  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x57e1  ldc.i4.0
0x57e2  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x57e7  br       loc_5C1F
0x57ec  ldarg.1
0x57ed  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x57f2  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x57f7  stloc.0
0x57f8  ldloc.0
0x57f9  switch   loc_584F, loc_5AC8, loc_584F, loc_5860, loc_58AC, loc_59E3, loc_5886, loc_5971, loc_5A56, loc_5997, loc_5A7C, loc_59BD, loc_5AA2, loc_5A09, loc_594B, loc_5925, loc_58D2, loc_5AC8, loc_5A2F
0x584a  br       loc_5AC8
0x584f  ldarg.0
0x5850  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5855  ldc.i4.0
0x5856  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x585b  br       loc_5C1F
0x5860  ldarg.0
0x5861  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5866  ldc.i4   0xF4
0x586b  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5870  ldarg.0
0x5871  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5876  ldarg.1
0x5877  unbox.any [mscorlib]System.Boolean
0x587c  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(bool)
0x5881  br       loc_5C1F
0x5886  ldarg.0
0x5887  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x588c  ldc.i4   0xFB
0x5891  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5896  ldarg.0
0x5897  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x589c  ldarg.1
0x589d  unbox.any [mscorlib]System.Byte
0x58a2  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(unsigned int8)
0x58a7  br       loc_5C1F
0x58ac  ldarg.0
0x58ad  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x58b2  ldc.i4   0xF3
0x58b7  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x58bc  ldarg.0
0x58bd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x58c2  ldarg.1
0x58c3  unbox.any [mscorlib]System.Char
0x58c8  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(char)
0x58cd  br       loc_5C1F
0x58d2  ldarg.1
0x58d3  unbox.any [mscorlib]System.DateTime
0x58d8  stloc.1
0x58d9  ldarg.0
0x58da  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_currentMember
0x58df  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_Token()
0x58e4  stloc.2
0x58e5  ldloc.2
0x58e6  ldc.i4.1
0x58e7  beq.s    loc_58F1
0x58e9  ldloc.2
0x58ea  ldc.i4   0xE9
0x58ef  bne.un.s loc_5907
0x58f1  ldloca.s 1
0x58f3  call     instance valuetype [mscorlib]System.DateTimeKind [mscorlib]System.DateTime::get_Kind()
0x58f8  brfalse.s loc_5901
0x58fa  ldc.i4   0xEC
0x58ff  br.s     loc_5906
0x5901  ldc.i4   0xF1
0x5906  stloc.2
0x5907  ldarg.0
0x5908  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x590d  ldloc.2
0x590e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5913  ldarg.0
0x5914  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5919  ldloc.1
0x591a  ldloc.2
0x591b  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype [mscorlib]System.DateTime dateTime, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5920  br       loc_5C1F
0x5925  ldarg.0
0x5926  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x592b  ldc.i4   0xFF
0x5930  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5935  ldarg.0
0x5936  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x593b  ldarg.1
0x593c  unbox.any [mscorlib]System.Decimal
0x5941  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(valuetype [mscorlib]System.Decimal)
0x5946  br       loc_5C1F
0x594b  ldarg.0
0x594c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5951  ldc.i4   0xFE
0x5956  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x595b  ldarg.0
0x595c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5961  ldarg.1
0x5962  unbox.any [mscorlib]System.Double
0x5967  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(float64)
0x596c  br       loc_5C1F
0x5971  ldarg.0
0x5972  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5977  ldc.i4   0xF5
0x597c  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5981  ldarg.0
0x5982  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5987  ldarg.1
0x5988  unbox.any [mscorlib]System.Int16
0x598d  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(int16)
0x5992  br       loc_5C1F
0x5997  ldarg.0
0x5998  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x599d  ldc.i4   0xF6
0x59a2  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x59a7  ldarg.0
0x59a8  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x59ad  ldarg.1
0x59ae  unbox.any [mscorlib]System.Int32
0x59b3  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(int32)
0x59b8  br       loc_5C1F
0x59bd  ldarg.0
0x59be  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x59c3  ldc.i4   0xF7
0x59c8  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x59cd  ldarg.0
0x59ce  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x59d3  ldarg.1
0x59d4  unbox.any [mscorlib]System.Int64
0x59d9  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(int64)
0x59de  br       loc_5C1F
0x59e3  ldarg.0
0x59e4  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x59e9  ldc.i4   0xFC
0x59ee  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x59f3  ldarg.0
0x59f4  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x59f9  ldarg.1
0x59fa  unbox.any [mscorlib]System.SByte
0x59ff  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(int8)
0x5a04  br       loc_5C1F
0x5a09  ldarg.0
0x5a0a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5a0f  ldc.i4   0xFD
0x5a14  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5a19  ldarg.0
0x5a1a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5a1f  ldarg.1
0x5a20  unbox.any [mscorlib]System.Single
0x5a25  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(float32)
0x5a2a  br       loc_5C1F
0x5a2f  ldarg.0
0x5a30  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5a35  ldc.i4   0xF0
0x5a3a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5a3f  ldarg.0
0x5a40  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5a45  ldarg.1
0x5a46  castclass [mscorlib]System.String
0x5a4b  ldc.i4.0
0x5a4c  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(string str, bool writeObjType)
0x5a51  br       loc_5C1F
0x5a56  ldarg.0
0x5a57  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5a5c  ldc.i4   0xF8
0x5a61  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5a66  ldarg.0
0x5a67  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5a6c  ldarg.1
0x5a6d  unbox.any [mscorlib]System.UInt16
0x5a72  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(unsigned int16)
0x5a77  br       loc_5C1F
0x5a7c  ldarg.0
0x5a7d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5a82  ldc.i4   0xF9
0x5a87  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5a8c  ldarg.0
0x5a8d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5a92  ldarg.1
0x5a93  unbox.any [mscorlib]System.UInt32
0x5a98  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(unsigned int32)
0x5a9d  br       loc_5C1F
0x5aa2  ldarg.0
0x5aa3  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5aa8  ldc.i4   0xFA
0x5aad  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5ab2  ldarg.0
0x5ab3  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5ab8  ldarg.1
0x5ab9  unbox.any [mscorlib]System.UInt64
0x5abe  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(unsigned int64)
0x5ac3  br       loc_5C1F
0x5ac8  ldarg.1
0x5ac9  isinst   [mscorlib]System.TimeSpan
0x5ace  brfalse.s loc_5AF6
0x5ad0  ldarg.0
0x5ad1  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5ad6  ldc.i4   0xF2
0x5adb  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5ae0  ldarg.0
0x5ae1  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5ae6  ldarg.1
0x5ae7  unbox.any [mscorlib]System.TimeSpan
0x5aec  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype [mscorlib]System.TimeSpan timeSpan)
0x5af1  br       loc_5C1F
0x5af6  ldarg.1
0x5af7  isinst   [mscorlib]System.DateTimeOffset
0x5afc  brfalse.s loc_5B24
0x5afe  ldarg.0
0x5aff  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5b04  ldc.i4   0xED
0x5b09  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5b0e  ldarg.0
0x5b0f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5b14  ldarg.1
0x5b15  unbox.any [mscorlib]System.DateTimeOffset
0x5b1a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype [mscorlib]System.DateTimeOffset dateTimeOffset)
0x5b1f  br       loc_5C1F
0x5b24  ldarg.1
0x5b25  isinst   [mscorlib]System.Guid
0x5b2a  brfalse.s loc_5B52
0x5b2c  ldarg.0
0x5b2d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5b32  ldc.i4   0xEF
0x5b37  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5b3c  ldarg.0
0x5b3d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5b42  ldarg.1
0x5b43  unbox.any [mscorlib]System.Guid
0x5b48  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype [mscorlib]System.Guid guid)
0x5b4d  br       loc_5C1F
0x5b52  ldarg.1
0x5b53  isinst   [mscorlib]System.Enum
0x5b58  brfalse.s loc_5B6F
0x5b5a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::get_Tracer()
0x5b5f  ldc.i4.0
0x5b60  ldstr    aYouMustCallWri// "You must call WriteEnum for enums"
0x5b65  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x5b6a  br       loc_5C1F
0x5b6f  ldarg.1
0x5b70  isinst   unsigned int8[]
0x5b75  brfalse.s loc_5B9D
0x5b77  ldarg.0
0x5b78  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5b7d  ldc.i4   0xEE
0x5b82  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5b87  ldarg.0
0x5b88  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5b8d  ldarg.1
0x5b8e  castclass unsigned int8[]
0x5b93  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(unsigned int8[])
0x5b98  br       loc_5C1F
0x5b9d  ldarg.1
0x5b9e  isinst   [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeography
0x5ba3  brfalse.s loc_5BC8
0x5ba5  ldarg.0
0x5ba6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5bab  ldc.i4   0xEB
0x5bb0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5bb5  ldarg.0
0x5bb6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5bbb  ldarg.1
0x5bbc  castclass [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeography
0x5bc1  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(class [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeography sqlGeography)
0x5bc6  br.s     loc_5C1F
0x5bc8  ldarg.1
0x5bc9  isinst   [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeometry
0x5bce  brfalse.s loc_5BF3
0x5bd0  ldarg.0
0x5bd1  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5bd6  ldc.i4   0xEA
0x5bdb  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5be0  ldarg.0
0x5be1  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5be6  ldarg.1
0x5be7  castclass [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeometry
0x5bec  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(class [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeometry sqlGeometry)
0x5bf1  br.s     loc_5C1F
0x5bf3  ldarg.3
0x5bf4  brfalse.s loc_5C1D
0x5bf6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::get_Tracer()
0x5bfb  ldc.i4.0
0x5bfc  ldstr    aUnsupportedObj// "Unsupported object type: "
0x5c01  ldarg.1
0x5c02  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5c07  dup
0x5c08  brtrue.s loc_5C0E
0x5c0a  pop
0x5c0b  ldnull
0x5c0c  br.s     loc_5C13
0x5c0e  callvirt instance string [mscorlib]System.Object::ToString()
0x5c13  call     string [mscorlib]System.String::Concat(string, string)
0x5c18  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x5c1d  ldc.i4.0
0x5c1e  ret
0x5c1f  ldc.i4.1
0x5c20  ret
```
