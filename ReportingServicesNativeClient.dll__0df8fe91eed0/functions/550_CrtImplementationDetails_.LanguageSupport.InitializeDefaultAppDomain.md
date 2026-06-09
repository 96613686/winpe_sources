# ::<CrtImplementationDetails>.LanguageSupport.InitializeDefaultAppDomain

- ea: `0x550`
- end: `0x562`
- name: `::<CrtImplementationDetails>.LanguageSupport.InitializeDefaultAppDomain`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x690`

## callees

- `0x4a0`
- `0x920`

## string_xrefs

- `0x551`: `The C++ module failed to load while attempting to initialize the default appdomain.\n`

## pseudocode

```c

```

## disassembly

```asm
0x550  ldarg.0
0x551  ldstr    aTheCModuleFail_0// "The C++ module failed to load while att"...
0x556  call     modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype 'gcroot<System::String ^>'* 'gcroot<System::String ^>.='(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype 'gcroot<System::String ^>'* t, string pDtor)
0x55b  pop
0x55c  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.DefaultDomain.Initialize()
0x561  ret
```
