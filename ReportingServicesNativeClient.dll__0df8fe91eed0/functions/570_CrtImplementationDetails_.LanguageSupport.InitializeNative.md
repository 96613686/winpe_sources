# ::<CrtImplementationDetails>.LanguageSupport.InitializeNative

- ea: `0x570`
- end: `0x5f1`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializeNative`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x690`

## callees

- `0x1c0`
- `0x360`
- `0x570`
- `0x900`
- `0x920`
- `0xda0`
- `0xdd0`
- `0x1230`
- `0x1240`

## string_xrefs

- `0x571`: `The C++ module failed to load during native initialization.\n`

## pseudocode

```c

```

## disassembly

```asm
0x570  ldarg.0
0x571  ldstr    aTheCModuleFail_1// "The C++ module failed to load during na"...
0x576  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0x57b  pop
0x57c  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void __security_init_cookie()
0x581  ldc.i4.1
0x582  stsfld   bool ?InitializedNative@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x587  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool __scrt_is_safe_for_managed_code()
0x58c  brtrue.s loc_593
0x58e  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void abort()
0x593  ldsfld   valuetype __scrt_native_startup_state __scrt_current_native_startup_state
0x598  ldc.i4.1
0x599  bne.un.s loc_5A0
0x59b  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void abort()
0x5a0  ldsfld   valuetype __scrt_native_startup_state __scrt_current_native_startup_state
0x5a5  brtrue.s loc_5F0
0x5a7  ldc.i4.1
0x5a8  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedNative@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x5ad  ldc.i4.1
0x5ae  stsfld   valuetype __scrt_native_startup_state __scrt_current_native_startup_state
0x5b3  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AHXZ __xi_a
0x5b8  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AHXZ __xi_z
0x5bd  call     int32 _initterm_e(cdecl modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32(())* pfbegin, cdecl modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32(())* pfend)
0x5c2  brfalse.s loc_5CF
0x5c4  ldarg.0
0x5c5  call     string 'gcroot<System::String ^>..PE$AAVString@System@@'(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t)
0x5ca  call     void <CrtImplementationDetails>.ThrowModuleLoadException(string errorMessage)
0x5cf  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AXXZ __xc_a
0x5d4  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AXXZ __xc_z
0x5d9  call     void _initterm(cdecl modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void(())* pfbegin, cdecl modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void(())* pfend)
0x5de  ldc.i4.2
0x5df  stsfld   valuetype __scrt_native_startup_state __scrt_current_native_startup_state
0x5e4  ldc.i4.1
0x5e5  stsfld   bool ?InitializedNativeFromCCTOR@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x5ea  ldc.i4.2
0x5eb  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedNative@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x5f0  ret
```
