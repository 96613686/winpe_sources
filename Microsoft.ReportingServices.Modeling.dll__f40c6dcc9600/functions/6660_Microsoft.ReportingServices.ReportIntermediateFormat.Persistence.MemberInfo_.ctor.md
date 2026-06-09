# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::.ctor

- ea: `0x6660`
- end: `0x6695`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::.ctor`
- size: `53`
- prototype: ``
- caller_count: `28`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1440`
- `0x61a0`
- `0x6a20`
- `0x2e630`
- `0x2e760`
- `0x2e850`
- `0x2ec20`
- `0x2ee00`
- `0x2f050`
- `0x2f430`
- `0x2fd20`
- `0x332b0`
- `0x33470`
- `0x338a0`
- `0x33a70`
- `0x33d20`
- `0x342d0`
- `0x348a0`
- `0x36b10`
- `0x36e80`
- `0x370b0`
- `0x3a660`
- `0x3a8b0`
- `0x3aa20`
- `0x3ab50`
- `0x3abe0`
- `0x3ad50`
- `0x3af40`

## callees

- `0x6540`

## pseudocode

```c

```

## disassembly

```asm
0x6660  ldarg.0
0x6661  ldc.i4.1
0x6662  stfld    valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::m_token
0x6667  ldarg.0
0x6668  ldc.i4.1
0x6669  stfld    valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::m_type
0x666e  ldarg.0
0x666f  ldc.i4.1
0x6670  stfld    valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::m_containedType
0x6675  ldarg.0
0x6676  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Lifetime Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Lifetime::get_Unspecified()
0x667b  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Lifetime Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::m_lifetime
0x6680  ldarg.0
0x6681  call     instance void [mscorlib]System.Object::.ctor()
0x6686  ldarg.0
0x6687  ldarg.1
0x6688  stfld    valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::m_name
0x668d  ldarg.0
0x668e  ldarg.2
0x668f  stfld    valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::m_token
0x6694  ret
```
