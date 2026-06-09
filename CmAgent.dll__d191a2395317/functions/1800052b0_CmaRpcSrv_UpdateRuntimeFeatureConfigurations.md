# CmaRpcSrv_UpdateRuntimeFeatureConfigurations

- ea: `0x1800052b0`
- end: `0x1800052e1`
- name: `CmaRpcSrv_UpdateRuntimeFeatureConfigurations`
- size: `49`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, const struct _CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *, Container::Manager::Agent::Core *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180020000`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800052cd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800052cd`

## pseudocode

```c
RPC_STATUS __fastcall CmaRpcSrv_UpdateRuntimeFeatureConfigurations(
        PRPC_ASYNC_STATE pAsync,
        const struct _CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *a2,
        Container::Manager::Agent::Core *a3)
{
  int Reply; // [rsp+48h] [rbp+20h] BYREF

  Reply = Container::Manager::Agent::Core::UpdateRuntimeFeatureConfigurations(a3, a2);
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x1800052b0  push    rbx
0x1800052b2  sub     rsp, 20h
0x1800052b6  mov     rbx, rcx
0x1800052b9  mov     rcx, r8; this
0x1800052bc  call    ?UpdateRuntimeFeatureConfigurations@Core@Agent@Manager@Container@@YAJAEBU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@@Z; Container::Manager::Agent::Core::UpdateRuntimeFeatureConfigurations(_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION const &)
0x1800052c1  mov     [rsp+28h+Reply], eax
0x1800052c5  lea     rdx, [rsp+28h+Reply]; Reply
0x1800052ca  mov     rcx, rbx; pAsync
0x1800052cd  call    cs:__imp_RpcAsyncCompleteCall
0x1800052d4  nop     dword ptr [rax+rax+00h]
0x1800052d9  nop
0x1800052da  add     rsp, 20h
0x1800052de  pop     rbx
0x1800052df  retn
```
