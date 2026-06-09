# Microsoft.VisualStudio.Setup.InstallSize::get_Item

- ea: `0x7ad0`
- end: `0x7ae4`
- name: `Microsoft.VisualStudio.Setup.InstallSize::get_Item`
- size: `20`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7a50`
- `0x7a70`
- `0x7ab0`
- `0x7b00`
- `0x7cc0`

## callees

- `0x7ad0`

## pseudocode

```c

```

## disassembly

```asm
0x7ad0  ldarg.0
0x7ad1  ldarg.1
0x7ad2  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::ContainsKey(var<u1>)
0x7ad7  brfalse.s loc_7AE1
0x7ad9  ldarg.0
0x7ada  ldarg.1
0x7adb  call     instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::get_Item(void)
0x7ae0  ret
0x7ae1  ldc.i4.0
0x7ae2  conv.i8
0x7ae3  ret
```
