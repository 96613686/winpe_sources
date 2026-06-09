# Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::Decrypt_0

- ea: `0x38f0`
- end: `0x3948`
- name: `Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::Decrypt_0`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x38e0`
- `0x3980`

## callees

- `0x37f0`
- `0x38f0`
- `0x3a20`
- `0x6e80`

## pseudocode

```c

```

## disassembly

```asm
0x38f0  ldarg.1
0x38f1  brtrue.s loc_38F5
0x38f3  ldnull
0x38f4  ret
0x38f5  ldarg.0
0x38f6  ldarg.1
0x38f7  callvirt instance unsigned int8[] Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::DecryptInternal(unsigned int8[] data)
0x38fc  stloc.0
0x38fd  ldarg.2
0x38fe  brtrue.s loc_3902
0x3900  ldloc.0
0x3901  ret
0x3902  nop
0x3903  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x3908  ldarg.2
0x3909  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x390e  stloc.1
0x390f  ldloc.0
0x3910  ldloc.1
0x3911  ldlen
0x3912  conv.i4
0x3913  call     T0x2B000028
0x3918  ldloc.1
0x3919  call     T0x2B000029
0x391e  brtrue.s loc_392B
0x3920  ldstr    aEncryptedDataI// "Encrypted data is missing expected tag "...
0x3925  newobj   instance void TagMissing::.ctor(string message)
0x392a  throw
0x392b  ldloc.0
0x392c  ldloc.1
0x392d  ldlen
0x392e  conv.i4
0x392f  call     T0x2B00002A
0x3934  call     T0x2B00002B
0x3939  stloc.2
0x393a  leave.s  loc_3946
0x393c  ldarg.0
0x393d  ldloc.0
0x393e  call     instance void Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::Clear(unsigned int8[] data)
0x3943  ldnull
0x3944  stloc.0
0x3945  endfinally
0x3946  ldloc.2
0x3947  ret
```
