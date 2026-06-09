# CmaRpcSrv_UpdateHotPatches

- ea: `0x180005270`
- end: `0x1800052a1`
- name: `CmaRpcSrv_UpdateHotPatches`
- size: `49`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, struct _CMA_HOT_PATCH_MIRRORING_INFORMATION *, Container::Manager::Agent::Core *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18001fb70`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18000528d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000528d`

## pseudocode

```c
RPC_STATUS __fastcall CmaRpcSrv_UpdateHotPatches(
        PRPC_ASYNC_STATE pAsync,
        struct _CMA_HOT_PATCH_MIRRORING_INFORMATION *a2,
        Container::Manager::Agent::Core *a3,
        __int64 a4)
{
  int Reply; // [rsp+48h] [rbp+20h] BYREF

  Reply = Container::Manager::Agent::Core::UpdateHotPatches(a3, a2, (__int64)a3, a4);
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x180005270  push    rbx
0x180005272  sub     rsp, 20h
0x180005276  mov     rbx, rcx
0x180005279  mov     rcx, r8; this
0x18000527c  call    ?UpdateHotPatches@Core@Agent@Manager@Container@@YAJAEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@Z; Container::Manager::Agent::Core::UpdateHotPatches(_CMA_HOT_PATCH_MIRRORING_INFORMATION &)
0x180005281  mov     [rsp+28h+Reply], eax
0x180005285  lea     rdx, [rsp+28h+Reply]; Reply
0x18000528a  mov     rcx, rbx; pAsync
0x18000528d  call    cs:__imp_RpcAsyncCompleteCall
0x180005294  nop     dword ptr [rax+rax+00h]
0x180005299  nop
0x18000529a  add     rsp, 20h
0x18000529e  pop     rbx
0x18000529f  retn
```
