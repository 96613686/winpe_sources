# ::<CrtImplementationDetails>.LanguageSupport.InitializePerAppDomain

- ea: `0x19b0`
- end: `0x19fd`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializePerAppDomain`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1a20`

## callees

- `0x1920`
- `0x1b60`
- `0x1eb0`
- `0x2050`
- `0x2130`
- `0x2210`
- `0x22e0`
- `0x23a0`
- `0x2460`

## string_xrefs

- `0x19b1`: `The C++ module failed to load during appdomain initialization.\n`

## pseudocode

```c

```

## disassembly

```asm
0x19b0  ldarg.0
0x19b1  ldstr    aTheCModuleFail_0// "The C++ module failed to load during ap"...
0x19b6  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string value)
0x19bb  pop
0x19bc  ldc.i4.1
0x19bd  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedPerAppDomain@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x19c2  ldarg.0
0x19c3  call     void <CrtImplementationDetails>.LanguageSupport.ForceLoadRuntimeApis(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CrtImplementationDetails>.LanguageSupport* A_0)
0x19c8  call     void __scrt_initialize_stdio_msvcrt_compatibility_mode()
0x19cd  call     void __scrt_initialize_default_local_stdio_options()
0x19d2  call     void __scrt_initialize_printf_standard_rounding_mode()
0x19d7  call     void __scrt_initialize_iso_stdio_wide_specifier_mode()
0x19dc  call     void __scrt_initialize_legacy_stdio_wide_specifier_mode()
0x19e1  call     int32 _initatexit_app_domain()
0x19e6  pop
0x19e7  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.__xc_ma_a$$BY0A@Q6MPEBXXZ __xc_ma_a
0x19ec  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.__xc_ma_z$$BY0A@Q6MPEBXXZ __xc_ma_z
0x19f1  call     void _initterm_m(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfbegin, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfend)
0x19f6  ldc.i4.2
0x19f7  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedPerAppDomain@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x19fc  ret
```
