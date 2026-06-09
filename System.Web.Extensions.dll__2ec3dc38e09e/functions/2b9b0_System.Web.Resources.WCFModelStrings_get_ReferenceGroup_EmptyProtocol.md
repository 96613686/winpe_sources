# System.Web.Resources.WCFModelStrings::get_ReferenceGroup_EmptyProtocol

- ea: `0x2b9b0`
- end: `0x2b9c5`
- name: `System.Web.Resources.WCFModelStrings::get_ReferenceGroup_EmptyProtocol`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2d00`

## callees

- `0x2b8c0`

## string_xrefs

- `0x2b9b5`: `ReferenceGroup_EmptyProtocol`

## pseudocode

```c

```

## disassembly

```asm
0x2b9b0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.WCFModelStrings::get_ResourceManager()
0x2b9b5  ldstr    aReferencegroup_5// "ReferenceGroup_EmptyProtocol"
0x2b9ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.WCFModelStrings::resourceCulture
0x2b9bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b9c4  ret
```
