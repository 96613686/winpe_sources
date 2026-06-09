# Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeReferenceCreator::TryCreateReference_0

- ea: `0x208d50`
- end: `0x209080`
- name: `Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeReferenceCreator::TryCreateReference_0`
- size: `816`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `service_task, broker_com_uri`

## callers

- `0x208d30`

## callees

- `0x208d50`
- `0x2093f0`
- `0x209430`
- `0x209480`
- `0x2094d0`
- `0x209510`
- `0x209580`
- `0x209600`
- `0x209620`
- `0x209670`
- `0x2096b0`
- `0x2096f0`
- `0x2097c0`
- `0x209820`
- `0x209870`
- `0x2098d0`
- `0x2098f0`
- `0x209930`
- `0x209970`
- `0x2099d0`
- `0x209a30`
- `0x209a50`
- `0x209a90`
- `0x209ad0`
- `0x209b10`
- `0x209b50`
- `0x209b90`
- `0x209bd0`
- `0x209c10`
- `0x209c40`
- `0x20c9b0`

## string_xrefs

- `0x208e80`: `Cannot create reference to Nothing or Null`

## pseudocode

```c

```

## disassembly

```asm
0x208d50  ldarg.1
0x208d51  ldc.i4.s 0x72
0x208d53  bgt      loc_208DDF
0x208d58  ldarg.1
0x208d59  ldc.i4.s 0x17
0x208d5b  bgt.s    loc_208D71
0x208d5d  ldarg.1
0x208d5e  ldc.i4.1
0x208d5f  ble.un   loc_208E7A
0x208d64  ldarg.1
0x208d65  ldc.i4.s 0x17
0x208d67  beq      loc_209066
0x208d6c  br       loc_209079
0x208d71  ldarg.1
0x208d72  ldc.i4.s 0x1D
0x208d74  beq      loc_20905C
0x208d79  ldarg.1
0x208d7a  ldc.i4.s 0x5D
0x208d7c  sub
0x208d7d  switch   loc_208FCA, loc_208F5B, loc_209036, loc_209053, loc_20904A, loc_208FBD, loc_20902C, loc_208E8F, loc_208FF1, loc_209040, loc_208FA3, loc_208FE4, loc_208EE3, loc_20900F, loc_208EFB, loc_209006, loc_209079, loc_208F67, loc_208F73, loc_208F97, loc_208F1F, loc_208F2B
0x208dda  br       loc_209079
0x208ddf  ldarg.1
0x208de0  ldc.i4   0x145
0x208de5  bgt.s    loc_208E47
0x208de7  ldarg.1
0x208de8  ldc.i4   0x121
0x208ded  sub
0x208dee  switch   loc_208F4F, loc_208FD7, loc_208EBF, loc_209022, loc_209079, loc_208F37, loc_208F43, loc_208F13, loc_208ECB, loc_208F07, loc_209019, loc_208ED7, loc_208FFD, loc_209079, loc_208EEF, loc_209079, loc_208FB0
0x208e37  ldarg.1
0x208e38  ldc.i4   0x145
0x208e3d  beq      loc_208F7F
0x208e42  br       loc_209079
0x208e47  ldarg.1
0x208e48  ldc.i4   0x17F
0x208e4d  beq      loc_20906F
0x208e52  ldarg.1
0x208e53  ldc.i4   0x186
0x208e58  beq      loc_208F8B
0x208e5d  ldarg.1
0x208e5e  ldc.i4   0x208
0x208e63  sub
0x208e64  switch   loc_208EB3, loc_208EA7, loc_208E9B
0x208e75  br       loc_209079
0x208e7a  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x208e7f  ldc.i4.0
0x208e80  ldstr    aCannotCreateRe// "Cannot create reference to Nothing or N"...
0x208e85  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x208e8a  ldarg.2
0x208e8b  ldnull
0x208e8c  stind.ref
0x208e8d  ldc.i4.0
0x208e8e  ret
0x208e8f  ldarg.2
0x208e90  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeTablixCellReference::.ctor()
0x208e95  stind.ref
0x208e96  br       loc_20907E
0x208e9b  ldarg.2
0x208e9c  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeDataShapeIntersectionReference::.ctor()
0x208ea1  stind.ref
0x208ea2  br       loc_20907E
0x208ea7  ldarg.2
0x208ea8  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeDataShapeGroupLeafObjReference::.ctor()
0x208ead  stind.ref
0x208eae  br       loc_20907E
0x208eb3  ldarg.2
0x208eb4  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeDataShapeObjReference::.ctor()
0x208eb9  stind.ref
0x208eba  br       loc_20907E
0x208ebf  ldarg.2
0x208ec0  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeCellReference::.ctor()
0x208ec5  stind.ref
0x208ec6  br       loc_20907E
0x208ecb  ldarg.2
0x208ecc  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeDetailObjReference::.ctor()
0x208ed1  stind.ref
0x208ed2  br       loc_20907E
0x208ed7  ldarg.2
0x208ed8  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeDataTablixObjReference::.ctor()
0x208edd  stind.ref
0x208ede  br       loc_20907E
0x208ee3  ldarg.2
0x208ee4  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeHierarchyObjReference::.ctor()
0x208ee9  stind.ref
0x208eea  br       loc_20907E
0x208eef  ldarg.2
0x208ef0  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeDataRegionObjReference::.ctor()
0x208ef5  stind.ref
0x208ef6  br       loc_20907E
0x208efb  ldarg.2
0x208efc  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeDataTablixGroupRootObjReference::.ctor()
0x208f01  stind.ref
0x208f02  br       loc_20907E
0x208f07  ldarg.2
0x208f08  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeGroupRootObjReference::.ctor()
0x208f0d  stind.ref
0x208f0e  br       loc_20907E
0x208f13  ldarg.2
0x208f14  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeGroupObjReference::.ctor()
0x208f19  stind.ref
0x208f1a  br       loc_20907E
0x208f1f  ldarg.2
0x208f20  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeTablixGroupLeafObjReference::.ctor()
0x208f25  stind.ref
0x208f26  br       loc_20907E
0x208f2b  ldarg.2
0x208f2c  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeChartCriGroupLeafObjReference::.ctor()
0x208f31  stind.ref
0x208f32  br       loc_20907E
0x208f37  ldarg.2
0x208f38  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeDataTablixGroupLeafObjReference::.ctor()
0x208f3d  stind.ref
0x208f3e  br       loc_20907E
0x208f43  ldarg.2
0x208f44  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeGroupLeafObjReference::.ctor()
0x208f49  stind.ref
0x208f4a  br       loc_20907E
0x208f4f  ldarg.2
0x208f50  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeOnDemandDataSetObjReference::.ctor()
0x208f55  stind.ref
0x208f56  br       loc_20907E
0x208f5b  ldarg.2
0x208f5c  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeSortHierarchyObjReference::.ctor()
0x208f61  stind.ref
0x208f62  br       loc_20907E
0x208f67  ldarg.2
0x208f68  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeTablixObjReference::.ctor()
0x208f6d  stind.ref
0x208f6e  br       loc_20907E
0x208f73  ldarg.2
0x208f74  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeChartObjReference::.ctor()
0x208f79  stind.ref
0x208f7a  br       loc_20907E
0x208f7f  ldarg.2
0x208f80  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeGaugePanelObjReference::.ctor()
0x208f85  stind.ref
0x208f86  br       loc_20907E
0x208f8b  ldarg.2
0x208f8c  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeMapDataRegionObjReference::.ctor()
0x208f91  stind.ref
0x208f92  br       loc_20907E
0x208f97  ldarg.2
0x208f98  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeCriObjReference::.ctor()
0x208f9d  stind.ref
0x208f9e  br       loc_20907E
0x208fa3  ldarg.2
0x208fa4  ldarg.1
0x208fa5  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.AggregateRow>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x208faa  stind.ref
0x208fab  br       loc_20907E
0x208fb0  ldarg.2
0x208fb1  ldarg.1
0x208fb2  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregate>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x208fb7  stind.ref
0x208fb8  br       loc_20907E
0x208fbd  ldarg.2
0x208fbe  ldarg.1
0x208fbf  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x208fc4  stind.ref
0x208fc5  br       loc_20907E
0x208fca  ldarg.2
0x208fcb  ldarg.1
0x208fcc  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataFieldRow>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x208fd1  stind.ref
0x208fd2  br       loc_20907E
0x208fd7  ldarg.2
0x208fd8  ldarg.1
0x208fd9  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.IHierarchyObj>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x208fde  stind.ref
0x208fdf  br       loc_20907E
0x208fe4  ldarg.2
0x208fe5  ldarg.1
0x208fe6  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeCells>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x208feb  stind.ref
0x208fec  br       loc_20907E
0x208ff1  ldarg.2
0x208ff2  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeChartCriCellReference::.ctor()
0x208ff7  stind.ref
0x208ff8  br       loc_20907E
0x208ffd  ldarg.2
0x208ffe  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeChartCriObjReference::.ctor()
0x209003  stind.ref
0x209004  br.s     loc_20907E
0x209006  ldarg.2
0x209007  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeDataTablixMemberObjReference::.ctor()
0x20900c  stind.ref
0x20900d  br.s     loc_20907E
0x20900f  ldarg.2
0x209010  ldarg.1
0x209011  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeGroupingObj>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x209016  stind.ref
0x209017  br.s     loc_20907E
0x209019  ldarg.2
0x20901a  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.RuntimeMemberObjReference::.ctor()
0x20901f  stind.ref
0x209020  br.s     loc_20907E
0x209022  ldarg.2
0x209023  ldarg.1
0x209024  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeRDLDataRegionObj>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x209029  stind.ref
0x20902a  br.s     loc_20907E
0x20902c  ldarg.2
0x20902d  ldarg.1
0x20902e  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeRICollection>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x209033  stind.ref
0x209034  br.s     loc_20907E
0x209036  ldarg.2
0x209037  ldarg.1
0x209038  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeSortFilterEventInfo>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x20903d  stind.ref
0x20903e  br.s     loc_20907E
0x209040  ldarg.2
0x209041  ldarg.1
0x209042  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeUserSortTargetInfo>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x209047  stind.ref
0x209048  br.s     loc_20907E
0x20904a  ldarg.2
0x20904b  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.SortExpressionScopeInstanceHolderReference::.ctor()
0x209050  stind.ref
0x209051  br.s     loc_20907E
0x209053  ldarg.2
0x209054  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.SortFilterExpressionScopeObjReference::.ctor()
0x209059  stind.ref
0x20905a  br.s     loc_20907E
0x20905c  ldarg.2
0x20905d  ldarg.1
0x20905e  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x209063  stind.ref
0x209064  br.s     loc_20907E
0x209066  ldarg.2
0x209067  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryNodeReference::.ctor()
0x20906c  stind.ref
0x20906d  br.s     loc_20907E
0x20906f  ldarg.2
0x209070  ldarg.1
0x209071  newobj   instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SimpleReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupTable>::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType)
0x209076  stind.ref
0x209077  br.s     loc_20907E
0x209079  ldarg.2
0x20907a  ldnull
0x20907b  stind.ref
0x20907c  ldc.i4.0
0x20907d  ret
0x20907e  ldc.i4.1
0x20907f  ret
```
