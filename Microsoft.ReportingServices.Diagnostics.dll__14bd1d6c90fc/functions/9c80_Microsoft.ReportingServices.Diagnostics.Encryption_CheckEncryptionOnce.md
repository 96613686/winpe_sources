# Microsoft.ReportingServices.Diagnostics.Encryption::CheckEncryptionOnce

- ea: `0x9c80`
- end: `0x9cbe`
- name: `Microsoft.ReportingServices.Diagnostics.Encryption::CheckEncryptionOnce`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x9cc0`

## callees

- `0x9c40`
- `0x9c50`
- `0x9c60`
- `0x9c70`
- `0x9c80`

## pseudocode

```c

```

## disassembly

```asm
0x9c80  ldarg.0
0x9c81  callvirt instance bool Microsoft.ReportingServices.Diagnostics.Encryption::IsEncryptionChecked()
0x9c86  brtrue.s loc_9CBD
0x9c88  ldarg.0
0x9c89  ldsfld   unsigned int8[] Microsoft.ReportingServices.Diagnostics.Encryption::unencoded
0x9c8e  callvirt instance unsigned int8[] Microsoft.ReportingServices.Diagnostics.Encryption::EncryptInternal(unsigned int8[] data)
0x9c93  stloc.0
0x9c94  ldarg.0
0x9c95  ldloc.0
0x9c96  ldc.i4.1
0x9c97  callvirt instance unsigned int8[] Microsoft.ReportingServices.Diagnostics.Encryption::Decrypt(unsigned int8[] data, [opt] bool useSalt)
0x9c9c  stloc.1
0x9c9d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x9ca2  ldsfld   unsigned int8[] Microsoft.ReportingServices.Diagnostics.Encryption::unencoded
0x9ca7  ldloc.1
0x9ca8  call     T0x2B000008
0x9cad  ldstr    aBasicEncryptio// "Basic Encryption Test"
0x9cb2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x9cb7  ldarg.0
0x9cb8  callvirt instance void Microsoft.ReportingServices.Diagnostics.Encryption::SetEncryptionChecked()
0x9cbd  ret
```
