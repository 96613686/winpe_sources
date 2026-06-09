# Microsoft.VisualStudio.Setup.CheckForUpdatesResult::Deconstruct

- ea: `0x2910`
- end: `0x2932`
- name: `Microsoft.VisualStudio.Setup.CheckForUpdatesResult::Deconstruct`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2640`
- `0x2660`
- `0x2680`
- `0x26a0`

## pseudocode

```c

```

## disassembly

```asm
0x2910  ldarg.1
0x2911  ldarg.0
0x2912  call     instance bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_EngineUpdateRequired()
0x2917  stind.i1
0x2918  ldarg.2
0x2919  ldarg.0
0x291a  call     instance string Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_OpcUrl()
0x291f  stind.ref
0x2920  ldarg.3
0x2921  ldarg.0
0x2922  call     instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_OpcVersion()
0x2927  stind.ref
0x2928  ldarg.s  4
0x292a  ldarg.0
0x292b  call     instance int32 Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_UpdateResultCode()
0x2930  stind.i4
0x2931  ret
```
