# ::<CrtImplementationDetails>.LanguageSupport.InitializeDefaultAppDomain

- ea: `0x740`
- end: `0x752`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializeDefaultAppDomain`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x880`

## callees

- `0x690`
- `0xb10`

## string_xrefs

- `0x741`: `The C++ module failed to load while attempting to initialize the default appdomain.\n`

## pseudocode

```c

```

## disassembly

```asm
0x740  ldarg.0
0x741  ldstr    aTheCModuleFail_0// "The C++ module failed to load while att"...
0x746  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0x74b  pop
0x74c  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.DefaultDomain.Initialize()
0x751  ret
```
