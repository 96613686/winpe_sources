# Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_FullyQualifiedUserName

- ea: `0x3830`
- end: `0x3856`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_FullyQualifiedUserName`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2500`
- `0x3910`

## callees

- `0x3830`

## pseudocode

```c

```

## disassembly

```asm
0x3830  ldarg.0
0x3831  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::m_Domain
0x3836  brtrue.s loc_383F
0x3838  ldarg.0
0x3839  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::m_UserName
0x383e  ret
0x383f  ldarg.0
0x3840  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::m_Domain
0x3845  ldstr    asc_55E6// "\\"
0x384a  ldarg.0
0x384b  ldfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::m_UserName
0x3850  call     string [mscorlib]System.String::Concat(string, string, string)
0x3855  ret
```
