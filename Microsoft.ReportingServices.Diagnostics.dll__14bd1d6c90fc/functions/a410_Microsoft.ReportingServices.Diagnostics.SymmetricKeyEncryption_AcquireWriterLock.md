# Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::AcquireWriterLock

- ea: `0xa410`
- end: `0xa435`
- name: `Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::AcquireWriterLock`
- size: `37`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xa3b0`
- `0xa3e0`
- `0xa4e0`

## callees

- `0xa330`
- `0xa410`

## pseudocode

```c

```

## disassembly

```asm
0xa410  call     class [mscorlib]System.Threading.ReaderWriterLock Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_RWLock()
0xa415  callvirt instance bool [mscorlib]System.Threading.ReaderWriterLock::get_IsReaderLockHeld()
0xa41a  brfalse.s loc_A429
0xa41c  call     class [mscorlib]System.Threading.ReaderWriterLock Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_RWLock()
0xa421  ldc.i4.m1
0xa422  callvirt instance valuetype [mscorlib]System.Threading.LockCookie [mscorlib]System.Threading.ReaderWriterLock::UpgradeToWriterLock(int32)
0xa427  pop
0xa428  ret
0xa429  call     class [mscorlib]System.Threading.ReaderWriterLock Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_RWLock()
0xa42e  ldc.i4.m1
0xa42f  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::AcquireWriterLock(int32)
0xa434  ret
```
