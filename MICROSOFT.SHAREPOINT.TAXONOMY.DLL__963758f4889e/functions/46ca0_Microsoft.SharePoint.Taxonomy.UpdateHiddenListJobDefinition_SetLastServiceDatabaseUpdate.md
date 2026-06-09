# Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::SetLastServiceDatabaseUpdate

- ea: `0x46ca0`
- end: `0x46d02`
- name: `Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::SetLastServiceDatabaseUpdate`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x47a50`

## callees

- `0x2ac60`
- `0x2ac90`
- `0x46ca0`

## string_xrefs

- `0x46ca6`: `TimeOfLastTaxonomyUpdate`
- `0x46ccc`: `TimeOfLastTaxonomyUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x46ca0  ldarg.0
0x46ca1  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x46ca6  ldstr    aTimeoflasttaxo// "TimeOfLastTaxonomyUpdate"
0x46cab  ldarga.s 1
0x46cad  constrained. [mscorlib]System.Guid
0x46cb3  callvirt instance string [mscorlib]System.Object::ToString()
0x46cb8  call     string [mscorlib]System.String::Concat(string, string)
0x46cbd  callvirt T0x2B000060
0x46cc2  stloc.0
0x46cc3  ldloc.0
0x46cc4  ldnull
0x46cc5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x46cca  brfalse.s loc_46CF4
0x46ccc  ldstr    aTimeoflasttaxo// "TimeOfLastTaxonomyUpdate"
0x46cd1  ldarga.s 1
0x46cd3  constrained. [mscorlib]System.Guid
0x46cd9  callvirt instance string [mscorlib]System.Object::ToString()
0x46cde  call     string [mscorlib]System.String::Concat(string, string)
0x46ce3  ldarg.0
0x46ce4  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x46ce9  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x46cee  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.PersistedTimeStamp::.ctor(string name, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject parent, valuetype [mscorlib]System.Guid id)
0x46cf3  stloc.0
0x46cf4  ldloc.0
0x46cf5  ldarg.2
0x46cf6  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.PersistedTimeStamp::set_LastUpdate(valuetype [mscorlib]System.DateTime value)
0x46cfb  ldloc.0
0x46cfc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x46d01  ret
```
