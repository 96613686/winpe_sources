# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::TryReadByteArray

- ea: `0x2fa70`
- end: `0x2fb8b`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::TryReadByteArray`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2ece0`

## callees

- `0x16f10`
- `0x178e0`
- `0x17b50`
- `0x2ec80`
- `0x2fa70`
- `0x2fc90`
- `0x30530`
- `0x30780`

## string_xrefs

- `0x2fb65`: `JsonNotWellFormated`

## pseudocode

```c

```

## disassembly

```asm
0x2fa70  ldnull
0x2fa71  stloc.1
0x2fa72  ldc.i4.0
0x2fa73  stloc.2
0x2fa74  br.s     loc_2FA7A
0x2fa76  ldloc.2
0x2fa77  ldc.i4.1
0x2fa78  add
0x2fa79  stloc.2
0x2fa7a  ldloc.2
0x2fa7b  ldsfld   int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ByteArrayPrefixLength
0x2fa80  bge.s    loc_2FA9B
0x2fa82  ldarg.0
0x2fa83  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fa88  ldloc.2
0x2fa89  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Peek(int32 position)
0x2fa8e  ldstr    aBase64binary// "\"\\/Base64Binary("
0x2fa93  ldloc.2
0x2fa94  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2fa99  beq.s    loc_2FA76
0x2fa9b  ldloc.2
0x2fa9c  ldsfld   int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ByteArrayPrefixLength
0x2faa1  bne.un   loc_2FB89
0x2faa6  ldc.i4.s 0xD
0x2faa8  ldarg.1
0x2faa9  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2faae  stloc.1
0x2faaf  ldarg.0
0x2fab0  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fab5  ldsfld   int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ByteArrayPrefixLength
0x2faba  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip(int32 count)
0x2fabf  pop
0x2fac0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2fac5  stloc.3
0x2fac6  br.s     loc_2FAD1
0x2fac8  ldloc.3
0x2fac9  ldloc.0
0x2faca  conv.u2
0x2facb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2fad0  pop
0x2fad1  ldarg.0
0x2fad2  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fad7  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2fadc  dup
0x2fadd  stloc.0
0x2fade  ldc.i4.m1
0x2fadf  beq.s    loc_2FAE6
0x2fae1  ldloc.0
0x2fae2  ldc.i4.s 0x29
0x2fae4  bne.un.s loc_2FAC8
0x2fae6  ldloc.0
0x2fae7  ldc.i4.s 0x29
0x2fae9  bne.un.s loc_2FB65
0x2faeb  ldarg.0
0x2faec  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2faf1  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2faf6  ldc.i4.s 0x5C
0x2faf8  bne.un.s loc_2FB65
0x2fafa  ldarg.0
0x2fafb  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fb00  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2fb05  ldc.i4.s 0x2F
0x2fb07  bne.un.s loc_2FB65
0x2fb09  ldarg.0
0x2fb0a  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fb0f  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2fb14  ldc.i4.s 0x22
0x2fb16  bne.un.s loc_2FB65
0x2fb18  ldloc.3
0x2fb19  callvirt instance string [mscorlib]System.Object::ToString()
0x2fb1e  stloc.s  4
0x2fb20  ldloc.s  4
0x2fb22  ldstr    aU002f// "\\u002f"
0x2fb27  ldstr    asc_3FC68// "/"
0x2fb2c  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2fb31  stloc.s  4
0x2fb33  ldloc.s  4
0x2fb35  ldstr    aU002f_0// "\\u002F"
0x2fb3a  ldstr    asc_3FC68// "/"
0x2fb3f  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2fb44  stloc.s  4
0x2fb46  ldloc.s  4
0x2fb48  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x2fb4d  stloc.s  5
0x2fb4f  ldloc.1
0x2fb50  ldloc.s  5
0x2fb52  callvirt instance void Token::set_ByteArrayValue(unsigned int8[] value)
0x2fb57  ldarg.0
0x2fb58  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipToNextToken()
0x2fb5d  ldarg.0
0x2fb5e  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IncreaseObjectCount()
0x2fb63  ldloc.1
0x2fb64  ret
0x2fb65  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2fb6a  ldc.i4.1
0x2fb6b  newarr   [mscorlib]System.Object
0x2fb70  stloc.s  6
0x2fb72  ldloc.s  6
0x2fb74  ldc.i4.0
0x2fb75  ldarg.1
0x2fb76  box      [mscorlib]System.Int32
0x2fb7b  stelem.ref
0x2fb7c  ldloc.s  6
0x2fb7e  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2fb83  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2fb88  throw
0x2fb89  ldloc.1
0x2fb8a  ret
```
