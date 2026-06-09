# ::<CrtImplementationDetails>.LanguageSupport.InitializePerProcess

- ea: `0x600`
- end: `0x634`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializePerProcess`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x690`

## callees

- `0x920`
- `0xc30`
- `0xe10`

## string_xrefs

- `0x601`: `The C++ module failed to load during process initialization.\n`

## pseudocode

```c

```

## disassembly

```asm
0x600  ldarg.0
0x601  ldstr    aTheCModuleFail_2// "The C++ module failed to load during pr"...
0x606  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0x60b  pop
0x60c  ldc.i4.1
0x60d  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedPerProcess@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x612  call     int32 _initatexit_m()
0x617  pop
0x618  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xc_mp_a
0x61d  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xc_mp_z
0x622  call     void _initterm_m(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfbegin, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfend)
0x627  ldc.i4.2
0x628  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedPerProcess@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x62d  ldc.i4.1
0x62e  stsfld   bool ?InitializedPerProcess@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x633  ret
```
