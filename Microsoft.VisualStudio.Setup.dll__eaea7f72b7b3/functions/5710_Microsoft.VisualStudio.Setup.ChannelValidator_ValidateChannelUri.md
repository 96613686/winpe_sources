# Microsoft.VisualStudio.Setup.ChannelValidator::ValidateChannelUri

- ea: `0x5710`
- end: `0x5780`
- name: `Microsoft.VisualStudio.Setup.ChannelValidator::ValidateChannelUri`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5710`

## string_xrefs

- `0x5750`: ` needs to be an absolute uri.`
- `0x5713`: `The channel's update uri is null and is necessary to identify the channel`
- `0x5745`: `The channel's update url: `

## pseudocode

```c

```

## disassembly

```asm
0x5710  ldarg.1
0x5711  brtrue.s loc_573D
0x5713  ldstr    aTheChannelSUpd// "The channel's update uri is null and is"...
0x5718  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x571d  stloc.0
0x571e  ldarg.0
0x571f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelValidator::logger
0x5724  dup
0x5725  brtrue.s loc_572A
0x5727  pop
0x5728  br.s     loc_573B
0x572a  ldloc.0
0x572b  ldloc.0
0x572c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5731  call     T0x2B000003
0x5736  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x573b  ldloc.0
0x573c  throw
0x573d  ldarg.1
0x573e  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x5743  brtrue.s loc_577F
0x5745  ldstr    aTheChannelSUpd_0// "The channel's update url: "
0x574a  ldarg.1
0x574b  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x5750  ldstr    aNeedsToBeAnAbs// " needs to be an absolute uri."
0x5755  call     string [mscorlib]System.String::Concat(string, string, string)
0x575a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x575f  stloc.1
0x5760  ldarg.0
0x5761  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelValidator::logger
0x5766  dup
0x5767  brtrue.s loc_576C
0x5769  pop
0x576a  br.s     loc_577D
0x576c  ldloc.1
0x576d  ldloc.1
0x576e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5773  call     T0x2B000003
0x5778  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x577d  ldloc.1
0x577e  throw
0x577f  ret
```
