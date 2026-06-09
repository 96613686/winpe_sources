# Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::SetLastUpdate

- ea: `0x3de30`
- end: `0x3de88`
- name: `Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::SetLastUpdate`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3d4b0`

## callees

- `0x2ac60`
- `0x2ac90`
- `0x3de30`

## string_xrefs

- `0x3de31`: `TimeOfLastTaxonomyUpdate`
- `0x3de57`: `TimeOfLastTaxonomyUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x3de30  ldarg.1
0x3de31  ldstr    aTimeoflasttaxo// "TimeOfLastTaxonomyUpdate"
0x3de36  ldarga.s 0
0x3de38  constrained. [mscorlib]System.Guid
0x3de3e  callvirt instance string [mscorlib]System.Object::ToString()
0x3de43  call     string [mscorlib]System.String::Concat(string, string)
0x3de48  callvirt T0x2B000060
0x3de4d  stloc.0
0x3de4e  ldloc.0
0x3de4f  ldnull
0x3de50  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x3de55  brfalse.s loc_3DE7A
0x3de57  ldstr    aTimeoflasttaxo// "TimeOfLastTaxonomyUpdate"
0x3de5c  ldarga.s 0
0x3de5e  constrained. [mscorlib]System.Guid
0x3de64  callvirt instance string [mscorlib]System.Object::ToString()
0x3de69  call     string [mscorlib]System.String::Concat(string, string)
0x3de6e  ldarg.1
0x3de6f  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3de74  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.PersistedTimeStamp::.ctor(string name, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject parent, valuetype [mscorlib]System.Guid id)
0x3de79  stloc.0
0x3de7a  ldloc.0
0x3de7b  ldarg.2
0x3de7c  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.PersistedTimeStamp::set_LastUpdate(valuetype [mscorlib]System.DateTime value)
0x3de81  ldloc.0
0x3de82  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x3de87  ret
```
