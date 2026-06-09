# Microsoft.BIServer.Configuration.WebConfigFile::GetFormsCookieTimeoutMinutes

- ea: `0x3ca0`
- end: `0x3cc8`
- name: `Microsoft.BIServer.Configuration.WebConfigFile::GetFormsCookieTimeoutMinutes`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x3ca0`
- `0x3d20`
- `0x3d30`

## pseudocode

```c

```

## disassembly

```asm
0x3ca0  ldarg.0
0x3ca1  ldstr    aSystemWebAuthe_0// "system.web/authentication/forms"
0x3ca6  call     instance class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.WebConfigFile::GetNode(string xPath)
0x3cab  stloc.0
0x3cac  ldarg.0
0x3cad  ldloc.0
0x3cae  ldstr    aTimeout// "timeout"
0x3cb3  call     instance string Microsoft.BIServer.Configuration.WebConfigFile::GetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string name)
0x3cb8  ldc.i4.0
0x3cb9  stloc.1
0x3cba  ldloca.s 1
0x3cbc  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x3cc1  brfalse.s loc_3CC5
0x3cc3  ldloc.1
0x3cc4  ret
0x3cc5  ldc.i4.s 0x3C
0x3cc7  ret
```
