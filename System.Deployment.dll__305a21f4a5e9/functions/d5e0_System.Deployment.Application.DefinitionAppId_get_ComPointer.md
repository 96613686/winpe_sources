# System.Deployment.Application.DefinitionAppId::get_ComPointer

- ea: `0xd5e0`
- end: `0xd5e7`
- name: `System.Deployment.Application.DefinitionAppId::get_ComPointer`
- size: `7`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xd660`
- `0xe290`
- `0xe920`
- `0xeb60`
- `0xf160`
- `0xf1a0`
- `0xf280`
- `0xf340`
- `0xf380`
- `0xf610`
- `0xf990`
- `0xf9d0`
- `0x1f1c0`
- `0x287b0`
- `0x28930`

## pseudocode

```c

```

## disassembly

```asm
0xd5e0  ldarg.0
0xd5e1  ldfld    class System.Deployment.Internal.Isolation.IDefinitionAppId System.Deployment.Application.DefinitionAppId::_idComPtr
0xd5e6  ret
```
