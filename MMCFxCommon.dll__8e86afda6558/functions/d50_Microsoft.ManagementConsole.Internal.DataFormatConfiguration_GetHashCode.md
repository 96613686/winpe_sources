# Microsoft.ManagementConsole.Internal.DataFormatConfiguration::GetHashCode

- ea: `0xd50`
- end: `0xd5c`
- name: `Microsoft.ManagementConsole.Internal.DataFormatConfiguration::GetHashCode`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xcc0`

## pseudocode

```c

```

## disassembly

```asm
0xd50  ldarg.0
0xd51  call     instance string Microsoft.ManagementConsole.Internal.DataFormatConfiguration::get_ClipboardFormatId()
0xd56  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xd5b  ret
```
