# BrpRpcContextProcessWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180069660`
- end: `0x1800696f6`
- name: `?BrpRpcContextProcessWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `150`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800693e4`
- `0x180069594`
- `0x180069660`

## import_xrefs

- `ntdll!TpReleaseWait` at `0x1800696d1`
- `ntdll!TpReleaseWait` at `0x1800696d1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800696b6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800696e0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800696b6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800696e0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18006967d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18006967d`
- `ntdll!RtlRbRemoveNode` at `0x18006969d`
- `ntdll!RtlRbRemoveNode` at `0x18006969d`

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
    RtlRbRemoveNode(&xmmword_18008D488, a2);
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
0x180069660  mov     [rsp+arg_0], rbx
0x180069665  mov     [rsp+arg_8], rsi
0x18006966a  push    rdi
0x18006966b  sub     rsp, 20h
0x18006966f  mov     rbx, [rdx+18h]
0x180069673  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x18006967a  mov     rdi, rdx
0x18006967d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180069683  mov     rcx, rbx; unsigned __int64
0x180069686  call    ?BrpRpcContextFindWithLockHeld@@YAPEAU_BR_RPC_CONTEXT_ENTRY@@_K@Z; BrpRpcContextFindWithLockHeld(unsigned __int64)
0x18006968b  mov     rsi, rax
0x18006968e  test    rax, rax
0x180069691  jz      short loc_1800696D9
0x180069693  mov     rdx, rdi
0x180069696  lea     rcx, xmmword_18008D488
0x18006969d  call    cs:__imp_RtlRbRemoveNode
0x1800696a3  mov     rbx, [rdi+28h]
0x1800696a7  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x1800696ae  mov     qword ptr [rdi+28h], 0
0x1800696b6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800696bc  mov     edx, 3
0x1800696c1  mov     rcx, rsi
0x1800696c4  call    ?BrpRpcContextEntryDestroy@@YAXPEAU_BR_RPC_CONTEXT_ENTRY@@W4_BR_EVENT_CALL_REASON@@@Z; BrpRpcContextEntryDestroy(_BR_RPC_CONTEXT_ENTRY *,_BR_EVENT_CALL_REASON)
0x1800696c9  test    rbx, rbx
0x1800696cc  jz      short loc_1800696E6
0x1800696ce  mov     rcx, rbx
0x1800696d1  call    cs:__imp_TpReleaseWait
0x1800696d7  jmp     short loc_1800696E6
0x1800696d9  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x1800696e0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800696e6  mov     rbx, [rsp+28h+arg_0]
0x1800696eb  mov     rsi, [rsp+28h+arg_8]
0x1800696f0  add     rsp, 20h
0x1800696f4  pop     rdi
0x1800696f5  retn
```
