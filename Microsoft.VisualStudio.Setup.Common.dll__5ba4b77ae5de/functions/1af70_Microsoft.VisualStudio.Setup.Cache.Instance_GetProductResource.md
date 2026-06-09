# Microsoft.VisualStudio.Setup.Cache.Instance::GetProductResource

- ea: `0x1af70`
- end: `0x1af85`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::GetProductResource`
- size: `21`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1ac00`
- `0x1ac20`
- `0x1ac40`
- `0x1acc0`
- `0x1acf0`

## callees

- `0x1a930`
- `0x1af20`

## pseudocode

```c

```

## disassembly

```asm
0x1af70  ldarg.0
0x1af71  ldarg.0
0x1af72  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.LocalizedResource> Microsoft.VisualStudio.Setup.Cache.Instance::get_LocalizedResources()
0x1af77  ldarg.1
0x1af78  ldarg.2
0x1af79  ldarg.0
0x1af7a  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, class Microsoft.VisualStudio.Setup.LocalizedResource> Microsoft.VisualStudio.Setup.Cache.Instance::cachedProductResources
0x1af7f  call     instance class Microsoft.VisualStudio.Setup.LocalizedResource Microsoft.VisualStudio.Setup.Cache.Instance::GetResource(class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.LocalizedResource> source, class [mscorlib]System.Globalization.CultureInfo culture, valuetype Microsoft.VisualStudio.Setup.LocalizedResourceFallback fallback, class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, class Microsoft.VisualStudio.Setup.LocalizedResource> cache)
0x1af84  ret
```
