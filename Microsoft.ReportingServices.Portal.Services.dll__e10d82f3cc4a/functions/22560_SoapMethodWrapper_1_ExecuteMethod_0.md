# SoapMethodWrapper`1::ExecuteMethod_0

- ea: `0x22560`
- end: `0x225c4`
- name: `SoapMethodWrapper`1::ExecuteMethod_0`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x13e00`
- `0x22480`
- `0x22490`
- `0x224f0`
- `0x22560`

## string_xrefs

- `0x2258b`: `ReportService2010.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x22560  ldarg.0
0x22561  call     instance void class SoapMethodWrapper`1<var<u1>>::OnBeforeExecution()
0x22566  ldarg.1
0x22567  brfalse.s loc_22574
0x22569  ldarg.0
0x2256a  ldfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 class SoapMethodWrapper`1<var<u1>>::m_conn
0x2256f  callvirt instance void Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetConnectionProtocol()
0x22574  ldarg.0
0x22575  ldfld    class SoapMethod<var<u1>> class SoapMethodWrapper`1<var<u1>>::m_method
0x2257a  callvirt instance var<u1> class SoapMethod<var<u1>>::Invoke()
0x2257f  stloc.0
0x22580  leave.s  loc_225C2
0x22582  stloc.1
0x22583  ldarg.0
0x22584  ldloc.1
0x22585  call     instance void class SoapMethodWrapper`1<var<u1>>::OnExceptionEncountered(class [mscorlib]System.Exception)
0x2258a  ldloc.1
0x2258b  ldstr    aReportservice2_0// "ReportService2010.asmx"
0x22590  call     void SoapVersionMismatchException::ThrowIfVersionMismatch(class [System.Web.Services]System.Web.Services.Protocols.SoapException e, string expectedEndpoint)
0x22595  rethrow
0x22597  stloc.2
0x22598  ldarg.0
0x22599  ldloc.2
0x2259a  call     instance void class SoapMethodWrapper`1<var<u1>>::OnExceptionEncountered(class [mscorlib]System.Exception)
0x2259f  ldloc.2
0x225a0  call     void MissingEndpointException::ThrowIfEndpointMissing(class [System]System.Net.WebException e)
0x225a5  rethrow
0x225a7  stloc.3
0x225a8  ldarg.0
0x225a9  ldloc.3
0x225aa  call     instance void class SoapMethodWrapper`1<var<u1>>::OnExceptionEncountered(class [mscorlib]System.Exception)
0x225af  ldloc.3
0x225b0  newobj   instance void MissingEndpointException::.ctor(class [mscorlib]System.Exception inner)
0x225b5  throw
0x225b6  stloc.s  4
0x225b8  ldarg.0
0x225b9  ldloc.s  4
0x225bb  call     instance void class SoapMethodWrapper`1<var<u1>>::OnExceptionEncountered(class [mscorlib]System.Exception)
0x225c0  rethrow
0x225c2  ldloc.0
0x225c3  ret
```
