# Microsoft.BIServer.BIService.ServiceConfig::GetRequiredConfig

- ea: `0x2370`
- end: `0x23c2`
- name: `Microsoft.BIServer.BIService.ServiceConfig::GetRequiredConfig`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x21c0`
- `0x2280`

## callees

- `0x2370`

## string_xrefs

- `0x2385`: `Global Configuration [{0}] must be provided in {1}`
- `0x239e`: `service config file`

## pseudocode

```c

```

## disassembly

```asm
0x2370  ldarg.0
0x2371  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ServiceConfig::_serviceProperties
0x2376  ldarg.1
0x2377  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x237c  stloc.0
0x237d  ldloc.0
0x237e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2383  brfalse.s loc_2391
0x2385  ldstr    aGlobalConfigur// "Global Configuration [{0}] must be prov"...
0x238a  ldarg.1
0x238b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x2390  throw
0x2391  ldarg.1
0x2392  ldc.i4.2
0x2393  newarr   [mscorlib]System.Object
0x2398  dup
0x2399  ldc.i4.0
0x239a  ldloc.0
0x239b  stelem.ref
0x239c  dup
0x239d  ldc.i4.1
0x239e  ldstr    aServiceConfigF// "service config file"
0x23a3  stelem.ref
0x23a4  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Debug(string, object[])
0x23a9  ldloc.0
0x23aa  stloc.1
0x23ab  leave.s  loc_23C0
0x23ad  stloc.2
0x23ae  ldstr    aFetchingKey0// "Fetching Key [{0}]"
0x23b3  ldarg.1
0x23b4  call     string [mscorlib]System.String::Format(string, object)
0x23b9  ldloc.2
0x23ba  newobj   instance void [mscorlib]System.Exception::.ctor(string, class [mscorlib]System.Exception)
0x23bf  throw
0x23c0  ldloc.1
0x23c1  ret
```
