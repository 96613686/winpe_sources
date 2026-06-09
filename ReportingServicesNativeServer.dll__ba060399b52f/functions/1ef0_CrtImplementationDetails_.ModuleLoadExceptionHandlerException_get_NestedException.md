# <CrtImplementationDetails>.ModuleLoadExceptionHandlerException::get_NestedException

- ea: `0x1ef0`
- end: `0x1ef7`
- name: `<CrtImplementationDetails>.ModuleLoadExceptionHandlerException::get_NestedException`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1f10`
- `0x1fb0`

## pseudocode

```c

```

## disassembly

```asm
0x1ef0  ldarg.0
0x1ef1  ldfld    class [mscorlib]System.Exception <CrtImplementationDetails>.ModuleLoadExceptionHandlerException::<backing_store>NestedException
0x1ef6  ret
```
