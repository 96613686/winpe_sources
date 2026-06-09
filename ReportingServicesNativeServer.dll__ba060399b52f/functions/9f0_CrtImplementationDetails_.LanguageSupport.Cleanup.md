# ::<CrtImplementationDetails>.LanguageSupport.Cleanup

- ea: `0x9f0`
- end: `0xa23`
- name: `::<CrtImplementationDetails>.LanguageSupport.Cleanup`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xa50`

## callees

- `0x3a0`
- `0x950`
- `0x990`
- `0x9f0`

## pseudocode

```c

```

## disassembly

```asm
0x9f0  ldsflda  int32 ?Count@AllDomains@<CrtImplementationDetails>@@2HA
0x9f5  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x9fa  ldc.i4.0
0x9fb  ceq
0x9fd  conv.u1
0x9fe  stloc.1
0x9ff  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.UninitializeAppDomain()
0xa04  ldloc.1
0xa05  brfalse.s loc_A0C
0xa07  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.UninitializeDefaultDomain()
0xa0c  leave.s  loc_A22
0xa0e  stloc.0
0xa0f  ldarg.1
0xa10  ldloc.0
0xa11  call     void <CrtImplementationDetails>.ThrowNestedModuleLoadException(class [mscorlib]System.Exception innerException, class [mscorlib]System.Exception nestedException)
0xa16  leave.s  loc_A22
0xa18  stloc.2
0xa19  ldarg.1
0xa1a  ldnull
0xa1b  call     void <CrtImplementationDetails>.ThrowNestedModuleLoadException(class [mscorlib]System.Exception innerException, class [mscorlib]System.Exception nestedException)
0xa20  leave.s  loc_A22
0xa22  ret
```
