# Microsoft.ReportingServices.Library.CatalogParametersCacheBuilder::.cctor

- ea: `0x5abd0`
- end: `0x5ac25`
- name: `Microsoft.ReportingServices.Library.CatalogParametersCacheBuilder::.cctor`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x5abe9`: `Command`
- `0x5abf9`: `ErrorResponseAsXml`

## pseudocode

```c

```

## disassembly

```asm
0x5abd0  ldc.i4.s 9
0x5abd2  newarr   [mscorlib]System.String
0x5abd7  dup
0x5abd8  ldc.i4.0
0x5abd9  ldstr    aSessionid_1// "SessionID"
0x5abde  stelem.ref
0x5abdf  dup
0x5abe0  ldc.i4.1
0x5abe1  ldstr    aImageid// "ImageID"
0x5abe6  stelem.ref
0x5abe7  dup
0x5abe8  ldc.i4.2
0x5abe9  ldstr    aCommand_1// "Command"
0x5abee  stelem.ref
0x5abef  dup
0x5abf0  ldc.i4.3
0x5abf1  ldstr    aClearsession// "ClearSession"
0x5abf6  stelem.ref
0x5abf7  dup
0x5abf8  ldc.i4.4
0x5abf9  ldstr    aErrorresponsea// "ErrorResponseAsXml"
0x5abfe  stelem.ref
0x5abff  dup
0x5ac00  ldc.i4.5
0x5ac01  ldstr    aAllownewsessio// "AllowNewSessions"
0x5ac06  stelem.ref
0x5ac07  dup
0x5ac08  ldc.i4.6
0x5ac09  ldstr    aPagecountmode// "PageCountMode"
0x5ac0e  stelem.ref
0x5ac0f  dup
0x5ac10  ldc.i4.7
0x5ac11  ldstr    aShowhidetoggle// "ShowHideToggle"
0x5ac16  stelem.ref
0x5ac17  dup
0x5ac18  ldc.i4.8
0x5ac19  ldstr    aSnapshot// "Snapshot"
0x5ac1e  stelem.ref
0x5ac1f  stsfld   string[] Microsoft.ReportingServices.Library.CatalogParametersCacheBuilder::m_filteredParameters
0x5ac24  ret
```
