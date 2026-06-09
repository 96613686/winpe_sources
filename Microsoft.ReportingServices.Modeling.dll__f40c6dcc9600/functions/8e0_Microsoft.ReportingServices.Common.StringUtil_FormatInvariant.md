# Microsoft.ReportingServices.Common.StringUtil::FormatInvariant

- ea: `0x8e0`
- end: `0x8ed`
- name: `Microsoft.ReportingServices.Common.StringUtil::FormatInvariant`
- size: `13`
- prototype: ``
- caller_count: `23`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x8b00`
- `0x9720`
- `0x9740`
- `0x9760`
- `0x9780`
- `0x97a0`
- `0xab80`
- `0xac90`
- `0xb060`
- `0x19dd0`
- `0x1d040`
- `0x1d750`
- `0x1d9e0`
- `0x22f40`
- `0x25e50`
- `0x293a0`
- `0x2c340`
- `0x2c360`
- `0x2d210`
- `0x2d250`
- `0x2d280`
- `0x2d2b0`
- `0x2d370`

## pseudocode

```c

```

## disassembly

```asm
0x8e0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e5  ldarg.0
0x8e6  ldarg.1
0x8e7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8ec  ret
```
