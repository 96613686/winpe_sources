# CurrentHeaderFieldStore::CopyTo

- ea: `0xd9b0`
- end: `0xd9ef`
- name: `CurrentHeaderFieldStore::CopyTo`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0xa5a0`

## callees

- `0xd9b0`
- `0xda10`

## pseudocode

```c

```

## disassembly

```asm
0xd9b0  ldarg.0
0xd9b1  ldfld    class [mscorlib]System.Text.StringBuilder CurrentHeaderFieldStore::_name
0xd9b6  callvirt instance string [mscorlib]System.Object::ToString()
0xd9bb  stloc.0
0xd9bc  ldarg.0
0xd9bd  ldfld    class [mscorlib]System.Text.StringBuilder CurrentHeaderFieldStore::_value
0xd9c2  callvirt instance string [mscorlib]System.Object::ToString()
0xd9c7  ldsfld   char[] CurrentHeaderFieldStore::_linearWhiteSpace
0xd9cc  callvirt instance string [mscorlib]System.String::Trim(char[])
0xd9d1  stloc.1
0xd9d2  ldarg.2
0xd9d3  brfalse.s loc_D9E0
0xd9d5  ldarg.1
0xd9d6  ldloc.0
0xd9d7  ldloc.1
0xd9d8  callvirt instance bool [System.Net.Http]System.Net.Http.Headers.HttpHeaders::TryAddWithoutValidation(string, string)
0xd9dd  pop
0xd9de  br.s     loc_D9E8
0xd9e0  ldarg.1
0xd9e1  ldloc.0
0xd9e2  ldloc.1
0xd9e3  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, string)
0xd9e8  ldarg.0
0xd9e9  call     instance void CurrentHeaderFieldStore::Clear()
0xd9ee  ret
```
