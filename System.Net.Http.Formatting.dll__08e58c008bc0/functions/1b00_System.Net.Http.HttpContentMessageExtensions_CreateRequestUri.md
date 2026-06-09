# System.Net.Http.HttpContentMessageExtensions::CreateRequestUri

- ea: `0x1b00`
- end: `0x1b95`
- name: `System.Net.Http.HttpContentMessageExtensions::CreateRequestUri`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1c50`

## callees

- `0x1b00`
- `0x26b0`
- `0x26f0`
- `0x34d0`
- `0xb4b0`

## pseudocode

```c

```

## disassembly

```asm
0x1b00  ldarg.1
0x1b01  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaders System.Net.Http.HttpUnsortedRequest::get_HttpHeaders()
0x1b06  ldstr    aHost// "Host"
0x1b0b  ldloca.s 0
0x1b0d  callvirt instance bool [System.Net.Http]System.Net.Http.Headers.HttpHeaders::TryGetValues(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>&)
0x1b12  brfalse.s loc_1B41
0x1b14  ldloc.0
0x1b15  call     T0x2B00002C
0x1b1a  stloc.1
0x1b1b  ldloc.1
0x1b1c  ldc.i4.1
0x1b1d  beq.s    loc_1B63
0x1b1f  call     string System.Net.Http.Properties.Resources::get_HttpMessageParserInvalidHostCount()
0x1b24  ldc.i4.2
0x1b25  newarr   [mscorlib]System.Object
0x1b2a  dup
0x1b2b  ldc.i4.0
0x1b2c  ldstr    aHost// "Host"
0x1b31  stelem.ref
0x1b32  dup
0x1b33  ldc.i4.1
0x1b34  ldloc.1
0x1b35  box      [mscorlib]System.Int32
0x1b3a  stelem.ref
0x1b3b  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x1b40  throw
0x1b41  call     string System.Net.Http.Properties.Resources::get_HttpMessageParserInvalidHostCount()
0x1b46  ldc.i4.2
0x1b47  newarr   [mscorlib]System.Object
0x1b4c  dup
0x1b4d  ldc.i4.0
0x1b4e  ldstr    aHost// "Host"
0x1b53  stelem.ref
0x1b54  dup
0x1b55  ldc.i4.1
0x1b56  ldc.i4.0
0x1b57  box      [mscorlib]System.Int32
0x1b5c  stelem.ref
0x1b5d  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x1b62  throw
0x1b63  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b68  ldstr    a012// "{0}://{1}{2}"
0x1b6d  ldc.i4.3
0x1b6e  newarr   [mscorlib]System.Object
0x1b73  dup
0x1b74  ldc.i4.0
0x1b75  ldarg.0
0x1b76  stelem.ref
0x1b77  dup
0x1b78  ldc.i4.1
0x1b79  ldloc.0
0x1b7a  ldc.i4.0
0x1b7b  call     T0x2B00002D
0x1b80  stelem.ref
0x1b81  dup
0x1b82  ldc.i4.2
0x1b83  ldarg.1
0x1b84  callvirt instance string System.Net.Http.HttpUnsortedRequest::get_RequestUri()
0x1b89  stelem.ref
0x1b8a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b8f  newobj   instance void [System]System.Uri::.ctor(string)
0x1b94  ret
```
