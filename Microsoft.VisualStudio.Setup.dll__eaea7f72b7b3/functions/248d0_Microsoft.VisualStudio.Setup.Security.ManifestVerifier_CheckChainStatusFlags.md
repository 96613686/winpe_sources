# Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckChainStatusFlags

- ea: `0x248d0`
- end: `0x249b0`
- name: `Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckChainStatusFlags`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x247b0`

## callees

- `0x248d0`
- `0x6bc30`

## string_xrefs

- `0x248ed`: `ManifestVerifier failed checking for chain status flags.`
- `0x2495e`: `ManifestVerifier failed to build chain: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x248d0  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x248d5  stloc.0
0x248d6  ldarg.1
0x248d7  brfalse.s loc_248E1
0x248d9  ldarg.1
0x248da  call     T0x2B000155
0x248df  brtrue.s loc_24904
0x248e1  ldarg.0
0x248e2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x248e7  dup
0x248e8  brtrue.s loc_248ED
0x248ea  pop
0x248eb  br.s     loc_248FC
0x248ed  ldstr    aManifestverifi_12// "ManifestVerifier failed checking for ch"...
0x248f2  call     T0x2B000003
0x248f7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x248fc  ldc.i4.s 0x10
0x248fe  stloc.1
0x248ff  leave    loc_249AE
0x24904  ldloc.0
0x24905  ldc.i4   0x1000041
0x2490a  stfld    valuetype [System]System.Security.Cryptography.X509Certificates.X509ChainStatusFlags <>c__DisplayClass14_0::validChainStatusFlags
0x2490f  ldarg.1
0x24910  ldloc.0
0x24911  ldftn    instance bool <>c__DisplayClass14_0::<CheckChainStatusFlags>b__0(valuetype [System]System.Security.Cryptography.X509Certificates.X509ChainStatus s)
0x24917  newobj   instance void class [mscorlib]System.Func`2<valuetype [System]System.Security.Cryptography.X509Certificates.X509ChainStatus, bool>::.ctor(object, native int)
0x2491c  call     T0x2B000156
0x24921  brfalse.s loc_24988
0x24923  ldarg.1
0x24924  ldsfld   class [mscorlib]System.Func`2<valuetype [System]System.Security.Cryptography.X509Certificates.X509ChainStatus, bool> <>c::<>9__14_1
0x24929  dup
0x2492a  brtrue.s loc_24943
0x2492c  pop
0x2492d  ldsfld   class <>c <>c::<>9
0x24932  ldftn    instance bool <>c::<CheckChainStatusFlags>b__14_1(valuetype [System]System.Security.Cryptography.X509Certificates.X509ChainStatus s)
0x24938  newobj   instance void class [mscorlib]System.Func`2<valuetype [System]System.Security.Cryptography.X509Certificates.X509ChainStatus, bool>::.ctor(object, native int)
0x2493d  dup
0x2493e  stsfld   class [mscorlib]System.Func`2<valuetype [System]System.Security.Cryptography.X509Certificates.X509ChainStatus, bool> <>c::<>9__14_1
0x24943  call     T0x2B000156
0x24948  brfalse.s loc_24952
0x2494a  ldc.i4   0x10000
0x2494f  stloc.1
0x24950  leave.s  loc_249AE
0x24952  ldarg.0
0x24953  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x24958  dup
0x24959  brtrue.s loc_2495E
0x2495b  pop
0x2495c  br.s     loc_24983
0x2495e  ldstr    aManifestverifi_13// "ManifestVerifier failed to build chain:"...
0x24963  ldarg.1
0x24964  ldc.i4.0
0x24965  ldelema  [System]System.Security.Cryptography.X509Certificates.X509ChainStatus
0x2496a  call     instance valuetype [System]System.Security.Cryptography.X509Certificates.X509ChainStatusFlags [System]System.Security.Cryptography.X509Certificates.X509ChainStatus::get_Status()
0x2496f  box      [System]System.Security.Cryptography.X509Certificates.X509ChainStatusFlags
0x24974  call     string [mscorlib]System.String::Format(string, object)
0x24979  call     T0x2B000003
0x2497e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x24983  ldc.i4.s 0x10
0x24985  stloc.1
0x24986  leave.s  loc_249AE
0x24988  ldc.i4.0
0x24989  stloc.1
0x2498a  leave.s  loc_249AE
0x2498c  stloc.2
0x2498d  ldarg.0
0x2498e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x24993  dup
0x24994  brtrue.s loc_24999
0x24996  pop
0x24997  br.s     loc_249A9
0x24999  ldloc.2
0x2499a  ldstr    aUnexpectedErro// "Unexpected error checking cert status f"...
0x2499f  call     T0x2B000003
0x249a4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x249a9  ldc.i4.s 0x10
0x249ab  stloc.1
0x249ac  leave.s  loc_249AE
0x249ae  ldloc.1
0x249af  ret
```
