# Microsoft.ReportingServices.Modeling.ModelItem::InitializeID

- ea: `0x14630`
- end: `0x1467e`
- name: `Microsoft.ReportingServices.Modeling.ModelItem::InitializeID`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x139d0`
- `0x14390`

## callees

- `0x97d0`
- `0x9cf0`
- `0xa0f0`
- `0xa120`
- `0x13c60`
- `0x14630`

## string_xrefs

- `0x14667`: `__id is empty on compiled item`

## pseudocode

```c

```

## disassembly

```asm
0x14630  ldarg.0
0x14631  ldflda   valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::__id
0x14636  call     instance string Microsoft.ReportingServices.Modeling.QName::get_Name()
0x1463b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x14640  brtrue.s loc_1467D
0x14642  ldarg.0
0x14643  ldflda   valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::__id
0x14648  call     instance string Microsoft.ReportingServices.Modeling.QName::get_Namespace()
0x1464d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x14652  brfalse.s loc_1465F
0x14654  ldstr    aIdNameIsEmptyB// "__id.Name is empty but Namespace is non"...
0x14659  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1465e  throw
0x1465f  ldarg.0
0x14660  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x14665  brfalse.s loc_14672
0x14667  ldstr    aIdIsEmptyOnCom// "__id is empty on compiled item"
0x1466c  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x14671  throw
0x14672  ldarg.0
0x14673  call     valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::NewID()
0x14678  stfld    valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::__id
0x1467d  ret
```
