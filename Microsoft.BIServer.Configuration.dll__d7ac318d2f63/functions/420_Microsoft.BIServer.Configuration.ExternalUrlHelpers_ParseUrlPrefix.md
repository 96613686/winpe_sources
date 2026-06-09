# Microsoft.BIServer.Configuration.ExternalUrlHelpers::ParseUrlPrefix

- ea: `0x420`
- end: `0x4be`
- name: `Microsoft.BIServer.Configuration.ExternalUrlHelpers::ParseUrlPrefix`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x220`

## callees

- `0x420`

## string_xrefs

- `0x432`: `^(?<prefix>(?<scheme>.+)://(?<host>[^/]+):(?<port>[0-9]+))/?(?<path>.*)`

## pseudocode

```c

```

## disassembly

```asm
0x420  ldarg.1
0x421  ldnull
0x422  stind.ref
0x423  ldarg.s  4
0x425  ldnull
0x426  stind.ref
0x427  ldarg.s  5
0x429  ldnull
0x42a  stind.ref
0x42b  ldarg.2
0x42c  ldnull
0x42d  stind.ref
0x42e  ldarg.3
0x42f  ldnull
0x430  stind.ref
0x431  ldarg.0
0x432  ldstr    aPrefixSchemeHo// "^(?<prefix>(?<scheme>.+)://(?<host>[^/]"...
0x437  call     class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string, string)
0x43c  stloc.0
0x43d  ldloc.0
0x43e  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x443  brtrue.s loc_447
0x445  ldc.i4.0
0x446  ret
0x447  ldarg.1
0x448  ldloc.0
0x449  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x44e  ldstr    aScheme// "scheme"
0x453  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x458  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x45d  stind.ref
0x45e  ldarg.s  4
0x460  ldloc.0
0x461  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x466  ldstr    aPrefix// "prefix"
0x46b  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x470  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x475  stind.ref
0x476  ldarg.s  5
0x478  ldloc.0
0x479  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x47e  ldstr    aPath// "path"
0x483  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x488  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x48d  stind.ref
0x48e  ldarg.2
0x48f  ldloc.0
0x490  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x495  ldstr    aHost// "host"
0x49a  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x49f  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x4a4  stind.ref
0x4a5  ldarg.3
0x4a6  ldloc.0
0x4a7  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x4ac  ldstr    aPort// "port"
0x4b1  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x4b6  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x4bb  stind.ref
0x4bc  ldc.i4.1
0x4bd  ret
```
