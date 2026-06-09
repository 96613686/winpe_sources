# CurrentNameValuePair::CopyNameOnlyTo

- ea: `0xd8b0`
- end: `0xd8db`
- name: `CurrentNameValuePair::CopyNameOnlyTo`
- size: `43`
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
0xd8b0  ldarg.0
0xd8b1  ldfld    class [mscorlib]System.Text.StringBuilder CurrentNameValuePair::_name
0xd8b6  callvirt instance string [mscorlib]System.Object::ToString()
0xd8bb  call     string System.Web.Http.UriQueryUtility::UrlDecode(string str)
0xd8c0  stloc.0
0xd8c1  ldsfld   string [mscorlib]System.String::Empty
0xd8c6  stloc.1
0xd8c7  ldarg.1
0xd8c8  ldloc.0
0xd8c9  ldloc.1
0xd8ca  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::.ctor(var<u1>, !!T0)
0xd8cf  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::Add(var<u1>)
0xd8d4  ldarg.0
0xd8d5  call     instance void CurrentNameValuePair::Clear()
0xd8da  ret
```
