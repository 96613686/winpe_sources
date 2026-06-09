# CurrentNameValuePair::CopyTo

- ea: `0xd870`
- end: `0xd8a6`
- name: `CurrentNameValuePair::CopyTo`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x97f0`
- `0x9980`

## callees

- `0xb520`
- `0xd8e0`

## pseudocode

```c

```

## disassembly

```asm
0xd870  ldarg.0
0xd871  ldfld    class [mscorlib]System.Text.StringBuilder CurrentNameValuePair::_name
0xd876  callvirt instance string [mscorlib]System.Object::ToString()
0xd87b  call     string System.Web.Http.UriQueryUtility::UrlDecode(string str)
0xd880  stloc.0
0xd881  ldarg.0
0xd882  ldfld    class [mscorlib]System.Text.StringBuilder CurrentNameValuePair::_value
0xd887  callvirt instance string [mscorlib]System.Object::ToString()
0xd88c  call     string System.Web.Http.UriQueryUtility::UrlDecode(string str)
0xd891  stloc.1
0xd892  ldarg.1
0xd893  ldloc.0
0xd894  ldloc.1
0xd895  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::.ctor(var<u1>, !!T0)
0xd89a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::Add(var<u1>)
0xd89f  ldarg.0
0xd8a0  call     instance void CurrentNameValuePair::Clear()
0xd8a5  ret
```
