# Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken

- ea: `0xc170`
- end: `0xc17c`
- name: `Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken`
- size: `12`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x4970`
- `0xa000`
- `0xa3a0`
- `0xa3c0`
- `0xa3e0`
- `0xa400`
- `0xa420`
- `0xa440`
- `0xa570`
- `0xa800`
- `0xa980`
- `0xac00`

## callees

- `0xc170`

## pseudocode

```c

```

## disassembly

```asm
0xc170  ldarg.0
0xc171  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc176  brfalse.s loc_C17A
0xc178  ldnull
0xc179  ret
0xc17a  ldarg.0
0xc17b  ret
```
