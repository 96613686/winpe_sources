# System.Net.Http.Formatting.MediaTypeFormatterCollection::FindWriter

- ea: `0x8490`
- end: `0x8526`
- name: `System.Net.Http.Formatting.MediaTypeFormatterCollection::FindWriter`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x5ce0`
- `0x7e60`
- `0x81b0`
- `0x8490`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x8490  ldarg.1
0x8491  ldnull
0x8492  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x8497  brfalse.s loc_84A4
0x8499  ldstr    aType// "type"
0x849e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x84a3  throw
0x84a4  ldarg.2
0x84a5  brtrue.s loc_84B2
0x84a7  ldstr    aMediatype// "mediaType"
0x84ac  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x84b1  throw
0x84b2  ldarg.0
0x84b3  call     instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeFormatter>::get_Items()
0x84b8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Net.Http.Formatting.MediaTypeFormatter>::GetEnumerator()
0x84bd  stloc.0
0x84be  br.s     loc_850D
0x84c0  ldloc.0
0x84c1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Net.Http.Formatting.MediaTypeFormatter>::get_Current()
0x84c6  stloc.1
0x84c7  ldloc.1
0x84c8  brfalse.s loc_850D
0x84ca  ldloc.1
0x84cb  ldarg.1
0x84cc  callvirt instance bool System.Net.Http.Formatting.MediaTypeFormatter::CanWriteType(class [mscorlib]System.Type type)
0x84d1  brfalse.s loc_850D
0x84d3  ldloc.1
0x84d4  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue> System.Net.Http.Formatting.MediaTypeFormatter::get_SupportedMediaTypes()
0x84d9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue>::GetEnumerator()
0x84de  stloc.2
0x84df  br.s     loc_84F9
0x84e1  ldloc.2
0x84e2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue>::get_Current()
0x84e7  stloc.3
0x84e8  ldloc.3
0x84e9  brfalse.s loc_84F9
0x84eb  ldloc.3
0x84ec  ldarg.2
0x84ed  call     bool System.Net.Http.Formatting.MediaTypeHeaderValueExtensions::IsSubsetOf(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType1, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType2)
0x84f2  brfalse.s loc_84F9
0x84f4  ldloc.1
0x84f5  stloc.s  4
0x84f7  leave.s  loc_8523
0x84f9  ldloc.2
0x84fa  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x84ff  brtrue.s loc_84E1
0x8501  leave.s  loc_850D
0x8503  ldloc.2
0x8504  brfalse.s loc_850C
0x8506  ldloc.2
0x8507  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x850c  endfinally
0x850d  ldloc.0
0x850e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8513  brtrue.s loc_84C0
0x8515  leave.s  loc_8521
0x8517  ldloc.0
0x8518  brfalse.s loc_8520
0x851a  ldloc.0
0x851b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8520  endfinally
0x8521  ldnull
0x8522  ret
0x8523  ldloc.s  4
0x8525  ret
```
