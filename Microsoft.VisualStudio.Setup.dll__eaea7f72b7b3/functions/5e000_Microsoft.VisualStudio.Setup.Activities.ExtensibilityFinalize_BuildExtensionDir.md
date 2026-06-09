# Microsoft.VisualStudio.Setup.Activities.ExtensibilityFinalize::BuildExtensionDir

- ea: `0x5e000`
- end: `0x5e03e`
- name: `Microsoft.VisualStudio.Setup.Activities.ExtensibilityFinalize::BuildExtensionDir`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5dfd0`

## callees

- `0x10ef0`
- `0x11980`
- `0x1cfd0`
- `0x5e000`
- `0x600c0`

## string_xrefs

- `0x5e018`: `[extensionDir]`
- `0x5e027`: `ExtensionDir property not found in the extended properties of the VSIX payload. This indicates an authoring error.`

## pseudocode

```c

```

## disassembly

```asm
0x5e000  ldarg.0
0x5e001  call     instance class Microsoft.VisualStudio.Setup.IEngineContext Microsoft.VisualStudio.Setup.Activities.RunProductCommand::get_EngineContext()
0x5e006  callvirt instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.IEngineContext::get_Properties()
0x5e00b  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.VariableCollection::ToDictionary()
0x5e010  dup
0x5e011  ldarg.1
0x5e012  ldarg.2
0x5e013  call     void Microsoft.VisualStudio.Setup.Extensions::AppendExtendedProperties(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPackage, string installDir)
0x5e018  ldstr    aExtensiondir_0// "[extensionDir]"
0x5e01d  stloc.0
0x5e01e  dup
0x5e01f  ldloc.0
0x5e020  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x5e025  brtrue.s loc_5E032
0x5e027  ldstr    aExtensiondirPr// "ExtensionDir property not found in the "...
0x5e02c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5e031  throw
0x5e032  ldloc.0
0x5e033  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x5e038  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x5e03d  ret
```
