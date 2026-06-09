# <>c::<GetTotalNonCacheInstallSize>b__36_0

- ea: `0x1c6f0`
- end: `0x1c706`
- name: `<>c::<GetTotalNonCacheInstallSize>b__36_0`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x1c6f7`: `cache`

## pseudocode

```c

```

## disassembly

```asm
0x1c6f0  ldarga.s 1
0x1c6f2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, int64>::get_Key()
0x1c6f7  ldstr    aCache// "cache"
0x1c6fc  ldc.i4.5
0x1c6fd  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1c702  ldc.i4.0
0x1c703  ceq
0x1c705  ret
```
