# System.Web.Resources.WCFModelStrings::get_ReferenceGroup_OperationDefinedInOneOfDuplicatedServiceContract

- ea: `0x2bab0`
- end: `0x2bac5`
- name: `System.Web.Resources.WCFModelStrings::get_ReferenceGroup_OperationDefinedInOneOfDuplicatedServiceContract`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x5f50`

## callees

- `0x2b8c0`

## string_xrefs

- `0x2bab5`: `ReferenceGroup_OperationDefinedInOneOfDuplicatedServiceContract`

## pseudocode

```c

```

## disassembly

```asm
0x2bab0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.WCFModelStrings::get_ResourceManager()
0x2bab5  ldstr    aReferencegroup_13// "ReferenceGroup_OperationDefinedInOneOfD"...
0x2baba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.WCFModelStrings::resourceCulture
0x2babf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2bac4  ret
```
