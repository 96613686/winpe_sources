# Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetExcelWopiUrl_0

- ea: `0x5e0`
- end: `0x608`
- name: `Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetExcelWopiUrl_0`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6b50`

## callees

- `0x5e0`

## pseudocode

```c

```

## disassembly

```asm
0x5e0  ldarg.0
0x5e1  ldstr    aAppNameExcelAc// "app[@name='Excel']/action[@name='view']"...
0x5e6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5eb  stloc.0
0x5ec  ldloc.0
0x5ed  brfalse.s loc_606
0x5ef  ldloc.0
0x5f0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5f5  newobj   instance void [System]System.Uri::.ctor(string)
0x5fa  ldc.i4.2
0x5fb  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0x600  newobj   instance void [System]System.Uri::.ctor(string)
0x605  ret
0x606  ldnull
0x607  ret
```
