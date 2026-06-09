# Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString_3

- ea: `0x9ee0`
- end: `0x9f05`
- name: `Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString_3`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9eb0`
- `0x9ed0`

## callees

- `0x9ee0`
- `0x9f10`

## pseudocode

```c

```

## disassembly

```asm
0x9ee0  ldarg.0
0x9ee1  ldarg.1
0x9ee2  ldarg.2
0x9ee3  ldarg.3
0x9ee4  call     instance unsigned int8[] Microsoft.ReportingServices.Diagnostics.Encryption::Decrypt(int32 version, unsigned int8[] protectedData, string tag)
0x9ee9  stloc.0
0x9eea  ldloc.0
0x9eeb  brtrue.s loc_9EEF
0x9eed  ldnull
0x9eee  ret
0x9eef  ldloc.0
0x9ef0  ldlen
0x9ef1  brtrue.s loc_9EF9
0x9ef3  ldsfld   string [mscorlib]System.String::Empty
0x9ef8  ret
0x9ef9  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x9efe  ldloc.0
0x9eff  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x9f04  ret
```
