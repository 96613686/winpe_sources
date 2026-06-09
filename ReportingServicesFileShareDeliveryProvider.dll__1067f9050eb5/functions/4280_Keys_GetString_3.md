# Keys::GetString_3

- ea: `0x4280`
- end: `0x4291`
- name: `Keys::GetString_3`
- size: `17`
- prototype: ``
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x3c50`
- `0x3c60`
- `0x3c70`
- `0x3c80`
- `0x3c90`
- `0x3ca0`
- `0x3cb0`
- `0x3cc0`
- `0x3cd0`
- `0x3ce0`
- `0x3cf0`
- `0x3d00`
- `0x3d10`
- `0x3d20`
- `0x3d30`
- `0x3d40`
- `0x3d50`
- `0x3d60`
- `0x3d70`
- `0x3d80`
- `0x3d90`
- `0x3da0`
- `0x3db0`
- `0x3dc0`

## pseudocode

```c

```

## disassembly

```asm
0x4280  ldsfld   class [mscorlib]System.Resources.ResourceManager Keys::resourceManager
0x4285  ldarg.0
0x4286  ldsfld   class [mscorlib]System.Globalization.CultureInfo Keys::_culture
0x428b  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x4290  ret
```
