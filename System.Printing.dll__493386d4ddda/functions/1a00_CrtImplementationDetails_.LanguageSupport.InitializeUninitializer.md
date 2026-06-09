# ::<CrtImplementationDetails>.LanguageSupport.InitializeUninitializer

- ea: `0x1a00`
- end: `0x1a1e`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializeUninitializer`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1a20`

## callees

- `0x1780`
- `0x1b60`

## string_xrefs

- `0x1a01`: `The C++ module failed to load during registration for the unload events.\n`

## pseudocode

```c

```

## disassembly

```asm
0x1a00  ldarg.0
0x1a01  ldstr    aTheCModuleFail_1// "The C++ module failed to load during re"...
0x1a06  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string value)
0x1a0b  pop
0x1a0c  ldnull
0x1a0d  ldftn    void <CrtImplementationDetails>.LanguageSupport.DomainUnload(object A_0, class [mscorlib]System.EventArgs A_1)
0x1a13  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1a18  call     void <CrtImplementationDetails>.RegisterModuleUninitializer(class [mscorlib]System.EventHandler handler)
0x1a1d  ret
```
