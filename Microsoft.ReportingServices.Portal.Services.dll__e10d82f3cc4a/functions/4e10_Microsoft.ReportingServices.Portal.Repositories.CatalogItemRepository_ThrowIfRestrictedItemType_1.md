# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType_1

- ea: `0x4e10`
- end: `0x4e2a`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType_1`
- size: `26`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`
- `0x2a20`
- `0x2c20`
- `0x3830`
- `0x4e00`

## callees

- `0x4d90`
- `0x4e10`

## pseudocode

```c

```

## disassembly

```asm
0x4e10  ldarg.0
0x4e11  ldarg.1
0x4e12  call     instance bool Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::IsRestrictedItemType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType type)
0x4e17  brfalse.s loc_4E29
0x4e19  ldarg.2
0x4e1a  dup
0x4e1b  brtrue.s loc_4E23
0x4e1d  pop
0x4e1e  ldsfld   string [mscorlib]System.String::Empty
0x4e23  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RestrictedItemException::.ctor(string)
0x4e28  throw
0x4e29  ret
```
