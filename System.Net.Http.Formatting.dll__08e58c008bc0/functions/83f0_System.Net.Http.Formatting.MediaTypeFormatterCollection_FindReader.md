# System.Net.Http.Formatting.MediaTypeFormatterCollection::FindReader

- ea: `0x83f0`
- end: `0x8486`
- name: `System.Net.Http.Formatting.MediaTypeFormatterCollection::FindReader`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1670`

## callees

- `0x5ce0`
- `0x7e60`
- `0x81a0`
- `0x83f0`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x83f0  ldarg.1
0x83f1  ldnull
0x83f2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x83f7  brfalse.s loc_8404
0x83f9  ldstr    aType// "type"
0x83fe  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x8403  throw
0x8404  ldarg.2
0x8405  brtrue.s loc_8412
0x8407  ldstr    aMediatype// "mediaType"
0x840c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x8411  throw
0x8412  ldarg.0
0x8413  call     instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeFormatter>::get_Items()
0x8418  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Net.Http.Formatting.MediaTypeFormatter>::GetEnumerator()
0x841d  stloc.0
0x841e  br.s     loc_846D
0x8420  ldloc.0
0x8421  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Net.Http.Formatting.MediaTypeFormatter>::get_Current()
0x8426  stloc.1
0x8427  ldloc.1
0x8428  brfalse.s loc_846D
0x842a  ldloc.1
0x842b  ldarg.1
0x842c  callvirt instance bool System.Net.Http.Formatting.MediaTypeFormatter::CanReadType(class [mscorlib]System.Type type)
0x8431  brfalse.s loc_846D
0x8433  ldloc.1
0x8434  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue> System.Net.Http.Formatting.MediaTypeFormatter::get_SupportedMediaTypes()
0x8439  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue>::GetEnumerator()
0x843e  stloc.2
0x843f  br.s     loc_8459
0x8441  ldloc.2
0x8442  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue>::get_Current()
0x8447  stloc.3
0x8448  ldloc.3
0x8449  brfalse.s loc_8459
0x844b  ldloc.3
0x844c  ldarg.2
0x844d  call     bool System.Net.Http.Formatting.MediaTypeHeaderValueExtensions::IsSubsetOf(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType1, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType2)
0x8452  brfalse.s loc_8459
0x8454  ldloc.1
0x8455  stloc.s  4
0x8457  leave.s  loc_8483
0x8459  ldloc.2
0x845a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x845f  brtrue.s loc_8441
0x8461  leave.s  loc_846D
0x8463  ldloc.2
0x8464  brfalse.s loc_846C
0x8466  ldloc.2
0x8467  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x846c  endfinally
0x846d  ldloc.0
0x846e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8473  brtrue.s loc_8420
0x8475  leave.s  loc_8481
0x8477  ldloc.0
0x8478  brfalse.s loc_8480
0x847a  ldloc.0
0x847b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8480  endfinally
0x8481  ldnull
0x8482  ret
0x8483  ldloc.s  4
0x8485  ret
```
