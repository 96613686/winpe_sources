# Microsoft.ReportingServices.Diagnostics.ReportServerThreadPool::IsThreadPoolPressure

- ea: `0xb100`
- end: `0xb15b`
- name: `Microsoft.ReportingServices.Diagnostics.ReportServerThreadPool::IsThreadPoolPressure`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb030`

## callees

- `0x10310`

## string_xrefs

- `0xb120`: `Thread pool settings: Available worker: {0}, Max worker: {1}, Available IO: {2}, Max IO: {3}`

## pseudocode

```c

```

## disassembly

```asm
0xb100  ldc.i4.0
0xb101  stloc.0
0xb102  ldc.i4.0
0xb103  stloc.1
0xb104  ldc.i4.0
0xb105  stloc.2
0xb106  ldc.i4.0
0xb107  stloc.3
0xb108  ldloca.s 0
0xb10a  ldloca.s 1
0xb10c  call     void [mscorlib]System.Threading.ThreadPool::GetAvailableThreads(int32&, int32&)
0xb111  ldloca.s 2
0xb113  ldloca.s 3
0xb115  call     void [mscorlib]System.Threading.ThreadPool::GetMaxThreads(int32&, int32&)
0xb11a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xb11f  ldc.i4.4
0xb120  ldstr    aThreadPoolSett// "Thread pool settings: Available worker:"...
0xb125  ldc.i4.4
0xb126  newarr   [mscorlib]System.Object
0xb12b  dup
0xb12c  ldc.i4.0
0xb12d  ldloc.0
0xb12e  box      [mscorlib]System.Int32
0xb133  stelem.ref
0xb134  dup
0xb135  ldc.i4.1
0xb136  ldloc.2
0xb137  box      [mscorlib]System.Int32
0xb13c  stelem.ref
0xb13d  dup
0xb13e  ldc.i4.2
0xb13f  ldloc.1
0xb140  box      [mscorlib]System.Int32
0xb145  stelem.ref
0xb146  dup
0xb147  ldc.i4.3
0xb148  ldloc.3
0xb149  box      [mscorlib]System.Int32
0xb14e  stelem.ref
0xb14f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xb154  ldloc.2
0xb155  ldloc.0
0xb156  sub
0xb157  ldc.i4.7
0xb158  cgt
0xb15a  ret
```
