# System.Net.Http.HttpContentMessageExtensions::CreateHeaderFields

- ea: `0x1ba0`
- end: `0x1c4e`
- name: `System.Net.Http.HttpContentMessageExtensions::CreateHeaderFields`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1c50`
- `0x1ca0`

## callees

- `0x12e0`
- `0x1ba0`
- `0x1ed0`
- `0x3430`
- `0xb4b0`

## string_xrefs

- `0x1c14`: `ContentReadStream`

## pseudocode

```c

```

## disassembly

```asm
0x1ba0  ldnull
0x1ba1  stloc.0
0x1ba2  ldnull
0x1ba3  stloc.1
0x1ba4  ldarg.0
0x1ba5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>> [System.Net.Http]System.Net.Http.Headers.HttpHeaders::GetEnumerator()
0x1baa  stloc.2
0x1bab  br.s     loc_1BE8
0x1bad  ldloc.2
0x1bae  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>>::get_Current()
0x1bb3  stloc.3
0x1bb4  ldarg.1
0x1bb5  ldloca.s 3
0x1bb7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_Key()
0x1bbc  ldloca.s 3
0x1bbe  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_Value()
0x1bc3  callvirt instance bool [System.Net.Http]System.Net.Http.Headers.HttpHeaders::TryAddWithoutValidation(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x1bc8  brtrue.s loc_1BE8
0x1bca  ldloc.0
0x1bcb  brtrue.s loc_1BD3
0x1bcd  call     class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders System.Net.Http.FormattingUtilities::CreateEmptyContentHeaders()
0x1bd2  stloc.0
0x1bd3  ldloc.0
0x1bd4  ldloca.s 3
0x1bd6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_Key()
0x1bdb  ldloca.s 3
0x1bdd  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_Value()
0x1be2  callvirt instance bool [System.Net.Http]System.Net.Http.Headers.HttpHeaders::TryAddWithoutValidation(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x1be7  pop
0x1be8  ldloc.2
0x1be9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1bee  brtrue.s loc_1BAD
0x1bf0  leave.s  loc_1BFC
0x1bf2  ldloc.2
0x1bf3  brfalse.s loc_1BFB
0x1bf5  ldloc.2
0x1bf6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bfb  endfinally
0x1bfc  ldloc.0
0x1bfd  brfalse.s loc_1C4C
0x1bff  ldarg.2
0x1c00  callvirt instance bool [mscorlib]System.IO.Stream::get_CanSeek()
0x1c05  brtrue.s loc_1C2D
0x1c07  call     string System.Net.Http.Properties.Resources::get_HttpMessageContentStreamMustBeSeekable()
0x1c0c  ldc.i4.2
0x1c0d  newarr   [mscorlib]System.Object
0x1c12  dup
0x1c13  ldc.i4.0
0x1c14  ldstr    aContentreadstr// "ContentReadStream"
0x1c19  stelem.ref
0x1c1a  dup
0x1c1b  ldc.i4.1
0x1c1c  ldsfld   class [mscorlib]System.Type System.Net.Http.FormattingUtilities::HttpResponseMessageType
0x1c21  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1c26  stelem.ref
0x1c27  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x1c2c  throw
0x1c2d  ldarg.2
0x1c2e  ldc.i4.0
0x1c2f  ldarg.3
0x1c30  sub
0x1c31  conv.i8
0x1c32  ldc.i4.1
0x1c33  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x1c38  pop
0x1c39  ldarg.2
0x1c3a  newobj   instance void [System.Net.Http]System.Net.Http.StreamContent::.ctor(class [mscorlib]System.IO.Stream)
0x1c3f  stloc.1
0x1c40  ldloc.0
0x1c41  ldloc.1
0x1c42  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x1c47  call     void System.Net.Http.HttpHeaderExtensions::CopyTo(class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders fromHeaders, class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders toHeaders)
0x1c4c  ldloc.1
0x1c4d  ret
```
