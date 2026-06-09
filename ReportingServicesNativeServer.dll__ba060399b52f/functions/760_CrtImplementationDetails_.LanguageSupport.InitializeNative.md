# ::<CrtImplementationDetails>.LanguageSupport.InitializeNative

- ea: `0x760`
- end: `0x7e1`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializeNative`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x880`

## callees

- `0x3b0`
- `0x550`
- `0x760`
- `0xaf0`
- `0xb10`
- `0x10a0`
- `0x10d0`
- `0x1390`
- `0x13a0`

## string_xrefs

- `0x761`: `The C++ module failed to load during native initialization.\n`

## pseudocode

```c

```

## disassembly

```asm
0x760  ldarg.0
0x761  ldstr    aTheCModuleFail_1// "The C++ module failed to load during na"...
0x766  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0x76b  pop
0x76c  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void __security_init_cookie()
0x771  ldc.i4.1
0x772  stsfld   bool ?InitializedNative@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x777  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool __scrt_is_safe_for_managed_code()
0x77c  brtrue.s loc_783
0x77e  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void abort()
0x783  ldsfld   valuetype __scrt_native_startup_state __scrt_current_native_startup_state
0x788  ldc.i4.1
0x789  bne.un.s loc_790
0x78b  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void abort()
0x790  ldsfld   valuetype __scrt_native_startup_state __scrt_current_native_startup_state
0x795  brtrue.s loc_7E0
0x797  ldc.i4.1
0x798  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedNative@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x79d  ldc.i4.1
0x79e  stsfld   valuetype __scrt_native_startup_state __scrt_current_native_startup_state
0x7a3  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AHXZ __xi_a
0x7a8  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AHXZ __xi_z
0x7ad  call     int32 _initterm_e(cdecl modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32(())* pfbegin, cdecl modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32(())* pfend)
0x7b2  brfalse.s loc_7BF
0x7b4  ldarg.0
0x7b5  call     string 'gcroot<System::String ^>..PE$AAVString@System@@'(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t)
0x7ba  call     void <CrtImplementationDetails>.ThrowModuleLoadException(string errorMessage)
0x7bf  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AXXZ __xc_a
0x7c4  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AXXZ __xc_z
0x7c9  call     void _initterm(cdecl modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void(())* pfbegin, cdecl modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void(())* pfend)
0x7ce  ldc.i4.2
0x7cf  stsfld   valuetype __scrt_native_startup_state __scrt_current_native_startup_state
0x7d4  ldc.i4.1
0x7d5  stsfld   bool ?InitializedNativeFromCCTOR@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x7da  ldc.i4.2
0x7db  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedNative@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x7e0  ret
```
