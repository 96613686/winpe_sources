# System.Web.Resources.AtlasWeb::get_JSON_IllegalPrimitive

- ea: `0x28df0`
- end: `0x28e05`
- name: `System.Web.Resources.AtlasWeb::get_JSON_IllegalPrimitive`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x30e30`
- `0x31490`

## callees

- `0x28080`

## string_xrefs

- `0x28df5`: `JSON_IllegalPrimitive`

## pseudocode

```c

```

## disassembly

```asm
0x28df0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28df5  ldstr    aJsonIllegalpri// "JSON_IllegalPrimitive"
0x28dfa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28dff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28e04  ret
```
