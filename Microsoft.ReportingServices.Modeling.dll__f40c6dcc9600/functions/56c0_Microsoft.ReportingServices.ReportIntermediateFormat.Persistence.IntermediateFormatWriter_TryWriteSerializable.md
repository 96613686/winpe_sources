# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::TryWriteSerializable

- ea: `0x56c0`
- end: `0x577a`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::TryWriteSerializable`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x56a0`

## callees

- `0xf60`
- `0x3fa0`
- `0x56c0`
- `0x57c0`
- `0x7470`

## string_xrefs

- `0x575d`: `Error occurred during serialization: `

## pseudocode

```c

```

## disassembly

```asm
0x56c0  ldarg.0
0x56c1  ldarg.1
0x56c2  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::TryWrite(object obj)
0x56c7  brtrue   loc_5776
0x56cc  ldarg.0
0x56cd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x56d2  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.IO.BinaryWriter::get_BaseStream()
0x56d7  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x56dc  stloc.0
0x56dd  ldarg.0
0x56de  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::get_ProhibitSerializableValues()
0x56e3  brtrue.s loc_573C
0x56e5  ldarg.1
0x56e6  isinst   [mscorlib]System.Runtime.Serialization.ISerializable
0x56eb  brtrue.s loc_5700
0x56ed  ldarg.1
0x56ee  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x56f3  callvirt instance valuetype [mscorlib]System.Reflection.TypeAttributes [mscorlib]System.Type::get_Attributes()
0x56f8  ldc.i4   0x2000
0x56fd  and
0x56fe  brfalse.s loc_573C
0x5700  ldarg.0
0x5701  ldfld    class [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_binaryFormatter
0x5706  brtrue.s loc_5713
0x5708  ldarg.0
0x5709  newobj   instance void [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::.ctor()
0x570e  stfld    class [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_binaryFormatter
0x5713  ldarg.0
0x5714  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x5719  ldc.i4   0xE9
0x571e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::Write(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x5723  ldarg.0
0x5724  ldfld    class [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_binaryFormatter
0x5729  ldarg.0
0x572a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x572f  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.IO.BinaryWriter::get_BaseStream()
0x5734  ldarg.1
0x5735  callvirt instance void [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::Serialize(class [mscorlib]System.IO.Stream, object)
0x573a  br.s     loc_5740
0x573c  ldc.i4.0
0x573d  stloc.1
0x573e  leave.s  loc_5778
0x5740  leave.s  loc_5776
0x5742  pop
0x5743  rethrow
0x5745  stloc.2
0x5746  ldarg.0
0x5747  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writer
0x574c  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.IO.BinaryWriter::get_BaseStream()
0x5751  ldloc.0
0x5752  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x5757  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::get_Tracer()
0x575c  ldc.i4.2
0x575d  ldstr    aErrorOccurredD// "Error occurred during serialization: "
0x5762  ldloc.2
0x5763  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5768  call     string [mscorlib]System.String::Concat(string, string)
0x576d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5772  ldc.i4.0
0x5773  stloc.1
0x5774  leave.s  loc_5778
0x5776  ldc.i4.1
0x5777  ret
0x5778  ldloc.1
0x5779  ret
```
