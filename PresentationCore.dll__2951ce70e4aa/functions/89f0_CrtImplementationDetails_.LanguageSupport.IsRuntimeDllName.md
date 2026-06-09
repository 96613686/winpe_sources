# ::<CrtImplementationDetails>.LanguageSupport.IsRuntimeDllName

- ea: `0x89f0`
- end: `0x8a51`
- name: `::<CrtImplementationDetails>.LanguageSupport.IsRuntimeDllName`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x8a60`

## callees

- `0x8970`
- `0x89f0`

## string_xrefs

- `0x89f1`: `ucrtbased.dll`

## pseudocode

```c

```

## disassembly

```asm
0x89f0  ldarg.1
0x89f1  ldstr    aUcrtbasedDll// "ucrtbased.dll"
0x89f6  ldc.i4.5
0x89f7  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x89fc  brfalse.s loc_8A00
0x89fe  ldc.i4.1
0x89ff  ret
0x8a00  ldarg.1
0x8a01  ldstr    aApiMsWinCrt// "api-ms-win-crt-"
0x8a06  ldc.i4.5
0x8a07  call     instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x8a0c  brfalse.s loc_8A1E
0x8a0e  ldarg.1
0x8a0f  ldstr    aDll// ".dll"
0x8a14  ldc.i4.5
0x8a15  call     instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x8a1a  brfalse.s loc_8A1E
0x8a1c  ldc.i4.1
0x8a1d  ret
0x8a1e  ldarg.0
0x8a1f  ldarg.1
0x8a20  ldstr    aMsvcp// "msvcp"
0x8a25  call     bool <CrtImplementationDetails>.LanguageSupport.IsDllNameCppSupportLike([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* value, string dllName, string prefix)
0x8a2a  brtrue.s loc_8A4C
0x8a2c  ldarg.0
0x8a2d  ldarg.1
0x8a2e  ldstr    aVcruntime// "vcruntime"
0x8a33  call     bool <CrtImplementationDetails>.LanguageSupport.IsDllNameCppSupportLike([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* value, string dllName, string prefix)
0x8a38  brtrue.s loc_8A4C
0x8a3a  ldarg.0
0x8a3b  ldarg.1
0x8a3c  ldstr    aConcrt// "concrt"
0x8a41  call     bool <CrtImplementationDetails>.LanguageSupport.IsDllNameCppSupportLike([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* value, string dllName, string prefix)
0x8a46  brtrue.s loc_8A4C
0x8a48  ldc.i4.0
0x8a49  stloc.0
0x8a4a  br.s     loc_8A4E
0x8a4c  ldc.i4.1
0x8a4d  stloc.0
0x8a4e  ldloc.0
0x8a4f  conv.u1
0x8a50  ret
```
