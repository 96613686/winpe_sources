# ::<CrtImplementationDetails>.LanguageSupport.InitializePerAppDomain

- ea: `0x640`
- end: `0x66e`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializePerAppDomain`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x690`

## callees

- `0x920`
- `0xc70`
- `0xe10`

## string_xrefs

- `0x641`: `The C++ module failed to load during appdomain initialization.\n`

## pseudocode

```c

```

## disassembly

```asm
0x640  ldarg.0
0x641  ldstr    aTheCModuleFail_3// "The C++ module failed to load during ap"...
0x646  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0x64b  pop
0x64c  ldc.i4.1
0x64d  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedPerAppDomain@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x652  call     int32 _initatexit_app_domain()
0x657  pop
0x658  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xc_ma_a
0x65d  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xc_ma_z
0x662  call     void _initterm_m(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfbegin, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfend)
0x667  ldc.i4.2
0x668  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedPerAppDomain@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x66d  ret
```
