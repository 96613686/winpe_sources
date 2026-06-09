# <CrtImplementationDetails>.ModuleLoadExceptionHandlerException::get_NestedException

- ea: `0x28e0`
- end: `0x28e7`
- name: `<CrtImplementationDetails>.ModuleLoadExceptionHandlerException::get_NestedException`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x2900`
- `0x29a0`

## pseudocode

```c

```

## disassembly

```asm
0x28e0  ldarg.0
0x28e1  ldfld    class [mscorlib]System.Exception <CrtImplementationDetails>.ModuleLoadExceptionHandlerException::<backing_store>NestedException
0x28e6  ret
```
