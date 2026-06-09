# Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::FailInternal

- ea: `0x11d40`
- end: `0x11d89`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::FailInternal`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x11a70`
- `0x11a90`

## callees

- `0x11c70`
- `0x11c90`
- `0x11d40`
- `0x127c0`

## pseudocode

```c

```

## disassembly

```asm
0x11d40  ldarg.0
0x11d41  ldc.i4.1
0x11d42  ldarg.1
0x11d43  call     instance bool Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::IsTracingEnabled(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string componentName)
0x11d48  brfalse.s loc_11D82
0x11d4a  ldc.i4.1
0x11d4b  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor(bool)
0x11d50  ldarg.2
0x11d51  ldc.i4   0x400
0x11d56  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string, int32)
0x11d5b  stloc.0
0x11d5c  ldloc.0
0x11d5d  ldstr    aCallStack// "   Call stack:"
0x11d62  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11d67  pop
0x11d68  ldc.i4.3
0x11d69  ldloc.0
0x11d6a  call     void Microsoft.ReportingServices.Diagnostics.Utilities.StackTraceUtil::StackTraceToString(class [mscorlib]System.Diagnostics.StackTrace trace, int32 firstStep, class [mscorlib]System.Text.StringBuilder sb)
0x11d6f  ldloc.0
0x11d70  callvirt instance string [mscorlib]System.Object::ToString()
0x11d75  stloc.1
0x11d76  ldarg.0
0x11d77  ldc.i4.1
0x11d78  ldarg.1
0x11d79  ldloc.1
0x11d7a  ldc.i4.1
0x11d7b  ldc.i4.0
0x11d7c  ldc.i4.1
0x11d7d  call     instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::TraceInternal(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string componentName, string message, bool isAssert, bool isException, bool allowEventlogWrite)
0x11d82  ldarg.2
0x11d83  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x11d88  throw
```
