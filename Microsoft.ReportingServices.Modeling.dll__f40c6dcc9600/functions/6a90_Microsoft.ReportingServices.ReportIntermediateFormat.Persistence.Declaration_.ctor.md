# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::.ctor

- ea: `0x6a90`
- end: `0x6ab7`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::.ctor`
- size: `39`
- prototype: ``
- caller_count: `59`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x61a0`
- `0x6c00`
- `0x7110`
- `0x2e630`
- `0x2e760`
- `0x2e850`
- `0x2e970`
- `0x2ec20`
- `0x2ec80`
- `0x2ee00`
- `0x2ee60`
- `0x2f050`
- `0x2f430`
- `0x2fd20`
- `0x332b0`
- `0x33470`
- `0x337e0`
- `0x33840`
- `0x338a0`
- `0x33910`
- `0x33970`
- `0x339d0`
- `0x33a20`
- `0x33a70`
- `0x33c80`
- `0x33cd0`
- `0x33d20`
- `0x33e60`
- `0x33ef0`
- `0x342d0`
- `0x34660`
- `0x348a0`
- `0x36b10`
- `0x36d40`
- `0x36e30`
- `0x36e80`
- `0x36f90`
- `0x36ff0`
- `0x370b0`
- `0x37280`
- `0x372e0`
- `0x37340`
- `0x37460`
- `0x375d0`
- `0x3a660`
- `0x3a7d0`
- `0x3a8b0`
- `0x3a950`
- `0x3aa20`
- `0x3aae0`

## pseudocode

```c

```

## disassembly

```asm
0x6a90  ldarg.0
0x6a91  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo>::.ctor()
0x6a96  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo> Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::m_memberInfoList
0x6a9b  ldarg.0
0x6a9c  call     instance void [mscorlib]System.Object::.ctor()
0x6aa1  ldarg.0
0x6aa2  ldarg.1
0x6aa3  stfld    valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::m_type
0x6aa8  ldarg.0
0x6aa9  ldarg.2
0x6aaa  stfld    valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::m_baseType
0x6aaf  ldarg.0
0x6ab0  ldarg.3
0x6ab1  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo> Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::m_memberInfoList
0x6ab6  ret
```
