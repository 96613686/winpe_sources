# Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ReleaseWriterLock

- ea: `0xa440`
- end: `0xa44b`
- name: `Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ReleaseWriterLock`
- size: `11`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa3b0`
- `0xa3e0`
- `0xa4e0`

## callees

- `0xa330`

## pseudocode

```c

```

## disassembly

```asm
0xa440  call     class [mscorlib]System.Threading.ReaderWriterLock Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_RWLock()
0xa445  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::ReleaseWriterLock()
0xa44a  ret
```
