# Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ThrowIfNotInitialized

- ea: `0xa320`
- end: `0xa32e`
- name: `Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ThrowIfNotInitialized`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xa1e0`
- `0xa270`

## callees

- `0xa320`
- `0xa500`

## pseudocode

```c

```

## disassembly

```asm
0xa320  call     bool Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_IsInitialized()
0xa325  brtrue.s loc_A32D
0xa327  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CannotValidateEncryptedDataException::.ctor()
0xa32c  throw
0xa32d  ret
```
