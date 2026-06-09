# Microsoft.BIServer.Configuration.XmlConfigFile::DeleteUrlApplications

- ea: `0x3fa0`
- end: `0x3fb1`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::DeleteUrlApplications`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4080`

## callees

- `0x3fa0`
- `0x4350`

## pseudocode

```c

```

## disassembly

```asm
0x3fa0  ldarg.0
0x3fa1  call     instance class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::GetUrlReservations()
0x3fa6  stloc.0
0x3fa7  ldloc.0
0x3fa8  brfalse.s loc_3FB0
0x3faa  ldloc.0
0x3fab  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::RemoveNodes()
0x3fb0  ret
```
