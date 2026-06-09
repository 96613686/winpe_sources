# Microsoft.VisualStudio.Setup.ElevationRequest::get_EqualityContract

- ea: `0xa20`
- end: `0xa2b`
- name: `Microsoft.VisualStudio.Setup.ElevationRequest::get_EqualityContract`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc60`
- `0xd30`

## pseudocode

```c

```

## disassembly

```asm
0xa20  ldtoken  Microsoft.VisualStudio.Setup.ElevationRequest
0xa25  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa2a  ret
```
