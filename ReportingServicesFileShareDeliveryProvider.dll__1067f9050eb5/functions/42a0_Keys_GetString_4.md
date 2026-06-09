# Keys::GetString_4

- ea: `0x42a0`
- end: `0x42bc`
- name: `Keys::GetString_4`
- size: `28`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x3de0`
- `0x3e00`
- `0x3e10`
- `0x3e20`
- `0x3e30`
- `0x3e40`

## pseudocode

```c

```

## disassembly

```asm
0x42a0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x42a5  ldsfld   class [mscorlib]System.Resources.ResourceManager Keys::resourceManager
0x42aa  ldarg.0
0x42ab  ldsfld   class [mscorlib]System.Globalization.CultureInfo Keys::_culture
0x42b0  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x42b5  ldarg.1
0x42b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x42bb  ret
```
