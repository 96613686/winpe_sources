# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileWatcherManager::PropertiesAreEqual

- ea: `0x9210`
- end: `0x92ba`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileWatcherManager::PropertiesAreEqual`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x90d0`

## callees

- `0x17c0`
- `0x9210`
- `0x92c0`

## pseudocode

```c

```

## disassembly

```asm
0x9210  ldarg.1
0x9211  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Count()
0x9216  ldarg.2
0x9217  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Count()
0x921c  beq.s    loc_9220
0x921e  ldc.i4.0
0x921f  ret
0x9220  ldarg.1
0x9221  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::GetEnumerator()
0x9226  stloc.0
0x9227  br.s     loc_929C
0x9229  ldloca.s 0
0x922b  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Current()
0x9230  stloc.1
0x9231  ldarg.2
0x9232  ldloca.s 1
0x9234  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Key()
0x9239  ldloca.s 2
0x923b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::TryGetValue(var<u1>, !!T0)
0x9240  brtrue.s loc_9247
0x9242  ldc.i4.0
0x9243  stloc.s  5
0x9245  leave.s  loc_92B7
0x9247  ldloca.s 1
0x9249  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Value()
0x924e  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x9253  stloc.3
0x9254  ldloc.2
0x9255  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x925a  stloc.s  4
0x925c  ldloc.3
0x925d  brtrue.s loc_9268
0x925f  ldloc.s  4
0x9261  brfalse.s loc_929C
0x9263  ldc.i4.0
0x9264  stloc.s  5
0x9266  leave.s  loc_92B7
0x9268  ldloc.3
0x9269  isinst   [mscorlib]System.String
0x926e  brtrue.s loc_927D
0x9270  ldloc.3
0x9271  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x9276  callvirt instance bool [mscorlib]System.Type::get_IsClass()
0x927b  brtrue.s loc_928C
0x927d  ldloc.3
0x927e  ldloc.s  4
0x9280  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x9285  brtrue.s loc_929C
0x9287  ldc.i4.0
0x9288  stloc.s  5
0x928a  leave.s  loc_92B7
0x928c  ldarg.0
0x928d  ldloc.3
0x928e  ldloc.s  4
0x9290  call     instance bool Microsoft.ReportingServices.Diagnostics.RSConfigurationFileWatcherManager::ObjectsAreEqual(object value1, object value2)
0x9295  brtrue.s loc_929C
0x9297  ldc.i4.0
0x9298  stloc.s  5
0x929a  leave.s  loc_92B7
0x929c  ldloca.s 0
0x929e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::MoveNext()
0x92a3  brtrue.s loc_9229
0x92a5  leave.s  loc_92B5
0x92a7  ldloca.s 0
0x92a9  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>
0x92af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x92b4  endfinally
0x92b5  ldc.i4.1
0x92b6  ret
0x92b7  ldloc.s  5
0x92b9  ret
```
