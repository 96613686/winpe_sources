# System.Deployment.Application.ReferenceIdentity::get_PublicKeyToken

- ea: `0xdd70`
- end: `0xdd7c`
- name: `System.Deployment.Application.ReferenceIdentity::get_PublicKeyToken`
- size: `12`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x26d30`
- `0x26ea0`

## callees

- `0xdd10`

## string_xrefs

- `0xdd71`: `publicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0xdd70  ldarg.0
0xdd71  ldstr    aPublickeytoken// "publicKeyToken"
0xdd76  call     instance string System.Deployment.Application.ReferenceIdentity::get_Item(string name)
0xdd7b  ret
```
