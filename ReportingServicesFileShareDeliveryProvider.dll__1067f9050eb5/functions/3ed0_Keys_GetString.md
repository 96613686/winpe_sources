# Keys::GetString

- ea: `0x3ed0`
- end: `0x3ee1`
- name: `Keys::GetString`
- size: `17`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x90`
- `0xa0`
- `0xb0`
- `0xc0`
- `0xd0`
- `0xe0`
- `0xf0`

## pseudocode

```c

```

## disassembly

```asm
0x3ed0  ldsfld   class [mscorlib]System.Resources.ResourceManager Keys::resourceManager
0x3ed5  ldarg.0
0x3ed6  ldsfld   class [mscorlib]System.Globalization.CultureInfo Keys::_culture
0x3edb  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3ee0  ret
```
