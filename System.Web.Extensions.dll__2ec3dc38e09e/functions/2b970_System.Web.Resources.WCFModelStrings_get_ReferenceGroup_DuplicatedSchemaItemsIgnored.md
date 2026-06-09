# System.Web.Resources.WCFModelStrings::get_ReferenceGroup_DuplicatedSchemaItemsIgnored

- ea: `0x2b970`
- end: `0x2b985`
- name: `System.Web.Resources.WCFModelStrings::get_ReferenceGroup_DuplicatedSchemaItemsIgnored`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x3330`

## callees

- `0x2b8c0`

## string_xrefs

- `0x2b975`: `ReferenceGroup_DuplicatedSchemaItemsIgnored`

## pseudocode

```c

```

## disassembly

```asm
0x2b970  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.WCFModelStrings::get_ResourceManager()
0x2b975  ldstr    aReferencegroup_3// "ReferenceGroup_DuplicatedSchemaItemsIgn"...
0x2b97a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.WCFModelStrings::resourceCulture
0x2b97f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b984  ret
```
