# Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::get_PermissionAliasMap

- ea: `0x1e6d0`
- end: `0x1e709`
- name: `Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::get_PermissionAliasMap`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1e710`

## callees

- `0x1e6d0`

## string_xrefs

- `0x1e6de`: `termstore.read.all`
- `0x1e6e3`: `termstore.read`
- `0x1e6ee`: `termstore.readwrite.all`
- `0x1e6f3`: `termstore.write`

## pseudocode

```c

```

## disassembly

```asm
0x1e6d0  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::permissionMap
0x1e6d5  brtrue.s loc_1E703
0x1e6d7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x1e6dc  stloc.0
0x1e6dd  ldloc.0
0x1e6de  ldstr    aTermstoreReadA// "termstore.read.all"
0x1e6e3  ldstr    aTermstoreRead// "termstore.read"
0x1e6e8  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x1e6ed  ldloc.0
0x1e6ee  ldstr    aTermstoreReadw// "termstore.readwrite.all"
0x1e6f3  ldstr    aTermstoreWrite// "termstore.write"
0x1e6f8  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x1e6fd  ldloc.0
0x1e6fe  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::permissionMap
0x1e703  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::permissionMap
0x1e708  ret
```
