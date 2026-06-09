# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceHelper::Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IRIFObjectCreator.CreateRIFObject

- ea: `0x10f0`
- end: `0x139f`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceHelper::Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IRIFObjectCreator.CreateRIFObject`
- size: `687`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `service_task, broker_com_uri`

## callees

- `0x10f0`
- `0x5c90`
- `0x8ba0`
- `0x97d0`
- `0xc260`
- `0xc6b0`
- `0xca70`
- `0xd380`
- `0xd390`
- `0xe200`
- `0xe2d0`
- `0xe680`
- `0xe730`
- `0xe8e0`
- `0xe990`
- `0xea10`
- `0xeb70`
- `0xec00`
- `0xec70`
- `0x103b0`
- `0x11ac0`
- `0x12120`
- `0x129f0`
- `0x12bf0`
- `0x13480`
- `0x151d0`
- `0x16450`
- `0x16910`
- `0x186a0`
- `0x1a380`
- `0x1b2a0`
- `0x1bb30`
- `0x1c450`
- `0x1dbd0`
- `0x1ed20`
- `0x1f390`
- `0x2de70`
- `0x367a0`

## pseudocode

```c

```

## disassembly

```asm
0x10f0  ldarg.1
0x10f1  brtrue.s loc_10F5
0x10f3  ldnull
0x10f4  ret
0x10f5  ldarg.1
0x10f6  ldc.i4.s 0x13
0x10f8  sub
0x10f9  switch   loc_130B, loc_1318, loc_1320, loc_132D, loc_1374, loc_133A, loc_1347, loc_1354, loc_135C, loc_1364, loc_11E6, loc_136C, loc_1374, loc_1374, loc_1374, loc_1374, loc_125F, loc_1374, loc_12EA, loc_12F5, loc_1300, loc_11FC, loc_1207, loc_1374, loc_1374, loc_1374, loc_1374, loc_1212, loc_121D, loc_1228, loc_1233, loc_123E, loc_1374, loc_1374, loc_1249, loc_1254, loc_12AF, loc_1374, loc_11F1, loc_1374, loc_1374, loc_128F, loc_1374, loc_129F, loc_12CA, loc_1374, loc_12DA, loc_1374, loc_12BF, loc_1374, loc_127F, loc_126F, loc_1374, loc_11DB
0x11d6  br       loc_1374
0x11db  newobj   instance void Microsoft.ReportingServices.Modeling.SemanticModel::.ctor()
0x11e0  stloc.0
0x11e1  br       loc_1391
0x11e6  call     class Microsoft.ReportingServices.Modeling.DataSourceView Microsoft.ReportingServices.Modeling.DataSourceView::FromBinary()
0x11eb  stloc.0
0x11ec  br       loc_1391
0x11f1  newobj   instance void Microsoft.ReportingServices.Modeling.CustomProperty::.ctor()
0x11f6  stloc.0
0x11f7  br       loc_1391
0x11fc  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor()
0x1201  stloc.0
0x1202  br       loc_1391
0x1207  newobj   instance void ResultTypePersistable::.ctor()
0x120c  stloc.0
0x120d  br       loc_1391
0x1212  newobj   instance void Microsoft.ReportingServices.Modeling.FunctionNode::.ctor()
0x1217  stloc.0
0x1218  br       loc_1391
0x121d  newobj   instance void Microsoft.ReportingServices.Modeling.AttributeRefNode::.ctor()
0x1222  stloc.0
0x1223  br       loc_1391
0x1228  newobj   instance void Microsoft.ReportingServices.Modeling.EntityRefNode::.ctor()
0x122d  stloc.0
0x122e  br       loc_1391
0x1233  newobj   instance void Microsoft.ReportingServices.Modeling.LiteralNode::.ctor()
0x1238  stloc.0
0x1239  br       loc_1391
0x123e  newobj   instance void Microsoft.ReportingServices.Modeling.NullNode::.ctor()
0x1243  stloc.0
0x1244  br       loc_1391
0x1249  newobj   instance void Microsoft.ReportingServices.Modeling.RolePathItem::.ctor()
0x124e  stloc.0
0x124f  br       loc_1391
0x1254  newobj   instance void Microsoft.ReportingServices.Modeling.InheritancePathItem::.ctor()
0x1259  stloc.0
0x125a  br       loc_1391
0x125f  newobj   instance void Microsoft.ReportingServices.Modeling.Perspective::.ctor()
0x1264  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x1269  stloc.0
0x126a  br       loc_1391
0x126f  newobj   instance void Microsoft.ReportingServices.Modeling.ModelEntityFolder::.ctor()
0x1274  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x1279  stloc.0
0x127a  br       loc_1391
0x127f  newobj   instance void Microsoft.ReportingServices.Modeling.ModelEntity::.ctor()
0x1284  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x1289  stloc.0
0x128a  br       loc_1391
0x128f  newobj   instance void Microsoft.ReportingServices.Modeling.ModelFieldFolder::.ctor()
0x1294  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x1299  stloc.0
0x129a  br       loc_1391
0x129f  newobj   instance void Microsoft.ReportingServices.Modeling.ModelAttribute::.ctor()
0x12a4  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x12a9  stloc.0
0x12aa  br       loc_1391
0x12af  newobj   instance void Microsoft.ReportingServices.Modeling.ModelRole::.ctor()
0x12b4  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x12b9  stloc.0
0x12ba  br       loc_1391
0x12bf  newobj   instance void Microsoft.ReportingServices.Modeling.EntityInheritance::.ctor()
0x12c4  stloc.0
0x12c5  br       loc_1391
0x12ca  newobj   instance void Microsoft.ReportingServices.Modeling.AttributeReference::.ctor()
0x12cf  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x12d4  stloc.0
0x12d5  br       loc_1391
0x12da  newobj   instance void Microsoft.ReportingServices.Modeling.SortAttribute::.ctor()
0x12df  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x12e4  stloc.0
0x12e5  br       loc_1391
0x12ea  newobj   instance void Microsoft.ReportingServices.Modeling.TableBinding::.ctor()
0x12ef  stloc.0
0x12f0  br       loc_1391
0x12f5  newobj   instance void Microsoft.ReportingServices.Modeling.ColumnBinding::.ctor()
0x12fa  stloc.0
0x12fb  br       loc_1391
0x1300  newobj   instance void Microsoft.ReportingServices.Modeling.RelationBinding::.ctor()
0x1305  stloc.0
0x1306  br       loc_1391
0x130b  call     class Microsoft.ReportingServices.Modeling.DsvColumn Microsoft.ReportingServices.Modeling.DsvColumn::FromBinary()
0x1310  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x1315  stloc.0
0x1316  br.s     loc_1391
0x1318  call     class Microsoft.ReportingServices.Modeling.DsvColumnCollection Microsoft.ReportingServices.Modeling.DsvColumnCollection::FromBinary()
0x131d  stloc.0
0x131e  br.s     loc_1391
0x1320  call     class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.DsvTable::FromBinary()
0x1325  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x132a  stloc.0
0x132b  br.s     loc_1391
0x132d  call     class Microsoft.ReportingServices.Modeling.DsvRelation Microsoft.ReportingServices.Modeling.DsvRelation::FromBinary()
0x1332  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x1337  stloc.0
0x1338  br.s     loc_1391
0x133a  call     class Microsoft.ReportingServices.Modeling.DsvForeignKeyConstraint Microsoft.ReportingServices.Modeling.DsvForeignKeyConstraint::FromBinary()
0x133f  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x1344  stloc.0
0x1345  br.s     loc_1391
0x1347  call     class Microsoft.ReportingServices.Modeling.DsvUniqueConstraint Microsoft.ReportingServices.Modeling.DsvUniqueConstraint::FromBinary()
0x134c  call     class RefHelper RefHelper::CreateForDeserialization(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable obj)
0x1351  stloc.0
0x1352  br.s     loc_1391
0x1354  call     class Microsoft.ReportingServices.Modeling.DsvConstraintCollection Microsoft.ReportingServices.Modeling.DsvConstraintCollection::FromBinary()
0x1359  stloc.0
0x135a  br.s     loc_1391
0x135c  call     class Microsoft.ReportingServices.Modeling.DsvRelationCollection Microsoft.ReportingServices.Modeling.DsvRelationCollection::FromBinary()
0x1361  stloc.0
0x1362  br.s     loc_1391
0x1364  call     class Microsoft.ReportingServices.Modeling.DsvTableCollection Microsoft.ReportingServices.Modeling.DsvTableCollection::FromBinary()
0x1369  stloc.0
0x136a  br.s     loc_1391
0x136c  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable Microsoft.ReportingServices.Modeling.DataSourceView::CreateDsvSchemaPersistable()
0x1371  stloc.0
0x1372  br.s     loc_1391
0x1374  ldstr    aUnexpectedObje// "Unexpected object type: "
0x1379  ldarga.s 1
0x137b  constrained. Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType
0x1381  callvirt instance string [mscorlib]System.Object::ToString()
0x1386  call     string [mscorlib]System.String::Concat(string, string)
0x138b  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1390  throw
0x1391  ldloc.0
0x1392  ldarg.2
0x1393  ldobj    Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader
0x1398  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Deserialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader reader)
0x139d  ldloc.0
0x139e  ret
```
