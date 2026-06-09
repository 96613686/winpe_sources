# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseUrlPrefix

- ea: `0x8ef0`
- end: `0x8f8e`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseUrlPrefix`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8690`

## callees

- `0x8ef0`

## string_xrefs

- `0x8f02`: `^(?<prefix>(?<scheme>.+)://(?<host>[^/]+):(?<port>[0-9]+))/?(?<path>.*)`

## pseudocode

```c

```

## disassembly

```asm
0x8ef0  ldarg.1
0x8ef1  ldnull
0x8ef2  stind.ref
0x8ef3  ldarg.s  4
0x8ef5  ldnull
0x8ef6  stind.ref
0x8ef7  ldarg.s  5
0x8ef9  ldnull
0x8efa  stind.ref
0x8efb  ldarg.2
0x8efc  ldnull
0x8efd  stind.ref
0x8efe  ldarg.3
0x8eff  ldnull
0x8f00  stind.ref
0x8f01  ldarg.0
0x8f02  ldstr    aPrefixSchemeHo// "^(?<prefix>(?<scheme>.+)://(?<host>[^/]"...
0x8f07  call     class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string, string)
0x8f0c  stloc.0
0x8f0d  ldloc.0
0x8f0e  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x8f13  brtrue.s loc_8F17
0x8f15  ldc.i4.0
0x8f16  ret
0x8f17  ldarg.1
0x8f18  ldloc.0
0x8f19  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x8f1e  ldstr    aScheme// "scheme"
0x8f23  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x8f28  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x8f2d  stind.ref
0x8f2e  ldarg.s  4
0x8f30  ldloc.0
0x8f31  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x8f36  ldstr    aPrefix// "prefix"
0x8f3b  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x8f40  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x8f45  stind.ref
0x8f46  ldarg.s  5
0x8f48  ldloc.0
0x8f49  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x8f4e  ldstr    aPath// "path"
0x8f53  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x8f58  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x8f5d  stind.ref
0x8f5e  ldarg.2
0x8f5f  ldloc.0
0x8f60  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x8f65  ldstr    aHost// "host"
0x8f6a  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x8f6f  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x8f74  stind.ref
0x8f75  ldarg.3
0x8f76  ldloc.0
0x8f77  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x8f7c  ldstr    aPort// "port"
0x8f81  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x8f86  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x8f8b  stind.ref
0x8f8c  ldc.i4.1
0x8f8d  ret
```
