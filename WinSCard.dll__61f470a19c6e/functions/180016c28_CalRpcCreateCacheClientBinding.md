# CalRpcCreateCacheClientBinding

- ea: `0x180016c28`
- end: `0x180016c9b`
- name: `CalRpcCreateCacheClientBinding`
- size: `115`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e8f8`

## callees

- `0x180016c28`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x180016c54`
- `RPCRT4!RpcBindingCreateW` at `0x180016c54`
- `RPCRT4!RpcBindingBind` at `0x180016c6c`
- `RPCRT4!RpcBindingBind` at `0x180016c6c`
- `RPCRT4!RpcBindingFree` at `0x180016c81`
- `RPCRT4!RpcBindingFree` at `0x180016c81`

## pseudocode

```c
__int64 __fastcall CalRpcCreateCacheClientBinding(RPC_BINDING_HANDLE *Binding)
{
  unsigned int v2; // edi

  *Binding = 0;
  v2 = RpcBindingCreateW(&CALRPC_Template, &CALRPC_Security, &CALRPC_Options, Binding);
  if ( v2 || (v2 = RpcBindingBind(0, *Binding, qword_1800343D0)) != 0 )
  {
    if ( *Binding )
    {
      RpcBindingFree(Binding);
      *Binding = 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180016c28  mov     [rsp+arg_0], rbx
0x180016c2d  push    rdi
0x180016c2e  sub     rsp, 20h
0x180016c32  mov     rbx, rcx
0x180016c35  mov     qword ptr [rcx], 0
0x180016c3c  mov     r9, rcx; Binding
0x180016c3f  lea     r8, ?CALRPC_Options@@3U_RPC_BINDING_HANDLE_OPTIONS_V1@@A; Options
0x180016c46  lea     rcx, ?CALRPC_Template@@3U_RPC_BINDING_HANDLE_TEMPLATE_V1_W@@A; Template
0x180016c4d  lea     rdx, ?CALRPC_Security@@3U_RPC_BINDING_HANDLE_SECURITY_V1_W@@A; Security
0x180016c54  call    cs:__imp_RpcBindingCreateW
0x180016c5a  mov     edi, eax
0x180016c5c  test    eax, eax
0x180016c5e  jnz     short loc_180016C78
0x180016c60  mov     rdx, [rbx]; Binding
0x180016c63  lea     r8, qword_1800343D0; IfSpec
0x180016c6a  xor     ecx, ecx; pAsync
0x180016c6c  call    cs:__imp_RpcBindingBind
0x180016c72  mov     edi, eax
0x180016c74  test    eax, eax
0x180016c76  jz      short loc_180016C8E
0x180016c78  cmp     qword ptr [rbx], 0
0x180016c7c  jz      short loc_180016C8E
0x180016c7e  mov     rcx, rbx; Binding
0x180016c81  call    cs:__imp_RpcBindingFree
0x180016c87  mov     qword ptr [rbx], 0
0x180016c8e  mov     rbx, [rsp+28h+arg_0]
0x180016c93  mov     eax, edi
0x180016c95  add     rsp, 20h
0x180016c99  pop     rdi
0x180016c9a  retn
```
