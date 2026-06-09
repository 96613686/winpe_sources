# BrpRpcContextProcessWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18001aaf0`
- end: `0x18001ab86`
- name: `?BrpRpcContextProcessWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `150`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000af58`
- `0x18000aff4`
- `0x18001aaf0`

## import_xrefs

- `ntdll!TpReleaseWait` at `0x18001ab61`
- `ntdll!TpReleaseWait` at `0x18001ab61`
- `ntdll!RtlRbRemoveNode` at `0x18001ab2d`
- `ntdll!RtlRbRemoveNode` at `0x18001ab2d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001ab0d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001ab0d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001ab46`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001ab70`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001ab46`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001ab70`

## pseudocode

```c
void __fastcall BrpRpcContextProcessWaitCallback(struct _TP_CALLBACK_INSTANCE *a1, _QWORD *a2, struct _TP_WAIT *a3)
{
  unsigned __int64 v3; // rbx
  struct _BR_RPC_CONTEXT_ENTRY *v5; // rsi
  __int64 v6; // rbx

  v3 = a2[3];
  RtlAcquireSRWLockExclusive(&RpcContextTable);
  v5 = BrpRpcContextFindWithLockHeld(v3);
  if ( v5 )
  {
    RtlRbRemoveNode(&xmmword_180028970, a2);
    v6 = a2[5];
    a2[5] = 0;
    RtlReleaseSRWLockExclusive(&RpcContextTable);
    BrpRpcContextEntryDestroy(v5, 3);
    if ( v6 )
      TpReleaseWait(v6);
  }
  else
  {
    RtlReleaseSRWLockExclusive(&RpcContextTable);
  }
}

```

## disassembly

```asm
0x18001aaf0  mov     [rsp+arg_0], rbx
0x18001aaf5  mov     [rsp+arg_8], rsi
0x18001aafa  push    rdi
0x18001aafb  sub     rsp, 20h
0x18001aaff  mov     rbx, [rdx+18h]
0x18001ab03  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x18001ab0a  mov     rdi, rdx
0x18001ab0d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001ab13  mov     rcx, rbx; unsigned __int64
0x18001ab16  call    ?BrpRpcContextFindWithLockHeld@@YAPEAU_BR_RPC_CONTEXT_ENTRY@@_K@Z; BrpRpcContextFindWithLockHeld(unsigned __int64)
0x18001ab1b  mov     rsi, rax
0x18001ab1e  test    rax, rax
0x18001ab21  jz      short loc_18001AB69
0x18001ab23  mov     rdx, rdi
0x18001ab26  lea     rcx, xmmword_180028970
0x18001ab2d  call    cs:__imp_RtlRbRemoveNode
0x18001ab33  mov     rbx, [rdi+28h]
0x18001ab37  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x18001ab3e  mov     qword ptr [rdi+28h], 0
0x18001ab46  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001ab4c  mov     edx, 3
0x18001ab51  mov     rcx, rsi
0x18001ab54  call    ?BrpRpcContextEntryDestroy@@YAXPEAU_BR_RPC_CONTEXT_ENTRY@@W4_BR_EVENT_CALL_REASON@@@Z; BrpRpcContextEntryDestroy(_BR_RPC_CONTEXT_ENTRY *,_BR_EVENT_CALL_REASON)
0x18001ab59  test    rbx, rbx
0x18001ab5c  jz      short loc_18001AB76
0x18001ab5e  mov     rcx, rbx
0x18001ab61  call    cs:__imp_TpReleaseWait
0x18001ab67  jmp     short loc_18001AB76
0x18001ab69  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x18001ab70  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001ab76  mov     rbx, [rsp+28h+arg_0]
0x18001ab7b  mov     rsi, [rsp+28h+arg_8]
0x18001ab80  add     rsp, 20h
0x18001ab84  pop     rdi
0x18001ab85  retn
```
