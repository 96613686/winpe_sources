# Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::get_CustomProperties

- ea: `0x9eb0`
- end: `0x9edd`
- name: `Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::get_CustomProperties`
- size: `45`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x9f40`
- `0x9fb0`
- `0x13920`
- `0x13f10`
- `0x17130`
- `0x17a30`
- `0x18d70`
- `0x19480`
- `0x234f0`

## callees

- `0x8d50`
- `0x97d0`
- `0x9cf0`
- `0x9eb0`

## string_xrefs

- `0x9ec0`: `Object is compiled and m_customProperties is null`

## pseudocode

```c

```

## disassembly

```asm
0x9eb0  ldarg.0
0x9eb1  ldfld    class Microsoft.ReportingServices.Modeling.CustomPropertyCollection Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::m_customProperties
0x9eb6  brtrue.s loc_9ED6
0x9eb8  ldarg.0
0x9eb9  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x9ebe  brfalse.s loc_9ECB
0x9ec0  ldstr    aObjectIsCompil// "Object is compiled and m_customProperti"...
0x9ec5  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x9eca  throw
0x9ecb  ldarg.0
0x9ecc  newobj   instance void Microsoft.ReportingServices.Modeling.CustomPropertyCollection::.ctor()
0x9ed1  stfld    class Microsoft.ReportingServices.Modeling.CustomPropertyCollection Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::m_customProperties
0x9ed6  ldarg.0
0x9ed7  ldfld    class Microsoft.ReportingServices.Modeling.CustomPropertyCollection Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::m_customProperties
0x9edc  ret
```
