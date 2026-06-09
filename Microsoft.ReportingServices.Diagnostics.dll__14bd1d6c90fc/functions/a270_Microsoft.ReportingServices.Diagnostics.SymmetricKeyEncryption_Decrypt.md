# Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::Decrypt

- ea: `0xa270`
- end: `0xa31a`
- name: `Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::Decrypt`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xa270`
- `0xa320`
- `0xa330`

## pseudocode

```c

```

## disassembly

```asm
0xa270  ldarg.1
0xa271  brtrue.s loc_A275
0xa273  ldnull
0xa274  ret
0xa275  nop
0xa276  call     class [mscorlib]System.Threading.ReaderWriterLock Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_RWLock()
0xa27b  ldc.i4.m1
0xa27c  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::AcquireReaderLock(int32)
0xa281  call     void Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ThrowIfNotInitialized()
0xa286  ldsfld   class [ReportingServicesNativeClient]RSManagedCrypto.RSCrypto Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::_crypto
0xa28b  ldarg.1
0xa28c  ldarg.2
0xa28d  callvirt instance unsigned int8[] [ReportingServicesNativeClient]RSManagedCrypto.RSCrypto::DecryptData(unsigned int8[], bool)
0xa292  stloc.0
0xa293  leave    loc_A318
0xa298  stloc.1
0xa299  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0xa29e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0xa2a3  brfalse.s loc_A2C7
0xa2a5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0xa2aa  ldc.i4.1
0xa2ab  ldstr    aDecryptionFail// "Decryption failed, Current user: {0} : "...
0xa2b0  ldc.i4.2
0xa2b1  newarr   [mscorlib]System.Object
0xa2b6  dup
0xa2b7  ldc.i4.0
0xa2b8  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserUtil::GetWindowsIdentityName()
0xa2bd  stelem.ref
0xa2be  dup
0xa2bf  ldc.i4.1
0xa2c0  ldloc.1
0xa2c1  stelem.ref
0xa2c2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xa2c7  ldloc.1
0xa2c8  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0xa2cd  ldc.i4   0x80090005
0xa2d2  bne.un.s loc_A2DA
0xa2d4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CannotValidateEncryptedDataException::.ctor()
0xa2d9  throw
0xa2da  rethrow
0xa2dc  stloc.2
0xa2dd  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0xa2e2  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0xa2e7  brfalse.s loc_A30B
0xa2e9  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0xa2ee  ldc.i4.1
0xa2ef  ldstr    aDecryptionFail// "Decryption failed, Current user: {0} : "...
0xa2f4  ldc.i4.2
0xa2f5  newarr   [mscorlib]System.Object
0xa2fa  dup
0xa2fb  ldc.i4.0
0xa2fc  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserUtil::GetWindowsIdentityName()
0xa301  stelem.ref
0xa302  dup
0xa303  ldc.i4.1
0xa304  ldloc.2
0xa305  stelem.ref
0xa306  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xa30b  rethrow
0xa30d  call     class [mscorlib]System.Threading.ReaderWriterLock Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_RWLock()
0xa312  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::ReleaseReaderLock()
0xa317  endfinally
0xa318  ldloc.0
0xa319  ret
```
