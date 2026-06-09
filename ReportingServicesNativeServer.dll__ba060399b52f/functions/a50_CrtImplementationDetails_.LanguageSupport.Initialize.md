# ::<CrtImplementationDetails>.LanguageSupport.Initialize

- ea: `0xa50`
- end: `0xab3`
- name: `::<CrtImplementationDetails>.LanguageSupport.Initialize`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0xac0`

## callees

- `0x3c0`
- `0x880`
- `0x9f0`
- `0xa50`
- `0xaf0`
- `0xb10`

## pseudocode

```c

```

## disassembly

```asm
0xa50  ldc.i4.0
0xa51  stloc.0
0xa52  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0xa57  ldarg.0
0xa58  ldstr    aTheCModuleFail_5// "The C++ module failed to load.\n"
0xa5d  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0xa62  pop
0xa63  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0xa68  leave.s  loc_A78
0xa6a  ldsflda  int32 ?Count@AllDomains@<CrtImplementationDetails>@@2HA
0xa6f  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0xa74  pop
0xa75  ldc.i4.1
0xa76  stloc.0
0xa77  endfinally
0xa78  ldarg.0
0xa79  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.LanguageSupport._Initialize(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* cookie)
0xa7e  leave.s  loc_AB2
0xa80  stloc.1
0xa81  ldloc.0
0xa82  brfalse.s loc_A8B
0xa84  ldarg.0
0xa85  ldloc.1
0xa86  call     void <CrtImplementationDetails>.LanguageSupport.Cleanup(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* innerException, class [mscorlib]System.Exception t)
0xa8b  ldarg.0
0xa8c  call     string 'gcroot<System::String ^>..PE$AAVString@System@@'(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t)
0xa91  ldloc.1
0xa92  call     void <CrtImplementationDetails>.ThrowModuleLoadException(string errorMessage, class [mscorlib]System.Exception innerException)
0xa97  leave.s  loc_AB2
0xa99  stloc.2
0xa9a  ldloc.0
0xa9b  brfalse.s loc_AA4
0xa9d  ldarg.0
0xa9e  ldnull
0xa9f  call     void <CrtImplementationDetails>.LanguageSupport.Cleanup(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* innerException, class [mscorlib]System.Exception t)
0xaa4  ldarg.0
0xaa5  call     string 'gcroot<System::String ^>..PE$AAVString@System@@'(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t)
0xaaa  ldnull
0xaab  call     void <CrtImplementationDetails>.ThrowModuleLoadException(string errorMessage, class [mscorlib]System.Exception innerException)
0xab0  leave.s  loc_AB2
0xab2  ret
```
