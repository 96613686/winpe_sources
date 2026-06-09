# ::<CrtImplementationDetails>.LanguageSupport.UninitializeDefaultDomain

- ea: `0x7a0`
- end: `0x7ca`
- name: `::<CrtImplementationDetails>.LanguageSupport.UninitializeDefaultDomain`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x7d0`
- `0x800`

## callees

- `0x2f0`
- `0x490`
- `0x770`
- `0x7a0`

## pseudocode

```c

```

## disassembly

```asm
0x7a0  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool <CrtImplementationDetails>.DefaultDomain.NeedsUninitialization()
0x7a5  brfalse.s loc_7C9
0x7a7  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x7ac  call     instance bool [mscorlib]System.AppDomain::IsDefaultAppDomain()
0x7b1  brfalse.s loc_7BD
0x7b3  ldc.i4.0
0x7b4  conv.i8
0x7b5  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 <CrtImplementationDetails>.LanguageSupport._UninitializeDefaultDomain(void* cookie)
0x7ba  pop
0x7bb  br.s     loc_7C9
0x7bd  ldsfld   int32** __unep@?_UninitializeDefaultDomain@LanguageSupport@<CrtImplementationDetails>@@$$FCAJPEAX@Z
0x7c2  ldc.i4.0
0x7c3  conv.i8
0x7c4  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.DoCallBackInDefaultDomain(cdecl modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32((void*)) function, void* cookie)
0x7c9  ret
```
