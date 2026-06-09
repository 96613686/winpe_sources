# Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::WriteBuffer

- ea: `0x11b10`
- end: `0x11ba7`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::WriteBuffer`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x3c20`
- `0x11820`
- `0x11b10`
- `0x123b0`
- `0x124b0`

## pseudocode

```c

```

## disassembly

```asm
0x11b10  ldarg.0
0x11b11  ldfld    object Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::m_bufferLockObject
0x11b16  stloc.0
0x11b17  ldc.i4.0
0x11b18  stloc.1
0x11b19  ldloc.0
0x11b1a  ldloca.s 1
0x11b1c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x11b21  ldarg.0
0x11b22  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype BufferedOutput> Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::m_buffer
0x11b27  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype BufferedOutput>::GetEnumerator()
0x11b2c  stloc.2
0x11b2d  br.s     loc_11B65
0x11b2f  ldloca.s 2
0x11b31  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype BufferedOutput>::get_Current()
0x11b36  stloc.3
0x11b37  ldsfld   class Microsoft.ReportingServices.Diagnostics.SafeNativeLoggingPointer Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::m_traceInternalObject
0x11b3c  ldloc.3
0x11b3d  ldfld    valuetype [System]System.Diagnostics.TraceLevel BufferedOutput::m_traceLevel
0x11b42  ldloc.3
0x11b43  ldfld    string BufferedOutput::m_componentName
0x11b48  ldloc.3
0x11b49  ldfld    string BufferedOutput::m_message
0x11b4e  ldloc.3
0x11b4f  ldfld    bool BufferedOutput::m_isAssert
0x11b54  ldloc.3
0x11b55  ldfld    bool BufferedOutput::m_isException
0x11b5a  ldloc.3
0x11b5b  ldfld    bool BufferedOutput::m_allowEventlogWrite
0x11b60  call     void Microsoft.ReportingServices.Diagnostics.NativeLoggingMethods::NativeLoggingTrace(class Microsoft.ReportingServices.Diagnostics.SafeNativeLoggingPointer nativeLoggingObject, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string componentName, string message, bool isAssert, bool isException, bool allowEventLogWrite)
0x11b65  ldloca.s 2
0x11b67  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype BufferedOutput>::MoveNext()
0x11b6c  brtrue.s loc_11B2F
0x11b6e  leave.s  loc_11B7E
0x11b70  ldloca.s 2
0x11b72  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype BufferedOutput>
0x11b78  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11b7d  endfinally
0x11b7e  ldarg.0
0x11b7f  callvirt instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::ClearBuffer()
0x11b84  leave.s  loc_11B90
0x11b86  ldloc.1
0x11b87  brfalse.s loc_11B8F
0x11b89  ldloc.0
0x11b8a  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x11b8f  endfinally
0x11b90  leave.s  loc_11BA6
0x11b92  pop
0x11b93  call     class Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x11b98  ldc.i4.s 0x7B
0x11b9a  call     T0x2B00000D
0x11b9f  callvirt instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteWarning(valuetype Microsoft.ReportingServices.Diagnostics.Event id, object[] args)
0x11ba4  leave.s  loc_11BA6
0x11ba6  ret
```
