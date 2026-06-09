# System.Net.Http.HttpRequestHeadersExtensions::GetCookies

- ea: `0xe40`
- end: `0xe98`
- name: `System.Net.Http.HttpRequestHeadersExtensions::GetCookies`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0xea0`

## callees

- `0xe40`
- `0x3dd0`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0xe40  ldarg.0
0xe41  brtrue.s loc_E4E
0xe43  ldstr    aHeaders// "headers"
0xe48  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0xe4d  throw
0xe4e  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Headers.CookieHeaderValue>::.ctor()
0xe53  stloc.0
0xe54  ldarg.0
0xe55  ldstr    aCookie// "Cookie"
0xe5a  ldloca.s 1
0xe5c  callvirt instance bool [System.Net.Http]System.Net.Http.Headers.HttpHeaders::TryGetValues(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>&)
0xe61  brfalse.s loc_E96
0xe63  ldloc.1
0xe64  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0xe69  stloc.2
0xe6a  br.s     loc_E82
0xe6c  ldloc.2
0xe6d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0xe72  ldloca.s 3
0xe74  call     bool System.Net.Http.Headers.CookieHeaderValue::TryParse(string input, [out] class System.Net.Http.Headers.CookieHeaderValue& parsedValue)
0xe79  brfalse.s loc_E82
0xe7b  ldloc.0
0xe7c  ldloc.3
0xe7d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Headers.CookieHeaderValue>::Add(var<u1>)
0xe82  ldloc.2
0xe83  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe88  brtrue.s loc_E6C
0xe8a  leave.s  loc_E96
0xe8c  ldloc.2
0xe8d  brfalse.s loc_E95
0xe8f  ldloc.2
0xe90  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe95  endfinally
0xe96  ldloc.0
0xe97  ret
```
