# System.Web.Resources.AtlasWeb::get_SqlHelper_SqlEverywhereNotInstalled

- ea: `0x2b2f0`
- end: `0x2b305`
- name: `System.Web.Resources.AtlasWeb::get_SqlHelper_SqlEverywhereNotInstalled`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x37320`
- `0x375f0`

## callees

- `0x28080`

## string_xrefs

- `0x2b2f5`: `SqlHelper_SqlEverywhereNotInstalled`

## pseudocode

```c

```

## disassembly

```asm
0x2b2f0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b2f5  ldstr    aSqlhelperSqlev// "SqlHelper_SqlEverywhereNotInstalled"
0x2b2fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b2ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b304  ret
```
