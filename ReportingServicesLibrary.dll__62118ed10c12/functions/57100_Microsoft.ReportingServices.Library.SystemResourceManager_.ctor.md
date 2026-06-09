# Microsoft.ReportingServices.Library.SystemResourceManager::.ctor

- ea: `0x57100`
- end: `0x57126`
- name: `Microsoft.ReportingServices.Library.SystemResourceManager::.ctor`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e3a0`

## callees

- `0x57100`

## string_xrefs

- `0x57109`: `rsService`
- `0x57113`: `rsService`

## pseudocode

```c

```

## disassembly

```asm
0x57100  ldarg.0
0x57101  call     instance void [mscorlib]System.Object::.ctor()
0x57106  ldarg.1
0x57107  brtrue.s loc_5711E
0x57109  ldstr    aRsservice// "rsService"
0x5710e  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStringsWrapper::rsMissingParameter(string)
0x57113  ldstr    aRsservice// "rsService"
0x57118  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x5711d  throw
0x5711e  ldarg.0
0x5711f  ldarg.1
0x57120  stfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.SystemResourceManager::_rsService
0x57125  ret
```
