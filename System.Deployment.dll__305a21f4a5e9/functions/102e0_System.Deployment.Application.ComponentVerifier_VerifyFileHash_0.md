# System.Deployment.Application.ComponentVerifier::VerifyFileHash_0

- ea: `0x102e0`
- end: `0x103ba`
- name: `System.Deployment.Application.ComponentVerifier::VerifyFileHash_0`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10240`

## callees

- `0x10060`
- `0x10070`
- `0x10080`
- `0x102e0`
- `0x103c0`
- `0x147a0`
- `0x147b0`
- `0x17d40`
- `0x23020`

## string_xrefs

- `0x1035f`: `, has a different computed hash than specified in manifest. Computed hash is `

## pseudocode

```c

```

## disassembly

```asm
0x102e0  ldarg.0
0x102e1  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x102e6  stloc.0
0x102e7  ldarg.0
0x102e8  ldarg.1
0x102e9  callvirt instance valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_DIGESTMETHOD System.Deployment.Application.Hash::get_DigestMethod()
0x102ee  ldarg.1
0x102ef  callvirt instance valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_TRANSFORM System.Deployment.Application.Hash::get_Transform()
0x102f4  call     unsigned int8[] System.Deployment.Application.ComponentVerifier::GenerateDigestValue(string filePath, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_DIGESTMETHOD digestMethod, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_TRANSFORM transform)
0x102f9  stloc.1
0x102fa  leave.s  loc_10312
0x102fc  stloc.s  4
0x102fe  ldc.i4.s 0x19
0x10300  ldstr    aExHashvalidati// "Ex_HashValidationException"
0x10305  call     string System.Deployment.Application.Resources::GetString(string s)
0x1030a  ldloc.s  4
0x1030c  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x10311  throw
0x10312  ldarg.1
0x10313  callvirt instance unsigned int8[] System.Deployment.Application.Hash::get_DigestValue()
0x10318  stloc.2
0x10319  ldc.i4.0
0x1031a  stloc.3
0x1031b  ldloc.1
0x1031c  ldlen
0x1031d  conv.i4
0x1031e  ldloc.2
0x1031f  ldlen
0x10320  conv.i4
0x10321  bne.un.s loc_10348
0x10323  ldc.i4.0
0x10324  stloc.s  5
0x10326  br.s     loc_10338
0x10328  ldloc.2
0x10329  ldloc.s  5
0x1032b  ldelem.u1
0x1032c  ldloc.1
0x1032d  ldloc.s  5
0x1032f  ldelem.u1
0x10330  bne.un.s loc_1033F
0x10332  ldloc.s  5
0x10334  ldc.i4.1
0x10335  add
0x10336  stloc.s  5
0x10338  ldloc.s  5
0x1033a  ldloc.2
0x1033b  ldlen
0x1033c  conv.i4
0x1033d  blt.s    loc_10328
0x1033f  ldloc.s  5
0x10341  ldloc.2
0x10342  ldlen
0x10343  conv.i4
0x10344  blt.s    loc_10348
0x10346  ldc.i4.1
0x10347  stloc.3
0x10348  ldloc.3
0x10349  brtrue.s loc_103B9
0x1034b  ldc.i4.6
0x1034c  newarr   [mscorlib]System.String
0x10351  dup
0x10352  ldc.i4.0
0x10353  ldstr    aFile// "File,"
0x10358  stelem.ref
0x10359  dup
0x1035a  ldc.i4.1
0x1035b  ldloc.0
0x1035c  stelem.ref
0x1035d  dup
0x1035e  ldc.i4.2
0x1035f  ldstr    aHasADifferentC// ", has a different computed hash than sp"...
0x10364  stelem.ref
0x10365  dup
0x10366  ldc.i4.3
0x10367  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x1036c  ldloc.1
0x1036d  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x10372  stelem.ref
0x10373  dup
0x10374  ldc.i4.4
0x10375  ldstr    aSpecifiedHashI// ". Specified hash is "
0x1037a  stelem.ref
0x1037b  dup
0x1037c  ldc.i4.5
0x1037d  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x10382  ldloc.2
0x10383  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x10388  stelem.ref
0x10389  call     string [mscorlib]System.String::Concat(string[])
0x1038e  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x10393  ldc.i4.s 0x19
0x10395  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1039a  ldstr    aExDifferenthas// "Ex_DifferentHashes"
0x1039f  call     string System.Deployment.Application.Resources::GetString(string s)
0x103a4  ldc.i4.1
0x103a5  newarr   [mscorlib]System.Object
0x103aa  dup
0x103ab  ldc.i4.0
0x103ac  ldloc.0
0x103ad  stelem.ref
0x103ae  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x103b3  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x103b8  throw
0x103b9  ret
```
