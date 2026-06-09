# <CrtImplementationDetails>.ModuleLoadExceptionHandlerException::set_NestedException

- ea: `0x28f0`
- end: `0x28f8`
- name: `<CrtImplementationDetails>.ModuleLoadExceptionHandlerException::set_NestedException`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x28a0`
- `0x28d0`

## pseudocode

```c

```

## disassembly

```asm
0x28f0  ldarg.0
0x28f1  ldarg.1
0x28f2  stfld    class [mscorlib]System.Exception <CrtImplementationDetails>.ModuleLoadExceptionHandlerException::<backing_store>NestedException
0x28f7  ret
```
