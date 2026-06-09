# System.Web.Resources.AtlasWeb::get_ScriptManager_CannotAddHistoryPointOutsideOfAsyncPostBack

- ea: `0x2aa90`
- end: `0x2aaa5`
- name: `System.Web.Resources.AtlasWeb::get_ScriptManager_CannotAddHistoryPointOutsideOfAsyncPostBack`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x15260`

## callees

- `0x28080`

## string_xrefs

- `0x2aa95`: `ScriptManager_CannotAddHistoryPointOutsideOfAsyncPostBack`

## pseudocode

```c

```

## disassembly

```asm
0x2aa90  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2aa95  ldstr    aScriptmanagerC// "ScriptManager_CannotAddHistoryPointOuts"...
0x2aa9a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2aa9f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2aaa4  ret
```
