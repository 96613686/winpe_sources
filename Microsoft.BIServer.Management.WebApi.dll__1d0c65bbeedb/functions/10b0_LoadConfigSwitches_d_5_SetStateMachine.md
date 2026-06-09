# <LoadConfigSwitches>d__5::SetStateMachine

- ea: `0x10b0`
- end: `0x10bd`
- name: `<LoadConfigSwitches>d__5::SetStateMachine`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c

```

## disassembly

```asm
0x10b0  ldarg.0
0x10b1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>> <LoadConfigSwitches>d__5::<>t__builder
0x10b6  ldarg.1
0x10b7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>>::SetStateMachine(class [mscorlib]System.Runtime.CompilerServices.IAsyncStateMachine)
0x10bc  ret
```
