# Microsoft.VisualStudio.Setup.Package::SetToken_0

- ea: `0xa000`
- end: `0xa014`
- name: `Microsoft.VisualStudio.Setup.Package::SetToken_0`
- size: `20`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9ab0`
- `0x9ad0`
- `0x9af0`
- `0x9b10`
- `0x9b30`
- `0x9b50`

## callees

- `0xa000`
- `0xc170`

## pseudocode

```c

```

## disassembly

```asm
0xa000  ldarg.3
0xa001  brfalse.s loc_A00B
0xa003  ldarg.2
0xa004  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa009  starg.s  2
0xa00b  ldarg.0
0xa00c  ldarg.1
0xa00d  ldarg.2
0xa00e  call     T0x2B00004A
0xa013  ret
```
