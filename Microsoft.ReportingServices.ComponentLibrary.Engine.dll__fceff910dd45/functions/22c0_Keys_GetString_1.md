# Keys::GetString_1

- ea: `0x22c0`
- end: `0x22dd`
- name: `Keys::GetString_1`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0xd30`

## pseudocode

```c

```

## disassembly

```asm
0x22c0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x22c5  ldsfld   class [mscorlib]System.Resources.ResourceManager Keys::resourceManager
0x22ca  ldarg.0
0x22cb  ldsfld   class [mscorlib]System.Globalization.CultureInfo Keys::_culture
0x22d0  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x22d5  ldarg.1
0x22d6  ldarg.2
0x22d7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x22dc  ret
```
