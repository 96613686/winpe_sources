# Microsoft.ReportingServices.Diagnostics.WebRequestUtil::DeclareClientRequestAsLocal

- ea: `0x850`
- end: `0x869`
- name: `Microsoft.ReportingServices.Diagnostics.WebRequestUtil::DeclareClientRequestAsLocal`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x858`: `ReportingServices.IsLocalRequest`

## pseudocode

```c

```

## disassembly

```asm
0x850  ldloca.s 0
0x852  ldarg.0
0x853  call     instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x858  ldstr    aReportingservi// "ReportingServices.IsLocalRequest"
0x85d  ldloc.0
0x85e  box      valuetype [mscorlib]System.Nullable`1<bool>
0x863  call     void [mscorlib]System.Runtime.Remoting.Messaging.CallContext::SetData(string, object)
0x868  ret
```
