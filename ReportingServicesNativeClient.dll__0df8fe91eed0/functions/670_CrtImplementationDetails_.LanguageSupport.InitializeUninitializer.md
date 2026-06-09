# ::<CrtImplementationDetails>.LanguageSupport.InitializeUninitializer

- ea: `0x670`
- end: `0x68e`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializeUninitializer`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x690`

## callees

- `0x1e0`
- `0x920`

## string_xrefs

- `0x671`: `The C++ module failed to load during registration for the unload events.\n`

## pseudocode

```c

```

## disassembly

```asm
0x670  ldarg.0
0x671  ldstr    aTheCModuleFail_4// "The C++ module failed to load during re"...
0x676  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0x67b  pop
0x67c  ldnull
0x67d  ldftn    void <CrtImplementationDetails>.LanguageSupport.DomainUnload(object A_0, class [mscorlib]System.EventArgs A_1)
0x683  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x688  call     void <CrtImplementationDetails>.RegisterModuleUninitializer(class [mscorlib]System.EventHandler handler)
0x68d  ret
```
