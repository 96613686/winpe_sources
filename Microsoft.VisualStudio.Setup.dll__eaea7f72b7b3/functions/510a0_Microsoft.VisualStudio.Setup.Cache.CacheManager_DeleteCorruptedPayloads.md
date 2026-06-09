# Microsoft.VisualStudio.Setup.Cache.CacheManager::DeleteCorruptedPayloads

- ea: `0x510a0`
- end: `0x51189`
- name: `Microsoft.VisualStudio.Setup.Cache.CacheManager::DeleteCorruptedPayloads`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x50330`

## callees

- `0xfed0`
- `0x510a0`
- `0x571b0`
- `0x571c0`
- `0x571e0`

## string_xrefs

- `0x5110e`: `Unable to delete corrupt payload '`
- `0x51177`: `Unable to delete corrupt payloads.`

## pseudocode

```c

```

## disassembly

```asm
0x510a0  ldarg.1
0x510a1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype Microsoft.VisualStudio.Setup.Cache.PayloadState>::GetEnumerator()
0x510a6  stloc.0
0x510a7  br       loc_5114E
0x510ac  ldloc.0
0x510ad  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype Microsoft.VisualStudio.Setup.Cache.PayloadState>::get_Current()
0x510b2  stloc.1
0x510b3  ldloca.s 1
0x510b5  call     instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Cache.PayloadState::get_IsVerified()
0x510ba  stloc.2
0x510bb  ldloca.s 2
0x510bd  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x510c2  brfalse  loc_5114E
0x510c7  ldloca.s 1
0x510c9  call     instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Cache.PayloadState::get_IsVerified()
0x510ce  stloc.2
0x510cf  ldloca.s 2
0x510d1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x510d6  brtrue.s loc_5114E
0x510d8  ldarg.0
0x510d9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.CacheManager::fileSystem
0x510de  ldloca.s 1
0x510e0  call     instance string Microsoft.VisualStudio.Setup.Cache.PayloadState::get_Path()
0x510e5  ldloca.s 3
0x510e7  ldc.i4.0
0x510e8  ldc.i4.2
0x510e9  ldc.i4   0x1F4
0x510ee  ldnull
0x510ef  ldnull
0x510f0  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x510f5  pop
0x510f6  leave.s  loc_5114E
0x510f8  stloc.s  4
0x510fa  ldarg.0
0x510fb  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.CacheManager::logger
0x51100  dup
0x51101  brtrue.s loc_51106
0x51103  pop
0x51104  br.s     loc_5114C
0x51106  ldc.i4.5
0x51107  newarr   [mscorlib]System.String
0x5110c  dup
0x5110d  ldc.i4.0
0x5110e  ldstr    aUnableToDelete_1// "Unable to delete corrupt payload '"
0x51113  stelem.ref
0x51114  dup
0x51115  ldc.i4.1
0x51116  ldloca.s 1
0x51118  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload Microsoft.VisualStudio.Setup.Cache.PayloadState::get_Payload()
0x5111d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload::get_FileName()
0x51122  stelem.ref
0x51123  dup
0x51124  ldc.i4.2
0x51125  ldstr    aWith// "' with '"
0x5112a  stelem.ref
0x5112b  dup
0x5112c  ldc.i4.3
0x5112d  ldloc.s  4
0x5112f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x51134  stelem.ref
0x51135  dup
0x51136  ldc.i4.4
0x51137  ldstr    asc_7F7FA// "'."
0x5113c  stelem.ref
0x5113d  call     string [mscorlib]System.String::Concat(string[])
0x51142  call     T0x2B000003
0x51147  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5114c  leave.s  loc_5114E
0x5114e  ldloc.0
0x5114f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x51154  brtrue   loc_510AC
0x51159  leave.s  loc_51165
0x5115b  ldloc.0
0x5115c  brfalse.s loc_51164
0x5115e  ldloc.0
0x5115f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51164  endfinally
0x51165  leave.s  loc_51188
0x51167  stloc.s  5
0x51169  ldarg.0
0x5116a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.CacheManager::logger
0x5116f  dup
0x51170  brtrue.s loc_51175
0x51172  pop
0x51173  br.s     loc_51186
0x51175  ldloc.s  5
0x51177  ldstr    aUnableToDelete_2// "Unable to delete corrupt payloads."
0x5117c  call     T0x2B000003
0x51181  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x51186  rethrow
0x51188  ret
```
