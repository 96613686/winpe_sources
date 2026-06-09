# ::<CrtImplementationDetails>.LanguageSupport._Initialize

- ea: `0x880`
- end: `0x941`
- name: `::<CrtImplementationDetails>.LanguageSupport._Initialize`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0xa50`

## callees

- `0x650`
- `0x710`
- `0x740`
- `0x760`
- `0x7f0`
- `0x830`
- `0x860`
- `0x880`
- `0x1360`
- `0x1380`

## pseudocode

```c

```

## disassembly

```asm
0x880  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x885  call     instance bool [mscorlib]System.AppDomain::IsDefaultAppDomain()
0x88a  stsfld   bool ?IsDefaultDomain@CurrentDomain@<CrtImplementationDetails>@@$$Q2_NA
0x88f  ldsfld   bool ?IsDefaultDomain@CurrentDomain@<CrtImplementationDetails>@@$$Q2_NA
0x894  ldc.i4.0
0x895  bne.un.s loc_89E
0x897  ldsfld   bool ?Entered@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x89c  br.s     loc_89F
0x89e  ldc.i4.1
0x89f  stsfld   bool ?Entered@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x8a4  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void* _getFiberPtrId()
0x8a9  stloc.s  4
0x8ab  ldc.i4.0
0x8ac  stloc.3
0x8ad  ldc.i4.0
0x8ae  stloc.0
0x8af  ldc.i4.0
0x8b0  stloc.1
0x8b1  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x8b6  ldloc.0
0x8b7  brtrue.s loc_8EA
0x8b9  leave.s  loc_8DB
0x8bb  ldsflda  void* __scrt_native_startup_lock
0x8c0  ldloc.s  4
0x8c2  ldc.i4.0
0x8c3  conv.i8
0x8c4  call     int64 [mscorlib]System.Threading.Interlocked::CompareExchange(int64&, int64, int64)
0x8c9  stloc.2
0x8ca  ldloc.2
0x8cb  brtrue.s loc_8D1
0x8cd  ldc.i4.1
0x8ce  stloc.0
0x8cf  br.s     loc_8DA
0x8d1  ldloc.2
0x8d2  ldloc.s  4
0x8d4  bne.un.s loc_8DA
0x8d6  ldc.i4.1
0x8d7  stloc.3
0x8d8  ldc.i4.1
0x8d9  stloc.0
0x8da  endfinally
0x8db  ldloc.0
0x8dc  brtrue.s loc_8E8
0x8de  ldc.i4   0x3E8
0x8e3  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void Sleep(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 rpcEndpointName)
0x8e8  br.s     loc_8B6
0x8ea  ldarg.0
0x8eb  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.InitializeVtables(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0x8f0  ldsfld   bool ?IsDefaultDomain@CurrentDomain@<CrtImplementationDetails>@@$$Q2_NA
0x8f5  brfalse.s loc_905
0x8f7  ldarg.0
0x8f8  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.InitializeNative(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0x8fd  ldarg.0
0x8fe  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.InitializePerProcess(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0x903  br.s     loc_912
0x905  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool <CrtImplementationDetails>.DefaultDomain.NeedsInitialization()
0x90a  ldc.i4.0
0x90b  bne.un.s loc_910
0x90d  ldloc.1
0x90e  br.s     loc_911
0x910  ldc.i4.1
0x911  stloc.1
0x912  leave.s  loc_925
0x914  ldloc.3
0x915  brtrue.s loc_924
0x917  ldsflda  void* __scrt_native_startup_lock
0x91c  ldc.i4.0
0x91d  conv.i8
0x91e  call     int64 [mscorlib]System.Threading.Interlocked::Exchange(int64&, int64)
0x923  pop
0x924  endfinally
0x925  ldloc.1
0x926  brfalse.s loc_92E
0x928  ldarg.0
0x929  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.InitializeDefaultAppDomain(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0x92e  ldarg.0
0x92f  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.InitializePerAppDomain(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0x934  ldc.i4.1
0x935  stsfld   int32 ?Initialized@CurrentDomain@<CrtImplementationDetails>@@$$Q2HA
0x93a  ldarg.0
0x93b  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.InitializeUninitializer(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0x940  ret
```
