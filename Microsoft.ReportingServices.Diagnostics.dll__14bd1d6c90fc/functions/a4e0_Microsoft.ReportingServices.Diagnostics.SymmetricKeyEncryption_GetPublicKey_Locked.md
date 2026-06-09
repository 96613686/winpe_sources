# Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::GetPublicKey_Locked

- ea: `0xa4e0`
- end: `0xa4ff`
- name: `Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::GetPublicKey_Locked`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xa450`
- `0xa490`

## callees

- `0xa3b0`
- `0xa410`
- `0xa440`
- `0xa4e0`

## pseudocode

```c

```

## disassembly

```asm
0xa4e0  call     void Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::AcquireWriterLock()
0xa4e5  call     void Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ResetKeyManager()
0xa4ea  ldsfld   class [ReportingServicesNativeClient]RSManagedCrypto.RSCrypto Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::_crypto
0xa4ef  callvirt instance unsigned int8[] [ReportingServicesNativeClient]RSManagedCrypto.RSCrypto::ExportPublicKey()
0xa4f4  stloc.0
0xa4f5  leave.s  loc_A4FD
0xa4f7  call     void Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ReleaseWriterLock()
0xa4fc  endfinally
0xa4fd  ldloc.0
0xa4fe  ret
```
