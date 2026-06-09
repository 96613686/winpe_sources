# Microsoft.ReportingServices.Modeling.SRErrors::ObjectDescriptor_TypeAndName

- ea: `0x24380`
- end: `0x2438d`
- name: `Microsoft.ReportingServices.Modeling.SRErrors::ObjectDescriptor_TypeAndName`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x25560`

## callees

- `0x38e70`

## string_xrefs

- `0x24380`: `ObjectDescriptor_TypeAndName`

## pseudocode

```c

```

## disassembly

```asm
0x24380  ldstr    aObjectdescript// "ObjectDescriptor_TypeAndName"
0x24385  ldarg.0
0x24386  ldarg.1
0x24387  call     string Keys::GetString(string key, object arg0, object arg1)
0x2438c  ret
```
