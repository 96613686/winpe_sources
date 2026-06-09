# Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::DecryptToSecureString_2

- ea: `0x39e0`
- end: `0x3a1c`
- name: `Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::DecryptToSecureString_2`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x39c0`
- `0x39d0`

## callees

- `0x3980`
- `0x39e0`

## pseudocode

```c

```

## disassembly

```asm
0x39e0  ldarg.1
0x39e1  brtrue.s loc_39E5
0x39e3  ldnull
0x39e4  ret
0x39e5  newobj   instance void [mscorlib]System.Security.SecureString::.ctor()
0x39ea  stloc.0
0x39eb  ldarg.0
0x39ec  ldarg.1
0x39ed  ldarg.2
0x39ee  call     instance string Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::DecryptToString(unsigned int8[] protectedData, string tag)
0x39f3  stloc.1
0x39f4  ldc.i4.0
0x39f5  stloc.2
0x39f6  br.s     loc_3A0B
0x39f8  ldloc.1
0x39f9  ldloc.2
0x39fa  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x39ff  stloc.3
0x3a00  ldloc.0
0x3a01  ldloc.3
0x3a02  callvirt instance void [mscorlib]System.Security.SecureString::AppendChar(char)
0x3a07  ldloc.2
0x3a08  ldc.i4.1
0x3a09  add
0x3a0a  stloc.2
0x3a0b  ldloc.2
0x3a0c  ldloc.1
0x3a0d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3a12  blt.s    loc_39F8
0x3a14  ldloc.0
0x3a15  callvirt instance void [mscorlib]System.Security.SecureString::MakeReadOnly()
0x3a1a  ldloc.0
0x3a1b  ret
```
