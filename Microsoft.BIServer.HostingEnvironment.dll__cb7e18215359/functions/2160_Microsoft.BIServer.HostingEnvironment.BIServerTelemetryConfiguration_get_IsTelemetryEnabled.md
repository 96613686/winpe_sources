# Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::get_IsTelemetryEnabled

- ea: `0x2160`
- end: `0x218e`
- name: `Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::get_IsTelemetryEnabled`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2160`
- `0x21f0`

## pseudocode

```c

```

## disassembly

```asm
0x2160  ldstr    aCustomerfeedba// "CustomerFeedback"
0x2165  stloc.0
0x2166  ldarg.0
0x2167  ldloc.0
0x2168  call     instance object Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::ReadCpeRegKey(string keyName)
0x216d  isinst   valuetype [mscorlib]System.Nullable`1<int32>
0x2172  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x2177  stloc.1
0x2178  ldc.i4.1
0x2179  stloc.2
0x217a  ldloca.s 1
0x217c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x2181  ldloc.2
0x2182  beq.s    loc_2186
0x2184  ldc.i4.0
0x2185  ret
0x2186  ldloca.s 1
0x2188  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x218d  ret
```
