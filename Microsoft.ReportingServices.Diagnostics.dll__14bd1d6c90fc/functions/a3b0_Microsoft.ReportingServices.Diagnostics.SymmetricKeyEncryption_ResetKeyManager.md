# Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ResetKeyManager

- ea: `0xa3b0`
- end: `0xa3d2`
- name: `Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ResetKeyManager`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xa4e0`

## callees

- `0xa3b0`
- `0xa410`
- `0xa440`

## pseudocode

```c

```

## disassembly

```asm
0xa3b0  call     void Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::AcquireWriterLock()
0xa3b5  ldsfld   class [ReportingServicesNativeClient]RSManagedCrypto.RSCrypto Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::_crypto
0xa3ba  callvirt instance void [ReportingServicesNativeClient]RSManagedCrypto.RSCrypto::Dispose()
0xa3bf  newobj   instance void [ReportingServicesNativeClient]RSManagedCrypto.RSCrypto::.ctor()
0xa3c4  stsfld   class [ReportingServicesNativeClient]RSManagedCrypto.RSCrypto Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::_crypto
0xa3c9  leave.s  loc_A3D1
0xa3cb  call     void Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ReleaseWriterLock()
0xa3d0  endfinally
0xa3d1  ret
```
