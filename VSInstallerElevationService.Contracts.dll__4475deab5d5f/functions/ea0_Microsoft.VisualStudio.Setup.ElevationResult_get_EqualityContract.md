# Microsoft.VisualStudio.Setup.ElevationResult::get_EqualityContract

- ea: `0xea0`
- end: `0xeab`
- name: `Microsoft.VisualStudio.Setup.ElevationResult::get_EqualityContract`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0xfb0`
- `0x1000`

## pseudocode

```c

```

## disassembly

```asm
0xea0  ldtoken  Microsoft.VisualStudio.Setup.ElevationResult
0xea5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xeaa  ret
```
