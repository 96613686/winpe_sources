# System.Deployment.Application.DefinitionIdentity::get_PublicKeyToken

- ea: `0xdaa0`
- end: `0xdaac`
- name: `System.Deployment.Application.DefinitionIdentity::get_PublicKeyToken`
- size: `12`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0xe080`
- `0x105d0`
- `0x10650`
- `0x13d80`
- `0x161b0`
- `0x1efe0`
- `0x20220`
- `0x25a00`
- `0x25bc0`

## callees

- `0xda30`

## string_xrefs

- `0xdaa1`: `publicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0xdaa0  ldarg.0
0xdaa1  ldstr    aPublickeytoken// "publicKeyToken"
0xdaa6  call     instance string System.Deployment.Application.DefinitionIdentity::get_Item(string name)
0xdaab  ret
```
