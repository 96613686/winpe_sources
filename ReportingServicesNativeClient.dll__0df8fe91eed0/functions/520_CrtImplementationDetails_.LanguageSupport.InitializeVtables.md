# ::<CrtImplementationDetails>.LanguageSupport.InitializeVtables

- ea: `0x520`
- end: `0x548`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializeVtables`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x690`

## callees

- `0x920`
- `0xe10`

## string_xrefs

- `0x521`: `The C++ module failed to load during vtable initialization.\n`

## pseudocode

```c

```

## disassembly

```asm
0x520  ldarg.0
0x521  ldstr    aTheCModuleFail// "The C++ module failed to load during vt"...
0x526  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0x52b  pop
0x52c  ldc.i4.1
0x52d  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedVtables@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x532  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xi_vt_a
0x537  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xi_vt_z
0x53c  call     void _initterm_m(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfbegin, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfend)
0x541  ldc.i4.2
0x542  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedVtables@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x547  ret
```
