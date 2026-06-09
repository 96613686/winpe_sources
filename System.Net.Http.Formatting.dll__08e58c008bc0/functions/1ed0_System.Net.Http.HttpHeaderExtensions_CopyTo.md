# System.Net.Http.HttpHeaderExtensions::CopyTo

- ea: `0x1ed0`
- end: `0x1f0a`
- name: `System.Net.Http.HttpHeaderExtensions::CopyTo`
- size: `58`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x60`
- `0x1ba0`
- `0x2830`
- `0x42c0`
- `0xd220`

## callees

- `0x1ed0`

## pseudocode

```c

```

## disassembly

```asm
0x1ed0  ldarg.0
0x1ed1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>> [System.Net.Http]System.Net.Http.Headers.HttpHeaders::GetEnumerator()
0x1ed6  stloc.0
0x1ed7  br.s     loc_1EF5
0x1ed9  ldloc.0
0x1eda  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>>::get_Current()
0x1edf  stloc.1
0x1ee0  ldarg.1
0x1ee1  ldloca.s 1
0x1ee3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_Key()
0x1ee8  ldloca.s 1
0x1eea  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_Value()
0x1eef  callvirt instance bool [System.Net.Http]System.Net.Http.Headers.HttpHeaders::TryAddWithoutValidation(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x1ef4  pop
0x1ef5  ldloc.0
0x1ef6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1efb  brtrue.s loc_1ED9
0x1efd  leave.s  loc_1F09
0x1eff  ldloc.0
0x1f00  brfalse.s loc_1F08
0x1f02  ldloc.0
0x1f03  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f08  endfinally
0x1f09  ret
```
