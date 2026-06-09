# ClSerializerHost::GetExtensionNamespaces

- ea: `0x1e10`
- end: `0x1e3d`
- name: `ClSerializerHost::GetExtensionNamespaces`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x1e1d`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition`
- `0x1e30`: `http://schemas.microsoft.com/SQLServer/reporting/reportdesigner`

## pseudocode

```c

```

## disassembly

```asm
0x1e10  ldc.i4.2
0x1e11  newarr   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.ExtensionNamespace
0x1e16  dup
0x1e17  ldc.i4.0
0x1e18  ldstr    aRdl// "rdl"
0x1e1d  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sqlserver/"...
0x1e22  ldc.i4.0
0x1e23  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.ExtensionNamespace::.ctor(string, string, bool)
0x1e28  stelem.ref
0x1e29  dup
0x1e2a  ldc.i4.1
0x1e2b  ldstr    aRd// "rd"
0x1e30  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/SQLServer/"...
0x1e35  ldc.i4.0
0x1e36  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.ExtensionNamespace::.ctor(string, string, bool)
0x1e3b  stelem.ref
0x1e3c  ret
```
