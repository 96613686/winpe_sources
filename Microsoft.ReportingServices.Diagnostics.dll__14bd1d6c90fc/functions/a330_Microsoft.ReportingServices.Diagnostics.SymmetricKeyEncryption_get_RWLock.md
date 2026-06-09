# Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_RWLock

- ea: `0xa330`
- end: `0xa336`
- name: `Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_RWLock`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xa1e0`
- `0xa270`
- `0xa410`
- `0xa440`
- `0xa500`

## pseudocode

```c

```

## disassembly

```asm
0xa330  ldsfld   class [mscorlib]System.Threading.ReaderWriterLock Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::_rwLock
0xa335  ret
```
