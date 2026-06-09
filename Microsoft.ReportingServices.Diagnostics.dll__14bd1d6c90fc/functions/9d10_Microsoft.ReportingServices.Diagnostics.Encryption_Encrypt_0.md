# Microsoft.ReportingServices.Diagnostics.Encryption::Encrypt_0

- ea: `0x9d10`
- end: `0x9d29`
- name: `Microsoft.ReportingServices.Diagnostics.Encryption::Encrypt_0`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d30`

## callees

- `0x9cc0`
- `0x9d10`

## pseudocode

```c

```

## disassembly

```asm
0x9d10  ldarg.1
0x9d11  brtrue.s loc_9D15
0x9d13  ldnull
0x9d14  ret
0x9d15  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x9d1a  ldarg.1
0x9d1b  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x9d20  stloc.0
0x9d21  ldarg.0
0x9d22  ldloc.0
0x9d23  call     instance unsigned int8[] Microsoft.ReportingServices.Diagnostics.Encryption::Encrypt(unsigned int8[] data)
0x9d28  ret
```
