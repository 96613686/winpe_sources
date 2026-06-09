# Microsoft.BIServer.HostingEnvironment.MeterCollector::GetOrCreateMeterData

- ea: `0x1820`
- end: `0x1846`
- name: `Microsoft.BIServer.HostingEnvironment.MeterCollector::GetOrCreateMeterData`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800`
- `0x1810`

## callees

- `0x17d0`
- `0x1820`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x1820  ldarg.0
0x1821  call     instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, class MeterData> Microsoft.BIServer.HostingEnvironment.MeterCollector::get_MeterDataDictionary()
0x1826  ldarg.1
0x1827  ldloca.s 0
0x1829  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, class MeterData>::TryGetValue(var<u1>, !!T0)
0x182e  brtrue.s loc_1844
0x1830  ldarg.1
0x1831  newobj   instance void MeterData::.ctor(string name)
0x1836  stloc.0
0x1837  ldarg.0
0x1838  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class MeterData> Microsoft.BIServer.HostingEnvironment.MeterCollector::_meters
0x183d  ldarg.1
0x183e  ldloc.0
0x183f  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class MeterData>::set_Item(var<u1>, !!T0)
0x1844  ldloc.0
0x1845  ret
```
