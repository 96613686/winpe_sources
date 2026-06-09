# Microsoft.VisualStudio.Setup.Services.ElevationRequestService::AddOptionalParameter

- ea: `0x1800`
- end: `0x181c`
- name: `Microsoft.VisualStudio.Setup.Services.ElevationRequestService::AddOptionalParameter`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1730`

## callees

- `0x1800`
- `0x1820`

## pseudocode

```c

```

## disassembly

```asm
0x1800  ldarg.2
0x1801  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1806  brtrue.s loc_181B
0x1808  ldarg.0
0x1809  ldstr    a01// " --{0} \"{1}\""
0x180e  ldarg.1
0x180f  ldarg.2
0x1810  call     string Microsoft.VisualStudio.Setup.Services.ElevationRequestService::SanitizeString(string value)
0x1815  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x181a  pop
0x181b  ret
```
