# Microsoft.VisualStudio.Setup.InstallSize::get_RequestedCacheDelta

- ea: `0x7b80`
- end: `0x7ba6`
- name: `Microsoft.VisualStudio.Setup.InstallSize::get_RequestedCacheDelta`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7b40`
- `0x7b80`

## string_xrefs

- `0x7b86`: `cache`
- `0x7b9b`: `cache`

## pseudocode

```c

```

## disassembly

```asm
0x7b80  ldarg.0
0x7b81  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> Microsoft.VisualStudio.Setup.InstallSize::get_RequestedSizes()
0x7b86  ldstr    aCache// "cache"
0x7b8b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::ContainsKey(var<u1>)
0x7b90  brtrue.s loc_7B95
0x7b92  ldc.i4.0
0x7b93  conv.i8
0x7b94  ret
0x7b95  ldarg.0
0x7b96  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> Microsoft.VisualStudio.Setup.InstallSize::get_RequestedSizes()
0x7b9b  ldstr    aCache// "cache"
0x7ba0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::get_Item(void)
0x7ba5  ret
```
