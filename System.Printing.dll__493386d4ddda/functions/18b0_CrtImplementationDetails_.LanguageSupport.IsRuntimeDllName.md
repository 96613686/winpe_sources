# ::<CrtImplementationDetails>.LanguageSupport.IsRuntimeDllName

- ea: `0x18b0`
- end: `0x1911`
- name: `::<CrtImplementationDetails>.LanguageSupport.IsRuntimeDllName`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1920`

## callees

- `0x1830`
- `0x18b0`

## string_xrefs

- `0x18b1`: `ucrtbased.dll`

## pseudocode

```c

```

## disassembly

```asm
0x18b0  ldarg.1
0x18b1  ldstr    aUcrtbasedDll// "ucrtbased.dll"
0x18b6  ldc.i4.5
0x18b7  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x18bc  brfalse.s loc_18C0
0x18be  ldc.i4.1
0x18bf  ret
0x18c0  ldarg.1
0x18c1  ldstr    aApiMsWinCrt// "api-ms-win-crt-"
0x18c6  ldc.i4.5
0x18c7  call     instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x18cc  brfalse.s loc_18DE
0x18ce  ldarg.1
0x18cf  ldstr    aDll// ".dll"
0x18d4  ldc.i4.5
0x18d5  call     instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x18da  brfalse.s loc_18DE
0x18dc  ldc.i4.1
0x18dd  ret
0x18de  ldarg.0
0x18df  ldarg.1
0x18e0  ldstr    aMsvcp// "msvcp"
0x18e5  call     bool <CrtImplementationDetails>.LanguageSupport.IsDllNameCppSupportLike([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* value, string dllName, string prefix)
0x18ea  brtrue.s loc_190C
0x18ec  ldarg.0
0x18ed  ldarg.1
0x18ee  ldstr    aVcruntime// "vcruntime"
0x18f3  call     bool <CrtImplementationDetails>.LanguageSupport.IsDllNameCppSupportLike([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* value, string dllName, string prefix)
0x18f8  brtrue.s loc_190C
0x18fa  ldarg.0
0x18fb  ldarg.1
0x18fc  ldstr    aConcrt// "concrt"
0x1901  call     bool <CrtImplementationDetails>.LanguageSupport.IsDllNameCppSupportLike([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* value, string dllName, string prefix)
0x1906  brtrue.s loc_190C
0x1908  ldc.i4.0
0x1909  stloc.0
0x190a  br.s     loc_190E
0x190c  ldc.i4.1
0x190d  stloc.0
0x190e  ldloc.0
0x190f  conv.u1
0x1910  ret
```
