# System.Net.Http.HttpResponseHeadersExtensions::AddCookies

- ea: `0xdc0`
- end: `0xe2c`
- name: `System.Net.Http.HttpResponseHeadersExtensions::AddCookies`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0xdc0`
- `0x3310`
- `0xb330`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0xdc0  ldarg.0
0xdc1  brtrue.s loc_DCE
0xdc3  ldstr    aHeaders// "headers"
0xdc8  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0xdcd  throw
0xdce  ldarg.1
0xdcf  brtrue.s loc_DDC
0xdd1  ldstr    aCookies// "cookies"
0xdd6  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0xddb  throw
0xddc  ldarg.1
0xddd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Net.Http.Headers.CookieHeaderValue>::GetEnumerator()
0xde2  stloc.0
0xde3  br.s     loc_E17
0xde5  ldloc.0
0xde6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Net.Http.Headers.CookieHeaderValue>::get_Current()
0xdeb  stloc.1
0xdec  ldloc.1
0xded  brtrue.s loc_E05
0xdef  ldstr    aCookies// "cookies"
0xdf4  call     string System.Net.Http.Properties.Resources::get_CookieNull()
0xdf9  ldc.i4.0
0xdfa  newarr   [mscorlib]System.Object
0xdff  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0xe04  throw
0xe05  ldarg.0
0xe06  ldstr    aSetCookie// "Set-Cookie"
0xe0b  ldloc.1
0xe0c  callvirt instance string [mscorlib]System.Object::ToString()
0xe11  callvirt instance bool [System.Net.Http]System.Net.Http.Headers.HttpHeaders::TryAddWithoutValidation(string, string)
0xe16  pop
0xe17  ldloc.0
0xe18  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe1d  brtrue.s loc_DE5
0xe1f  leave.s  loc_E2B
0xe21  ldloc.0
0xe22  brfalse.s loc_E2A
0xe24  ldloc.0
0xe25  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe2a  endfinally
0xe2b  ret
```
