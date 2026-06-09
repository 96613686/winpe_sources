# Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::.ctor

- ea: `0x3410`
- end: `0x3482`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::.ctor`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x33c0`

## callees

- `0x3410`

## string_xrefs

- `0x3427`: `classicBasePath`
- `0x3435`: `newBasePath`

## pseudocode

```c

```

## disassembly

```asm
0x3410  ldarg.0
0x3411  call     instance void [mscorlib]System.Object::.ctor()
0x3416  ldarg.1
0x3417  brtrue.s loc_3424
0x3419  ldstr    aVirtualroot// "virtualRoot"
0x341e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3423  throw
0x3424  ldarg.2
0x3425  brtrue.s loc_3432
0x3427  ldstr    aClassicbasepat// "classicBasePath"
0x342c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3431  throw
0x3432  ldarg.3
0x3433  brtrue.s loc_3440
0x3435  ldstr    aNewbasepath// "newBasePath"
0x343a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x343f  throw
0x3440  ldarg.1
0x3441  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x3446  stloc.0
0x3447  ldarg.2
0x3448  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x344d  stloc.1
0x344e  ldstr    a01_1// "^({0}{1})"
0x3453  ldloc.0
0x3454  ldloc.1
0x3455  call     string [mscorlib]System.String::Format(string, object, object)
0x345a  stloc.2
0x345b  ldarg.0
0x345c  ldloc.2
0x345d  ldc.i4   0x201
0x3462  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x3467  stfld    class [System]System.Text.RegularExpressions.Regex Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::_matchClassicPath
0x346c  ldarg.0
0x346d  ldarg.1
0x346e  ldarg.3
0x346f  call     string [mscorlib]System.String::Concat(string, string)
0x3474  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::_newBasePath
0x3479  ldarg.0
0x347a  ldarg.s  4
0x347c  stfld    bool Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::_appendItemPath
0x3481  ret
```
