# Microsoft.ReportingServices.Diagnostics.RSConfiguration::ParseUrlPrefix

- ea: `0x3640`
- end: `0x36de`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::ParseUrlPrefix`
- size: `158`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6700`
- `0x6a00`
- `0x6cc0`

## callees

- `0x3640`

## string_xrefs

- `0x3652`: `^(?<prefix>(?<scheme>.+)://(?<host>[^/]+):(?<port>[0-9]+))/?(?<path>.*)`

## pseudocode

```c

```

## disassembly

```asm
0x3640  ldarg.1
0x3641  ldnull
0x3642  stind.ref
0x3643  ldarg.s  4
0x3645  ldnull
0x3646  stind.ref
0x3647  ldarg.s  5
0x3649  ldnull
0x364a  stind.ref
0x364b  ldarg.2
0x364c  ldnull
0x364d  stind.ref
0x364e  ldarg.3
0x364f  ldnull
0x3650  stind.ref
0x3651  ldarg.0
0x3652  ldstr    aPrefixSchemeHo// "^(?<prefix>(?<scheme>.+)://(?<host>[^/]"...
0x3657  call     class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string, string)
0x365c  stloc.0
0x365d  ldloc.0
0x365e  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x3663  brtrue.s loc_3667
0x3665  ldc.i4.0
0x3666  ret
0x3667  ldarg.1
0x3668  ldloc.0
0x3669  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x366e  ldstr    aScheme// "scheme"
0x3673  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x3678  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x367d  stind.ref
0x367e  ldarg.s  4
0x3680  ldloc.0
0x3681  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x3686  ldstr    aPrefix// "prefix"
0x368b  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x3690  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x3695  stind.ref
0x3696  ldarg.s  5
0x3698  ldloc.0
0x3699  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x369e  ldstr    aPath// "path"
0x36a3  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x36a8  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x36ad  stind.ref
0x36ae  ldarg.2
0x36af  ldloc.0
0x36b0  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x36b5  ldstr    aHost// "host"
0x36ba  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x36bf  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x36c4  stind.ref
0x36c5  ldarg.3
0x36c6  ldloc.0
0x36c7  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x36cc  ldstr    aPort// "port"
0x36d1  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x36d6  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x36db  stind.ref
0x36dc  ldc.i4.1
0x36dd  ret
```
