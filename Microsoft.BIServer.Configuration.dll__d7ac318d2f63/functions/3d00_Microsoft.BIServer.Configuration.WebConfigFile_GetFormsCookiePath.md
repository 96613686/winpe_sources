# Microsoft.BIServer.Configuration.WebConfigFile::GetFormsCookiePath

- ea: `0x3d00`
- end: `0x3d19`
- name: `Microsoft.BIServer.Configuration.WebConfigFile::GetFormsCookiePath`
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
0x3d00  ldarg.0
0x3d01  ldstr    aSystemWebAuthe_0// "system.web/authentication/forms"
0x3d06  call     instance class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.WebConfigFile::GetNode(string xPath)
0x3d0b  stloc.0
0x3d0c  ldarg.0
0x3d0d  ldloc.0
0x3d0e  ldstr    aPath// "path"
0x3d13  call     instance string Microsoft.BIServer.Configuration.WebConfigFile::GetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string name)
0x3d18  ret
```
