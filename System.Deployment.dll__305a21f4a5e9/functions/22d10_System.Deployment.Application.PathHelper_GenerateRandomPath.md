# System.Deployment.Application.PathHelper::GenerateRandomPath

- ea: `0x22d10`
- end: `0x22e5a`
- name: `System.Deployment.Application.PathHelper::GenerateRandomPath`
- size: `330`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x209e0`
- `0x20aa0`

## callees

- `0x146b0`
- `0x22d10`
- `0x22f30`
- `0x23020`

## string_xrefs

- `0x22d56`: `Ex_TempPathRandomStringTooShort`
- `0x22d72`: `Ex_TempPathRandomStringInvalid`
- `0x22d9b`: `Ex_TempPathRandomStringInvalid`
- `0x22de3`: `Ex_TempPathRandomStringInvalid`
- `0x22e09`: `Ex_TempPathRandomStringInvalid`

## pseudocode

```c

```

## disassembly

```asm
0x22d10  ldarg.0
0x22d11  brtrue.s loc_22D15
0x22d13  ldnull
0x22d14  ret
0x22d15  ldc.i4.s 0xB
0x22d17  ldarg.0
0x22d18  mul
0x22d19  stloc.0
0x22d1a  ldloc.0
0x22d1b  conv.r.un
0x22d1c  conv.r8
0x22d1d  ldc.r8   0.625
0x22d26  mul
0x22d27  call     float64 [mscorlib]System.Math::Ceiling(float64)
0x22d2c  conv.u4
0x22d2d  stloc.1
0x22d2e  ldloc.1
0x22d2f  newarr   [mscorlib]System.Byte
0x22d34  stloc.2
0x22d35  newobj   instance void [mscorlib]System.Security.Cryptography.RNGCryptoServiceProvider::.ctor()
0x22d3a  stloc.3
0x22d3b  ldloc.3
0x22d3c  ldloc.2
0x22d3d  callvirt instance void [mscorlib]System.Security.Cryptography.RandomNumberGenerator::GetBytes(unsigned int8[])
0x22d42  ldloc.2
0x22d43  call     string System.Deployment.Application.Base32String::FromBytes(unsigned int8[] bytes)
0x22d48  stloc.s  4
0x22d4a  ldloc.s  4
0x22d4c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x22d51  conv.i8
0x22d52  ldloc.0
0x22d53  conv.u8
0x22d54  bge.s    loc_22D66
0x22d56  ldstr    aExTemppathrand// "Ex_TempPathRandomStringTooShort"
0x22d5b  call     string System.Deployment.Application.Resources::GetString(string s)
0x22d60  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(string message)
0x22d65  throw
0x22d66  ldloc.s  4
0x22d68  ldc.i4.s 0x5C
0x22d6a  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x22d6f  ldc.i4.0
0x22d70  blt.s    loc_22D82
0x22d72  ldstr    aExTemppathrand_0// "Ex_TempPathRandomStringInvalid"
0x22d77  call     string System.Deployment.Application.Resources::GetString(string s)
0x22d7c  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(string message)
0x22d81  throw
0x22d82  ldarg.0
0x22d83  ldc.i4.1
0x22d84  sub
0x22d85  stloc.s  7
0x22d87  br.s     loc_22DC1
0x22d89  ldloc.s  7
0x22d8b  ldc.i4.s 0xB
0x22d8d  mul
0x22d8e  stloc.s  8
0x22d90  ldloc.s  8
0x22d92  ldloc.s  4
0x22d94  callvirt instance int32 [mscorlib]System.String::get_Length()
0x22d99  blt.s    loc_22DAB
0x22d9b  ldstr    aExTemppathrand_0// "Ex_TempPathRandomStringInvalid"
0x22da0  call     string System.Deployment.Application.Resources::GetString(string s)
0x22da5  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(string message)
0x22daa  throw
0x22dab  ldloc.s  4
0x22dad  ldloc.s  8
0x22daf  ldstr    asc_36B74// "\\"
0x22db4  callvirt instance string [mscorlib]System.String::Insert(int32, string)
0x22db9  stloc.s  4
0x22dbb  ldloc.s  7
0x22dbd  ldc.i4.1
0x22dbe  sub
0x22dbf  stloc.s  7
0x22dc1  ldloc.s  7
0x22dc3  ldc.i4.0
0x22dc4  bgt.s    loc_22D89
0x22dc6  ldloc.s  4
0x22dc8  ldc.i4.1
0x22dc9  newarr   [mscorlib]System.Char
0x22dce  dup
0x22dcf  ldc.i4.0
0x22dd0  ldc.i4.s 0x5C
0x22dd2  stelem.i2
0x22dd3  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x22dd8  stloc.s  5
0x22dda  ldloc.s  5
0x22ddc  ldlen
0x22ddd  conv.i4
0x22dde  conv.i8
0x22ddf  ldarg.0
0x22de0  conv.u8
0x22de1  bge.s    loc_22DF3
0x22de3  ldstr    aExTemppathrand_0// "Ex_TempPathRandomStringInvalid"
0x22de8  call     string System.Deployment.Application.Resources::GetString(string s)
0x22ded  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(string message)
0x22df2  throw
0x22df3  ldnull
0x22df4  stloc.s  6
0x22df6  ldc.i4.0
0x22df7  stloc.s  9
0x22df9  br.s     loc_22E52
0x22dfb  ldloc.s  5
0x22dfd  ldloc.s  9
0x22dff  ldelem.ref
0x22e00  callvirt instance int32 [mscorlib]System.String::get_Length()
0x22e05  ldc.i4.s 0xB
0x22e07  bge.s    loc_22E19
0x22e09  ldstr    aExTemppathrand_0// "Ex_TempPathRandomStringInvalid"
0x22e0e  call     string System.Deployment.Application.Resources::GetString(string s)
0x22e13  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(string message)
0x22e18  throw
0x22e19  ldloc.s  5
0x22e1b  ldloc.s  9
0x22e1d  ldelem.ref
0x22e1e  ldc.i4.0
0x22e1f  ldc.i4.s 0xB
0x22e21  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x22e26  stloc.s  0xA
0x22e28  ldloc.s  0xA
0x22e2a  ldc.i4.8
0x22e2b  ldstr    asc_36E38// "."
0x22e30  callvirt instance string [mscorlib]System.String::Insert(int32, string)
0x22e35  stloc.s  0xA
0x22e37  ldloc.s  6
0x22e39  brtrue.s loc_22E41
0x22e3b  ldloc.s  0xA
0x22e3d  stloc.s  6
0x22e3f  br.s     loc_22E4C
0x22e41  ldloc.s  6
0x22e43  ldloc.s  0xA
0x22e45  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x22e4a  stloc.s  6
0x22e4c  ldloc.s  9
0x22e4e  ldc.i4.1
0x22e4f  add
0x22e50  stloc.s  9
0x22e52  ldloc.s  9
0x22e54  ldarg.0
0x22e55  blt.un.s loc_22DFB
0x22e57  ldloc.s  6
0x22e59  ret
```
