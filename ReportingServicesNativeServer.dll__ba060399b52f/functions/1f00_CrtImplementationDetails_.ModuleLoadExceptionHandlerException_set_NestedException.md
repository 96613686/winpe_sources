# <CrtImplementationDetails>.ModuleLoadExceptionHandlerException::set_NestedException

- ea: `0x1f00`
- end: `0x1f08`
- name: `<CrtImplementationDetails>.ModuleLoadExceptionHandlerException::set_NestedException`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1eb0`
- `0x1ee0`

## pseudocode

```c

```

## disassembly

```asm
0x1f00  ldarg.0
0x1f01  ldarg.1
0x1f02  stfld    class [mscorlib]System.Exception <CrtImplementationDetails>.ModuleLoadExceptionHandlerException::<backing_store>NestedException
0x1f07  ret
```
