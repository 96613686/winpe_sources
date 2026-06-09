# Microsoft.ReportingServices.Diagnostics.Encryption::Decrypt_1

- ea: `0x9f10`
- end: `0x9f4c`
- name: `Microsoft.ReportingServices.Diagnostics.Encryption::Decrypt_1`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x9ee0`

## callees

- `0x9cd0`
- `0x9ce0`
- `0x9cf0`
- `0x9f10`
- `0x9f50`

## pseudocode

```c

```

## disassembly

```asm
0x9f10  ldarg.1
0x9f11  call     int32 Microsoft.ReportingServices.Diagnostics.Encryption::get_OldUntaggedVersion()
0x9f16  bne.un.s loc_9F22
0x9f18  ldarg.0
0x9f19  ldarg.2
0x9f1a  ldnull
0x9f1b  ldc.i4.0
0x9f1c  call     instance unsigned int8[] Microsoft.ReportingServices.Diagnostics.Encryption::Decrypt(unsigned int8[] protectedData, string tag, bool useSalt)
0x9f21  ret
0x9f22  ldarg.1
0x9f23  call     int32 Microsoft.ReportingServices.Diagnostics.Encryption::get_OldUnsaltedVersion()
0x9f28  bne.un.s loc_9F34
0x9f2a  ldarg.0
0x9f2b  ldarg.2
0x9f2c  ldarg.3
0x9f2d  ldc.i4.0
0x9f2e  call     instance unsigned int8[] Microsoft.ReportingServices.Diagnostics.Encryption::Decrypt(unsigned int8[] protectedData, string tag, bool useSalt)
0x9f33  ret
0x9f34  ldarg.1
0x9f35  call     int32 Microsoft.ReportingServices.Diagnostics.Encryption::get_CurrentVersion()
0x9f3a  bne.un.s loc_9F46
0x9f3c  ldarg.0
0x9f3d  ldarg.2
0x9f3e  ldarg.3
0x9f3f  ldc.i4.1
0x9f40  call     instance unsigned int8[] Microsoft.ReportingServices.Diagnostics.Encryption::Decrypt(unsigned int8[] protectedData, string tag, bool useSalt)
0x9f45  ret
0x9f46  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CannotValidateEncryptedDataException::.ctor()
0x9f4b  throw
```
