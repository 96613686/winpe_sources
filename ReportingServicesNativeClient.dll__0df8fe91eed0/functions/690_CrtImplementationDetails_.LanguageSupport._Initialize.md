# ::<CrtImplementationDetails>.LanguageSupport._Initialize

- ea: `0x690`
- end: `0x751`
- name: `::<CrtImplementationDetails>.LanguageSupport._Initialize`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x860`

## callees

- `0x460`
- `0x520`
- `0x550`
- `0x570`
- `0x600`
- `0x640`
- `0x670`
- `0x690`
- `0x1200`
- `0x1220`

## pseudocode

```c

```

## disassembly

```asm
0x690  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x695  call     instance bool [mscorlib]System.AppDomain::IsDefaultAppDomain()
0x69a  stsfld   bool ?IsDefaultDomain@CurrentDomain@<CrtImplementationDetails>@@$$Q2_NA
0x69f  ldsfld   bool ?IsDefaultDomain@CurrentDomain@<CrtImplementationDetails>@@$$Q2_NA
0x6a4  ldc.i4.0
0x6a5  bne.un.s loc_6AE
0x6a7  ldsfld   bool ?Entered@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x6ac  br.s     loc_6AF
0x6ae  ldc.i4.1
0x6af  stsfld   bool ?Entered@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x6b4  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void* _getFiberPtrId()
0x6b9  stloc.s  4
0x6bb  ldc.i4.0
0x6bc  stloc.3
0x6bd  ldc.i4.0
0x6be  stloc.0
0x6bf  ldc.i4.0
0x6c0  stloc.1
0x6c1  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x6c6  ldloc.0
0x6c7  brtrue.s loc_6FA
0x6c9  leave.s  loc_6EB
0x6cb  ldsflda  void* __scrt_native_startup_lock
0x6d0  ldloc.s  4
0x6d2  ldc.i4.0
0x6d3  conv.i8
0x6d4  call     int64 [mscorlib]System.Threading.Interlocked::CompareExchange(int64&, int64, int64)
0x6d9  stloc.2
0x6da  ldloc.2
0x6db  brtrue.s loc_6E1
0x6dd  ldc.i4.1
0x6de  stloc.0
0x6df  br.s     loc_6EA
0x6e1  ldloc.2
0x6e2  ldloc.s  4
0x6e4  bne.un.s loc_6EA
0x6e6  ldc.i4.1
0x6e7  stloc.3
0x6e8  ldc.i4.1
0x6e9  stloc.0
0x6ea  endfinally
0x6eb  ldloc.0
0x6ec  brtrue.s loc_6F8
0x6ee  ldc.i4   0x3E8
0x6f3  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void Sleep(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 nativeString)
0x6f8  br.s     loc_6C6
0x6fa  ldarg.0
0x6fb  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.InitializeVtables(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0x700  ldsfld   bool ?IsDefaultDomain@CurrentDomain@<CrtImplementationDetails>@@$$Q2_NA
0x705  brfalse.s loc_715
0x707  ldarg.0
0x708  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.InitializeNative(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0x70d  ldarg.0
0x70e  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.InitializePerProcess(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0x713  br.s     loc_722
0x715  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool <CrtImplementationDetails>.DefaultDomain.NeedsInitialization()
0x71a  ldc.i4.0
0x71b  bne.un.s loc_720
0x71d  ldloc.1
0x71e  br.s     loc_721
0x720  ldc.i4.1
0x721  stloc.1
0x722  leave.s  loc_735
0x724  ldloc.3
0x725  brtrue.s loc_734
0x727  ldsflda  void* __scrt_native_startup_lock
0x72c  ldc.i4.0
0x72d  conv.i8
0x72e  call     int64 [mscorlib]System.Threading.Interlocked::Exchange(int64&, int64)
0x733  pop
0x734  endfinally
0x735  ldloc.1
0x736  brfalse.s loc_73E
0x738  ldarg.0
0x739  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.InitializeDefaultAppDomain(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0x73e  ldarg.0
0x73f  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.InitializePerAppDomain(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0x744  ldc.i4.1
0x745  stsfld   int32 ?Initialized@CurrentDomain@<CrtImplementationDetails>@@$$Q2HA
0x74a  ldarg.0
0x74b  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport.InitializeUninitializer(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0x750  ret
```
