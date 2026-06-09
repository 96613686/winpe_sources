# System.Deployment.Application.DefinitionIdentity::ToPKTGroupId

- ea: `0xdbf0`
- end: `0xdc16`
- name: `System.Deployment.Application.DefinitionIdentity::ToPKTGroupId`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0xe080`

## callees

- `0xda40`
- `0xdc90`

## string_xrefs

- `0xdc09`: `publicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0xdbf0  ldarg.0
0xdbf1  call     instance object System.Deployment.Application.DefinitionIdentity::Clone()
0xdbf6  castclass System.Deployment.Application.DefinitionIdentity
0xdbfb  stloc.0
0xdbfc  ldloc.0
0xdbfd  ldstr    aVersion_0// "version"
0xdc02  ldnull
0xdc03  callvirt instance void System.Deployment.Application.DefinitionIdentity::set_Item(string name, string value)
0xdc08  ldloc.0
0xdc09  ldstr    aPublickeytoken// "publicKeyToken"
0xdc0e  ldnull
0xdc0f  callvirt instance void System.Deployment.Application.DefinitionIdentity::set_Item(string name, string value)
0xdc14  ldloc.0
0xdc15  ret
```
