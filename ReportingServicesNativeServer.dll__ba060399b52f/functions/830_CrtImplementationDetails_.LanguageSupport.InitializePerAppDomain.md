# ::<CrtImplementationDetails>.LanguageSupport.InitializePerAppDomain

- ea: `0x830`
- end: `0x85e`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializePerAppDomain`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x880`

## callees

- `0xb10`
- `0xf70`
- `0x1110`

## string_xrefs

- `0x831`: `The C++ module failed to load during appdomain initialization.\n`

## pseudocode

```c

```

## disassembly

```asm
0x830  ldarg.0
0x831  ldstr    aTheCModuleFail_3// "The C++ module failed to load during ap"...
0x836  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0x83b  pop
0x83c  ldc.i4.1
0x83d  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedPerAppDomain@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x842  call     int32 _initatexit_app_domain()
0x847  pop
0x848  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xc_ma_a
0x84d  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xc_ma_z
0x852  call     void _initterm_m(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfbegin, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfend)
0x857  ldc.i4.2
0x858  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedPerAppDomain@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x85d  ret
```
