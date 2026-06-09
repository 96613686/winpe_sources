# Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add_0

- ea: `0x26f0`
- end: `0x272a`
- name: `Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add_0`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x26e0`
- `0x10df0`

## callees

- `0x26f0`

## string_xrefs

- `0x270c`: `DeviceInfo Name already exists`

## pseudocode

```c

```

## disassembly

```asm
0x26f0  ldarg.1
0x26f1  brtrue.s loc_26FE
0x26f3  ldstr    aDeviceinfoname// "deviceInfoName"
0x26f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x26fd  throw
0x26fe  ldarg.0
0x26ff  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::m_blackList
0x2704  ldarg.1
0x2705  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x270a  brfalse.s loc_271C
0x270c  ldstr    aDeviceinfoName// "DeviceInfo Name already exists"
0x2711  ldstr    aDeviceinfoname// "deviceInfoName"
0x2716  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x271b  throw
0x271c  ldarg.0
0x271d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::m_blackList
0x2722  ldarg.1
0x2723  ldarg.2
0x2724  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2729  ret
```
