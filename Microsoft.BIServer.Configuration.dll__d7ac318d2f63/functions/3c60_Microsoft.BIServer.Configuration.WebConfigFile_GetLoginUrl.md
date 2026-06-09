# Microsoft.BIServer.Configuration.WebConfigFile::GetLoginUrl

- ea: `0x3c60`
- end: `0x3c79`
- name: `Microsoft.BIServer.Configuration.WebConfigFile::GetLoginUrl`
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
0x3c60  ldarg.0
0x3c61  ldstr    aSystemWebAuthe_0// "system.web/authentication/forms"
0x3c66  call     instance class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.WebConfigFile::GetNode(string xPath)
0x3c6b  stloc.0
0x3c6c  ldarg.0
0x3c6d  ldloc.0
0x3c6e  ldstr    aLoginurl// "loginUrl"
0x3c73  call     instance string Microsoft.BIServer.Configuration.WebConfigFile::GetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string name)
0x3c78  ret
```
