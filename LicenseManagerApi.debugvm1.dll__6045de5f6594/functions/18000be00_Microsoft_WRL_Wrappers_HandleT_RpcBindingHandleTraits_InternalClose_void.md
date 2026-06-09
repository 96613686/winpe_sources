# Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(void)

- ea: `0x18000be00`
- end: `0x18000be1f`
- name: `?InternalClose@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ`
- size: `31`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180006b58`
- `0x18000e9e0`
- `0x18000f060`
- `0x18000f7d0`
- `0x18000fdd0`
- `0x180010420`
- `0x180010710`
- `0x1800109a0`
- `0x180010cc0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000be12`
- `RPCRT4!RpcBindingFree` at `0x18000be12`

## pseudocode

```c
char __fastcall Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(__int64 a1)
{
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp+8h] BYREF

  Binding = *(RPC_BINDING_HANDLE *)(a1 + 8);
  RpcBindingFree(&Binding);
  return 1;
}

```

## disassembly

```asm
0x18000be00  sub     rsp, 28h
0x18000be04  mov     rax, [rcx+8]
0x18000be08  lea     rcx, [rsp+28h+Binding]; Binding
0x18000be0d  mov     [rsp+28h+Binding], rax
0x18000be12  call    cs:__imp_RpcBindingFree
0x18000be18  mov     al, 1
0x18000be1a  add     rsp, 28h
0x18000be1e  retn
```
