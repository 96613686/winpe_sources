# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::GetTokenPrivate

- ea: `0x2ece0`
- end: `0x2f046`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::GetTokenPrivate`
- size: `870`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2eb10`
- `0x2eb40`

## callees

- `0x16f00`
- `0x16f10`
- `0x178e0`
- `0x17b40`
- `0x17bc0`
- `0x2eb80`
- `0x2ebb0`
- `0x2ec80`
- `0x2ece0`
- `0x2f080`
- `0x2f120`
- `0x2f1d0`
- `0x2f260`
- `0x2f3f0`
- `0x2f7c0`
- `0x2fa70`
- `0x2fb90`
- `0x2fc90`
- `0x2fd30`
- `0x30530`
- `0x305b0`
- `0x307c0`
- `0x307d0`
- `0x307f0`

## string_xrefs

- `0x2ee19`: `JsonNotWellFormated`
- `0x2eeb8`: `JsonNotWellFormated`
- `0x2f022`: `JsonNotWellFormated`
- `0x2ecf0`: `JsonReachTheEndOfStream`

## pseudocode

```c

```

## disassembly

```asm
0x2ece0  ldarg.0
0x2ece1  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ece6  callvirt instance int32 [mscorlib]System.IO.TextReader::Peek()
0x2eceb  stloc.0
0x2ecec  ldloc.0
0x2eced  ldc.i4.m1
0x2ecee  bne.un.s loc_2ED00
0x2ecf0  ldstr    aJsonreachtheen// "JsonReachTheEndOfStream"
0x2ecf5  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0x2ecfa  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2ecff  throw
0x2ed00  ldnull
0x2ed01  stloc.1
0x2ed02  ldarg.0
0x2ed03  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ed08  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::get_Offset()
0x2ed0d  stloc.2
0x2ed0e  ldloc.0
0x2ed0f  stloc.3
0x2ed10  ldloc.3
0x2ed11  ldc.i4.s 0x66
0x2ed13  bgt      loc_2EDA3
0x2ed18  ldloc.3
0x2ed19  ldc.i4.s 0x22
0x2ed1b  sub
0x2ed1c  switch   loc_2EF0A, loc_2F022, loc_2F022, loc_2F022, loc_2F022, loc_2EF0A, loc_2F022, loc_2F022, loc_2F022, loc_2F022, loc_2F022, loc_2F012, loc_2F022, loc_2F022, loc_2F012, loc_2F012, loc_2F012, loc_2F012, loc_2F012, loc_2F012, loc_2F012, loc_2F012, loc_2F012, loc_2F012
0x2ed81  ldloc.3
0x2ed82  ldc.i4.s 0x5B
0x2ed84  sub
0x2ed85  switch   loc_2EDCD, loc_2F022, loc_2EDFA
0x2ed96  ldloc.3
0x2ed97  ldc.i4.s 0x66
0x2ed99  beq      loc_2EFF2
0x2ed9e  br       loc_2F022
0x2eda3  ldloc.3
0x2eda4  ldc.i4.s 0x6E
0x2eda6  beq      loc_2F002
0x2edab  ldloc.3
0x2edac  ldc.i4.s 0x74
0x2edae  beq      loc_2EFE2
0x2edb3  ldloc.3
0x2edb4  ldc.i4.s 0x7B
0x2edb6  sub
0x2edb7  switch   loc_2EE6B, loc_2F022, loc_2EE98
0x2edc8  br       loc_2F022
0x2edcd  ldc.i4.2
0x2edce  ldloc.2
0x2edcf  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2edd4  stloc.1
0x2edd5  ldarg.0
0x2edd6  ldfld    class [System]System.Collections.Generic.Stack`1<class Scope> Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_scopes
0x2eddb  ldc.i4.0
0x2eddc  newobj   instance void Scope::.ctor(valuetype ScopeType type)
0x2ede1  callvirt instance void class [System]System.Collections.Generic.Stack`1<class Scope>::Push(var<u1>)
0x2ede6  ldarg.0
0x2ede7  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2edec  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip()
0x2edf1  pop
0x2edf2  ldarg.0
0x2edf3  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipWhiteSpace()
0x2edf8  ldloc.1
0x2edf9  ret
0x2edfa  ldarg.0
0x2edfb  ldfld    class [System]System.Collections.Generic.Stack`1<class Scope> Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_scopes
0x2ee00  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class Scope>::get_Count()
0x2ee05  brfalse.s loc_2EE19
0x2ee07  ldarg.0
0x2ee08  ldfld    class [System]System.Collections.Generic.Stack`1<class Scope> Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_scopes
0x2ee0d  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Scope>::Peek()
0x2ee12  callvirt instance valuetype ScopeType Scope::get_Type()
0x2ee17  brfalse.s loc_2EE3D
0x2ee19  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2ee1e  ldc.i4.1
0x2ee1f  newarr   [mscorlib]System.Object
0x2ee24  stloc.s  4
0x2ee26  ldloc.s  4
0x2ee28  ldc.i4.0
0x2ee29  ldloc.2
0x2ee2a  box      [mscorlib]System.Int32
0x2ee2f  stelem.ref
0x2ee30  ldloc.s  4
0x2ee32  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2ee37  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2ee3c  throw
0x2ee3d  ldc.i4.3
0x2ee3e  ldloc.2
0x2ee3f  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2ee44  stloc.1
0x2ee45  ldarg.0
0x2ee46  ldfld    class [System]System.Collections.Generic.Stack`1<class Scope> Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_scopes
0x2ee4b  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Scope>::Pop()
0x2ee50  pop
0x2ee51  ldarg.0
0x2ee52  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ee57  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip()
0x2ee5c  pop
0x2ee5d  ldarg.0
0x2ee5e  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipToNextToken()
0x2ee63  ldarg.0
0x2ee64  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IncreaseObjectCount()
0x2ee69  ldloc.1
0x2ee6a  ret
0x2ee6b  ldc.i4.0
0x2ee6c  ldloc.2
0x2ee6d  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2ee72  stloc.1
0x2ee73  ldarg.0
0x2ee74  ldfld    class [System]System.Collections.Generic.Stack`1<class Scope> Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_scopes
0x2ee79  ldc.i4.1
0x2ee7a  newobj   instance void Scope::.ctor(valuetype ScopeType type)
0x2ee7f  callvirt instance void class [System]System.Collections.Generic.Stack`1<class Scope>::Push(var<u1>)
0x2ee84  ldarg.0
0x2ee85  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ee8a  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip()
0x2ee8f  pop
0x2ee90  ldarg.0
0x2ee91  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipWhiteSpace()
0x2ee96  ldloc.1
0x2ee97  ret
0x2ee98  ldarg.0
0x2ee99  ldfld    class [System]System.Collections.Generic.Stack`1<class Scope> Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_scopes
0x2ee9e  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class Scope>::get_Count()
0x2eea3  brfalse.s loc_2EEB8
0x2eea5  ldarg.0
0x2eea6  ldfld    class [System]System.Collections.Generic.Stack`1<class Scope> Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_scopes
0x2eeab  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Scope>::Peek()
0x2eeb0  callvirt instance valuetype ScopeType Scope::get_Type()
0x2eeb5  ldc.i4.1
0x2eeb6  beq.s    loc_2EEDC
0x2eeb8  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2eebd  ldc.i4.1
0x2eebe  newarr   [mscorlib]System.Object
0x2eec3  stloc.s  5
0x2eec5  ldloc.s  5
0x2eec7  ldc.i4.0
0x2eec8  ldloc.2
0x2eec9  box      [mscorlib]System.Int32
0x2eece  stelem.ref
0x2eecf  ldloc.s  5
0x2eed1  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2eed6  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2eedb  throw
0x2eedc  ldc.i4.1
0x2eedd  ldloc.2
0x2eede  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2eee3  stloc.1
0x2eee4  ldarg.0
0x2eee5  ldfld    class [System]System.Collections.Generic.Stack`1<class Scope> Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_scopes
0x2eeea  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Scope>::Pop()
0x2eeef  pop
0x2eef0  ldarg.0
0x2eef1  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2eef6  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip()
0x2eefb  pop
0x2eefc  ldarg.0
0x2eefd  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipToNextToken()
0x2ef02  ldarg.0
0x2ef03  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IncreaseObjectCount()
0x2ef08  ldloc.1
0x2ef09  ret
0x2ef0a  ldarg.0
0x2ef0b  ldfld    class [System]System.Collections.Generic.Stack`1<class Scope> Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_scopes
0x2ef10  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class Scope>::get_Count()
0x2ef15  ldc.i4.0
0x2ef16  ble.s    loc_2EF60
0x2ef18  ldarg.0
0x2ef19  ldfld    class [System]System.Collections.Generic.Stack`1<class Scope> Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_scopes
0x2ef1e  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Scope>::Peek()
0x2ef23  callvirt instance valuetype ScopeType Scope::get_Type()
0x2ef28  ldc.i4.1
0x2ef29  bne.un.s loc_2EF60
0x2ef2b  ldarg.0
0x2ef2c  ldfld    class [System]System.Collections.Generic.Stack`1<class Scope> Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_scopes
0x2ef31  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Scope>::Peek()
0x2ef36  callvirt instance int32 Scope::get_ObjectCount()
0x2ef3b  ldc.i4.2
0x2ef3c  rem
0x2ef3d  brtrue.s loc_2EF60
0x2ef3f  ldc.i4.s 0xC
0x2ef41  ldloc.2
0x2ef42  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2ef47  stloc.1
0x2ef48  ldloc.1
0x2ef49  ldarg.0
0x2ef4a  ldloc.2
0x2ef4b  ldc.i4.1
0x2ef4c  call     instance string Microsoft.SharePoint.Client.ServerRuntime.JsonReader::DecodeString(int32 tokenPosition, bool isName)
0x2ef51  callvirt instance void Token::set_StringValue(string value)
0x2ef56  ldarg.0
0x2ef57  ldc.i4.s 0x3A
0x2ef59  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipWhiteSpaceAndSeparator(char separator)
0x2ef5e  br.s     loc_2EFDA
0x2ef60  ldarg.0
0x2ef61  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ef66  ldc.i4.1
0x2ef67  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Peek(int32 position)
0x2ef6c  ldc.i4.s 0x5C
0x2ef6e  bne.un.s loc_2EFBE
0x2ef70  ldarg.0
0x2ef71  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ef76  ldc.i4.2
0x2ef77  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Peek(int32 position)
0x2ef7c  ldc.i4.s 0x2F
0x2ef7e  bne.un.s loc_2EFBE
0x2ef80  ldarg.0
0x2ef81  ldfld    valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonReaderOptions Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_options
0x2ef86  ldc.i4.1
0x2ef87  and
0x2ef88  brtrue.s loc_2EFBE
0x2ef8a  ldarg.0
0x2ef8b  ldloc.2
0x2ef8c  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::TryReadDateTime(int32 tokenPosition)
0x2ef91  stloc.1
0x2ef92  ldloc.1
0x2ef93  brfalse.s loc_2EF97
0x2ef95  ldloc.1
0x2ef96  ret
0x2ef97  ldarg.0
0x2ef98  ldloc.2
0x2ef99  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::TryReadGuid(int32 tokenPosition)
0x2ef9e  stloc.1
0x2ef9f  ldloc.1
0x2efa0  brfalse.s loc_2EFA4
0x2efa2  ldloc.1
0x2efa3  ret
0x2efa4  ldarg.0
0x2efa5  ldloc.2
0x2efa6  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::TryReadByteArray(int32 tokenPosition)
0x2efab  stloc.1
0x2efac  ldloc.1
0x2efad  brfalse.s loc_2EFB1
0x2efaf  ldloc.1
0x2efb0  ret
0x2efb1  ldarg.0
0x2efb2  ldloc.2
0x2efb3  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::TryReadStreamLink(int32 tokenPosition)
0x2efb8  stloc.1
0x2efb9  ldloc.1
0x2efba  brfalse.s loc_2EFDA
0x2efbc  ldloc.1
0x2efbd  ret
0x2efbe  ldc.i4.4
0x2efbf  ldloc.2
0x2efc0  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2efc5  stloc.1
0x2efc6  ldloc.1
0x2efc7  ldarg.0
0x2efc8  ldloc.2
0x2efc9  ldc.i4.0
0x2efca  call     instance string Microsoft.SharePoint.Client.ServerRuntime.JsonReader::DecodeString(int32 tokenPosition, bool isName)
0x2efcf  callvirt instance void Token::set_StringValue(string value)
0x2efd4  ldarg.0
0x2efd5  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipToNextToken()
0x2efda  ldarg.0
0x2efdb  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IncreaseObjectCount()
0x2efe0  ldloc.1
0x2efe1  ret
0x2efe2  ldarg.0
0x2efe3  ldloc.2
0x2efe4  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTokenTrue(int32 tokenPosition)
0x2efe9  stloc.1
0x2efea  ldarg.0
0x2efeb  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IncreaseObjectCount()
0x2eff0  ldloc.1
0x2eff1  ret
0x2eff2  ldarg.0
0x2eff3  ldloc.2
0x2eff4  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTokenFalse(int32 tokenPosition)
0x2eff9  stloc.1
0x2effa  ldarg.0
0x2effb  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IncreaseObjectCount()
0x2f000  ldloc.1
0x2f001  ret
0x2f002  ldarg.0
0x2f003  ldloc.2
0x2f004  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTokenNull(int32 tokenPosition)
0x2f009  stloc.1
0x2f00a  ldarg.0
0x2f00b  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IncreaseObjectCount()
0x2f010  ldloc.1
0x2f011  ret
0x2f012  ldarg.0
0x2f013  ldloc.2
0x2f014  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTokenNumber(int32 tokenPosition)
0x2f019  stloc.1
0x2f01a  ldarg.0
0x2f01b  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IncreaseObjectCount()
0x2f020  ldloc.1
0x2f021  ret
0x2f022  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2f027  ldc.i4.1
0x2f028  newarr   [mscorlib]System.Object
0x2f02d  stloc.s  6
0x2f02f  ldloc.s  6
0x2f031  ldc.i4.0
0x2f032  ldloc.2
0x2f033  box      [mscorlib]System.Int32
0x2f038  stelem.ref
0x2f039  ldloc.s  6
0x2f03b  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
  ... truncated ...
```
