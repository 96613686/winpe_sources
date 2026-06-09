# System.Xaml.Schema.XamlNamespace::GetTypeExtensionName

- ea: `0x19e00`
- end: `0x19e0c`
- name: `System.Xaml.Schema.XamlNamespace::GetTypeExtensionName`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x19a40`

## string_xrefs

- `0x19e01`: `Extension`

## pseudocode

```c

```

## disassembly

```asm
0x19e00  ldarg.1
0x19e01  ldstr    aExtension// "Extension"
0x19e06  call     string [mscorlib]System.String::Concat(string, string)
0x19e0b  ret
```
