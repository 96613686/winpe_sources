# Microsoft.BIServer.Configuration.WebConfigFile::GetAuthenticationType

- ea: `0x3c40`
- end: `0x3c59`
- name: `Microsoft.BIServer.Configuration.WebConfigFile::GetAuthenticationType`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1360`

## callees

- `0x3d20`
- `0x3d30`

## pseudocode

```c

```

## disassembly

```asm
0x3c40  ldarg.0
0x3c41  ldstr    aSystemWebAuthe// "system.web/authentication"
0x3c46  call     instance class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.WebConfigFile::GetNode(string xPath)
0x3c4b  stloc.0
0x3c4c  ldarg.0
0x3c4d  ldloc.0
0x3c4e  ldstr    aMode// "mode"
0x3c53  call     instance string Microsoft.BIServer.Configuration.WebConfigFile::GetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string name)
0x3c58  ret
```
