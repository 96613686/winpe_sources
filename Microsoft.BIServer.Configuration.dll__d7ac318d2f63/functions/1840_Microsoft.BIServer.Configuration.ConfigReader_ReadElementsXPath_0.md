# Microsoft.BIServer.Configuration.ConfigReader::ReadElementsXPath_0

- ea: `0x1840`
- end: `0x1870`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReadElementsXPath_0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1840`
- `0x7880`

## string_xrefs

- `0x185d`: `Required config entry is missing: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x1840  ldarg.1
0x1841  ldarg.2
0x1842  call     object [System.Xml.Linq]System.Xml.XPath.Extensions::XPathEvaluate(class [System.Xml.Linq]System.Xml.Linq.XNode, string)
0x1847  castclass [mscorlib]System.Collections.IEnumerable
0x184c  call     T0x2B00001B
0x1851  stloc.0
0x1852  ldarg.3
0x1853  brfalse.s loc_186E
0x1855  ldloc.0
0x1856  call     T0x2B00001C
0x185b  brtrue.s loc_186E
0x185d  ldstr    aRequiredConfig_0// "Required config entry is missing: {0}."
0x1862  ldarg.3
0x1863  call     string [mscorlib]System.String::Format(string, object)
0x1868  newobj   instance void MissingConfigFileEntry::.ctor(string message)
0x186d  throw
0x186e  ldloc.0
0x186f  ret
```
