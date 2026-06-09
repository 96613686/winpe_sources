# System.Net.Http.HttpRequestHeadersExtensions::GetCookies_0

- ea: `0xea0`
- end: `0xee2`
- name: `System.Net.Http.HttpRequestHeadersExtensions::GetCookies_0`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0xe40`
- `0xea0`
- `0xb3c0`
- `0xc1b0`

## pseudocode

```c

```

## disassembly

```asm
0xea0  newobj   instance void <>c__DisplayClass2_0::.ctor()
0xea5  stloc.0
0xea6  ldloc.0
0xea7  ldarg.1
0xea8  stfld    string <>c__DisplayClass2_0::name
0xead  ldloc.0
0xeae  ldfld    string <>c__DisplayClass2_0::name
0xeb3  brtrue.s loc_EC0
0xeb5  ldstr    aName// "name"
0xeba  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0xebf  throw
0xec0  ldarg.0
0xec1  call     class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Headers.CookieHeaderValue> System.Net.Http.HttpRequestHeadersExtensions::GetCookies(class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders headers)
0xec6  ldloc.0
0xec7  ldftn    instance bool <>c__DisplayClass2_0::<GetCookies>b__0(class System.Net.Http.Headers.CookieHeaderValue header)
0xecd  newobj   instance void class [mscorlib]System.Func`2<class System.Net.Http.Headers.CookieHeaderValue, bool>::.ctor(object, native int)
0xed2  call     T0x2B00000B
0xed7  call     T0x2B00000C
0xedc  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Headers.CookieHeaderValue>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xee1  ret
```
