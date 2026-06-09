# Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::EncryptInternal

- ea: `0xa1e0`
- end: `0xa265`
- name: `Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::EncryptInternal`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xa1e0`
- `0xa320`
- `0xa330`

## pseudocode

```c

```

## disassembly

```asm
0xa1e0  ldarg.1
0xa1e1  brtrue.s loc_A1E5
0xa1e3  ldnull
0xa1e4  ret
0xa1e5  nop
0xa1e6  call     class [mscorlib]System.Threading.ReaderWriterLock Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_RWLock()
0xa1eb  ldc.i4.m1
0xa1ec  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::AcquireReaderLock(int32)
0xa1f1  call     void Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ThrowIfNotInitialized()
0xa1f6  ldsfld   class [ReportingServicesNativeClient]RSManagedCrypto.RSCrypto Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::_crypto
0xa1fb  ldarg.1
0xa1fc  callvirt instance unsigned int8[] [ReportingServicesNativeClient]RSManagedCrypto.RSCrypto::EncryptData(unsigned int8[])
0xa201  stloc.0
0xa202  leave.s  loc_A263
0xa204  stloc.1
0xa205  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0xa20a  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0xa20f  brfalse.s loc_A22C
0xa211  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0xa216  ldc.i4.1
0xa217  ldstr    aProtectdataFai// "ProtectData failed: "
0xa21c  ldloc.1
0xa21d  callvirt instance string [mscorlib]System.Object::ToString()
0xa222  call     string [mscorlib]System.String::Concat(string, string)
0xa227  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xa22c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0xa231  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0xa236  brfalse.s loc_A256
0xa238  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0xa23d  ldc.i4.3
0xa23e  ldstr    aCurrentUser0// "Current user: {0}"
0xa243  ldc.i4.1
0xa244  newarr   [mscorlib]System.Object
0xa249  dup
0xa24a  ldc.i4.0
0xa24b  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserUtil::GetWindowsIdentityName()
0xa250  stelem.ref
0xa251  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xa256  rethrow
0xa258  call     class [mscorlib]System.Threading.ReaderWriterLock Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_RWLock()
0xa25d  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::ReleaseReaderLock()
0xa262  endfinally
0xa263  ldloc.0
0xa264  ret
```
