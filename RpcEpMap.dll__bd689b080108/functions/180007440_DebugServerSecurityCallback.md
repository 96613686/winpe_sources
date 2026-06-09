# DebugServerSecurityCallback

- ea: `0x180007440`
- end: `0x1800074b2`
- name: `DebugServerSecurityCallback`
- size: `114`
- prototype: `RPC_STATUS __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007440`
- `0x180009990`
- `0x1800099b8`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x18000749f`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000749f`
- `RPCRT4!RpcImpersonateClient` at `0x180007462`
- `RPCRT4!RpcImpersonateClient` at `0x180007462`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000746c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000746c`

## pseudocode

```c
RPC_STATUS __fastcall DebugServerSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  RPC_STATUS result; // eax
  DWORD CurrentProcessId; // eax
  int v5; // edi
  void *v6; // [rsp+40h] [rbp+18h] BYREF
  void *SectionHandle; // [rsp+48h] [rbp+20h] BYREF

  SectionHandle = 0;
  v6 = 0;
  result = RpcImpersonateClient(Context);
  if ( !result )
  {
    CurrentProcessId = GetCurrentProcessId();
    v5 = OpenDbgSection(&SectionHandle, &v6, CurrentProcessId, 0);
    if ( !v5 )
      CloseDbgSection(SectionHandle, v6);
    RpcRevertToSelfEx(Context);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180007440  mov     [rsp+arg_0], rbx
0x180007445  push    rdi
0x180007446  sub     rsp, 20h
0x18000744a  mov     rcx, rdx; BindingHandle
0x18000744d  mov     [rsp+28h+SectionHandle], 0
0x180007456  mov     rbx, rdx
0x180007459  mov     [rsp+28h+arg_10], 0
0x180007462  call    cs:__imp_RpcImpersonateClient
0x180007468  test    eax, eax
0x18000746a  jnz     short loc_1800074A7
0x18000746c  call    cs:__imp_GetCurrentProcessId
0x180007472  xor     r9d, r9d; unsigned int *
0x180007475  lea     rdx, [rsp+28h+arg_10]; void **
0x18000747a  mov     r8d, eax; unsigned int
0x18000747d  lea     rcx, [rsp+28h+SectionHandle]; SectionHandle
0x180007482  call    ?OpenDbgSection@@YAJPEAPEAX0KPEAK@Z; OpenDbgSection(void * *,void * *,ulong,ulong *)
0x180007487  mov     edi, eax
0x180007489  test    eax, eax
0x18000748b  jnz     short loc_18000749C
0x18000748d  mov     rdx, [rsp+28h+arg_10]; void *
0x180007492  mov     rcx, [rsp+28h+SectionHandle]; void *
0x180007497  call    ?CloseDbgSection@@YAXPEAX0@Z; CloseDbgSection(void *,void *)
0x18000749c  mov     rcx, rbx; BindingHandle
0x18000749f  call    cs:__imp_RpcRevertToSelfEx
0x1800074a5  mov     eax, edi
0x1800074a7  mov     rbx, [rsp+28h+arg_0]
0x1800074ac  add     rsp, 20h
0x1800074b0  pop     rdi
0x1800074b1  retn
```
