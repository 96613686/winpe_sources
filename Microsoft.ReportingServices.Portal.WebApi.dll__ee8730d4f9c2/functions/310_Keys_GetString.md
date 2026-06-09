# Keys::GetString

- ea: `0x310`
- end: `0x321`
- name: `Keys::GetString`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x310  ldsfld   class [mscorlib]System.Resources.ResourceManager Keys::resourceManager
0x315  ldarg.0
0x316  ldsfld   class [mscorlib]System.Globalization.CultureInfo Keys::_culture
0x31b  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x320  ret
```
