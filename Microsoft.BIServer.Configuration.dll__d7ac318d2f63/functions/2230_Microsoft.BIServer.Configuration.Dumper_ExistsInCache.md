# Microsoft.BIServer.Configuration.Dumper::ExistsInCache

- ea: `0x2230`
- end: `0x22a3`
- name: `Microsoft.BIServer.Configuration.Dumper::ExistsInCache`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x21e0`

## callees

- `0x2230`
- `0x2390`

## pseudocode

```c

```

## disassembly

```asm
0x2230  ldarg.2
0x2231  ldc.i4.0
0x2232  stind.i4
0x2233  ldarg.1
0x2234  brtrue.s loc_2238
0x2236  ldc.i4.0
0x2237  ret
0x2238  ldc.i4.0
0x2239  stloc.0
0x223a  ldarg.1
0x223b  ldarg.2
0x223c  call     unsigned int8[] Microsoft.BIServer.Configuration.Dumper::GetExceptionFrames(class [mscorlib]System.Exception e, [out] int32& exceptionHash)
0x2241  stloc.1
0x2242  ldloc.1
0x2243  brfalse.s loc_22A1
0x2245  ldarg.2
0x2246  ldind.i4
0x2247  brfalse.s loc_22A1
0x2249  ldnull
0x224a  stloc.2
0x224b  ldsfld   object Microsoft.BIServer.Configuration.Dumper::_lockObj
0x2250  stloc.3
0x2251  ldc.i4.0
0x2252  stloc.s  4
0x2254  ldloc.3
0x2255  ldloca.s 4
0x2257  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x225c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, unsigned int8[]> Microsoft.BIServer.Configuration.Dumper::_dumpHashCache
0x2261  ldarg.2
0x2262  ldind.i4
0x2263  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, unsigned int8[]>::ContainsKey(var<u1>)
0x2268  brfalse.s loc_2279
0x226a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, unsigned int8[]> Microsoft.BIServer.Configuration.Dumper::_dumpHashCache
0x226f  ldarg.2
0x2270  ldind.i4
0x2271  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, unsigned int8[]>::get_Item(void)
0x2276  stloc.2
0x2277  leave.s  loc_2293
0x2279  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, unsigned int8[]> Microsoft.BIServer.Configuration.Dumper::_dumpHashCache
0x227e  ldarg.2
0x227f  ldind.i4
0x2280  ldloc.1
0x2281  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, unsigned int8[]>::Add(var<u1>, !!T0)
0x2286  leave.s  loc_2293
0x2288  ldloc.s  4
0x228a  brfalse.s loc_2292
0x228c  ldloc.3
0x228d  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2292  endfinally
0x2293  ldloc.2
0x2294  brfalse.s loc_229F
0x2296  ldloc.1
0x2297  ldloc.2
0x2298  call     T0x2B000023
0x229d  br.s     loc_22A0
0x229f  ldc.i4.0
0x22a0  stloc.0
0x22a1  ldloc.0
0x22a2  ret
```
