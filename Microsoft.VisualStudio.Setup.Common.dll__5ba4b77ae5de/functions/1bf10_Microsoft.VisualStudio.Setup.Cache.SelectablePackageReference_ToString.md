# Microsoft.VisualStudio.Setup.Cache.SelectablePackageReference::ToString

- ea: `0x1bf10`
- end: `0x1bf4b`
- name: `Microsoft.VisualStudio.Setup.Cache.SelectablePackageReference::ToString`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1b9c0`
- `0x1ba60`
- `0x1bb00`
- `0x1bb10`
- `0x1bed0`
- `0x1bf10`

## pseudocode

```c

```

## disassembly

```asm
0x1bf10  ldarg.0
0x1bf11  call     instance string Microsoft.VisualStudio.Setup.Cache.PackageReference::get_Id()
0x1bf16  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1bf1b  brtrue.s loc_1BF44
0x1bf1d  ldstr    a0Type1Selected// "{0}, Type = {1}, Selected = {2}"
0x1bf22  ldarg.0
0x1bf23  call     instance string Microsoft.VisualStudio.Setup.Cache.PackageReference::GetUniqueId()
0x1bf28  ldarg.0
0x1bf29  call     instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.Cache.PackageReference::get_Type()
0x1bf2e  box      Microsoft.VisualStudio.Setup.PackageType
0x1bf33  ldarg.0
0x1bf34  call     instance valuetype Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.Cache.SelectablePackageReference::get_SelectedState()
0x1bf39  box      Microsoft.VisualStudio.Setup.SelectedState
0x1bf3e  call     string [mscorlib]System.String::Format(string, object, object, object)
0x1bf43  ret
0x1bf44  ldarg.0
0x1bf45  call     instance string Microsoft.VisualStudio.Setup.Cache.PackageReference::ToString()
0x1bf4a  ret
```
