# Microsoft.BIServer.Configuration.InstanceRegistry::DeleteInstance

- ea: `0x3140`
- end: `0x3173`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::DeleteInstance`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x27f0`
- `0x2800`

## pseudocode

```c

```

## disassembly

```asm
0x3140  ldarg.0
0x3141  ldfld    class Microsoft.BIServer.Configuration.IRegistryStore Microsoft.BIServer.Configuration.InstanceRegistry::_registryStore
0x3146  ldnull
0x3147  ldarg.0
0x3148  ldfld    class Microsoft.BIServer.Configuration.InstanceId Microsoft.BIServer.Configuration.InstanceRegistry::_instanceId
0x314d  callvirt instance string [mscorlib]System.Object::ToString()
0x3152  callvirt instance void Microsoft.BIServer.Configuration.IRegistryStore::DeleteSubKey(string parent, string subKeyName)
0x3157  ldarg.0
0x3158  ldfld    class Microsoft.BIServer.Configuration.IRegistryStore Microsoft.BIServer.Configuration.InstanceRegistry::_registryStore
0x315d  ldstr    aInstanceNamesR// "Instance Names\\RS"
0x3162  ldarg.0
0x3163  ldfld    class Microsoft.BIServer.Configuration.InstanceName Microsoft.BIServer.Configuration.InstanceRegistry::_instanceName
0x3168  callvirt instance string [mscorlib]System.Object::ToString()
0x316d  callvirt instance void Microsoft.BIServer.Configuration.IRegistryStore::DeleteValue(string parent, string keyName)
0x3172  ret
```
