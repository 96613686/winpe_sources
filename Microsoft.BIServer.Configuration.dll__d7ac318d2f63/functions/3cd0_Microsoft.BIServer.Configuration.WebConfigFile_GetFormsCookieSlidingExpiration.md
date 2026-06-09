# Microsoft.BIServer.Configuration.WebConfigFile::GetFormsCookieSlidingExpiration

- ea: `0x3cd0`
- end: `0x3cf7`
- name: `Microsoft.BIServer.Configuration.WebConfigFile::GetFormsCookieSlidingExpiration`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x3cd0`
- `0x3d20`
- `0x3d30`

## pseudocode

```c

```

## disassembly

```asm
0x3cd0  ldarg.0
0x3cd1  ldstr    aSystemWebAuthe_0// "system.web/authentication/forms"
0x3cd6  call     instance class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.WebConfigFile::GetNode(string xPath)
0x3cdb  stloc.0
0x3cdc  ldarg.0
0x3cdd  ldloc.0
0x3cde  ldstr    aSlidingexpirat// "slidingExpiration"
0x3ce3  call     instance string Microsoft.BIServer.Configuration.WebConfigFile::GetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string name)
0x3ce8  ldc.i4.0
0x3ce9  stloc.1
0x3cea  ldloca.s 1
0x3cec  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x3cf1  brfalse.s loc_3CF5
0x3cf3  ldloc.1
0x3cf4  ret
0x3cf5  ldc.i4.0
0x3cf6  ret
```
