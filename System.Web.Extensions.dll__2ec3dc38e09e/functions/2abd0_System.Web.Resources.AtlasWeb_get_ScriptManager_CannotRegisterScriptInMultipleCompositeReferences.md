# System.Web.Resources.AtlasWeb::get_ScriptManager_CannotRegisterScriptInMultipleCompositeReferences

- ea: `0x2abd0`
- end: `0x2abe5`
- name: `System.Web.Resources.AtlasWeb::get_ScriptManager_CannotRegisterScriptInMultipleCompositeReferences`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x15ad0`

## callees

- `0x28080`

## string_xrefs

- `0x2abd5`: `ScriptManager_CannotRegisterScriptInMultipleCompositeReferences`

## pseudocode

```c

```

## disassembly

```asm
0x2abd0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2abd5  ldstr    aScriptmanagerC_9// "ScriptManager_CannotRegisterScriptInMul"...
0x2abda  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2abdf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2abe4  ret
```
