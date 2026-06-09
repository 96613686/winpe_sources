# Microsoft.BIServer.Configuration.WMI.RSInstance::get_MachineIPAddresses

- ea: `0x4b90`
- end: `0x4be9`
- name: `Microsoft.BIServer.Configuration.WMI.RSInstance::get_MachineIPAddresses`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4b90`
- `0x4c90`
- `0x5740`

## pseudocode

```c

```

## disassembly

```asm
0x4b90  ldarg.0
0x4b91  ldfld    class [System]System.Net.IPAddress[] Microsoft.BIServer.Configuration.WMI.RSInstance::machineIPAddresses
0x4b96  brtrue.s loc_4BE2
0x4b98  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Net.IPAddress>::.ctor()
0x4b9d  stloc.0
0x4b9e  ldloc.0
0x4b9f  ldarg.0
0x4ba0  call     instance string Microsoft.BIServer.Configuration.WMI.RSWmiInstance::get_MachineName()
0x4ba5  call     class [System]System.Net.IPHostEntry [System]System.Net.Dns::GetHostEntry(string)
0x4baa  callvirt instance class [System]System.Net.IPAddress[] [System]System.Net.IPHostEntry::get_AddressList()
0x4baf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Net.IPAddress>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x4bb4  ldarg.0
0x4bb5  call     instance string Microsoft.BIServer.Configuration.WMI.RSWmiInstance::get_MachineName()
0x4bba  call     bool Microsoft.BIServer.Configuration.WMI.WmiProvider::IsWellKnownLocalServer(string server)
0x4bbf  brfalse.s loc_4BD6
0x4bc1  ldloc.0
0x4bc2  call     string [mscorlib]System.Environment::get_MachineName()
0x4bc7  call     class [System]System.Net.IPHostEntry [System]System.Net.Dns::GetHostEntry(string)
0x4bcc  callvirt instance class [System]System.Net.IPAddress[] [System]System.Net.IPHostEntry::get_AddressList()
0x4bd1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Net.IPAddress>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x4bd6  ldarg.0
0x4bd7  ldloc.0
0x4bd8  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [System]System.Net.IPAddress>::ToArray()
0x4bdd  stfld    class [System]System.Net.IPAddress[] Microsoft.BIServer.Configuration.WMI.RSInstance::machineIPAddresses
0x4be2  ldarg.0
0x4be3  ldfld    class [System]System.Net.IPAddress[] Microsoft.BIServer.Configuration.WMI.RSInstance::machineIPAddresses
0x4be8  ret
```
