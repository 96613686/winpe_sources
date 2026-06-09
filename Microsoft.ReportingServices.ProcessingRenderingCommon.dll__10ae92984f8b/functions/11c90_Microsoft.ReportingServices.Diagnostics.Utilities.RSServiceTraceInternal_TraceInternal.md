# Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::TraceInternal

- ea: `0x11c90`
- end: `0x11d08`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::TraceInternal`
- size: `120`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x11980`
- `0x119a0`
- `0x119c0`
- `0x119e0`
- `0x11a10`
- `0x11a40`
- `0x11d40`

## callees

- `0x3c20`
- `0x11c90`
- `0x123b0`
- `0x124b0`
- `0x17640`

## pseudocode

```c

```

## disassembly

```asm
0x11c90  ldsfld   class Microsoft.ReportingServices.Diagnostics.SafeNativeLoggingPointer Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::m_traceInternalObject
0x11c95  brfalse.s loc_11CED
0x11c97  ldarg.0
0x11c98  volatile.
0x11c9a  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::m_bufferOutput
0x11c9f  brfalse.s loc_11CDA
0x11ca1  ldloca.s 0
0x11ca3  ldarg.1
0x11ca4  ldarg.2
0x11ca5  ldarg.3
0x11ca6  ldarg.s  4
0x11ca8  ldarg.s  5
0x11caa  ldarg.s  6
0x11cac  call     instance void BufferedOutput::.ctor(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string componentName, string message, bool isAssert, bool isException, bool allowEventlogWrite)
0x11cb1  ldarg.0
0x11cb2  ldfld    object Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::m_bufferLockObject
0x11cb7  stloc.1
0x11cb8  ldc.i4.0
0x11cb9  stloc.2
0x11cba  ldloc.1
0x11cbb  ldloca.s 2
0x11cbd  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x11cc2  ldarg.0
0x11cc3  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype BufferedOutput> Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::m_buffer
0x11cc8  ldloc.0
0x11cc9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype BufferedOutput>::Add(var<u1>)
0x11cce  leave.s  loc_11CED
0x11cd0  ldloc.2
0x11cd1  brfalse.s loc_11CD9
0x11cd3  ldloc.1
0x11cd4  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x11cd9  endfinally
0x11cda  ldsfld   class Microsoft.ReportingServices.Diagnostics.SafeNativeLoggingPointer Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::m_traceInternalObject
0x11cdf  ldarg.1
0x11ce0  ldarg.2
0x11ce1  ldarg.3
0x11ce2  ldarg.s  4
0x11ce4  ldarg.s  5
0x11ce6  ldarg.s  6
0x11ce8  call     void Microsoft.ReportingServices.Diagnostics.NativeLoggingMethods::NativeLoggingTrace(class Microsoft.ReportingServices.Diagnostics.SafeNativeLoggingPointer nativeLoggingObject, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string componentName, string message, bool isAssert, bool isException, bool allowEventLogWrite)
0x11ced  leave.s  loc_11D07
0x11cef  pop
0x11cf0  ldarg.s  6
0x11cf2  brfalse.s loc_11D05
0x11cf4  call     class Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x11cf9  ldc.i4.s 0x7B
0x11cfb  call     T0x2B00000D
0x11d00  callvirt instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteWarning(valuetype Microsoft.ReportingServices.Diagnostics.Event id, object[] args)
0x11d05  leave.s  loc_11D07
0x11d07  ret
```
