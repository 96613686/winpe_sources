# Microsoft.ReportingServices.Modeling.FunctionInfo::CreateFunctionInfos

- ea: `0x1f530`
- end: `0x20dba`
- name: `Microsoft.ReportingServices.Modeling.FunctionInfo::CreateFunctionInfos`
- size: `6282`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x217b0`

## callees

- `0x20dc0`
- `0x20de0`
- `0x20e00`
- `0x20e20`
- `0x20e70`
- `0x20ec0`
- `0x20f10`
- `0x37620`
- `0x37640`

## pseudocode

```c

```

## disassembly

```asm
0x1f530  newobj   instance void FunctionInfoDictionary::.ctor()
0x1f535  stloc.0
0x1f536  ldloc.0
0x1f537  ldc.i4.3
0x1f538  newarr   Microsoft.ReportingServices.Modeling.FunctionInfo
0x1f53d  dup
0x1f53e  ldc.i4.0
0x1f53f  ldc.i4.1
0x1f540  ldc.i4.0
0x1f541  ldc.i4.1
0x1f542  ldc.i4.1
0x1f543  ldc.i4.2
0x1f544  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f549  dup
0x1f54a  ldc.i4.0
0x1f54b  ldc.i4.1
0x1f54c  stelem.i1
0x1f54d  dup
0x1f54e  ldc.i4.1
0x1f54f  ldc.i4.1
0x1f550  stelem.i1
0x1f551  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f556  stelem.ref
0x1f557  dup
0x1f558  ldc.i4.1
0x1f559  ldc.i4.2
0x1f55a  ldc.i4.0
0x1f55b  ldc.i4.2
0x1f55c  ldc.i4.1
0x1f55d  ldc.i4.2
0x1f55e  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f563  dup
0x1f564  ldc.i4.0
0x1f565  ldc.i4.2
0x1f566  stelem.i1
0x1f567  dup
0x1f568  ldc.i4.1
0x1f569  ldc.i4.2
0x1f56a  stelem.i1
0x1f56b  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f570  stelem.ref
0x1f571  dup
0x1f572  ldc.i4.2
0x1f573  ldc.i4.3
0x1f574  ldc.i4.0
0x1f575  ldc.i4.3
0x1f576  ldc.i4.1
0x1f577  ldc.i4.2
0x1f578  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f57d  dup
0x1f57e  ldc.i4.0
0x1f57f  ldc.i4.3
0x1f580  stelem.i1
0x1f581  dup
0x1f582  ldc.i4.1
0x1f583  ldc.i4.3
0x1f584  stelem.i1
0x1f585  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f58a  stelem.ref
0x1f58b  callvirt instance void FunctionInfoDictionary::AddGroup(class Microsoft.ReportingServices.Modeling.FunctionInfo[] functionInfos)
0x1f590  ldloc.0
0x1f591  ldc.i4.3
0x1f592  newarr   Microsoft.ReportingServices.Modeling.FunctionInfo
0x1f597  dup
0x1f598  ldc.i4.0
0x1f599  ldc.i4.4
0x1f59a  ldc.i4.1
0x1f59b  ldc.i4.1
0x1f59c  ldc.i4.1
0x1f59d  ldc.i4.2
0x1f59e  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f5a3  dup
0x1f5a4  ldc.i4.0
0x1f5a5  ldc.i4.1
0x1f5a6  stelem.i1
0x1f5a7  dup
0x1f5a8  ldc.i4.1
0x1f5a9  ldc.i4.1
0x1f5aa  stelem.i1
0x1f5ab  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f5b0  stelem.ref
0x1f5b1  dup
0x1f5b2  ldc.i4.1
0x1f5b3  ldc.i4.5
0x1f5b4  ldc.i4.1
0x1f5b5  ldc.i4.2
0x1f5b6  ldc.i4.1
0x1f5b7  ldc.i4.2
0x1f5b8  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f5bd  dup
0x1f5be  ldc.i4.0
0x1f5bf  ldc.i4.2
0x1f5c0  stelem.i1
0x1f5c1  dup
0x1f5c2  ldc.i4.1
0x1f5c3  ldc.i4.2
0x1f5c4  stelem.i1
0x1f5c5  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f5ca  stelem.ref
0x1f5cb  dup
0x1f5cc  ldc.i4.2
0x1f5cd  ldc.i4.6
0x1f5ce  ldc.i4.1
0x1f5cf  ldc.i4.3
0x1f5d0  ldc.i4.1
0x1f5d1  ldc.i4.2
0x1f5d2  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f5d7  dup
0x1f5d8  ldc.i4.0
0x1f5d9  ldc.i4.3
0x1f5da  stelem.i1
0x1f5db  dup
0x1f5dc  ldc.i4.1
0x1f5dd  ldc.i4.3
0x1f5de  stelem.i1
0x1f5df  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f5e4  stelem.ref
0x1f5e5  callvirt instance void FunctionInfoDictionary::AddGroup(class Microsoft.ReportingServices.Modeling.FunctionInfo[] functionInfos)
0x1f5ea  ldloc.0
0x1f5eb  ldc.i4.3
0x1f5ec  newarr   Microsoft.ReportingServices.Modeling.FunctionInfo
0x1f5f1  dup
0x1f5f2  ldc.i4.0
0x1f5f3  ldc.i4.7
0x1f5f4  ldc.i4.2
0x1f5f5  ldc.i4.1
0x1f5f6  ldc.i4.1
0x1f5f7  ldc.i4.2
0x1f5f8  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f5fd  dup
0x1f5fe  ldc.i4.0
0x1f5ff  ldc.i4.1
0x1f600  stelem.i1
0x1f601  dup
0x1f602  ldc.i4.1
0x1f603  ldc.i4.1
0x1f604  stelem.i1
0x1f605  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f60a  stelem.ref
0x1f60b  dup
0x1f60c  ldc.i4.1
0x1f60d  ldc.i4.8
0x1f60e  ldc.i4.2
0x1f60f  ldc.i4.2
0x1f610  ldc.i4.1
0x1f611  ldc.i4.2
0x1f612  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f617  dup
0x1f618  ldc.i4.0
0x1f619  ldc.i4.2
0x1f61a  stelem.i1
0x1f61b  dup
0x1f61c  ldc.i4.1
0x1f61d  ldc.i4.2
0x1f61e  stelem.i1
0x1f61f  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f624  stelem.ref
0x1f625  dup
0x1f626  ldc.i4.2
0x1f627  ldc.i4.s 9
0x1f629  ldc.i4.2
0x1f62a  ldc.i4.3
0x1f62b  ldc.i4.1
0x1f62c  ldc.i4.2
0x1f62d  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f632  dup
0x1f633  ldc.i4.0
0x1f634  ldc.i4.3
0x1f635  stelem.i1
0x1f636  dup
0x1f637  ldc.i4.1
0x1f638  ldc.i4.3
0x1f639  stelem.i1
0x1f63a  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f63f  stelem.ref
0x1f640  callvirt instance void FunctionInfoDictionary::AddGroup(class Microsoft.ReportingServices.Modeling.FunctionInfo[] functionInfos)
0x1f645  ldloc.0
0x1f646  ldc.i4.2
0x1f647  newarr   Microsoft.ReportingServices.Modeling.FunctionInfo
0x1f64c  dup
0x1f64d  ldc.i4.0
0x1f64e  ldc.i4.s 0xA
0x1f650  ldc.i4.3
0x1f651  ldc.i4.2
0x1f652  ldc.i4.1
0x1f653  ldc.i4.2
0x1f654  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f659  dup
0x1f65a  ldc.i4.0
0x1f65b  ldc.i4.2
0x1f65c  stelem.i1
0x1f65d  dup
0x1f65e  ldc.i4.1
0x1f65f  ldc.i4.2
0x1f660  stelem.i1
0x1f661  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f666  stelem.ref
0x1f667  dup
0x1f668  ldc.i4.1
0x1f669  ldc.i4.s 0xB
0x1f66b  ldc.i4.3
0x1f66c  ldc.i4.3
0x1f66d  ldc.i4.1
0x1f66e  ldc.i4.2
0x1f66f  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f674  dup
0x1f675  ldc.i4.0
0x1f676  ldc.i4.3
0x1f677  stelem.i1
0x1f678  dup
0x1f679  ldc.i4.1
0x1f67a  ldc.i4.3
0x1f67b  stelem.i1
0x1f67c  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f681  stelem.ref
0x1f682  callvirt instance void FunctionInfoDictionary::AddGroup(class Microsoft.ReportingServices.Modeling.FunctionInfo[] functionInfos)
0x1f687  ldloc.0
0x1f688  ldc.i4.3
0x1f689  newarr   Microsoft.ReportingServices.Modeling.FunctionInfo
0x1f68e  dup
0x1f68f  ldc.i4.0
0x1f690  ldc.i4.s 0xC
0x1f692  ldc.i4.4
0x1f693  ldc.i4.1
0x1f694  ldc.i4.1
0x1f695  ldc.i4.1
0x1f696  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f69b  dup
0x1f69c  ldc.i4.0
0x1f69d  ldc.i4.1
0x1f69e  stelem.i1
0x1f69f  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f6a4  stelem.ref
0x1f6a5  dup
0x1f6a6  ldc.i4.1
0x1f6a7  ldc.i4.s 0xD
0x1f6a9  ldc.i4.4
0x1f6aa  ldc.i4.2
0x1f6ab  ldc.i4.1
0x1f6ac  ldc.i4.1
0x1f6ad  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f6b2  dup
0x1f6b3  ldc.i4.0
0x1f6b4  ldc.i4.2
0x1f6b5  stelem.i1
0x1f6b6  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f6bb  stelem.ref
0x1f6bc  dup
0x1f6bd  ldc.i4.2
0x1f6be  ldc.i4.s 0xE
0x1f6c0  ldc.i4.4
0x1f6c1  ldc.i4.3
0x1f6c2  ldc.i4.1
0x1f6c3  ldc.i4.1
0x1f6c4  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f6c9  dup
0x1f6ca  ldc.i4.0
0x1f6cb  ldc.i4.3
0x1f6cc  stelem.i1
0x1f6cd  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f6d2  stelem.ref
0x1f6d3  callvirt instance void FunctionInfoDictionary::AddGroup(class Microsoft.ReportingServices.Modeling.FunctionInfo[] functionInfos)
0x1f6d8  ldloc.0
0x1f6d9  ldc.i4.1
0x1f6da  newarr   Microsoft.ReportingServices.Modeling.FunctionInfo
0x1f6df  dup
0x1f6e0  ldc.i4.0
0x1f6e1  ldc.i4.s 0xF
0x1f6e3  ldc.i4.5
0x1f6e4  ldc.i4.1
0x1f6e5  ldc.i4.1
0x1f6e6  ldc.i4.2
0x1f6e7  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f6ec  dup
0x1f6ed  ldc.i4.0
0x1f6ee  ldc.i4.1
0x1f6ef  stelem.i1
0x1f6f0  dup
0x1f6f1  ldc.i4.1
0x1f6f2  ldc.i4.1
0x1f6f3  stelem.i1
0x1f6f4  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::CreateScalar(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.DataType returnDataType, bool returnNullable, valuetype Microsoft.ReportingServices.Modeling.DataType[] argumentDataTypes)
0x1f6f9  stelem.ref
0x1f6fa  callvirt instance void FunctionInfoDictionary::AddGroup(class Microsoft.ReportingServices.Modeling.FunctionInfo[] functionInfos)
0x1f6ff  ldloc.0
0x1f700  ldc.i4.3
0x1f701  newarr   Microsoft.ReportingServices.Modeling.FunctionInfo
0x1f706  dup
0x1f707  ldc.i4.0
0x1f708  ldc.i4.s 0x10
0x1f70a  ldc.i4.6
0x1f70b  ldc.i4.1
0x1f70c  ldc.i4.1
0x1f70d  ldc.i4.2
0x1f70e  newarr   Microsoft.ReportingServices.Modeling.DataType
0x1f713  dup
0x1f714  ldc.i4.0
0x1f715  ldc.i4.1
0x1f716  stelem.i1
0x1f717  dup
  ... truncated ...
```
