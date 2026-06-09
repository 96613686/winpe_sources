# Microsoft.ReportingServices.Diagnostics.Encryption::Decrypt_2

- ea: `0x9f50`
- end: `0xa001`
- name: `Microsoft.ReportingServices.Diagnostics.Encryption::Decrypt_2`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9f10`

## callees

- `0x9c50`
- `0x9f50`

## pseudocode

```c

```

## disassembly

```asm
0x9f50  ldarg.1
0x9f51  brtrue.s loc_9F55
0x9f53  ldnull
0x9f54  ret
0x9f55  ldarg.0
0x9f56  ldarg.1
0x9f57  ldarg.3
0x9f58  callvirt instance unsigned int8[] Microsoft.ReportingServices.Diagnostics.Encryption::Decrypt(unsigned int8[] data, [opt] bool useSalt)
0x9f5d  stloc.0
0x9f5e  ldarg.2
0x9f5f  brtrue.s loc_9F63
0x9f61  ldloc.0
0x9f62  ret
0x9f63  nop
0x9f64  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x9f69  ldarg.2
0x9f6a  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x9f6f  stloc.1
0x9f70  ldc.i4.0
0x9f71  stloc.2
0x9f72  ldloc.0
0x9f73  ldlen
0x9f74  conv.i4
0x9f75  ldloc.1
0x9f76  ldlen
0x9f77  conv.i4
0x9f78  blt.s    loc_9F9F
0x9f7a  ldc.i4.0
0x9f7b  stloc.s  4
0x9f7d  br.s     loc_9F8F
0x9f7f  ldloc.0
0x9f80  ldloc.s  4
0x9f82  ldelem.u1
0x9f83  ldloc.1
0x9f84  ldloc.s  4
0x9f86  ldelem.u1
0x9f87  bne.un.s loc_9F96
0x9f89  ldloc.s  4
0x9f8b  ldc.i4.1
0x9f8c  add
0x9f8d  stloc.s  4
0x9f8f  ldloc.s  4
0x9f91  ldloc.1
0x9f92  ldlen
0x9f93  conv.i4
0x9f94  blt.s    loc_9F7F
0x9f96  ldloc.s  4
0x9f98  ldloc.1
0x9f99  ldlen
0x9f9a  conv.i4
0x9f9b  bne.un.s loc_9F9F
0x9f9d  ldc.i4.1
0x9f9e  stloc.2
0x9f9f  ldloc.2
0x9fa0  brtrue.s loc_9FC4
0x9fa2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x9fa7  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x9fac  brfalse.s loc_9FBE
0x9fae  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x9fb3  ldc.i4.1
0x9fb4  ldstr    aEncryptedDataI// "Encrypted data is missing expected tag "...
0x9fb9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x9fbe  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CannotValidateEncryptedDataException::.ctor()
0x9fc3  throw
0x9fc4  ldloc.0
0x9fc5  ldlen
0x9fc6  conv.i4
0x9fc7  ldloc.1
0x9fc8  ldlen
0x9fc9  conv.i4
0x9fca  sub
0x9fcb  newarr   [mscorlib]System.Byte
0x9fd0  stloc.3
0x9fd1  ldloc.0
0x9fd2  ldloc.1
0x9fd3  ldlen
0x9fd4  conv.i4
0x9fd5  ldloc.3
0x9fd6  ldc.i4.0
0x9fd7  ldloc.3
0x9fd8  ldlen
0x9fd9  conv.i4
0x9fda  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x9fdf  ldloc.3
0x9fe0  stloc.s  5
0x9fe2  leave.s  loc_9FFE
0x9fe4  ldc.i4.0
0x9fe5  stloc.s  6
0x9fe7  br.s     loc_9FF4
0x9fe9  ldloc.0
0x9fea  ldloc.s  6
0x9fec  ldc.i4.0
0x9fed  stelem.i1
0x9fee  ldloc.s  6
0x9ff0  ldc.i4.1
0x9ff1  add
0x9ff2  stloc.s  6
0x9ff4  ldloc.s  6
0x9ff6  ldloc.0
0x9ff7  ldlen
0x9ff8  conv.i4
0x9ff9  blt.s    loc_9FE9
0x9ffb  ldnull
0x9ffc  stloc.0
0x9ffd  endfinally
0x9ffe  ldloc.s  5
0xa000  ret
```
