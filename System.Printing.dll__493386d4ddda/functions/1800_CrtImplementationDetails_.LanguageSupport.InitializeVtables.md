# ::<CrtImplementationDetails>.LanguageSupport.InitializeVtables

- ea: `0x1800`
- end: `0x1828`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializeVtables`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1a20`

## callees

- `0x1b60`
- `0x2050`

## string_xrefs

- `0x1801`: `The C++ module failed to load during vtable initialization.\n`

## pseudocode

```c

```

## disassembly

```asm
0x1800  ldarg.0
0x1801  ldstr    aTheCModuleFail// "The C++ module failed to load during vt"...
0x1806  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string value)
0x180b  pop
0x180c  ldc.i4.1
0x180d  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedVtables@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x1812  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.__xi_vt_a$$BY0A@Q6MPEBXXZ __xi_vt_a
0x1817  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.__xi_vt_z$$BY0A@Q6MPEBXXZ __xi_vt_z
0x181c  call     void _initterm_m(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfbegin, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfend)
0x1821  ldc.i4.2
0x1822  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedVtables@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x1827  ret
```
