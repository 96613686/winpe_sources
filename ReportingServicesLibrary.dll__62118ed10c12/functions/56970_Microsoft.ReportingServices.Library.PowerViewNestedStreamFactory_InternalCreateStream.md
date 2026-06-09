# Microsoft.ReportingServices.Library.PowerViewNestedStreamFactory::InternalCreateStream

- ea: `0x56970`
- end: `0x569c2`
- name: `Microsoft.ReportingServices.Library.PowerViewNestedStreamFactory::InternalCreateStream`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x55460`
- `0x55ba0`
- `0x56970`

## string_xrefs

- `0x5697c`: `RenderEditResponseStreamFactory.InternalCreateStream: !willSeek`
- `0x5698f`: `RenderEditResponseStreamFactory.InternalCreateStream: !needCacheableStream`

## pseudocode

```c

```

## disassembly

```asm
0x56970  ldarg.1
0x56971  brfalse.s loc_569AC
0x56973  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_BufferedResponseTracer()
0x56978  ldarg.2
0x56979  ldc.i4.0
0x5697a  ceq
0x5697c  ldstr    aRendereditresp// "RenderEditResponseStreamFactory.Interna"...
0x56981  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x56986  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_BufferedResponseTracer()
0x5698b  ldarg.3
0x5698c  ldc.i4.0
0x5698d  ceq
0x5698f  ldstr    aRendereditresp_0// "RenderEditResponseStreamFactory.Interna"...
0x56994  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x56999  ldarg.0
0x5699a  ldfld    class [Microsoft.ReportingServices.ProgressivePacking]Microsoft.ReportingServices.ProgressivePackaging.IMessageWriter Microsoft.ReportingServices.Library.PowerViewNestedStreamFactory::m_writer
0x5699f  ldstr    aRpds_0// "rpds"
0x569a4  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.ProgressivePacking]Microsoft.ReportingServices.ProgressivePackaging.IMessageWriter::CreateWritableStream(string)
0x569a9  stloc.0
0x569aa  br.s     loc_569B9
0x569ac  newobj   instance void Microsoft.ReportingServices.Library.MemoryThenFileStream::.ctor()
0x569b1  stloc.0
0x569b2  ldarg.0
0x569b3  ldloc.0
0x569b4  call     instance void Microsoft.ReportingServices.Library.StreamFactoryBase::RegisterStreamForClosing(class [mscorlib]System.IO.Stream stream)
0x569b9  ldarg.0
0x569ba  ldloc.0
0x569bb  call     instance void Microsoft.ReportingServices.Library.StreamFactoryBase::RegisterStreamForClosing(class [mscorlib]System.IO.Stream stream)
0x569c0  ldloc.0
0x569c1  ret
```
