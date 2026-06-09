# SetRestrictRemoteClients

- ea: `0x1800071e0`
- end: `0x180007290`
- name: `SetRestrictRemoteClients`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007094`
- `0x1800071e0`

## import_xrefs

- `RPCRT4!I_RpcSystemFunction001` at `0x180007226`
- `RPCRT4!I_RpcSystemFunction001` at `0x180007226`
- `RPCRT4!RpcServerRegisterIf2` at `0x18000726a`
- `RPCRT4!RpcServerRegisterIf2` at `0x18000726a`
- `RPCRT4!RpcRaiseException` at `0x18000727e`
- `RPCRT4!RpcRaiseException` at `0x18000727e`
- `RPCRT4!RpcServerUnregisterIf` at `0x180007212`
- `RPCRT4!RpcServerUnregisterIf` at `0x180007212`
- `RPCRT4!RpcImpersonateClient` at `0x1800071ee`
- `RPCRT4!RpcImpersonateClient` at `0x1800071ee`
- `RPCRT4!RpcRevertToSelf` at `0x180007272`
- `RPCRT4!RpcRevertToSelf` at `0x180007272`

## pseudocode

```c
RPC_STATUS __fastcall SetRestrictRemoteClients(__int64 a1, int a2)
{
  RPC_STATUS v3; // ebx
  RPC_STATUS v4; // eax
  RPC_STATUS result; // eax

  v3 = RpcImpersonateClient(0);
  if ( !v3 )
  {
    v3 = IsCurrentUserAdmin();
    if ( !v3 )
    {
      v3 = RpcServerUnregisterIf(&unk_18000C890, 0, 1u);
      if ( !v3 )
      {
        I_RpcSystemFunction001(3);
        if ( a2 )
          v4 = RpcServerRegisterIf2(
                 &unk_18000C890,
                 0,
                 0,
                 0x10u,
                 0x4D2u,
                 0x1000u,
                 (RPC_IF_CALLBACK_FN *)&RemoteEpmpServerSecurityCallback);
        else
          v4 = RpcServerRegisterIf2(&unk_18000C890, 0, 0, 0, 0x4D2u, 0x1000u, 0);
        v3 = v4;
      }
    }
  }
  result = RpcRevertToSelf();
  if ( v3 )
    RpcRaiseException(v3);
  return result;
}

```

## disassembly

```asm
0x1800071e0  mov     [rsp+arg_0], rbx
0x1800071e5  push    rdi
0x1800071e6  sub     rsp, 40h
0x1800071ea  xor     ecx, ecx; BindingHandle
0x1800071ec  mov     edi, edx
0x1800071ee  call    cs:__imp_RpcImpersonateClient
0x1800071f4  mov     ebx, eax
0x1800071f6  test    eax, eax
0x1800071f8  jnz     short loc_180007272
0x1800071fa  call    IsCurrentUserAdmin
0x1800071ff  mov     ebx, eax
0x180007201  test    eax, eax
0x180007203  jnz     short loc_180007272
0x180007205  xor     edx, edx; MgrTypeUuid
0x180007207  lea     r8d, [rax+1]; WaitForCallsToComplete
0x18000720b  lea     rcx, unk_18000C890; IfSpec
0x180007212  call    cs:__imp_RpcServerUnregisterIf
0x180007218  mov     ebx, eax
0x18000721a  test    eax, eax
0x18000721c  jnz     short loc_180007272
0x18000721e  mov     edx, edi
0x180007220  lea     ecx, [rax+3]
0x180007223  xor     r8d, r8d
0x180007226  call    cs:__imp_I_RpcSystemFunction001
0x18000722c  xor     r8d, r8d; MgrEpv
0x18000722f  lea     rcx, unk_18000C890; IfSpec
0x180007236  xor     edx, edx; MgrTypeUuid
0x180007238  test    edi, edi
0x18000723a  jz      short loc_18000724E
0x18000723c  lea     rax, RemoteEpmpServerSecurityCallback
0x180007243  mov     [rsp+48h+IfCallbackFn], rax
0x180007248  lea     r9d, [rbx+10h]
0x18000724c  jmp     short loc_18000725A
0x18000724e  mov     [rsp+48h+IfCallbackFn], 0; IfCallbackFn
0x180007257  xor     r9d, r9d; Flags
0x18000725a  mov     [rsp+48h+MaxRpcSize], 1000h; MaxRpcSize
0x180007262  mov     [rsp+48h+MaxCalls], 4D2h; MaxCalls
0x18000726a  call    cs:__imp_RpcServerRegisterIf2
0x180007270  mov     ebx, eax
0x180007272  call    cs:__imp_RpcRevertToSelf
0x180007278  test    ebx, ebx
0x18000727a  jz      short loc_180007285
0x18000727c  mov     ecx, ebx; exception
0x18000727e  call    cs:__imp_RpcRaiseException
0x180007284  int     3; Trap to Debugger
0x180007285  mov     rbx, [rsp+48h+arg_0]
0x18000728a  add     rsp, 40h
0x18000728e  pop     rdi
0x18000728f  retn
```
