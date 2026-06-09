# Microsoft.VisualStudio.Setup.Services.ElevationRequestService::AddBooleanParameter

- ea: `0x17e0`
- end: `0x17f1`
- name: `Microsoft.VisualStudio.Setup.Services.ElevationRequestService::AddBooleanParameter`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1730`

## callees

- `0x17e0`

## pseudocode

```c

```

## disassembly

```asm
0x17e0  ldarg.2
0x17e1  brfalse.s loc_17F0
0x17e3  ldarg.0
0x17e4  ldstr    a0// " --{0}"
0x17e9  ldarg.1
0x17ea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x17ef  pop
0x17f0  ret
```
