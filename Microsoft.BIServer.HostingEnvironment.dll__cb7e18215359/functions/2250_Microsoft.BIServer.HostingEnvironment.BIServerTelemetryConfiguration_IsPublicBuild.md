# Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::IsPublicBuild

- ea: `0x2250`
- end: `0x22af`
- name: `Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::IsPublicBuild`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x20c0`

## callees

- `0x21f0`
- `0x2250`

## pseudocode

```c

```

## disassembly

```asm
0x2250  ldsfld   bool Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::InitialRun
0x2255  brfalse.s loc_2299
0x2257  ldarg.0
0x2258  ldstr    aPrivatebuild// "PrivateBuild"
0x225d  call     instance object Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::ReadCpeRegKey(string keyName)
0x2262  isinst   valuetype [mscorlib]System.Nullable`1<int32>
0x2267  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x226c  stloc.0
0x226d  ldloca.s 0
0x226f  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x2274  brfalse.s loc_2293
0x2276  ldloc.0
0x2277  stloc.1
0x2278  ldc.i4.1
0x2279  stloc.2
0x227a  ldloca.s 1
0x227c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x2281  ldloc.2
0x2282  beq.s    loc_2287
0x2284  ldc.i4.1
0x2285  br.s     loc_2294
0x2287  ldloca.s 1
0x2289  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x228e  ldc.i4.0
0x228f  ceq
0x2291  br.s     loc_2294
0x2293  ldc.i4.1
0x2294  stsfld   bool Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::_isPublicBuild
0x2299  ldsfld   bool Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::InitialRun
0x229e  brfalse.s loc_22A3
0x22a0  ldc.i4.0
0x22a1  br.s     loc_22A4
0x22a3  ldc.i4.0
0x22a4  stsfld   bool Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::InitialRun
0x22a9  ldsfld   bool Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::_isPublicBuild
0x22ae  ret
```
