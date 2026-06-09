# Microsoft.ReportingServices.Library.KeyStorage::.ctor

- ea: `0x2850`
- end: `0x285e`
- name: `Microsoft.ReportingServices.Library.KeyStorage::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3ac0`

## callees

- `0x6a40`
- `0x6a50`

## pseudocode

```c

```

## disassembly

```asm
0x2850  ldarg.0
0x2851  call     instance void Microsoft.ReportingServices.Library.Storage::.ctor()
0x2856  ldarg.0
0x2857  ldarg.1
0x2858  callvirt instance void Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class Microsoft.ReportingServices.Library.ConnectionManager value)
0x285d  ret
```
