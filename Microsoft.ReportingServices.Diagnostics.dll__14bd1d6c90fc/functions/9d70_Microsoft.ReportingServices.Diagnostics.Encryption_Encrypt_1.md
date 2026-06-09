# Microsoft.ReportingServices.Diagnostics.Encryption::Encrypt_1

- ea: `0x9d70`
- end: `0x9d8a`
- name: `Microsoft.ReportingServices.Diagnostics.Encryption::Encrypt_1`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9c20`
- `0x9d50`

## callees

- `0x9d70`
- `0x9d90`

## pseudocode

```c

```

## disassembly

```asm
0x9d70  ldnull
0x9d71  stloc.0
0x9d72  ldarg.1
0x9d73  brfalse.s loc_9D81
0x9d75  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x9d7a  ldarg.1
0x9d7b  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x9d80  stloc.0
0x9d81  ldarg.0
0x9d82  ldloc.0
0x9d83  ldarg.2
0x9d84  call     instance unsigned int8[] Microsoft.ReportingServices.Diagnostics.Encryption::Encrypt(unsigned int8[] unprotectedData, string tag)
0x9d89  ret
```
