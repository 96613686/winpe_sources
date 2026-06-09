# Keys::GetString_5

- ea: `0x42c0`
- end: `0x42dd`
- name: `Keys::GetString_5`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x3dd0`
- `0x3df0`

## pseudocode

```c

```

## disassembly

```asm
0x42c0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x42c5  ldsfld   class [mscorlib]System.Resources.ResourceManager Keys::resourceManager
0x42ca  ldarg.0
0x42cb  ldsfld   class [mscorlib]System.Globalization.CultureInfo Keys::_culture
0x42d0  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x42d5  ldarg.1
0x42d6  ldarg.2
0x42d7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x42dc  ret
```
