# Microsoft.ManagementConsole.SnapInRegistration::BuildPath

- ea: `0x3ac0`
- end: `0x3adc`
- name: `Microsoft.ManagementConsole.SnapInRegistration::BuildPath`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3ae0`

## callees

- `0x3ac0`

## pseudocode

```c

```

## disassembly

```asm
0x3ac0  ldarg.2
0x3ac1  brfalse.s loc_3ADA
0x3ac3  ldarg.1
0x3ac4  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x3ac9  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x3ace  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x3ad3  ldarg.0
0x3ad4  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3ad9  ret
0x3ada  ldarg.0
0x3adb  ret
```
