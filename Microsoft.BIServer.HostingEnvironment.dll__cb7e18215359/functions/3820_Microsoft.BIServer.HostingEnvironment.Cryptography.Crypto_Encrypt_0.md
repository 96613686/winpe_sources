# Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::Encrypt_0

- ea: `0x3820`
- end: `0x3877`
- name: `Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::Encrypt_0`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3810`
- `0x3890`
- `0x38c0`

## callees

- `0x37e0`
- `0x3820`
- `0x3a20`

## pseudocode

```c

```

## disassembly

```asm
0x3820  ldarg.1
0x3821  brtrue.s loc_3825
0x3823  ldnull
0x3824  ret
0x3825  ldnull
0x3826  stloc.0
0x3827  ldarg.2
0x3828  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x382d  brfalse.s loc_3833
0x382f  ldarg.1
0x3830  stloc.0
0x3831  br.s     loc_385E
0x3833  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x3838  ldarg.2
0x3839  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x383e  stloc.1
0x383f  ldarg.1
0x3840  ldlen
0x3841  conv.i4
0x3842  ldloc.1
0x3843  ldlen
0x3844  conv.i4
0x3845  add
0x3846  newarr   [mscorlib]System.Byte
0x384b  stloc.0
0x384c  ldloc.1
0x384d  ldloc.0
0x384e  ldc.i4.0
0x384f  callvirt instance void [mscorlib]System.Array::CopyTo(class [mscorlib]System.Array, int32)
0x3854  ldarg.1
0x3855  ldloc.0
0x3856  ldloc.1
0x3857  ldlen
0x3858  conv.i4
0x3859  callvirt instance void [mscorlib]System.Array::CopyTo(class [mscorlib]System.Array, int32)
0x385e  ldarg.0
0x385f  ldloc.0
0x3860  callvirt instance unsigned int8[] Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::EncryptInternal(unsigned int8[] data)
0x3865  stloc.2
0x3866  leave.s  loc_3875
0x3868  ldarg.2
0x3869  brfalse.s loc_3872
0x386b  ldarg.0
0x386c  ldloc.0
0x386d  call     instance void Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::Clear(unsigned int8[] data)
0x3872  ldnull
0x3873  stloc.0
0x3874  endfinally
0x3875  ldloc.2
0x3876  ret
```
