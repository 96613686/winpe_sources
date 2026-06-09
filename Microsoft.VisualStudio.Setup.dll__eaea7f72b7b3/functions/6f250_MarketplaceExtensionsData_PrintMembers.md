# MarketplaceExtensionsData::PrintMembers

- ea: `0x6f250`
- end: `0x6f2a2`
- name: `MarketplaceExtensionsData::PrintMembers`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x6f210`

## callees

- `0x6f1b0`
- `0x6f1d0`
- `0x6f1f0`

## string_xrefs

- `0x6f288`: `, FailedExtensions = `
- `0x6f256`: `InstalledExtensions = `
- `0x6f26f`: `, InstalledExtensionDisplayNames = `

## pseudocode

```c

```

## disassembly

```asm
0x6f250  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x6f255  ldarg.1
0x6f256  ldstr    aInstalledexten// "InstalledExtensions = "
0x6f25b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6f260  pop
0x6f261  ldarg.1
0x6f262  ldarg.0
0x6f263  call     instance class [System.Core]System.Collections.Generic.HashSet`1<string> MarketplaceExtensionsData::get_InstalledExtensions()
0x6f268  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x6f26d  pop
0x6f26e  ldarg.1
0x6f26f  ldstr    aInstalledexten_0// ", InstalledExtensionDisplayNames = "
0x6f274  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6f279  pop
0x6f27a  ldarg.1
0x6f27b  ldarg.0
0x6f27c  call     instance class [System.Core]System.Collections.Generic.HashSet`1<string> MarketplaceExtensionsData::get_InstalledExtensionDisplayNames()
0x6f281  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x6f286  pop
0x6f287  ldarg.1
0x6f288  ldstr    aFailedextensio// ", FailedExtensions = "
0x6f28d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6f292  pop
0x6f293  ldarg.1
0x6f294  ldarg.0
0x6f295  call     instance class [System.Core]System.Collections.Generic.HashSet`1<string> MarketplaceExtensionsData::get_FailedExtensions()
0x6f29a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x6f29f  pop
0x6f2a0  ldc.i4.1
0x6f2a1  ret
```
