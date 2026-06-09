# Microsoft.ReportingServices.Library.ConnectionManager::SetNewSymmetricKey

- ea: `0x34c0`
- end: `0x3591`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::SetNewSymmetricKey`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3420`

## callees

- `0x2860`
- `0x34c0`
- `0x3710`

## string_xrefs

- `0x3527`: `NT Service is self activating using 1024 bit key but it already has a symmetric key`
- `0x356f`: `Keys table updated. Now importing symmetric key`

## pseudocode

```c

```

## disassembly

```asm
0x34c0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x34c5  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x34ca  brfalse.s loc_34DC
0x34cc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x34d1  ldc.i4.3
0x34d2  ldstr    aImportingExist// "Importing existing encryption key"
0x34d7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x34dc  ldarg.2
0x34dd  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::SetSymmetricKeyFromPublicKeyEncryptedBlob(unsigned int8[])
0x34e2  leave    loc_3590
0x34e7  stloc.0
0x34e8  ldloc.0
0x34e9  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x34ee  ldc.i4   0x80090005
0x34f3  bne.un   loc_3587
0x34f8  ldnull
0x34f9  stloc.1
0x34fa  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x34ff  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x3504  brfalse.s loc_3516
0x3506  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x350b  ldc.i4.3
0x350c  ldstr    aImportingExist_0// "Importing existing encryption key using"...
0x3511  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x3516  ldarg.2
0x3517  ldarg.3
0x3518  call     unsigned int8[] [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ReencryptSymmetricKey(unsigned int8[], unsigned int8[])
0x351d  stloc.1
0x351e  ldloc.1
0x351f  brtrue.s loc_3531
0x3521  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3526  ldc.i4.0
0x3527  ldstr    aNtServiceIsSel_0// "NT Service is self activating using 102"...
0x352c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x3531  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3536  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x353b  brfalse.s loc_354D
0x353d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3542  ldc.i4.3
0x3543  ldstr    aUpdatingSymmet// "Updating symmetric key in Keys table"
0x3548  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x354d  ldarg.s  4
0x354f  ldarg.1
0x3550  ldloc.1
0x3551  ldarg.3
0x3552  callvirt instance void Microsoft.ReportingServices.Library.KeyStorage::SetKeysForInstallation(valuetype [mscorlib]System.Guid installationID, unsigned int8[] symmetricKey, unsigned int8[] publicKey)
0x3557  ldarg.0
0x3558  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0x355d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3562  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x3567  brfalse.s loc_3579
0x3569  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x356e  ldc.i4.3
0x356f  ldstr    aKeysTableUpdat// "Keys table updated. Now importing symme"...
0x3574  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x3579  ldloc.1
0x357a  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::SetPublicKeyEncryptedSymmetricKey(unsigned int8[])
0x357f  leave.s  loc_358E
0x3581  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CannotValidateEncryptedDataException::.ctor(class [mscorlib]System.Exception)
0x3586  throw
0x3587  ldloc.0
0x3588  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CannotValidateEncryptedDataException::.ctor(class [mscorlib]System.Exception)
0x358d  throw
0x358e  leave.s  loc_3590
0x3590  ret
```
