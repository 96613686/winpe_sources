# Microsoft.BIServer.Configuration.ConfigReader::Init

- ea: `0x12f0`
- end: `0x135e`
- name: `Microsoft.BIServer.Configuration.ConfigReader::Init`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1100`
- `0x1180`
- `0x1220`

## callees

- `0x15d0`

## pseudocode

```c

```

## disassembly

```asm
0x12f0  ldarg.0
0x12f1  ldarg.0
0x12f2  ldstr    aInstanceid// "InstanceId"
0x12f7  call     instance string Microsoft.BIServer.Configuration.ConfigReader::ReadString(string fieldName)
0x12fc  stfld    string Microsoft.BIServer.Configuration.ConfigReader::_instanceId
0x1301  ldarg.0
0x1302  ldarg.0
0x1303  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application> Microsoft.BIServer.Configuration.ConfigReader::<Init>b__57_0()
0x1309  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application>>::.ctor(object, native int)
0x130e  newobj   instance void class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application>>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x1313  stfld    class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application>> Microsoft.BIServer.Configuration.ConfigReader::_applications
0x1318  ldarg.0
0x1319  ldarg.0
0x131a  ldftn    instance valuetype [mscorlib]System.Guid Microsoft.BIServer.Configuration.ConfigReader::<Init>b__57_1()
0x1320  newobj   instance void class [mscorlib]System.Func`1<valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x1325  newobj   instance void class [mscorlib]System.Lazy`1<valuetype [mscorlib]System.Guid>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x132a  stfld    class [mscorlib]System.Lazy`1<valuetype [mscorlib]System.Guid> Microsoft.BIServer.Configuration.ConfigReader::_installationId
0x132f  ldarg.0
0x1330  ldarg.0
0x1331  ldftn    instance string Microsoft.BIServer.Configuration.ConfigReader::<Init>b__57_2()
0x1337  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x133c  newobj   instance void class [mscorlib]System.Lazy`1<string>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x1341  stfld    class [mscorlib]System.Lazy`1<string> Microsoft.BIServer.Configuration.ConfigReader::_rsConnectionString
0x1346  ldarg.0
0x1347  ldarg.0
0x1348  ldftn    instance class Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.BIServer.Configuration.ConfigReader::<Init>b__57_3()
0x134e  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.BIServer.Configuration.ServerConfiguration>::.ctor(object, native int)
0x1353  newobj   instance void class [mscorlib]System.Lazy`1<class Microsoft.BIServer.Configuration.ServerConfiguration>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x1358  stfld    class [mscorlib]System.Lazy`1<class Microsoft.BIServer.Configuration.ServerConfiguration> Microsoft.BIServer.Configuration.ConfigReader::_serverConfiguration
0x135d  ret
```
