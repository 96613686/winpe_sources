# ::<CrtImplementationDetails>.LanguageSupport.InitializeVtables

- ea: `0x710`
- end: `0x738`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializeVtables`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x880`

## callees

- `0xb10`
- `0x1110`

## string_xrefs

- `0x711`: `The C++ module failed to load during vtable initialization.\n`

## pseudocode

```c

```

## disassembly

```asm
0x710  ldarg.0
0x711  ldstr    aTheCModuleFail// "The C++ module failed to load during vt"...
0x716  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0x71b  pop
0x71c  ldc.i4.1
0x71d  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedVtables@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x722  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xi_vt_a
0x727  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xi_vt_z
0x72c  call     void _initterm_m(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfbegin, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfend)
0x731  ldc.i4.2
0x732  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedVtables@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x737  ret
```
