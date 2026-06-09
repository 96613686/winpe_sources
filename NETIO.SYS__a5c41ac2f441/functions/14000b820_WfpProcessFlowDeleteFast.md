# WfpProcessFlowDeleteFast

- ea: `0x14000b820`
- end: `0x14000b979`
- name: `WfpProcessFlowDeleteFast`
- size: `345`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000b2b0`

## callees

- `0x14000b820`
- `0x140078080`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14000b95f`
- `ntoskrnl!KeLowerIrql` at `0x14000b95f`
- `ntoskrnl!KfRaiseIrql` at `0x14000b842`
- `ntoskrnl!KfRaiseIrql` at `0x14000b842`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b893`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b8f8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b893`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b8f8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b859`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b859`
- `NDIS!NdisReleaseRWLock` at `0x14000b92f`
- `NDIS!NdisReleaseRWLock` at `0x14000b92f`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b877`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b877`

## pseudocode

```c
void __fastcall WfpProcessFlowDeleteFast(__int64 a1)
{
  __int64 v2; // rsi
  void (__fastcall *v3)(_QWORD, __int64); // r14
  KIRQL v4; // al
  PNPAGED_LOOKASIDE_LIST v5; // rdi
  KIRQL v6; // r15
  KIRQL CurrentIrql; // bl
  __int64 v8; // rdx
  __int64 v9; // rax
  PNPAGED_LOOKASIDE_LIST v10; // rbx
  _DWORD *v11; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v2 = 0;
  v3 = 0;
  v4 = KfRaiseIrql(2u);
  v5 = gWfpGlobal;
  v6 = v4;
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)v5[3].L.AllocateEx, &LockState, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v8 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v8 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v8 = 4;
  }
  v9 = *(_QWORD *)(a1 + 48);
  if ( v9 )
  {
    *(_QWORD *)(a1 + 48) = 0;
    v2 = v9;
    v3 = *(void (__fastcall **)(_QWORD, __int64))&gWfpGlobal[13].L.LastTotalAllocates;
  }
  v10 = gWfpGlobal;
  if ( gWfpPerProContext )
  {
    v11 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v11 == 4 )
      *v11 = 0;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v10[3].L.AllocateEx, &LockState);
  if ( v2 )
  {
    v3(0, v2);
    _InterlockedDecrement((volatile signed __int32 *)gWfpGlobal[13].L.Future);
  }
  KeLowerIrql(v6);
}

```

## disassembly

```asm
0x14000b820  push    rbx
0x14000b822  push    rbp
0x14000b823  push    rsi
0x14000b824  push    rdi
0x14000b825  push    r14
0x14000b827  push    r15
0x14000b829  sub     rsp, 28h
0x14000b82d  xor     eax, eax
0x14000b82f  mov     rbp, rcx
0x14000b832  mov     cl, 2; NewIrql
0x14000b834  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x14000b839  mov     [rsp+58h+LockState.Flags], al
0x14000b83d  xor     esi, esi
0x14000b83f  xor     r14d, r14d
0x14000b842  call    cs:__imp_KfRaiseIrql
0x14000b849  nop     dword ptr [rax+rax+00h]
0x14000b84e  mov     rdi, cs:gWfpGlobal
0x14000b855  movzx   r15d, al
0x14000b859  call    cs:__imp_KeGetCurrentIrql
0x14000b860  nop     dword ptr [rax+rax+00h]
0x14000b865  mov     rcx, [rdi+1B0h]; Lock
0x14000b86c  lea     rdx, [rsp+58h+LockState]; LockState
0x14000b871  xor     r8d, r8d; Flags
0x14000b874  movzx   ebx, al
0x14000b877  call    cs:__imp_NdisAcquireRWLockWrite
0x14000b87e  nop     dword ptr [rax+rax+00h]
0x14000b883  cmp     bl, 2
0x14000b886  jz      short loc_14000B8C7
0x14000b888  cmp     cs:gWfpPerProContext, rsi
0x14000b88f  jz      short loc_14000B8C7
0x14000b891  xor     ecx, ecx; ProcNumber
0x14000b893  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000b89a  nop     dword ptr [rax+rax+00h]
0x14000b89f  imul    eax, cs:gWfpPerProContextSize
0x14000b8a6  mov     ecx, eax
0x14000b8a8  mov     rax, cs:gWfpPerProContext
0x14000b8af  mov     rdx, [rcx+rax]
0x14000b8b3  mov     rax, ds:0FFFFF78000000008h
0x14000b8bd  mov     [rdx+8], rax
0x14000b8c1  mov     dword ptr [rdx], 4
0x14000b8c7  mov     rax, [rbp+30h]
0x14000b8cb  test    rax, rax
0x14000b8ce  jz      short loc_14000B8E5
0x14000b8d0  mov     [rbp+30h], r14
0x14000b8d4  mov     rsi, rax
0x14000b8d7  mov     rax, cs:gWfpGlobal
0x14000b8de  mov     r14, [rax+6D0h]
0x14000b8e5  cmp     cs:gWfpPerProContext, 0
0x14000b8ed  mov     rbx, cs:gWfpGlobal
0x14000b8f4  jz      short loc_14000B923
0x14000b8f6  xor     ecx, ecx; ProcNumber
0x14000b8f8  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000b8ff  nop     dword ptr [rax+rax+00h]
0x14000b904  imul    eax, cs:gWfpPerProContextSize
0x14000b90b  mov     ecx, eax
0x14000b90d  mov     rax, cs:gWfpPerProContext
0x14000b914  mov     rdx, [rcx+rax]
0x14000b918  cmp     dword ptr [rdx], 4
0x14000b91b  jnz     short loc_14000B923
0x14000b91d  mov     dword ptr [rdx], 0
0x14000b923  mov     rcx, [rbx+1B0h]; Lock
0x14000b92a  lea     rdx, [rsp+58h+LockState]; LockState
0x14000b92f  call    cs:__imp_NdisReleaseRWLock
0x14000b936  nop     dword ptr [rax+rax+00h]
0x14000b93b  test    rsi, rsi
0x14000b93e  jz      short loc_14000B95B
0x14000b940  mov     rdx, rsi
0x14000b943  xor     ecx, ecx
0x14000b945  mov     rax, r14
0x14000b948  call    _guard_dispatch_icall
0x14000b94d  mov     rax, cs:gWfpGlobal
0x14000b954  lock dec dword ptr [rax+6D8h]
0x14000b95b  movzx   ecx, r15b; NewIrql
0x14000b95f  call    cs:__imp_KeLowerIrql
0x14000b966  nop     dword ptr [rax+rax+00h]
0x14000b96b  add     rsp, 28h
0x14000b96f  pop     r15
0x14000b971  pop     r14
0x14000b973  pop     rdi
0x14000b974  pop     rsi
0x14000b975  pop     rbp
0x14000b976  pop     rbx
0x14000b977  retn
```
