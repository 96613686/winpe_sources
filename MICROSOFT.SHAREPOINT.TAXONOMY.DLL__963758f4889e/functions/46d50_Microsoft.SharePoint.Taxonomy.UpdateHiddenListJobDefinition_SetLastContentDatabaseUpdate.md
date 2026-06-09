# Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::SetLastContentDatabaseUpdate

- ea: `0x46d50`
- end: `0x46da8`
- name: `Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::SetLastContentDatabaseUpdate`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x47a50`

## callees

- `0x2ac60`
- `0x2ac90`
- `0x46d50`

## string_xrefs

- `0x46d51`: `TimeOfLastTaxonomyExtensionUpdate-`
- `0x46d77`: `TimeOfLastTaxonomyExtensionUpdate-`

## pseudocode

```c

```

## disassembly

```asm
0x46d50  ldarg.1
0x46d51  ldstr    aTimeoflasttaxo_0// "TimeOfLastTaxonomyExtensionUpdate-"
0x46d56  ldarga.s 0
0x46d58  constrained. [mscorlib]System.Guid
0x46d5e  callvirt instance string [mscorlib]System.Object::ToString()
0x46d63  call     string [mscorlib]System.String::Concat(string, string)
0x46d68  callvirt T0x2B000060
0x46d6d  stloc.0
0x46d6e  ldloc.0
0x46d6f  ldnull
0x46d70  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x46d75  brfalse.s loc_46D9A
0x46d77  ldstr    aTimeoflasttaxo_0// "TimeOfLastTaxonomyExtensionUpdate-"
0x46d7c  ldarga.s 0
0x46d7e  constrained. [mscorlib]System.Guid
0x46d84  callvirt instance string [mscorlib]System.Object::ToString()
0x46d89  call     string [mscorlib]System.String::Concat(string, string)
0x46d8e  ldarg.1
0x46d8f  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x46d94  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.PersistedTimeStamp::.ctor(string name, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject parent, valuetype [mscorlib]System.Guid id)
0x46d99  stloc.0
0x46d9a  ldloc.0
0x46d9b  ldarg.2
0x46d9c  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.PersistedTimeStamp::set_LastUpdate(valuetype [mscorlib]System.DateTime value)
0x46da1  ldloc.0
0x46da2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x46da7  ret
```
