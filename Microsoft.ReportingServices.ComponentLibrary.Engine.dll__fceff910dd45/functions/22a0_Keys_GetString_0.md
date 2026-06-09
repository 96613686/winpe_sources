# Keys::GetString_0

- ea: `0x22a0`
- end: `0x22bc`
- name: `Keys::GetString_0`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0xd40`

## pseudocode

```c

```

## disassembly

```asm
0x22a0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x22a5  ldsfld   class [mscorlib]System.Resources.ResourceManager Keys::resourceManager
0x22aa  ldarg.0
0x22ab  ldsfld   class [mscorlib]System.Globalization.CultureInfo Keys::_culture
0x22b0  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x22b5  ldarg.1
0x22b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x22bb  ret
```
