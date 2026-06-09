# Microsoft.SharePoint.IdentityModel.SPProofTokenContext::FillProofToken

- ea: `0x19250`
- end: `0x19365`
- name: `Microsoft.SharePoint.IdentityModel.SPProofTokenContext::FillProofToken`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x19090`

## callees

- `0x19030`
- `0x19080`
- `0x19250`

## string_xrefs

- `0x19259`: `proofToken`
- `0x1929d`: `SPProofToken: Proof token isn't in the right format. Input:{0}`
- `0x192df`: `SPProofToken: Proof token file time isn't in the right format. Input:{0}`
- `0x19317`: `SPProofToken: Constructed a proof token with timestamp:{0}, UtcNow:{1}.`

## pseudocode

```c

```

## disassembly

```asm
0x19250  ldarg.0
0x19251  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x19256  brfalse.s loc_19264
0x19258  ldnull
0x19259  ldstr    aProoftoken_1// "proofToken"
0x1925e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x19263  throw
0x19264  ldarg.1
0x19265  ldind.ref
0x19266  brtrue.s loc_19273
0x19268  ldstr    aResult_0// "result"
0x1926d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x19272  throw
0x19273  ldarg.0
0x19274  ldc.i4.1
0x19275  newarr   [mscorlib]System.Char
0x1927a  stloc.s  5
0x1927c  ldloc.s  5
0x1927e  ldc.i4.0
0x1927f  ldc.i4.s 0x2E
0x19281  stelem.i2
0x19282  ldloc.s  5
0x19284  ldc.i4.1
0x19285  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x1928a  stloc.0
0x1928b  ldc.i4.2
0x1928c  ldloc.0
0x1928d  ldlen
0x1928e  conv.i4
0x1928f  beq.s    loc_192C1
0x19291  ldc.i4   0x142140
0x19296  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1929b  ldc.i4.s 0x32
0x1929d  ldstr    aSpprooftokenPr_0// "SPProofToken: Proof token isn't in the "...
0x192a2  ldc.i4.1
0x192a3  newarr   [mscorlib]System.Object
0x192a8  stloc.s  6
0x192aa  ldloc.s  6
0x192ac  ldc.i4.0
0x192ad  ldarg.0
0x192ae  stelem.ref
0x192af  ldloc.s  6
0x192b1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x192b6  ldstr    asc_336C0// ""
0x192bb  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x192c0  throw
0x192c1  ldloc.0
0x192c2  ldc.i4.0
0x192c3  ldelem.ref
0x192c4  stloc.1
0x192c5  ldloc.0
0x192c6  ldc.i4.1
0x192c7  ldelem.ref
0x192c8  stloc.2
0x192c9  ldloc.1
0x192ca  ldloca.s 3
0x192cc  call     bool [mscorlib]System.Int64::TryParse(string, int64&)
0x192d1  brtrue.s loc_19303
0x192d3  ldc.i4   0x142141
0x192d8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x192dd  ldc.i4.s 0x32
0x192df  ldstr    aSpprooftokenPr_1// "SPProofToken: Proof token file time isn"...
0x192e4  ldc.i4.1
0x192e5  newarr   [mscorlib]System.Object
0x192ea  stloc.s  7
0x192ec  ldloc.s  7
0x192ee  ldc.i4.0
0x192ef  ldloc.1
0x192f0  stelem.ref
0x192f1  ldloc.s  7
0x192f3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x192f8  ldstr    asc_336C0// ""
0x192fd  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x19302  throw
0x19303  ldloc.3
0x19304  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::FromFileTimeUtc(int64)
0x19309  stloc.s  4
0x1930b  ldc.i4   0x142142
0x19310  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x19315  ldc.i4.s 0x64
0x19317  ldstr    aSpprooftokenCo// "SPProofToken: Constructed a proof token"...
0x1931c  ldc.i4.2
0x1931d  newarr   [mscorlib]System.Object
0x19322  stloc.s  8
0x19324  ldloc.s  8
0x19326  ldc.i4.0
0x19327  ldloca.s 4
0x19329  constrained. [mscorlib]System.DateTime
0x1932f  callvirt instance string [mscorlib]System.Object::ToString()
0x19334  stelem.ref
0x19335  ldloc.s  8
0x19337  ldc.i4.1
0x19338  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1933d  stloc.s  9
0x1933f  ldloca.s 9
0x19341  constrained. [mscorlib]System.DateTime
0x19347  callvirt instance string [mscorlib]System.Object::ToString()
0x1934c  stelem.ref
0x1934d  ldloc.s  8
0x1934f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x19354  ldarg.1
0x19355  ldind.ref
0x19356  ldloc.2
0x19357  callvirt instance void Microsoft.SharePoint.IdentityModel.SPProofTokenContext::set_Signature(string value)
0x1935c  ldarg.1
0x1935d  ldind.ref
0x1935e  ldloc.1
0x1935f  callvirt instance void Microsoft.SharePoint.IdentityModel.SPProofTokenContext::set_RawTimestamp(string value)
0x19364  ret
```
