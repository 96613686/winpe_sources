# Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::ValidateTokenOrException

- ea: `0x3380`
- end: `0x34a9`
- name: `Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::ValidateTokenOrException`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x3370`

## callees

- `0x1490`
- `0x32f0`
- `0x3310`
- `0x3380`
- `0x3730`
- `0x3750`
- `0x3780`
- `0x3b60`
- `0x4f00`
- `0x4fe0`

## string_xrefs

- `0x338e`: `null token`
- `0x33b3`: `Invalid TrustedProcessToken`
- `0x3422`: `wrong user [{0}], expecting[{1}] in token {2}`

## pseudocode

```c

```

## disassembly

```asm
0x3380  call     valuetype [mscorlib]System.DateTime Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::NowTime()
0x3385  stloc.0
0x3386  ldarg.0
0x3387  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x338c  brfalse.s loc_339E
0x338e  ldstr    aNullToken// "null token"
0x3393  call     T0x2B00000A
0x3398  newobj   instance void Microsoft.BIServer.HostingEnvironment.Exceptions.InvalidTrustedProcessTokenException::.ctor(string message, object[] parameters)
0x339d  throw
0x339e  nop
0x339f  call     class Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0x33a4  callvirt instance class Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_CatalogCrypto()
0x33a9  ldarg.0
0x33aa  callvirt instance string Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::DecryptToString(string protectedData)
0x33af  stloc.1
0x33b0  leave.s  loc_33D2
0x33b2  dup
0x33b3  ldstr    aInvalidTrusted// "Invalid TrustedProcessToken"
0x33b8  call     T0x2B00000A
0x33bd  call     void Microsoft.BIServer.HostingEnvironment.Logger::Debug(class [mscorlib]System.Exception ex, string formatString, object[] formatParams)
0x33c2  ldstr    aFailedDecrypti// "failed decryption"
0x33c7  call     T0x2B00000A
0x33cc  newobj   instance void Microsoft.BIServer.HostingEnvironment.Exceptions.InvalidTrustedProcessTokenException::.ctor(class [mscorlib]System.Exception ex, string message, object[] parameters)
0x33d1  throw
0x33d2  ldloc.1
0x33d3  ldc.i4.1
0x33d4  newarr   [mscorlib]System.Char
0x33d9  dup
0x33da  ldc.i4.0
0x33db  ldc.i4.s 0x7C
0x33dd  stelem.i2
0x33de  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x33e3  stloc.2
0x33e4  ldloc.2
0x33e5  ldlen
0x33e6  conv.i4
0x33e7  ldc.i4.2
0x33e8  bge.s    loc_33FF
0x33ea  ldstr    aWrongNumberOfP// "wrong number of parameters [{0}]"
0x33ef  ldc.i4.1
0x33f0  newarr   [mscorlib]System.Object
0x33f5  dup
0x33f6  ldc.i4.0
0x33f7  ldloc.1
0x33f8  stelem.ref
0x33f9  newobj   instance void Microsoft.BIServer.HostingEnvironment.Exceptions.InvalidTrustedProcessTokenException::.ctor(string message, object[] parameters)
0x33fe  throw
0x33ff  ldloc.2
0x3400  ldc.i4.0
0x3401  ldelem.ref
0x3402  stloc.3
0x3403  ldarg.1
0x3404  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x3409  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x340e  stloc.s  4
0x3410  ldloc.3
0x3411  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3416  brtrue.s loc_3422
0x3418  ldloc.3
0x3419  ldloc.s  4
0x341b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3420  brfalse.s loc_3440
0x3422  ldstr    aWrongUser0Expe// "wrong user [{0}], expecting[{1}] in tok"...
0x3427  ldc.i4.3
0x3428  newarr   [mscorlib]System.Object
0x342d  dup
0x342e  ldc.i4.0
0x342f  ldloc.3
0x3430  stelem.ref
0x3431  dup
0x3432  ldc.i4.1
0x3433  ldloc.s  4
0x3435  stelem.ref
0x3436  dup
0x3437  ldc.i4.2
0x3438  ldloc.1
0x3439  stelem.ref
0x343a  newobj   instance void Microsoft.BIServer.HostingEnvironment.Exceptions.InvalidTrustedProcessTokenException::.ctor(string message, object[] parameters)
0x343f  throw
0x3440  ldloc.2
0x3441  ldc.i4.1
0x3442  ldelem.ref
0x3443  ldloca.s 5
0x3445  call     bool [mscorlib]System.Int64::TryParse(string, int64&)
0x344a  brtrue.s loc_3461
0x344c  ldstr    aBadTimestamp0// "Bad timestamp [{0}]"
0x3451  ldc.i4.1
0x3452  newarr   [mscorlib]System.Object
0x3457  dup
0x3458  ldc.i4.0
0x3459  ldloc.1
0x345a  stelem.ref
0x345b  newobj   instance void Microsoft.BIServer.HostingEnvironment.Exceptions.InvalidTrustedProcessTokenException::.ctor(string message, object[] parameters)
0x3460  throw
0x3461  ldloc.s  5
0x3463  call     valuetype [mscorlib]System.DateTime Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::FromFileTime(int64 fileTime)
0x3468  stloc.s  6
0x346a  ldloca.s 6
0x346c  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::RequestTimeout
0x3471  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x3476  stloc.s  7
0x3478  ldloc.s  7
0x347a  ldloc.0
0x347b  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3480  brfalse.s loc_34A8
0x3482  ldloca.s 0
0x3484  ldloc.s  7
0x3486  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x348b  stloc.s  8
0x348d  ldstr    aExpiredBy0// "Expired by {0}"
0x3492  ldc.i4.1
0x3493  newarr   [mscorlib]System.Object
0x3498  dup
0x3499  ldc.i4.0
0x349a  ldloc.s  8
0x349c  box      [mscorlib]System.TimeSpan
0x34a1  stelem.ref
0x34a2  newobj   instance void Microsoft.BIServer.HostingEnvironment.Exceptions.TrustedProcessTokenExpiredException::.ctor(string message, object[] parameters)
0x34a7  throw
0x34a8  ret
```
