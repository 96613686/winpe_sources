# Keys::GetString

- ea: `0x2280`
- end: `0x2291`
- name: `Keys::GetString`
- size: `17`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0xcb0`
- `0xcc0`
- `0xcd0`
- `0xce0`
- `0xcf0`
- `0xd00`
- `0xd10`
- `0xd20`

## pseudocode

```c

```

## disassembly

```asm
0x2280  ldsfld   class [mscorlib]System.Resources.ResourceManager Keys::resourceManager
0x2285  ldarg.0
0x2286  ldsfld   class [mscorlib]System.Globalization.CultureInfo Keys::_culture
0x228b  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2290  ret
```
