# Microsoft.BIServer.Configuration.Dumper::LogUnhandledException

- ea: `0x20b0`
- end: `0x211c`
- name: `Microsoft.BIServer.Configuration.Dumper::LogUnhandledException`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f90`

## callees

- `0x20b0`
- `0x2120`

## pseudocode

```c

```

## disassembly

```asm
0x20b0  ldarg.0
0x20b1  isinst   [mscorlib]System.AppDomainUnloadedException
0x20b6  brtrue.s loc_20D8
0x20b8  ldarg.0
0x20b9  isinst   [mscorlib]System.OutOfMemoryException
0x20be  brtrue.s loc_20D8
0x20c0  ldarg.0
0x20c1  isinst   [mscorlib]System.Threading.ThreadAbortException
0x20c6  brtrue.s loc_20D8
0x20c8  ldarg.0
0x20c9  isinst   [mscorlib]System.NullReferenceException
0x20ce  brfalse.s loc_20FA
0x20d0  ldarg.0
0x20d1  call     bool Microsoft.BIServer.Configuration.Dumper::IsOwinException(class [mscorlib]System.Exception owinException)
0x20d6  brfalse.s loc_20FA
0x20d8  ldstr    aUnhandledExcep// "Unhandled exception in Appdomain {0}, E"...
0x20dd  ldc.i4.2
0x20de  newarr   [mscorlib]System.Object
0x20e3  dup
0x20e4  ldc.i4.0
0x20e5  ldarg.0
0x20e6  stelem.ref
0x20e7  dup
0x20e8  ldc.i4.1
0x20e9  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x20ee  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x20f3  stelem.ref
0x20f4  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Trace(string, object[])
0x20f9  ret
0x20fa  ldstr    aUnhandledExcep// "Unhandled exception in Appdomain {0}, E"...
0x20ff  ldc.i4.2
0x2100  newarr   [mscorlib]System.Object
0x2105  dup
0x2106  ldc.i4.0
0x2107  ldarg.0
0x2108  stelem.ref
0x2109  dup
0x210a  ldc.i4.1
0x210b  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x2110  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x2115  stelem.ref
0x2116  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x211b  ret
```
