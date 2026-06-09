# System.Net.Http.HttpContentExtensions::ReadAsAsync_12

- ea: `0x1670`
- end: `0x1769`
- name: `System.Net.Http.HttpContentExtensions::ReadAsAsync_12`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x7d0`
- `0x1670`
- `0x2e20`
- `0x3790`
- `0x7c40`
- `0x81f0`
- `0x8280`
- `0x83f0`
- `0xb310`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x1670  ldarg.0
0x1671  brtrue.s loc_167E
0x1673  ldstr    aContent// "content"
0x1678  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x167d  throw
0x167e  ldarg.1
0x167f  ldnull
0x1680  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1685  brfalse.s loc_1692
0x1687  ldstr    aType// "type"
0x168c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x1691  throw
0x1692  ldarg.2
0x1693  brtrue.s loc_16A0
0x1695  ldstr    aFormatters// "formatters"
0x169a  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x169f  throw
0x16a0  ldarg.0
0x16a1  isinst   System.Net.Http.ObjectContent
0x16a6  stloc.0
0x16a7  ldloc.0
0x16a8  brfalse.s loc_16D6
0x16aa  ldloc.0
0x16ab  callvirt instance object System.Net.Http.ObjectContent::get_Value()
0x16b0  brfalse.s loc_16D6
0x16b2  ldarg.1
0x16b3  ldloc.0
0x16b4  callvirt instance object System.Net.Http.ObjectContent::get_Value()
0x16b9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x16be  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x16c3  brfalse.s loc_16D6
0x16c5  ldloc.0
0x16c6  callvirt instance object System.Net.Http.ObjectContent::get_Value()
0x16cb  unbox.any mvar<u1>
0x16d0  call     T0x2B000027
0x16d5  ret
0x16d6  ldnull
0x16d7  stloc.1
0x16d8  ldarg.0
0x16d9  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x16de  callvirt instance class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentType()
0x16e3  dup
0x16e4  brtrue.s loc_16EC
0x16e6  pop
0x16e7  call     class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::get_ApplicationOctetStreamMediaType()
0x16ec  stloc.2
0x16ed  ldarg.2
0x16ee  newobj   instance void System.Net.Http.Formatting.MediaTypeFormatterCollection::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Net.Http.Formatting.MediaTypeFormatter> formatters)
0x16f3  ldarg.1
0x16f4  ldloc.2
0x16f5  call     instance class System.Net.Http.Formatting.MediaTypeFormatter System.Net.Http.Formatting.MediaTypeFormatterCollection::FindReader(class [mscorlib]System.Type type, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType)
0x16fa  stloc.1
0x16fb  ldloc.1
0x16fc  brtrue.s loc_175D
0x16fe  ldarg.0
0x16ff  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x1704  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentLength()
0x1709  stloc.3
0x170a  ldc.i4.0
0x170b  conv.i8
0x170c  stloc.s  4
0x170e  ldloca.s 3
0x1710  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::GetValueOrDefault()
0x1715  ldloc.s  4
0x1717  ceq
0x1719  ldloca.s 3
0x171b  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x1720  and
0x1721  brfalse.s loc_1734
0x1723  ldarg.1
0x1724  call     object System.Net.Http.Formatting.MediaTypeFormatter::GetDefaultValueForType(class [mscorlib]System.Type type)
0x1729  unbox.any mvar<u1>
0x172e  call     T0x2B000027
0x1733  ret
0x1734  call     string System.Net.Http.Properties.Resources::get_NoReadSerializerAvailable()
0x1739  ldc.i4.2
0x173a  newarr   [mscorlib]System.Object
0x173f  dup
0x1740  ldc.i4.0
0x1741  ldarg.1
0x1742  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1747  stelem.ref
0x1748  dup
0x1749  ldc.i4.1
0x174a  ldloc.2
0x174b  callvirt instance string [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::get_MediaType()
0x1750  stelem.ref
0x1751  call     string System.Web.Http.Error::Format(string format, object[] args)
0x1756  ldloc.2
0x1757  newobj   instance void System.Net.Http.UnsupportedMediaTypeException::.ctor(string message, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType)
0x175c  throw
0x175d  ldarg.0
0x175e  ldarg.1
0x175f  ldarg.3
0x1760  ldloc.1
0x1761  ldarg.s  4
0x1763  call     T0x2B000028
0x1768  ret
```
