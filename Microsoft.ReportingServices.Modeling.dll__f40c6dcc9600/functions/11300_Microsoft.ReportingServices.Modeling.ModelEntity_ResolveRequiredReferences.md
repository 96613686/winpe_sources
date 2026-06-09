# Microsoft.ReportingServices.Modeling.ModelEntity::ResolveRequiredReferences

- ea: `0x11300`
- end: `0x11356`
- name: `Microsoft.ReportingServices.Modeling.ModelEntity::ResolveRequiredReferences`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x10760`
- `0x10960`
- `0x11300`
- `0x11db0`
- `0x14530`

## string_xrefs

- `0x11313`: `IdentifyingAttributes already initialized on ModelEntity`

## pseudocode

```c

```

## disassembly

```asm
0x11300  ldarg.0
0x11301  ldarg.1
0x11302  call     instance bool Microsoft.ReportingServices.Modeling.ModelItem::ResolveRequiredReferences(class Microsoft.ReportingServices.Modeling.SemanticModel newModel)
0x11307  brtrue.s loc_1130B
0x11309  ldc.i4.0
0x1130a  ret
0x1130b  ldarg.0
0x1130c  ldfld    class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::m_identAttrs
0x11311  brfalse.s loc_1131E
0x11313  ldstr    aIdentifyingatt_0// "IdentifyingAttributes already initializ"...
0x11318  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1131d  throw
0x1131e  ldarg.0
0x1131f  ldarg.0
0x11320  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelEntity::get_BaseItem()
0x11325  callvirt instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_IdentifyingAttributes()
0x1132a  ldarg.1
0x1132b  callvirt instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::CloneFor(class Microsoft.ReportingServices.Modeling.SemanticModel newModel)
0x11330  stfld    class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::m_identAttrs
0x11335  ldarg.0
0x11336  ldfld    class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::m_identAttrs
0x1133b  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Count()
0x11340  ldarg.0
0x11341  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelEntity::get_BaseItem()
0x11346  callvirt instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_IdentifyingAttributes()
0x1134b  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Count()
0x11350  beq.s    loc_11354
0x11352  ldc.i4.0
0x11353  ret
0x11354  ldc.i4.1
0x11355  ret
```
