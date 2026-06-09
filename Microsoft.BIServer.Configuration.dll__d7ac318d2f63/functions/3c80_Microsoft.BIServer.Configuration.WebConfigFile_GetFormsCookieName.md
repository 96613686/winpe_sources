# Microsoft.BIServer.Configuration.WebConfigFile::GetFormsCookieName

- ea: `0x3c80`
- end: `0x3c99`
- name: `Microsoft.BIServer.Configuration.WebConfigFile::GetFormsCookieName`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x3d20`
- `0x3d30`

## pseudocode

```c

```

## disassembly

```asm
0x3c80  ldarg.0
0x3c81  ldstr    aSystemWebAuthe_0// "system.web/authentication/forms"
0x3c86  call     instance class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.WebConfigFile::GetNode(string xPath)
0x3c8b  stloc.0
0x3c8c  ldarg.0
0x3c8d  ldloc.0
0x3c8e  ldstr    aName_0// "name"
0x3c93  call     instance string Microsoft.BIServer.Configuration.WebConfigFile::GetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string name)
0x3c98  ret
```
