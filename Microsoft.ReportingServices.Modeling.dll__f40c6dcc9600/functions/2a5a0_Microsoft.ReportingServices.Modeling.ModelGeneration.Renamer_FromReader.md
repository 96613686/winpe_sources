# Microsoft.ReportingServices.Modeling.ModelGeneration.Renamer::FromReader

- ea: `0x2a5a0`
- end: `0x2a5b4`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.Renamer::FromReader`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x29f80`

## callees

- `0xab10`
- `0x2a4c0`

## string_xrefs

- `0x2a5a7`: `renamer`

## pseudocode

```c

```

## disassembly

```asm
0x2a5a0  newobj   instance void Microsoft.ReportingServices.Modeling.ModelGeneration.Renamer::.ctor()
0x2a5a5  stloc.0
0x2a5a6  ldarg.0
0x2a5a7  ldstr    aRenamer// "renamer"
0x2a5ac  ldloc.0
0x2a5ad  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObject(string elementName, class Microsoft.ReportingServices.Modeling.IXmlLoadable obj)
0x2a5b2  ldloc.0
0x2a5b3  ret
```
