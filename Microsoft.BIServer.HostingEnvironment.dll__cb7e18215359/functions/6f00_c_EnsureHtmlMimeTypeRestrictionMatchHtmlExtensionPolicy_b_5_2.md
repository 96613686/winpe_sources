# <>c::<EnsureHtmlMimeTypeRestrictionMatchHtmlExtensionPolicy>b__5_2

- ea: `0x6f00`
- end: `0x6f1b`
- name: `<>c::<EnsureHtmlMimeTypeRestrictionMatchHtmlExtensionPolicy>b__5_2`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting`

## pseudocode

```c

```

## disassembly

```asm
0x6f00  ldarg.1
0x6f01  callvirt instance string [mscorlib]System.String::Trim()
0x6f06  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x6f0b  ldstr    aTextHtml// "text/html"
0x6f10  call     instance string [mscorlib]System.String::ToUpperInvariant()
0x6f15  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6f1a  ret
```
