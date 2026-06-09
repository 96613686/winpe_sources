# ::<CrtImplementationDetails>.LanguageSupport.UninitializeDefaultDomain

- ea: `0x990`
- end: `0x9ba`
- name: `::<CrtImplementationDetails>.LanguageSupport.UninitializeDefaultDomain`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x9c0`
- `0x9f0`

## callees

- `0x4e0`
- `0x680`
- `0x960`
- `0x990`

## pseudocode

```c

```

## disassembly

```asm
0x990  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool <CrtImplementationDetails>.DefaultDomain.NeedsUninitialization()
0x995  brfalse.s loc_9B9
0x997  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x99c  call     instance bool [mscorlib]System.AppDomain::IsDefaultAppDomain()
0x9a1  brfalse.s loc_9AD
0x9a3  ldc.i4.0
0x9a4  conv.i8
0x9a5  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 <CrtImplementationDetails>.LanguageSupport._UninitializeDefaultDomain(void* cookie)
0x9aa  pop
0x9ab  br.s     loc_9B9
0x9ad  ldsfld   int32** __unep@?_UninitializeDefaultDomain@LanguageSupport@<CrtImplementationDetails>@@$$FCAJPEAX@Z
0x9b2  ldc.i4.0
0x9b3  conv.i8
0x9b4  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.DoCallBackInDefaultDomain(cdecl modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32((void*)) function, void* cookie)
0x9b9  ret
```
