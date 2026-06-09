# Microsoft.ReportingServices.Modeling.ModelItem::get_ID

- ea: `0x139d0`
- end: `0x139dd`
- name: `Microsoft.ReportingServices.Modeling.ModelItem::get_ID`
- size: `13`
- prototype: ``
- caller_count: `38`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb530`
- `0xf1b0`
- `0xfa30`
- `0x118c0`
- `0x11a60`
- `0x126f0`
- `0x12930`
- `0x13b80`
- `0x14270`
- `0x14390`
- `0x144c0`
- `0x144e0`
- `0x14530`
- `0x14690`
- `0x14930`
- `0x14a30`
- `0x15b40`
- `0x15e40`
- `0x173d0`
- `0x17400`
- `0x17440`
- `0x174d0`
- `0x17680`
- `0x176e0`
- `0x17880`
- `0x1b600`
- `0x1b8e0`
- `0x1bcc0`
- `0x1bdd0`
- `0x1ee70`
- `0x1f020`
- `0x21f00`
- `0x22530`
- `0x270a0`
- `0x28ea0`
- `0x29070`
- `0x29250`
- `0x34820`

## callees

- `0x14630`

## pseudocode

```c

```

## disassembly

```asm
0x139d0  ldarg.0
0x139d1  call     instance void Microsoft.ReportingServices.Modeling.ModelItem::InitializeID()
0x139d6  ldarg.0
0x139d7  ldfld    valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::__id
0x139dc  ret
```
