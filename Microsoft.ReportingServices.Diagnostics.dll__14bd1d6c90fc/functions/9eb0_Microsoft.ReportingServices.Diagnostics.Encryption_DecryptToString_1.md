# Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString_1

- ea: `0x9eb0`
- end: `0x9ec6`
- name: `Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString_1`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9e90`
- `0x9ea0`

## callees

- `0x9eb0`
- `0x9ee0`

## pseudocode

```c

```

## disassembly

```asm
0x9eb0  ldarg.2
0x9eb1  brtrue.s loc_9EB5
0x9eb3  ldnull
0x9eb4  ret
0x9eb5  ldarg.2
0x9eb6  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x9ebb  stloc.0
0x9ebc  ldarg.0
0x9ebd  ldarg.1
0x9ebe  ldloc.0
0x9ebf  ldarg.3
0x9ec0  call     instance string Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString(int32 version, unsigned int8[] protectedData, string tag)
0x9ec5  ret
```
