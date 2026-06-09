# ::<CrtImplementationDetails>.LanguageSupport.InitializeUninitializer

- ea: `0x860`
- end: `0x87e`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializeUninitializer`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x880`

## callees

- `0x3d0`
- `0xb10`

## string_xrefs

- `0x861`: `The C++ module failed to load during registration for the unload events.\n`

## pseudocode

```c

```

## disassembly

```asm
0x860  ldarg.0
0x861  ldstr    aTheCModuleFail_4// "The C++ module failed to load during re"...
0x866  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0x86b  pop
0x86c  ldnull
0x86d  ldftn    void <CrtImplementationDetails>.LanguageSupport.DomainUnload(object A_0, class [mscorlib]System.EventArgs A_1)
0x873  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x878  call     void <CrtImplementationDetails>.RegisterModuleUninitializer(class [mscorlib]System.EventHandler handler)
0x87d  ret
```
