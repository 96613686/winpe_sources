# Microsoft.BIServer.Configuration.ExternalUrlHelpers::CalculateUrl

- ea: `0x220`
- end: `0x411`
- name: `Microsoft.BIServer.Configuration.ExternalUrlHelpers::CalculateUrl`
- size: `497`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x220`
- `0x420`
- `0x4750`
- `0x4770`
- `0x4900`

## pseudocode

```c

```

## disassembly

```asm
0x220  ldarg.0
0x221  brfalse.s loc_23D
0x223  ldarg.0
0x224  callvirt instance class Microsoft.BIServer.Configuration.URL[] Microsoft.BIServer.Configuration.Application::get_URLs()
0x229  call     T0x2B000001
0x22e  brfalse.s loc_23D
0x230  ldarg.0
0x231  callvirt instance string Microsoft.BIServer.Configuration.Application::get_VirtualDirectory()
0x236  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x23b  brfalse.s loc_23F
0x23d  ldnull
0x23e  ret
0x23f  ldarg.1
0x240  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x245  brtrue.s loc_25F
0x247  ldarg.1
0x248  newobj   instance void [System]System.UriBuilder::.ctor(string)
0x24d  dup
0x24e  ldarg.0
0x24f  callvirt instance string Microsoft.BIServer.Configuration.Application::get_VirtualDirectory()
0x254  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x259  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x25e  ret
0x25f  ldarg.2
0x260  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x265  brtrue.s loc_27F
0x267  ldarg.2
0x268  newobj   instance void [System]System.UriBuilder::.ctor(string)
0x26d  dup
0x26e  ldarg.0
0x26f  callvirt instance string Microsoft.BIServer.Configuration.Application::get_VirtualDirectory()
0x274  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x279  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x27e  ret
0x27f  ldnull
0x280  stloc.0
0x281  ldnull
0x282  stloc.1
0x283  ldnull
0x284  stloc.2
0x285  ldnull
0x286  stloc.3
0x287  ldnull
0x288  stloc.s  4
0x28a  ldnull
0x28b  stloc.s  5
0x28d  ldnull
0x28e  stloc.s  6
0x290  ldnull
0x291  stloc.s  7
0x293  ldnull
0x294  stloc.s  8
0x296  ldnull
0x297  stloc.s  9
0x299  ldarg.0
0x29a  callvirt instance class Microsoft.BIServer.Configuration.URL[] Microsoft.BIServer.Configuration.Application::get_URLs()
0x29f  stloc.s  0xA
0x2a1  ldc.i4.0
0x2a2  stloc.s  0xB
0x2a4  br       loc_382
0x2a9  ldloc.s  0xA
0x2ab  ldloc.s  0xB
0x2ad  ldelem.ref
0x2ae  callvirt instance string Microsoft.BIServer.Configuration.URL::get_UrlString()
0x2b3  ldloca.s 0xD
0x2b5  ldloca.s 0xC
0x2b7  ldloca.s 0x10
0x2b9  ldloca.s 0xE
0x2bb  ldloca.s 0xF
0x2bd  call     bool Microsoft.BIServer.Configuration.ExternalUrlHelpers::ParseUrlPrefix(string url, [out] string& scheme, [out] string& host, [out] string& port, [out] string& prefix, [out] string& path)
0x2c2  pop
0x2c3  ldloc.s  0xD
0x2c5  ldsfld   string [System]System.Uri::UriSchemeHttps
0x2ca  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x2cf  ldc.i4.0
0x2d0  ceq
0x2d2  stloc.s  0x12
0x2d4  ldloc.s  0xC
0x2d6  ldstr    asc_808E// "*"
0x2db  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x2e0  brfalse.s loc_2F0
0x2e2  ldloc.s  0xC
0x2e4  ldstr    asc_8092// "+"
0x2e9  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x2ee  brtrue.s loc_31B
0x2f0  call     string [mscorlib]System.Environment::get_MachineName()
0x2f5  ldstr    asc_8096// ":"
0x2fa  ldloc.s  0x10
0x2fc  call     string [mscorlib]System.String::Concat(string, string, string)
0x301  stloc.s  0x13
0x303  ldloc.s  0x12
0x305  brfalse.s loc_311
0x307  ldloc.s  7
0x309  brtrue.s loc_37C
0x30b  ldloc.s  0x13
0x30d  stloc.s  7
0x30f  br.s     loc_37C
0x311  ldloc.s  4
0x313  brtrue.s loc_37C
0x315  ldloc.s  0x13
0x317  stloc.s  4
0x319  br.s     loc_37C
0x31b  ldloc.s  0xC
0x31d  ldloca.s 0x11
0x31f  call     bool [System]System.Net.IPAddress::TryParse(string, class [System]System.Net.IPAddress&)
0x324  brfalse.s loc_34E
0x326  ldloc.s  0xC
0x328  ldstr    asc_8096// ":"
0x32d  ldloc.s  0x10
0x32f  call     string [mscorlib]System.String::Concat(string, string, string)
0x334  stloc.s  0x14
0x336  ldloc.s  0x12
0x338  brfalse.s loc_344
0x33a  ldloc.s  8
0x33c  brtrue.s loc_37C
0x33e  ldloc.s  0x14
0x340  stloc.s  8
0x342  br.s     loc_37C
0x344  ldloc.s  5
0x346  brtrue.s loc_37C
0x348  ldloc.s  0x14
0x34a  stloc.s  5
0x34c  br.s     loc_37C
0x34e  ldloc.s  6
0x350  brfalse.s loc_356
0x352  ldloc.s  9
0x354  brtrue.s loc_37C
0x356  ldloc.s  0xC
0x358  ldstr    asc_8096// ":"
0x35d  ldloc.s  0x10
0x35f  call     string [mscorlib]System.String::Concat(string, string, string)
0x364  stloc.s  0x15
0x366  ldloc.s  0x12
0x368  brfalse.s loc_374
0x36a  ldloc.s  9
0x36c  brtrue.s loc_37C
0x36e  ldloc.s  0x15
0x370  stloc.s  9
0x372  br.s     loc_37C
0x374  ldloc.s  6
0x376  brtrue.s loc_37C
0x378  ldloc.s  0x15
0x37a  stloc.s  6
0x37c  ldloc.s  0xB
0x37e  ldc.i4.1
0x37f  add
0x380  stloc.s  0xB
0x382  ldloc.s  0xB
0x384  ldloc.s  0xA
0x386  ldlen
0x387  conv.i4
0x388  blt      loc_2A9
0x38d  ldloc.s  7
0x38f  brfalse.s loc_396
0x391  ldloc.s  7
0x393  stloc.3
0x394  br.s     loc_3A6
0x396  ldloc.s  8
0x398  brfalse.s loc_39F
0x39a  ldloc.s  8
0x39c  stloc.3
0x39d  br.s     loc_3A6
0x39f  ldloc.s  9
0x3a1  brfalse.s loc_3A6
0x3a3  ldloc.s  9
0x3a5  stloc.3
0x3a6  ldloc.s  4
0x3a8  brfalse.s loc_3AF
0x3aa  ldloc.s  4
0x3ac  stloc.2
0x3ad  br.s     loc_3BF
0x3af  ldloc.s  5
0x3b1  brfalse.s loc_3B8
0x3b3  ldloc.s  5
0x3b5  stloc.2
0x3b6  br.s     loc_3BF
0x3b8  ldloc.s  6
0x3ba  brfalse.s loc_3BF
0x3bc  ldloc.s  6
0x3be  stloc.2
0x3bf  ldarg.3
0x3c0  ldc.i4.0
0x3c1  ble.s    loc_3DA
0x3c3  ldloc.3
0x3c4  brfalse.s loc_3D0
0x3c6  ldloc.3
0x3c7  stloc.0
0x3c8  ldsfld   string [System]System.Uri::UriSchemeHttps
0x3cd  stloc.1
0x3ce  br.s     loc_3EF
0x3d0  ldloc.2
0x3d1  stloc.0
0x3d2  ldsfld   string [System]System.Uri::UriSchemeHttp
0x3d7  stloc.1
0x3d8  br.s     loc_3EF
0x3da  ldloc.2
0x3db  brfalse.s loc_3E7
0x3dd  ldloc.2
0x3de  stloc.0
0x3df  ldsfld   string [System]System.Uri::UriSchemeHttp
0x3e4  stloc.1
0x3e5  br.s     loc_3EF
0x3e7  ldloc.3
0x3e8  stloc.0
0x3e9  ldsfld   string [System]System.Uri::UriSchemeHttps
0x3ee  stloc.1
0x3ef  ldloc.0
0x3f0  brtrue.s loc_3F4
0x3f2  ldnull
0x3f3  ret
0x3f4  ldloc.1
0x3f5  brtrue.s loc_3F9
0x3f7  ldnull
0x3f8  ret
0x3f9  ldloc.1
0x3fa  ldsfld   string [System]System.Uri::SchemeDelimiter
0x3ff  ldloc.0
0x400  ldarg.0
0x401  callvirt instance string Microsoft.BIServer.Configuration.Application::get_VirtualDirectory()
0x406  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x40b  newobj   instance void [System]System.Uri::.ctor(string)
0x410  ret
```
