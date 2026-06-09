# Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::FormatForProcessConfig

- ea: `0x4ca0`
- end: `0x4d54`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::FormatForProcessConfig`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4ca0`
- `0x4d60`
- `0x4d90`
- `0x50a0`

## string_xrefs

- `0x4cb5`: `Service configuration file not found [{0}]`
- `0x4cc9`: `rsConfigFilePath`
- `0x4d42`: `Hosting-configSwitches`

## pseudocode

```c

```

## disassembly

```asm
0x4ca0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x4ca5  stloc.0
0x4ca6  ldarg.1
0x4ca7  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x4cac  stloc.1
0x4cad  ldloc.1
0x4cae  call     bool [mscorlib]System.IO.File::Exists(string)
0x4cb3  brtrue.s loc_4CC1
0x4cb5  ldstr    aServiceConfigu// "Service configuration file not found [{"...
0x4cba  ldloc.1
0x4cbb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x4cc0  throw
0x4cc1  ldarg.2
0x4cc2  ldloc.0
0x4cc3  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::StoreEncryptionKeyInEnvironment(class Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState managementState, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> processConfigInfo)
0x4cc8  ldloc.0
0x4cc9  ldstr    aRsconfigfilepa// "rsConfigFilePath"
0x4cce  ldloc.1
0x4ccf  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::StoreProcessProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> processConfigInfo, string key, string value)
0x4cd4  ldloc.0
0x4cd5  ldstr    aHostingDatabas// "Hosting-databaseValidationStatus"
0x4cda  ldarg.2
0x4cdb  callvirt instance valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::get_DatabaseValidationStatus()
0x4ce0  stloc.2
0x4ce1  ldloca.s 2
0x4ce3  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus
0x4ce9  callvirt instance string [mscorlib]System.Object::ToString()
0x4cee  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::StoreProcessProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> processConfigInfo, string key, string value)
0x4cf3  ldarg.3
0x4cf4  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Uri>::GetEnumerator()
0x4cf9  stloc.3
0x4cfa  br.s     loc_4D28
0x4cfc  ldloca.s 3
0x4cfe  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System]System.Uri>::get_Current()
0x4d03  stloc.s  4
0x4d05  ldloc.0
0x4d06  ldstr    aHostingUrl// "Hosting-url-"
0x4d0b  ldloca.s 4
0x4d0d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System]System.Uri>::get_Key()
0x4d12  call     string [mscorlib]System.String::Concat(string, string)
0x4d17  ldloca.s 4
0x4d19  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System]System.Uri>::get_Value()
0x4d1e  callvirt instance string [mscorlib]System.Object::ToString()
0x4d23  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::StoreProcessProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> processConfigInfo, string key, string value)
0x4d28  ldloca.s 3
0x4d2a  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System]System.Uri>::MoveNext()
0x4d2f  brtrue.s loc_4CFC
0x4d31  leave.s  loc_4D41
0x4d33  ldloca.s 3
0x4d35  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System]System.Uri>
0x4d3b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d40  endfinally
0x4d41  ldloc.0
0x4d42  ldstr    aHostingConfigs// "Hosting-configSwitches"
0x4d47  ldarg.0
0x4d48  call     T0x2B000035
0x4d4d  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::StoreProcessProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> processConfigInfo, string key, string value)
0x4d52  ldloc.0
0x4d53  ret
```
