# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write_39

- ea: `0x148a60`
- end: `0x148eb1`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write_39`
- size: `1105`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x147a10`
- `0x1481b0`
- `0x148200`
- `0x148260`
- `0x148a40`
- `0x148a50`

## callees

- `0x148a60`
- `0x14a250`
- `0x14aba0`
- `0x14abd0`
- `0x14abf0`
- `0x14ac20`
- `0x14ad00`
- `0x14ad90`
- `0x14af70`
- `0x14af80`

## string_xrefs

- `0x148df0`: `You must call WriteEnum for enums`

## pseudocode

```c

```

## disassembly

```asm
0x148a60  ldarg.1
0x148a61  brfalse.s loc_148A6B
0x148a63  ldarg.1
0x148a64  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x148a69  bne.un.s loc_148A7C
0x148a6b  ldarg.0
0x148a6c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148a71  ldc.i4.0
0x148a72  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148a77  br       loc_148EAF
0x148a7c  ldarg.1
0x148a7d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x148a82  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x148a87  stloc.0
0x148a88  ldloc.0
0x148a89  switch   loc_148ADF, loc_148D58, loc_148ADF, loc_148AF0, loc_148B3C, loc_148C73, loc_148B16, loc_148C01, loc_148CE6, loc_148C27, loc_148D0C, loc_148C4D, loc_148D32, loc_148C99, loc_148BDB, loc_148BB5, loc_148B62, loc_148D58, loc_148CBF
0x148ada  br       loc_148D58
0x148adf  ldarg.0
0x148ae0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148ae5  ldc.i4.0
0x148ae6  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148aeb  br       loc_148EAF
0x148af0  ldarg.0
0x148af1  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148af6  ldc.i4   0xF4
0x148afb  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148b00  ldarg.0
0x148b01  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148b06  ldarg.1
0x148b07  unbox.any [mscorlib]System.Boolean
0x148b0c  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(bool)
0x148b11  br       loc_148EAF
0x148b16  ldarg.0
0x148b17  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148b1c  ldc.i4   0xFB
0x148b21  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148b26  ldarg.0
0x148b27  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148b2c  ldarg.1
0x148b2d  unbox.any [mscorlib]System.Byte
0x148b32  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(unsigned int8)
0x148b37  br       loc_148EAF
0x148b3c  ldarg.0
0x148b3d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148b42  ldc.i4   0xF3
0x148b47  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148b4c  ldarg.0
0x148b4d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148b52  ldarg.1
0x148b53  unbox.any [mscorlib]System.Char
0x148b58  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(char)
0x148b5d  br       loc_148EAF
0x148b62  ldarg.1
0x148b63  unbox.any [mscorlib]System.DateTime
0x148b68  stloc.1
0x148b69  ldarg.0
0x148b6a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_currentMember
0x148b6f  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_Token()
0x148b74  stloc.2
0x148b75  ldloc.2
0x148b76  ldc.i4.1
0x148b77  beq.s    loc_148B81
0x148b79  ldloc.2
0x148b7a  ldc.i4   0xE9
0x148b7f  bne.un.s loc_148B97
0x148b81  ldloca.s 1
0x148b83  call     instance valuetype [mscorlib]System.DateTimeKind [mscorlib]System.DateTime::get_Kind()
0x148b88  brfalse.s loc_148B91
0x148b8a  ldc.i4   0xEC
0x148b8f  br.s     loc_148B96
0x148b91  ldc.i4   0xF1
0x148b96  stloc.2
0x148b97  ldarg.0
0x148b98  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148b9d  ldloc.2
0x148b9e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148ba3  ldarg.0
0x148ba4  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148ba9  ldloc.1
0x148baa  ldloc.2
0x148bab  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype [mscorlib]System.DateTime dateTime, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148bb0  br       loc_148EAF
0x148bb5  ldarg.0
0x148bb6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148bbb  ldc.i4   0xFF
0x148bc0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148bc5  ldarg.0
0x148bc6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148bcb  ldarg.1
0x148bcc  unbox.any [mscorlib]System.Decimal
0x148bd1  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(valuetype [mscorlib]System.Decimal)
0x148bd6  br       loc_148EAF
0x148bdb  ldarg.0
0x148bdc  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148be1  ldc.i4   0xFE
0x148be6  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148beb  ldarg.0
0x148bec  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148bf1  ldarg.1
0x148bf2  unbox.any [mscorlib]System.Double
0x148bf7  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(float64)
0x148bfc  br       loc_148EAF
0x148c01  ldarg.0
0x148c02  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148c07  ldc.i4   0xF5
0x148c0c  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148c11  ldarg.0
0x148c12  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148c17  ldarg.1
0x148c18  unbox.any [mscorlib]System.Int16
0x148c1d  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(int16)
0x148c22  br       loc_148EAF
0x148c27  ldarg.0
0x148c28  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148c2d  ldc.i4   0xF6
0x148c32  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148c37  ldarg.0
0x148c38  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148c3d  ldarg.1
0x148c3e  unbox.any [mscorlib]System.Int32
0x148c43  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(int32)
0x148c48  br       loc_148EAF
0x148c4d  ldarg.0
0x148c4e  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148c53  ldc.i4   0xF7
0x148c58  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148c5d  ldarg.0
0x148c5e  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148c63  ldarg.1
0x148c64  unbox.any [mscorlib]System.Int64
0x148c69  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(int64)
0x148c6e  br       loc_148EAF
0x148c73  ldarg.0
0x148c74  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148c79  ldc.i4   0xFC
0x148c7e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148c83  ldarg.0
0x148c84  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148c89  ldarg.1
0x148c8a  unbox.any [mscorlib]System.SByte
0x148c8f  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(int8)
0x148c94  br       loc_148EAF
0x148c99  ldarg.0
0x148c9a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148c9f  ldc.i4   0xFD
0x148ca4  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148ca9  ldarg.0
0x148caa  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148caf  ldarg.1
0x148cb0  unbox.any [mscorlib]System.Single
0x148cb5  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(float32)
0x148cba  br       loc_148EAF
0x148cbf  ldarg.0
0x148cc0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148cc5  ldc.i4   0xF0
0x148cca  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148ccf  ldarg.0
0x148cd0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148cd5  ldarg.1
0x148cd6  castclass [mscorlib]System.String
0x148cdb  ldc.i4.0
0x148cdc  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(string str, bool writeObjType)
0x148ce1  br       loc_148EAF
0x148ce6  ldarg.0
0x148ce7  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148cec  ldc.i4   0xF8
0x148cf1  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148cf6  ldarg.0
0x148cf7  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148cfc  ldarg.1
0x148cfd  unbox.any [mscorlib]System.UInt16
0x148d02  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(unsigned int16)
0x148d07  br       loc_148EAF
0x148d0c  ldarg.0
0x148d0d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148d12  ldc.i4   0xF9
0x148d17  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148d1c  ldarg.0
0x148d1d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148d22  ldarg.1
0x148d23  unbox.any [mscorlib]System.UInt32
0x148d28  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(unsigned int32)
0x148d2d  br       loc_148EAF
0x148d32  ldarg.0
0x148d33  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148d38  ldc.i4   0xFA
0x148d3d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148d42  ldarg.0
0x148d43  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148d48  ldarg.1
0x148d49  unbox.any [mscorlib]System.UInt64
0x148d4e  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(unsigned int64)
0x148d53  br       loc_148EAF
0x148d58  ldarg.1
0x148d59  isinst   [mscorlib]System.TimeSpan
0x148d5e  brfalse.s loc_148D86
0x148d60  ldarg.0
0x148d61  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148d66  ldc.i4   0xF2
0x148d6b  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148d70  ldarg.0
0x148d71  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148d76  ldarg.1
0x148d77  unbox.any [mscorlib]System.TimeSpan
0x148d7c  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype [mscorlib]System.TimeSpan timeSpan)
0x148d81  br       loc_148EAF
0x148d86  ldarg.1
0x148d87  isinst   [mscorlib]System.DateTimeOffset
0x148d8c  brfalse.s loc_148DB4
0x148d8e  ldarg.0
0x148d8f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148d94  ldc.i4   0xED
0x148d99  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148d9e  ldarg.0
0x148d9f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148da4  ldarg.1
0x148da5  unbox.any [mscorlib]System.DateTimeOffset
0x148daa  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype [mscorlib]System.DateTimeOffset dateTimeOffset)
0x148daf  br       loc_148EAF
0x148db4  ldarg.1
0x148db5  isinst   [mscorlib]System.Guid
0x148dba  brfalse.s loc_148DE2
0x148dbc  ldarg.0
0x148dbd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148dc2  ldc.i4   0xEF
0x148dc7  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148dcc  ldarg.0
0x148dcd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148dd2  ldarg.1
0x148dd3  unbox.any [mscorlib]System.Guid
0x148dd8  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype [mscorlib]System.Guid guid)
0x148ddd  br       loc_148EAF
0x148de2  ldarg.1
0x148de3  isinst   [mscorlib]System.Enum
0x148de8  brfalse.s loc_148DFF
0x148dea  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x148def  ldc.i4.0
0x148df0  ldstr    aYouMustCallWri// "You must call WriteEnum for enums"
0x148df5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x148dfa  br       loc_148EAF
0x148dff  ldarg.1
0x148e00  isinst   unsigned int8[]
0x148e05  brfalse.s loc_148E2D
0x148e07  ldarg.0
0x148e08  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148e0d  ldc.i4   0xEE
0x148e12  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148e17  ldarg.0
0x148e18  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148e1d  ldarg.1
0x148e1e  castclass unsigned int8[]
0x148e23  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(unsigned int8[])
0x148e28  br       loc_148EAF
0x148e2d  ldarg.1
0x148e2e  isinst   [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeography
0x148e33  brfalse.s loc_148E58
0x148e35  ldarg.0
0x148e36  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148e3b  ldc.i4   0xEB
0x148e40  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148e45  ldarg.0
0x148e46  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148e4b  ldarg.1
0x148e4c  castclass [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeography
0x148e51  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(class [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeography sqlGeography)
0x148e56  br.s     loc_148EAF
0x148e58  ldarg.1
0x148e59  isinst   [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeometry
0x148e5e  brfalse.s loc_148E83
0x148e60  ldarg.0
0x148e61  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148e66  ldc.i4   0xEA
0x148e6b  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x148e70  ldarg.0
0x148e71  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x148e76  ldarg.1
0x148e77  castclass [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeometry
0x148e7c  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(class [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeometry sqlGeometry)
0x148e81  br.s     loc_148EAF
0x148e83  ldarg.3
0x148e84  brfalse.s loc_148EAD
0x148e86  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x148e8b  ldc.i4.0
0x148e8c  ldstr    aUnsupportedObj// "Unsupported object type: "
0x148e91  ldarg.1
0x148e92  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x148e97  dup
0x148e98  brtrue.s loc_148E9E
0x148e9a  pop
0x148e9b  ldnull
0x148e9c  br.s     loc_148EA3
0x148e9e  callvirt instance string [mscorlib]System.Object::ToString()
0x148ea3  call     string [mscorlib]System.String::Concat(string, string)
0x148ea8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x148ead  ldc.i4.0
0x148eae  ret
0x148eaf  ldc.i4.1
0x148eb0  ret
```
