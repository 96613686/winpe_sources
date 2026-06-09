# Microsoft.ReportingServices.Diagnostics.SkuResources::ThrowOperationNotSupportedException

- ea: `0xcec0`
- end: `0xcec7`
- name: `Microsoft.ReportingServices.Diagnostics.SkuResources::ThrowOperationNotSupportedException`
- size: `7`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xc840`
- `0xc850`
- `0xc860`

## callees

- `0xced0`

## pseudocode

```c

```

## disassembly

```asm
0xcec0  ldarg.0
0xcec1  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.OperationNotSupportedException Microsoft.ReportingServices.Diagnostics.SkuResources::GetOperationNotSupportedException(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures feature)
0xcec6  throw
```
