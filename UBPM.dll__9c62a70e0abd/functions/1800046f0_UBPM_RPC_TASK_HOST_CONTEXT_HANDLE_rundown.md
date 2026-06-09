# UBPM_RPC_TASK_HOST_CONTEXT_HANDLE_rundown

- ea: `0x1800046f0`
- end: `0x180004762`
- name: `UBPM_RPC_TASK_HOST_CONTEXT_HANDLE_rundown`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800046f0`
- `0x180004840`
- `0x18003819c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046fd`

## pseudocode

```c
PVOID *__fastcall UBPM_RPC_TASK_HOST_CONTEXT_HANDLE_rundown(__int64 a1)
{
  DWORD CurrentThreadId; // eax
  PVOID *result; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  CurrentThreadId = GetCurrentThreadId();
  if ( CurrentThreadId != _InterlockedCompareExchange(
                            (volatile signed __int32 *)(a1 + 324),
                            CurrentThreadId,
                            CurrentThreadId) )
    return (PVOID *)s_UbpmRpcCloseTaskHostChannel(&v4);
  ++*(_DWORD *)(a1 + 328);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    return (PVOID *)WPP_SF_q(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      24,
                      WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                      a1);
  return result;
}

```

## disassembly

```asm
0x1800046f0  mov     [rsp+arg_0], rcx
0x1800046f5  push    rbx
0x1800046f6  sub     rsp, 20h
0x1800046fa  mov     rbx, rcx
0x1800046fd  call    cs:__imp_GetCurrentThreadId
0x180004704  nop     dword ptr [rax+rax+00h]
0x180004709  mov     ecx, eax
0x18000470b  lock cmpxchg [rbx+144h], ecx
0x180004713  jz      short loc_180004726
0x180004715  lea     rcx, [rsp+28h+arg_0]
0x18000471a  call    s_UbpmRpcCloseTaskHostChannel
0x18000471f  add     rsp, 20h
0x180004723  pop     rbx
0x180004724  retn
0x180004726  inc     dword ptr [rbx+148h]
0x18000472c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004733  lea     rax, WPP_GLOBAL_Control
0x18000473a  cmp     rcx, rax
0x18000473d  jz      short loc_18000471F
0x18000473f  test    byte ptr [rcx+1Ch], 80h
0x180004743  jz      short loc_18000471F
0x180004745  mov     rcx, [rcx+10h]
0x180004749  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180004750  mov     edx, 18h
0x180004755  mov     r9, rbx
0x180004758  add     rsp, 20h
0x18000475c  pop     rbx
0x18000475d  jmp     WPP_SF_q
```
