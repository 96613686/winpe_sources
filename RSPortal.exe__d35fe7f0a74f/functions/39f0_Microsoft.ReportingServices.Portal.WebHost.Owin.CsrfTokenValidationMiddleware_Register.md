# Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenValidationMiddleware::Register

- ea: `0x39f0`
- end: `0x3a1a`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenValidationMiddleware::Register`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x39f0`
- `0x3a20`

## pseudocode

```c

```

## disassembly

```asm
0x39f0  call     bool Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenValidationMiddleware::IsXsrfValidationEnabled()
0x39f5  brfalse.s loc_3A0D
0x39f7  ldarg.0
0x39f8  ldc.i4.2
0x39f9  newarr   [mscorlib]System.Object
0x39fe  dup
0x39ff  ldc.i4.0
0x3a00  ldarg.3
0x3a01  stelem.ref
0x3a02  dup
0x3a03  ldc.i4.1
0x3a04  ldarg.2
0x3a05  stelem.ref
0x3a06  call     T0x2B00001D
0x3a0b  pop
0x3a0c  ret
0x3a0d  ldarg.2
0x3a0e  ldc.i4.2
0x3a0f  ldstr    aCsrfValidation// "CSRF Validation Disabled"
0x3a14  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x3a19  ret
```
