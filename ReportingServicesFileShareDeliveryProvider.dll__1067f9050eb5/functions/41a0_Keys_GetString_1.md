# Keys::GetString_1

- ea: `0x41a0`
- end: `0x41b1`
- name: `Keys::GetString_1`
- size: `17`
- prototype: ``
- caller_count: `26`
- callee_count: `0`
- tags: ``

## callers

- `0x3a50`
- `0x3a60`
- `0x3a70`
- `0x3a80`
- `0x3a90`
- `0x3aa0`
- `0x3ab0`
- `0x3ac0`
- `0x3ad0`
- `0x3ae0`
- `0x3af0`
- `0x3b00`
- `0x3b10`
- `0x3b20`
- `0x3b30`
- `0x3b40`
- `0x3b50`
- `0x3b60`
- `0x3b70`
- `0x3b80`
- `0x3b90`
- `0x3ba0`
- `0x3bb0`
- `0x3bc0`
- `0x3bd0`
- `0x3be0`

## pseudocode

```c

```

## disassembly

```asm
0x41a0  ldsfld   class [mscorlib]System.Resources.ResourceManager Keys::resourceManager
0x41a5  ldarg.0
0x41a6  ldsfld   class [mscorlib]System.Globalization.CultureInfo Keys::_culture
0x41ab  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x41b0  ret
```
