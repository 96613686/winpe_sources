# Microsoft.ReportingServices.Library.ConnectionManager::GetSymmetricKey

- ea: `0x3420`
- end: `0x34bc`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::GetSymmetricKey`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3ac0`

## callees

- `0x2860`
- `0x2d40`
- `0x2f00`
- `0x3420`
- `0x34c0`
- `0x3710`

## string_xrefs

- `0x3443`: `NT Service self activating`
- `0x3467`: `NT Service is self activating but it already has a symmetric key`
- `0x3495`: `NT Service not activated: can be added to scale out group with config tool`

## pseudocode

```c

```

## disassembly

```asm
0x3420  ldarg.1
0x3421  ldarg.2
0x3422  ldarg.3
0x3423  ldloca.s 0
0x3425  callvirt instance int32 Microsoft.ReportingServices.Library.KeyStorage::AnnouncePublicKeyOrGetSymmetricKey(valuetype [mscorlib]System.Guid installationID, unsigned int8[] publicKey, [out] unsigned int8[]& symmetricKey)
0x342a  stloc.1
0x342b  ldloc.0
0x342c  brtrue.s loc_34AB
0x342e  ldloc.1
0x342f  brtrue.s loc_3483
0x3431  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3436  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x343b  brfalse.s loc_344D
0x343d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3442  ldc.i4.3
0x3443  ldstr    aNtServiceSelfA// "NT Service self activating"
0x3448  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x344d  call     unsigned int8[] [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::CreateSymmetricKey()
0x3452  stloc.2
0x3453  ldloc.2
0x3454  brfalse.s loc_3461
0x3456  ldarg.1
0x3457  ldarg.2
0x3458  ldloc.2
0x3459  ldarg.3
0x345a  callvirt instance void Microsoft.ReportingServices.Library.KeyStorage::SetKeysForInstallation(valuetype [mscorlib]System.Guid installationID, unsigned int8[] symmetricKey, unsigned int8[] publicKey)
0x345f  br.s     loc_3471
0x3461  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3466  ldc.i4.0
0x3467  ldstr    aNtServiceIsSel// "NT Service is self activating but it al"...
0x346c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x3471  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x3476  ldc.i4.s 0x7C
0x3478  call     T0x2B000001
0x347d  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteInformation(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event, object[])
0x3482  ret
0x3483  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3488  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x348d  brfalse.s loc_349F
0x348f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3494  ldc.i4.3
0x3495  ldstr    aNtServiceNotAc// "NT Service not activated: can be added "...
0x349a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x349f  ldarg.0
0x34a0  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0x34a5  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CannotValidateEncryptedDataException::.ctor()
0x34aa  throw
0x34ab  ldarg.1
0x34ac  callvirt instance void Microsoft.ReportingServices.Library.KeyStorage::ValidateScaleoutEdition()
0x34b1  ldarg.0
0x34b2  ldarg.2
0x34b3  ldloc.0
0x34b4  ldarg.3
0x34b5  ldarg.1
0x34b6  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::SetNewSymmetricKey(valuetype [mscorlib]System.Guid installationID, unsigned int8[] symmetricKey, unsigned int8[] publicKey, class Microsoft.ReportingServices.Library.KeyStorage storage)
0x34bb  ret
```
