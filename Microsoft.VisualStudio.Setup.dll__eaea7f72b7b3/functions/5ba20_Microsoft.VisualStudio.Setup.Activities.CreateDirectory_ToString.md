# Microsoft.VisualStudio.Setup.Activities.CreateDirectory::ToString

- ea: `0x5ba20`
- end: `0x5ba79`
- name: `Microsoft.VisualStudio.Setup.Activities.CreateDirectory::ToString`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5ba00`
- `0x5ba10`
- `0x5ba20`

## string_xrefs

- `0x5ba35`: `Creating directory '`
- `0x5ba63`: `Creating directory '`
- `0x5ba46`: `' from template '`

## pseudocode

```c

```

## disassembly

```asm
0x5ba20  ldarg.0
0x5ba21  call     instance string Microsoft.VisualStudio.Setup.Activities.CreateDirectory::get_Template()
0x5ba26  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5ba2b  brtrue.s loc_5BA63
0x5ba2d  ldc.i4.5
0x5ba2e  newarr   [mscorlib]System.String
0x5ba33  dup
0x5ba34  ldc.i4.0
0x5ba35  ldstr    aCreatingDirect_1// "Creating directory '"
0x5ba3a  stelem.ref
0x5ba3b  dup
0x5ba3c  ldc.i4.1
0x5ba3d  ldarg.0
0x5ba3e  call     instance string Microsoft.VisualStudio.Setup.Activities.CreateDirectory::get_Path()
0x5ba43  stelem.ref
0x5ba44  dup
0x5ba45  ldc.i4.2
0x5ba46  ldstr    aFromTemplate// "' from template '"
0x5ba4b  stelem.ref
0x5ba4c  dup
0x5ba4d  ldc.i4.3
0x5ba4e  ldarg.0
0x5ba4f  call     instance string Microsoft.VisualStudio.Setup.Activities.CreateDirectory::get_Template()
0x5ba54  stelem.ref
0x5ba55  dup
0x5ba56  ldc.i4.4
0x5ba57  ldstr    asc_7FEB6// "'"
0x5ba5c  stelem.ref
0x5ba5d  call     string [mscorlib]System.String::Concat(string[])
0x5ba62  ret
0x5ba63  ldstr    aCreatingDirect_1// "Creating directory '"
0x5ba68  ldarg.0
0x5ba69  call     instance string Microsoft.VisualStudio.Setup.Activities.CreateDirectory::get_Path()
0x5ba6e  ldstr    asc_7FEB6// "'"
0x5ba73  call     string [mscorlib]System.String::Concat(string, string, string)
0x5ba78  ret
```
