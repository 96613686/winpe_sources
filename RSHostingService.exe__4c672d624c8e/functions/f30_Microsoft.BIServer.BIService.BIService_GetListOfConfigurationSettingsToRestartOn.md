# Microsoft.BIServer.BIService.BIService::GetListOfConfigurationSettingsToRestartOn

- ea: `0xf30`
- end: `0xfa8`
- name: `Microsoft.BIServer.BIService.BIService::GetListOfConfigurationSettingsToRestartOn`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe50`

## callees

- `0xf30`

## pseudocode

```c

```

## disassembly

```asm
0xf30  ldarg.0
0xf31  ldstr    aRestartonchang// "restartOnChangesTo"
0xf36  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0xf3b  brtrue.s loc_F44
0xf3d  ldsfld   string [mscorlib]System.String::Empty
0xf42  br.s     loc_F4F
0xf44  ldarg.0
0xf45  ldstr    aRestartonchang// "restartOnChangesTo"
0xf4a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0xf4f  ldc.i4.1
0xf50  newarr   [mscorlib]System.Char
0xf55  dup
0xf56  ldc.i4.0
0xf57  ldc.i4.s 0x2C
0xf59  stelem.i2
0xf5a  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xf5f  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__39_0
0xf64  dup
0xf65  brtrue.s loc_F7E
0xf67  pop
0xf68  ldsfld   class <>c <>c::<>9
0xf6d  ldftn    instance string <>c::<GetListOfConfigurationSettingsToRestartOn>b__39_0(string x)
0xf73  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0xf78  dup
0xf79  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__39_0
0xf7e  call     T0x2B00000E
0xf83  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__39_1
0xf88  dup
0xf89  brtrue.s loc_FA2
0xf8b  pop
0xf8c  ldsfld   class <>c <>c::<>9
0xf91  ldftn    instance bool <>c::<GetListOfConfigurationSettingsToRestartOn>b__39_1(string x)
0xf97  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xf9c  dup
0xf9d  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__39_1
0xfa2  call     T0x2B000004
0xfa7  ret
```
