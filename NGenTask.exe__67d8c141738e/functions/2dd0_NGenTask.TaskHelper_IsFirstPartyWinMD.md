# NGenTask.TaskHelper::IsFirstPartyWinMD

- ea: `0x2dd0`
- end: `0x2ded`
- name: `NGenTask.TaskHelper::IsFirstPartyWinMD`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x3c10`

## callees

- `0x2dd0`

## pseudocode

```c

```

## disassembly

```asm
0x2dd0  ldarg.0
0x2dd1  ldstr    aWinmd// ".winmd"
0x2dd6  ldc.i4.5
0x2dd7  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x2ddc  brtrue.s loc_2DE0
0x2dde  ldc.i4.0
0x2ddf  ret
0x2de0  ldarg.0
0x2de1  call     string [mscorlib]System.Environment::get_SystemDirectory()
0x2de6  ldc.i4.5
0x2de7  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2dec  ret
```
