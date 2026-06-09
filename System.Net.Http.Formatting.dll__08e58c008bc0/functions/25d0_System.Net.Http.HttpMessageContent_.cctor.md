# System.Net.Http.HttpMessageContent::.cctor

- ea: `0x25d0`
- end: `0x261f`
- name: `System.Net.Http.HttpMessageContent::.cctor`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## string_xrefs

- `0x260e`: `User-Agent`

## pseudocode

```c

```

## disassembly

```asm
0x25d0  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x25d5  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x25da  dup
0x25db  ldstr    aCookie// "Cookie"
0x25e0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x25e5  pop
0x25e6  dup
0x25e7  ldstr    aSetCookie// "Set-Cookie"
0x25ec  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x25f1  pop
0x25f2  dup
0x25f3  ldstr    aXPoweredBy// "X-Powered-By"
0x25f8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x25fd  pop
0x25fe  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> System.Net.Http.HttpMessageContent::_singleValueHeaderFields
0x2603  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x2608  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x260d  dup
0x260e  ldstr    aUserAgent// "User-Agent"
0x2613  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x2618  pop
0x2619  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> System.Net.Http.HttpMessageContent::_spaceSeparatedValueHeaderFields
0x261e  ret
```
