# Microsoft.ReportingServices.Modeling.SRErrors::XmlValidationException_MessageWithLineInfo

- ea: `0x242f0`
- end: `0x24308`
- name: `Microsoft.ReportingServices.Modeling.SRErrors::XmlValidationException_MessageWithLineInfo`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x9ba0`

## callees

- `0x38e90`

## string_xrefs

- `0x242f0`: `XmlValidationException_MessageWithLineInfo`

## pseudocode

```c

```

## disassembly

```asm
0x242f0  ldstr    aXmlvalidatione// "XmlValidationException_MessageWithLineI"...
0x242f5  ldarg.0
0x242f6  ldarg.1
0x242f7  box      [mscorlib]System.Int32
0x242fc  ldarg.2
0x242fd  box      [mscorlib]System.Int32
0x24302  call     string Keys::GetString(string key, object arg0, object arg1, object arg2)
0x24307  ret
```
