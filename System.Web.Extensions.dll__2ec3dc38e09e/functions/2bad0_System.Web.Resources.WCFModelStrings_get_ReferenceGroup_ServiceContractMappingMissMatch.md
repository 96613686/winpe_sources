# System.Web.Resources.WCFModelStrings::get_ReferenceGroup_ServiceContractMappingMissMatch

- ea: `0x2bad0`
- end: `0x2bae5`
- name: `System.Web.Resources.WCFModelStrings::get_ReferenceGroup_ServiceContractMappingMissMatch`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x4390`

## callees

- `0x2b8c0`

## string_xrefs

- `0x2bad5`: `ReferenceGroup_ServiceContractMappingMissMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2bad0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.WCFModelStrings::get_ResourceManager()
0x2bad5  ldstr    aReferencegroup_14// "ReferenceGroup_ServiceContractMappingMi"...
0x2bada  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.WCFModelStrings::resourceCulture
0x2badf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2bae4  ret
```
