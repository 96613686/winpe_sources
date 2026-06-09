# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteBatch

- ea: `0x2110`
- end: `0x21d1`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteBatch`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a90`

## callees

- `0x1a0`
- `0x1d70`
- `0x1e90`
- `0x2060`
- `0x20e0`
- `0x2110`
- `0x2300`

## pseudocode

```c

```

## disassembly

```asm
0x2110  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x2115  stloc.0
0x2116  ldarg.s  4
0x2118  stloc.2
0x2119  ldc.i4.0
0x211a  stloc.3
0x211b  br.s     loc_2144
0x211d  ldloc.2
0x211e  ldloc.3
0x211f  ldelem.ref
0x2120  stloc.s  4
0x2122  ldloc.0
0x2123  ldloc.s  4
0x2125  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x212a  brfalse.s loc_2137
0x212c  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrDuplicatedBatchItem()
0x2131  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x2136  throw
0x2137  ldloc.0
0x2138  ldloc.s  4
0x213a  ldnull
0x213b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x2140  ldloc.3
0x2141  ldc.i4.1
0x2142  add
0x2143  stloc.3
0x2144  ldloc.3
0x2145  ldloc.2
0x2146  ldlen
0x2147  conv.i4
0x2148  blt.s    loc_211D
0x214a  ldarg.1
0x214b  ldarg.0
0x214c  ldfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_encoding
0x2151  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding)
0x2156  stloc.1
0x2157  ldarg.s  4
0x2159  stloc.2
0x215a  ldc.i4.0
0x215b  stloc.3
0x215c  br.s     loc_21C3
0x215e  ldloc.2
0x215f  ldloc.3
0x2160  ldelem.ref
0x2161  stloc.s  5
0x2163  ldarg.0
0x2164  ldarg.1
0x2165  ldc.i4.1
0x2166  call     instance class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::CreateXmlWriter(class [mscorlib]System.IO.Stream stream, bool disableUTF8Bom)
0x216b  stloc.s  6
0x216d  ldloc.s  5
0x216f  ldstr    aMetadata// "Metadata"
0x2174  ldc.i4.5
0x2175  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x217a  brtrue.s loc_2190
0x217c  ldarg.0
0x217d  ldloc.1
0x217e  ldc.i4.0
0x217f  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteBatchItemHeader(class [mscorlib]System.IO.StreamWriter streamWriter, bool isDataFeed)
0x2184  ldarg.0
0x2185  ldloc.s  6
0x2187  ldarg.2
0x2188  ldarg.3
0x2189  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteCSDLMetadataDocument(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters)
0x218e  br.s     loc_21A4
0x2190  ldarg.0
0x2191  ldloc.1
0x2192  ldc.i4.1
0x2193  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteBatchItemHeader(class [mscorlib]System.IO.StreamWriter streamWriter, bool isDataFeed)
0x2198  ldarg.0
0x2199  ldloc.s  6
0x219b  ldarg.2
0x219c  ldarg.3
0x219d  ldloc.s  5
0x219f  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteAtomDataFeed(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters, string dataFeed)
0x21a4  ldloc.1
0x21a5  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine()
0x21aa  ldloc.s  6
0x21ac  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x21b1  leave.s  loc_21BF
0x21b3  ldloc.s  6
0x21b5  brfalse.s loc_21BE
0x21b7  ldloc.s  6
0x21b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21be  endfinally
0x21bf  ldloc.3
0x21c0  ldc.i4.1
0x21c1  add
0x21c2  stloc.3
0x21c3  ldloc.3
0x21c4  ldloc.2
0x21c5  ldlen
0x21c6  conv.i4
0x21c7  blt.s    loc_215E
0x21c9  ldarg.0
0x21ca  ldloc.1
0x21cb  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteBatchItemTermination(class [mscorlib]System.IO.StreamWriter streamWriter)
0x21d0  ret
```
