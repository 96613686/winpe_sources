# Microsoft.ReportingServices.Modeling.ExpressionPath::ResolveInheritancePath

- ea: `0x1e410`
- end: `0x1e4df`
- name: `Microsoft.ReportingServices.Modeling.ExpressionPath::ResolveInheritancePath`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e3f0`

## callees

- `0x97d0`
- `0x1de40`
- `0x1e0f0`
- `0x1e410`
- `0x1e4e0`
- `0x1e500`
- `0x1f1a0`
- `0x241a0`
- `0x241b0`

## string_xrefs

- `0x1e4be`: `sourceDepth passed zero without reaching common base entity`

## pseudocode

```c

```

## disassembly

```asm
0x1e410  ldarg.0
0x1e411  ldloca.s 0
0x1e413  call     class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.ExpressionPath::GetInheritanceRoot(class Microsoft.ReportingServices.Modeling.IQueryEntity entity, [out] int32& depth)
0x1e418  ldarg.1
0x1e419  ldloca.s 1
0x1e41b  call     class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.ExpressionPath::GetInheritanceRoot(class Microsoft.ReportingServices.Modeling.IQueryEntity entity, [out] int32& depth)
0x1e420  beq.s    loc_1E424
0x1e422  ldc.i4.0
0x1e423  ret
0x1e424  ldloc.0
0x1e425  newobj   instance void Microsoft.ReportingServices.Modeling.ExpressionPath::.ctor(int32 capacity)
0x1e42a  stloc.2
0x1e42b  ldloc.1
0x1e42c  newobj   instance void Microsoft.ReportingServices.Modeling.ExpressionPath::.ctor(int32 capacity)
0x1e431  stloc.3
0x1e432  ldloc.0
0x1e433  ldloc.1
0x1e434  ble.s    loc_1E443
0x1e436  ldloc.2
0x1e437  ldarga.s 0
0x1e439  ldloca.s 0
0x1e43b  ldloc.1
0x1e43c  call     void Microsoft.ReportingServices.Modeling.ExpressionPath::AddInheritancePathItems(class Microsoft.ReportingServices.Modeling.ExpressionPath path, class Microsoft.ReportingServices.Modeling.IQueryEntity& entity, int32& entityDepth, int32 stopDepth)
0x1e441  br.s     loc_1E452
0x1e443  ldloc.1
0x1e444  ldloc.0
0x1e445  ble.s    loc_1E452
0x1e447  ldloc.3
0x1e448  ldarga.s 1
0x1e44a  ldloca.s 1
0x1e44c  ldloc.0
0x1e44d  call     void Microsoft.ReportingServices.Modeling.ExpressionPath::AddInheritancePathItems(class Microsoft.ReportingServices.Modeling.ExpressionPath path, class Microsoft.ReportingServices.Modeling.IQueryEntity& entity, int32& entityDepth, int32 stopDepth)
0x1e452  ldloc.0
0x1e453  ldloc.1
0x1e454  beq.s    loc_1E461
0x1e456  ldstr    aSourcedepthDoe// "sourceDepth does not equal targetDepth "...
0x1e45b  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1e460  throw
0x1e461  ldarg.0
0x1e462  ldarg.1
0x1e463  beq.s    loc_1E4C9
0x1e465  ldarg.0
0x1e466  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_InheritsFrom()
0x1e46b  ldarg.1
0x1e46c  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_InheritsFrom()
0x1e471  bne.un.s loc_1E482
0x1e473  ldarg.0
0x1e474  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_InheritsFrom()
0x1e479  callvirt instance bool Microsoft.ReportingServices.Modeling.IQueryEntity::get_DisjointInheritance()
0x1e47e  brfalse.s loc_1E482
0x1e480  ldc.i4.0
0x1e481  ret
0x1e482  ldloc.2
0x1e483  ldarg.0
0x1e484  ldarg.0
0x1e485  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_InheritsFrom()
0x1e48a  newobj   instance void Microsoft.ReportingServices.Modeling.InheritancePathItem::.ctor(class Microsoft.ReportingServices.Modeling.IQueryEntity sourceEntity, class Microsoft.ReportingServices.Modeling.IQueryEntity targetEntity)
0x1e48f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.PathItem>::Add(var<u1>)
0x1e494  ldloc.3
0x1e495  ldarg.1
0x1e496  ldarg.1
0x1e497  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_InheritsFrom()
0x1e49c  newobj   instance void Microsoft.ReportingServices.Modeling.InheritancePathItem::.ctor(class Microsoft.ReportingServices.Modeling.IQueryEntity sourceEntity, class Microsoft.ReportingServices.Modeling.IQueryEntity targetEntity)
0x1e4a1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.PathItem>::Add(var<u1>)
0x1e4a6  ldarg.0
0x1e4a7  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_InheritsFrom()
0x1e4ac  starg.s  0
0x1e4ae  ldarg.1
0x1e4af  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_InheritsFrom()
0x1e4b4  starg.s  1
0x1e4b6  ldloc.0
0x1e4b7  ldc.i4.1
0x1e4b8  sub
0x1e4b9  stloc.0
0x1e4ba  ldloc.0
0x1e4bb  ldc.i4.0
0x1e4bc  bge.s    loc_1E461
0x1e4be  ldstr    aSourcedepthPas// "sourceDepth passed zero without reachin"...
0x1e4c3  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1e4c8  throw
0x1e4c9  ldarg.2
0x1e4ca  ldloc.2
0x1e4cb  callvirt instance void class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.PathItem>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1e4d0  ldloc.3
0x1e4d1  callvirt instance void Microsoft.ReportingServices.Modeling.ExpressionPath::Reverse()
0x1e4d6  ldarg.2
0x1e4d7  ldloc.3
0x1e4d8  callvirt instance void class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.PathItem>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1e4dd  ldc.i4.1
0x1e4de  ret
```
