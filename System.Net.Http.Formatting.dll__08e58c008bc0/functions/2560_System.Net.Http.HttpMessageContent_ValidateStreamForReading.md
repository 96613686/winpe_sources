# System.Net.Http.HttpMessageContent::ValidateStreamForReading

- ea: `0x2560`
- end: `0x25c4`
- name: `System.Net.Http.HttpMessageContent::ValidateStreamForReading`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xcd90`

## callees

- `0x2010`
- `0x2560`
- `0x3410`
- `0xb4b0`

## pseudocode

```c

```

## disassembly

```asm
0x2560  ldarg.0
0x2561  ldfld    bool System.Net.Http.HttpMessageContent::_contentConsumed
0x2566  brfalse.s loc_25BC
0x2568  ldarg.1
0x2569  brfalse.s loc_257D
0x256b  ldarg.1
0x256c  callvirt instance bool [mscorlib]System.IO.Stream::get_CanRead()
0x2571  brfalse.s loc_257D
0x2573  ldarg.1
0x2574  ldc.i4.0
0x2575  conv.i8
0x2576  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x257b  br.s     loc_25BC
0x257d  call     string System.Net.Http.Properties.Resources::get_HttpMessageContentAlreadyRead()
0x2582  ldc.i4.2
0x2583  newarr   [mscorlib]System.Object
0x2588  dup
0x2589  ldc.i4.0
0x258a  ldsfld   class [mscorlib]System.Type System.Net.Http.FormattingUtilities::HttpContentType
0x258f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2594  stelem.ref
0x2595  dup
0x2596  ldc.i4.1
0x2597  ldarg.0
0x2598  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage System.Net.Http.HttpMessageContent::get_HttpRequestMessage()
0x259d  brtrue.s loc_25AB
0x259f  ldsfld   class [mscorlib]System.Type System.Net.Http.FormattingUtilities::HttpResponseMessageType
0x25a4  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x25a9  br.s     loc_25B5
0x25ab  ldsfld   class [mscorlib]System.Type System.Net.Http.FormattingUtilities::HttpRequestMessageType
0x25b0  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x25b5  stelem.ref
0x25b6  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x25bb  throw
0x25bc  ldarg.0
0x25bd  ldc.i4.1
0x25be  stfld    bool System.Net.Http.HttpMessageContent::_contentConsumed
0x25c3  ret
```
