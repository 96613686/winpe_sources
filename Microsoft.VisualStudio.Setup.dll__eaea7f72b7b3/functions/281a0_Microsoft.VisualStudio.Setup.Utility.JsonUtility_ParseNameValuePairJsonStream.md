# Microsoft.VisualStudio.Setup.Utility.JsonUtility::ParseNameValuePairJsonStream

- ea: `0x281a0`
- end: `0x28236`
- name: `Microsoft.VisualStudio.Setup.Utility.JsonUtility::ParseNameValuePairJsonStream`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1dff0`

## callees

- `0x281a0`
- `0x28240`

## string_xrefs

- `0x281ef`: `Failed to read the json stream. Stream was empty.`
- `0x28215`: `Failed to read json values from stream.`

## pseudocode

```c

```

## disassembly

```asm
0x281a0  ldarg.1
0x281a1  callvirt instance bool [mscorlib]System.IO.Stream::get_CanSeek()
0x281a6  brfalse.s loc_281B8
0x281a8  ldarg.1
0x281a9  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x281ae  brfalse.s loc_281B8
0x281b0  ldarg.1
0x281b1  ldc.i4.0
0x281b2  conv.i8
0x281b3  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x281b8  ldarg.1
0x281b9  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x281be  stloc.0
0x281bf  ldloc.0
0x281c0  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x281c5  stloc.1
0x281c6  ldloc.1
0x281c7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x281cc  brtrue.s loc_281DC
0x281ce  ldloc.1
0x281cf  call     class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.VisualStudio.Setup.Utility.JsonUtility::ParseNameValuePairJson(string jsonContents)
0x281d4  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x281d9  stloc.2
0x281da  leave.s  loc_28234
0x281dc  ldarg.0
0x281dd  brtrue.s loc_281E2
0x281df  ldnull
0x281e0  br.s     loc_281E9
0x281e2  ldarg.0
0x281e3  ldc.i4.0
0x281e4  call     T0x2B000001
0x281e9  dup
0x281ea  brtrue.s loc_281EF
0x281ec  pop
0x281ed  br.s     loc_281FE
0x281ef  ldstr    aFailedToReadTh// "Failed to read the json stream. Stream "...
0x281f4  call     T0x2B000003
0x281f9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x281fe  leave.s  loc_28226
0x28200  stloc.3
0x28201  ldarg.0
0x28202  brtrue.s loc_28207
0x28204  ldnull
0x28205  br.s     loc_2820E
0x28207  ldarg.0
0x28208  ldc.i4.0
0x28209  call     T0x2B000001
0x2820e  dup
0x2820f  brtrue.s loc_28214
0x28211  pop
0x28212  br.s     loc_28224
0x28214  ldloc.3
0x28215  ldstr    aFailedToReadJs// "Failed to read json values from stream."
0x2821a  call     T0x2B000003
0x2821f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x28224  leave.s  loc_28226
0x28226  ldnull
0x28227  stloc.2
0x28228  leave.s  loc_28234
0x2822a  ldloc.0
0x2822b  brfalse.s loc_28233
0x2822d  ldloc.0
0x2822e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28233  endfinally
0x28234  ldloc.2
0x28235  ret
```
