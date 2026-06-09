# System.Web.Resources.AtlasWeb::get_UpdateProgress_DisplayAfterInvalid

- ea: `0x2b5f0`
- end: `0x2b605`
- name: `System.Web.Resources.AtlasWeb::get_UpdateProgress_DisplayAfterInvalid`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1a090`

## callees

- `0x28080`

## string_xrefs

- `0x2b5f5`: `UpdateProgress_DisplayAfterInvalid`

## pseudocode

```c

```

## disassembly

```asm
0x2b5f0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b5f5  ldstr    aUpdateprogress_1// "UpdateProgress_DisplayAfterInvalid"
0x2b5fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b5ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b604  ret
```
