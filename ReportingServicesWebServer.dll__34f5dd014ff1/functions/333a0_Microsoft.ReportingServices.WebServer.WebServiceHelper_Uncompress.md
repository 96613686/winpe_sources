# Microsoft.ReportingServices.WebServer.WebServiceHelper::Uncompress

- ea: `0x333a0`
- end: `0x33458`
- name: `Microsoft.ReportingServices.WebServer.WebServiceHelper::Uncompress`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2db60`

## callees

- `0x333a0`

## string_xrefs

- `0x333fe`: `Decompressed UserToken length did not match.`
- `0x33444`: `Invalid user token length.`

## pseudocode

```c

```

## disassembly

```asm
0x333a0  ldc.i4.0
0x333a1  stloc.0
0x333a2  ldarg.0
0x333a3  ldc.i4.0
0x333a4  call     int32 [mscorlib]System.BitConverter::ToInt32(unsigned int8[], int32)
0x333a9  stloc.0
0x333aa  leave.s  loc_333B5
0x333ac  stloc.1
0x333ad  ldarg.1
0x333ae  ldloc.1
0x333af  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string, class [mscorlib]System.Exception)
0x333b4  throw
0x333b5  ldloc.0
0x333b6  ldc.i4.0
0x333b7  ble.s    loc_33432
0x333b9  ldarg.0
0x333ba  ldc.i4.4
0x333bb  ldarg.0
0x333bc  ldlen
0x333bd  conv.i4
0x333be  ldc.i4.4
0x333bf  sub
0x333c0  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[], int32, int32)
0x333c5  stloc.2
0x333c6  ldloc.2
0x333c7  ldc.i4.0
0x333c8  newobj   instance void [System]System.IO.Compression.GZipStream::.ctor(class [mscorlib]System.IO.Stream, valuetype [System]System.IO.Compression.CompressionMode)
0x333cd  stloc.3
0x333ce  ldloc.0
0x333cf  newarr   [mscorlib]System.Byte
0x333d4  dup
0x333d5  ldc.i4.0
0x333d6  ldloc.0
0x333d7  ldloc.3
0x333d8  dup
0x333d9  ldvirtftn instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x333df  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.StreamSupport/StreamRead::.ctor(object, native int)
0x333e4  call     int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.StreamSupport::ReadToCountOrEnd(unsigned int8[], int32, int32, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.StreamSupport/StreamRead)
0x333e9  ldloc.0
0x333ea  beq.s    loc_3340F
0x333ec  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x333f1  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x333f6  brfalse.s loc_33408
0x333f8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x333fd  ldc.i4.1
0x333fe  ldstr    aDecompressedUs// "Decompressed UserToken length did not m"...
0x33403  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x33408  ldarg.1
0x33409  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x3340e  throw
0x3340f  stloc.s  4
0x33411  leave.s  loc_33455
0x33413  ldloc.3
0x33414  brfalse.s loc_3341C
0x33416  ldloc.3
0x33417  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3341c  endfinally
0x3341d  ldloc.2
0x3341e  brfalse.s loc_33426
0x33420  ldloc.2
0x33421  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33426  endfinally
0x33427  stloc.s  5
0x33429  ldarg.1
0x3342a  ldloc.s  5
0x3342c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string, class [mscorlib]System.Exception)
0x33431  throw
0x33432  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x33437  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x3343c  brfalse.s loc_3344E
0x3343e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x33443  ldc.i4.1
0x33444  ldstr    aInvalidUserTok// "Invalid user token length."
0x33449  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x3344e  ldarg.1
0x3344f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x33454  throw
0x33455  ldloc.s  4
0x33457  ret
```
