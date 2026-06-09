# CalRpcSCardSecurityCallback(void *,void *)

- ea: `0x18002f5f0`
- end: `0x18002f643`
- name: `?CalRpcSCardSecurityCallback@@YAJPEAX0@Z`
- size: `83`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002f5f0`
- `0x18002f6f8`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18002f635`
- `RPCRT4!RpcRevertToSelf` at `0x18002f635`
- `RPCRT4!RpcImpersonateClient` at `0x18002f61c`
- `RPCRT4!RpcImpersonateClient` at `0x18002f61c`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18002f60a`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18002f60a`

## pseudocode

```c
__int64 __fastcall CalRpcSCardSecurityCallback(void *a1, void *a2)
{
  unsigned int v2; // ebx
  unsigned int ClientLocalFlag; // [rsp+40h] [rbp+18h] BYREF

  ClientLocalFlag = 0;
  v2 = 5;
  if ( !I_RpcBindingIsClientLocal(0, &ClientLocalFlag) && ClientLocalFlag && !RpcImpersonateClient(0) )
  {
    v2 = CheckCallerPrivilege() != 0 ? 5 : 0;
    RpcRevertToSelf();
  }
  return v2;
}

```

## disassembly

```asm
0x18002f5f0  push    rbx
0x18002f5f2  sub     rsp, 20h
0x18002f5f6  lea     rdx, [rsp+28h+ClientLocalFlag]; ClientLocalFlag
0x18002f5fb  mov     [rsp+28h+ClientLocalFlag], 0
0x18002f603  xor     ecx, ecx; BindingHandle
0x18002f605  mov     ebx, 5
0x18002f60a  call    cs:__imp_I_RpcBindingIsClientLocal
0x18002f610  test    eax, eax
0x18002f612  jnz     short loc_18002F63B
0x18002f614  cmp     [rsp+28h+ClientLocalFlag], eax
0x18002f618  jz      short loc_18002F63B
0x18002f61a  xor     ecx, ecx; BindingHandle
0x18002f61c  call    cs:__imp_RpcImpersonateClient
0x18002f622  test    eax, eax
0x18002f624  jnz     short loc_18002F63B
0x18002f626  call    ?CheckCallerPrivilege@@YAKXZ; CheckCallerPrivilege(void)
0x18002f62b  xor     ecx, ecx
0x18002f62d  sub     ecx, eax
0x18002f62f  neg     ecx
0x18002f631  sbb     eax, eax
0x18002f633  and     ebx, eax
0x18002f635  call    cs:__imp_RpcRevertToSelf
0x18002f63b  mov     eax, ebx
0x18002f63d  add     rsp, 20h
0x18002f641  pop     rbx
0x18002f642  retn
```
