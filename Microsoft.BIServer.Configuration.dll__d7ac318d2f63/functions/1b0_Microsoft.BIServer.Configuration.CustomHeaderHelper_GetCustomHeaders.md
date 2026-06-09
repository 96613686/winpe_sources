# Microsoft.BIServer.Configuration.CustomHeaderHelper::GetCustomHeaders

- ea: `0x1b0`
- end: `0x20c`
- name: `Microsoft.BIServer.Configuration.CustomHeaderHelper::GetCustomHeaders`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x130`

## callees

- `0x1b0`
- `0x67c0`

## pseudocode

```c

```

## disassembly

```asm
0x1b0  ldnull
0x1b1  stloc.0
0x1b2  ldarg.0
0x1b3  ldfld    string Microsoft.BIServer.Configuration.CustomHeaderHelper::_customHeaderXml
0x1b8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1bd  brtrue.s loc_1FB
0x1bf  ldarg.0
0x1c0  ldfld    string Microsoft.BIServer.Configuration.CustomHeaderHelper::_customHeaderXml
0x1c5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1ca  brtrue.s loc_1FB
0x1cc  ldtoken  class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Header>
0x1d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d6  ldstr    aCustomheaders// "CustomHeaders"
0x1db  newobj   instance void [System.Xml]System.Xml.Serialization.XmlRootAttribute::.ctor(string)
0x1e0  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type, class [System.Xml]System.Xml.Serialization.XmlRootAttribute)
0x1e5  ldarg.0
0x1e6  ldfld    string Microsoft.BIServer.Configuration.CustomHeaderHelper::_customHeaderXml
0x1eb  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x1f0  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [mscorlib]System.IO.TextReader)
0x1f5  castclass class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Header>
0x1fa  stloc.0
0x1fb  leave.s  loc_20A
0x1fd  stloc.1
0x1fe  ldstr    aFailedToGenera// "Failed to generate custom headers rules"...
0x203  ldloc.1
0x204  newobj   instance void Microsoft.BIServer.Configuration.Exceptions.ConfigException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x209  throw
0x20a  ldloc.0
0x20b  ret
```
