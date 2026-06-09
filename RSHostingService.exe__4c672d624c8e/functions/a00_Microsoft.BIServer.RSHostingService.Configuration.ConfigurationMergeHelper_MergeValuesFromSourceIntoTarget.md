# Microsoft.BIServer.RSHostingService.Configuration.ConfigurationMergeHelper::MergeValuesFromSourceIntoTarget

- ea: `0xa00`
- end: `0xa39`
- name: `Microsoft.BIServer.RSHostingService.Configuration.ConfigurationMergeHelper::MergeValuesFromSourceIntoTarget`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x9d0`

## callees

- `0xa00`

## pseudocode

```c

```

## disassembly

```asm
0xa00  ldarg.1
0xa01  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0xa06  stloc.0
0xa07  br.s     loc_A24
0xa09  ldloc.0
0xa0a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0xa0f  stloc.1
0xa10  ldarg.0
0xa11  ldloca.s 1
0xa13  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0xa18  ldloca.s 1
0xa1a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0xa1f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa24  ldloc.0
0xa25  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa2a  brtrue.s loc_A09
0xa2c  leave.s  loc_A38
0xa2e  ldloc.0
0xa2f  brfalse.s loc_A37
0xa31  ldloc.0
0xa32  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa37  endfinally
0xa38  ret
```
