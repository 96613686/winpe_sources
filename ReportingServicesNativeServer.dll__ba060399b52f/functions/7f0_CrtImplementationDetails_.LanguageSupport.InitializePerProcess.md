# ::<CrtImplementationDetails>.LanguageSupport.InitializePerProcess

- ea: `0x7f0`
- end: `0x824`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializePerProcess`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x880`

## callees

- `0xb10`
- `0xf10`
- `0x1110`

## string_xrefs

- `0x7f1`: `The C++ module failed to load during process initialization.\n`

## pseudocode

```c

```

## disassembly

```asm
0x7f0  ldarg.0
0x7f1  ldstr    aTheCModuleFail_2// "The C++ module failed to load during pr"...
0x7f6  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0x7fb  pop
0x7fc  ldc.i4.1
0x7fd  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedPerProcess@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x802  call     int32 _initatexit_m()
0x807  pop
0x808  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xc_mp_a
0x80d  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xc_mp_z
0x812  call     void _initterm_m(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfbegin, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(())* pfend)
0x817  ldc.i4.2
0x818  stsfld   valuetype <CrtImplementationDetails>.Progress ?InitializedPerProcess@CurrentDomain@<CrtImplementationDetails>@@$$Q2W4Progress@2@A
0x81d  ldc.i4.1
0x81e  stsfld   bool ?InitializedPerProcess@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x823  ret
```
