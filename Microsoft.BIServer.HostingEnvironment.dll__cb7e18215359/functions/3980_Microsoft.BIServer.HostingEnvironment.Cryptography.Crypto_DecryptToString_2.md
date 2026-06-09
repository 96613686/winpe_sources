# Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::DecryptToString_2

- ea: `0x3980`
- end: `0x39a4`
- name: `Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::DecryptToString_2`
- size: `36`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3960`
- `0x3970`
- `0x39e0`

## callees

- `0x38f0`
- `0x3980`

## pseudocode

```c

```

## disassembly

```asm
0x3980  ldarg.0
0x3981  ldarg.1
0x3982  ldarg.2
0x3983  call     instance unsigned int8[] Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::Decrypt(unsigned int8[] protectedData, string tag)
0x3988  stloc.0
0x3989  ldloc.0
0x398a  brtrue.s loc_398E
0x398c  ldnull
0x398d  ret
0x398e  ldloc.0
0x398f  ldlen
0x3990  brtrue.s loc_3998
0x3992  ldsfld   string [mscorlib]System.String::Empty
0x3997  ret
0x3998  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x399d  ldloc.0
0x399e  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x39a3  ret
```
