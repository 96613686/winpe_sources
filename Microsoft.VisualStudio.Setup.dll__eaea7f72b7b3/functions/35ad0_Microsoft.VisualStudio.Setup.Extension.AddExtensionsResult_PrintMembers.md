# Microsoft.VisualStudio.Setup.Extension.AddExtensionsResult::PrintMembers

- ea: `0x35ad0`
- end: `0x35b22`
- name: `Microsoft.VisualStudio.Setup.Extension.AddExtensionsResult::PrintMembers`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x35a90`

## callees

- `0x35a30`
- `0x35a50`
- `0x35a70`

## string_xrefs

- `0x35ad6`: `AddedExtensions = `
- `0x35aef`: `, ExistingExtensions = `
- `0x35b08`: `, SupersededExtensions = `

## pseudocode

```c

```

## disassembly

```asm
0x35ad0  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x35ad5  ldarg.1
0x35ad6  ldstr    aAddedextension// "AddedExtensions = "
0x35adb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35ae0  pop
0x35ae1  ldarg.1
0x35ae2  ldarg.0
0x35ae3  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<class [System]System.Uri, class Microsoft.VisualStudio.Setup.Extension.ExtensionContents> Microsoft.VisualStudio.Setup.Extension.AddExtensionsResult::get_AddedExtensions()
0x35ae8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x35aed  pop
0x35aee  ldarg.1
0x35aef  ldstr    aExistingextens// ", ExistingExtensions = "
0x35af4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35af9  pop
0x35afa  ldarg.1
0x35afb  ldarg.0
0x35afc  call     instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Extension.AddExtensionsResult::get_ExistingExtensions()
0x35b01  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x35b06  pop
0x35b07  ldarg.1
0x35b08  ldstr    aSupersededexte// ", SupersededExtensions = "
0x35b0d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35b12  pop
0x35b13  ldarg.1
0x35b14  ldarg.0
0x35b15  call     instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Extension.AddExtensionsResult::get_SupersededExtensions()
0x35b1a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x35b1f  pop
0x35b20  ldc.i4.1
0x35b21  ret
```
