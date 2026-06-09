# Microsoft.ReportingServices.Library.CatalogQuery::Run

- ea: `0x2290`
- end: `0x22c9`
- name: `Microsoft.ReportingServices.Library.CatalogQuery::Run`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x2190`
- `0x2240`
- `0x2270`
- `0x2290`
- `0x9200`

## pseudocode

```c

```

## disassembly

```asm
0x2290  ldarg.1
0x2291  brfalse.s loc_2299
0x2293  ldarg.1
0x2294  callvirt instance void Code::Invoke()
0x2299  ldarg.3
0x229a  brfalse.s loc_22A2
0x229c  ldarg.0
0x229d  call     instance void Microsoft.ReportingServices.Library.CatalogQuery::Commit()
0x22a2  leave.s  loc_22C8
0x22a4  pop
0x22a5  ldarg.3
0x22a6  brfalse.s loc_22AE
0x22a8  ldarg.0
0x22a9  call     instance void Microsoft.ReportingServices.Library.CatalogQuery::AbortTransaction()
0x22ae  ldarg.2
0x22af  brfalse.s loc_22B7
0x22b1  ldarg.2
0x22b2  callvirt instance void Code::Invoke()
0x22b7  leave.s  loc_22BC
0x22b9  pop
0x22ba  leave.s  loc_22BC
0x22bc  rethrow
0x22be  ldarg.3
0x22bf  brfalse.s loc_22C7
0x22c1  ldarg.0
0x22c2  call     instance void Microsoft.ReportingServices.Library.CatalogQuery::Close()
0x22c7  endfinally
0x22c8  ret
```
