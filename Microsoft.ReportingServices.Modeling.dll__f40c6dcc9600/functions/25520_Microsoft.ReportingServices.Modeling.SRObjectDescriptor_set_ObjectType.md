# Microsoft.ReportingServices.Modeling.SRObjectDescriptor::set_ObjectType

- ea: `0x25520`
- end: `0x2553b`
- name: `Microsoft.ReportingServices.Modeling.SRObjectDescriptor::set_ObjectType`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x254f0`
- `0x25590`

## callees

- `0x97d0`
- `0x25520`

## string_xrefs

- `0x25528`: `SRObjectDescriptor.ObjectType set to null/empty`

## pseudocode

```c

```

## disassembly

```asm
0x25520  ldarg.1
0x25521  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25526  brfalse.s loc_25533
0x25528  ldstr    aSrobjectdescri// "SRObjectDescriptor.ObjectType set to nu"...
0x2552d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x25532  throw
0x25533  ldarg.0
0x25534  ldarg.1
0x25535  stfld    string Microsoft.ReportingServices.Modeling.SRObjectDescriptor::__objectType
0x2553a  ret
```
