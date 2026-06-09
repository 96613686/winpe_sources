# Microsoft.ReportingServices.Portal.Services.DataService::RenderReport

- ea: `0x9b50`
- end: `0x9be6`
- name: `Microsoft.ReportingServices.Portal.Services.DataService::RenderReport`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x94e0`
- `0x9540`

## callees

- `0x99c0`
- `0x9b50`
- `0x20550`

## pseudocode

```c

```

## disassembly

```asm
0x9b50  newobj   instance void <>c__DisplayClass29_0::.ctor()
0x9b55  stloc.0
0x9b56  ldstr    aDeviceinfoShar// "<DeviceInfo><SharedDataSetTable>true</S"...
0x9b5b  stloc.1
0x9b5c  ldarga.s 4
0x9b5e  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x9b63  brfalse.s loc_9B92
0x9b65  ldloc.1
0x9b66  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Parse(string)
0x9b6b  dup
0x9b6c  ldstr    aMaxrows// "MaxRows"
0x9b71  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x9b76  ldarga.s 4
0x9b78  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x9b7d  box      [mscorlib]System.Int32
0x9b82  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x9b87  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::Add(object)
0x9b8c  callvirt instance string [mscorlib]System.Object::ToString()
0x9b91  stloc.1
0x9b92  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializer [ReportingServicesLibrary]Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlSerializer()
0x9b97  stloc.2
0x9b98  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x9b9d  stloc.3
0x9b9e  ldloc.2
0x9b9f  ldloc.3
0x9ba0  ldarg.2
0x9ba1  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializer::Serialize(class [mscorlib]System.IO.Stream, object)
0x9ba6  ldloc.0
0x9ba7  ldloc.3
0x9ba8  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x9bad  stfld    unsigned int8[] <>c__DisplayClass29_0::reportBytes
0x9bb2  ldarg.0
0x9bb3  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Services.DataService::_logger
0x9bb8  ldc.i4.4
0x9bb9  ldloc.0
0x9bba  ldftn    instance string <>c__DisplayClass29_0::<RenderReport>b__0()
0x9bc0  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x9bc5  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0x9bca  leave.s  loc_9BD6
0x9bcc  ldloc.3
0x9bcd  brfalse.s loc_9BD5
0x9bcf  ldloc.3
0x9bd0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9bd5  endfinally
0x9bd6  ldarg.0
0x9bd7  ldarg.1
0x9bd8  ldloc.0
0x9bd9  ldfld    unsigned int8[] <>c__DisplayClass29_0::reportBytes
0x9bde  ldloc.1
0x9bdf  ldarg.3
0x9be0  call     instance string Microsoft.ReportingServices.Portal.Services.DataService::RenderRdlToJson(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, unsigned int8[] rdlBytes, string deviceInfo, string path)
0x9be5  ret
```
