# SetPendingAdds

- ea: `0x14000a610`
- end: `0x14000a8f5`
- name: `SetPendingAdds`
- size: `741`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140047dc0`

## callees

- `0x140006c40`
- `0x140009520`
- `0x140009d80`
- `0x140009e00`
- `0x14000a610`
- `0x14000afa0`
- `0x14001cfe0`
- `0x14001d050`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000a72f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000a7da`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000a72f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000a7da`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a6f4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a6f4`
- `NDIS!NdisReleaseRWLock` at `0x14000a80b`
- `NDIS!NdisReleaseRWLock` at `0x14000a80b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000a712`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000a712`

## string_xrefs

- `0x14000a77b`: `FeAcquireWriteEngineLock`
- `0x14000a8b8`: `FeAcquireWriteEngineLock`

## pseudocode

```c
__int64 __fastcall SetPendingAdds(__int64 a1)
{
  __int64 v2; // rbp
  int v3; // r13d
  __int64 v4; // rcx
  int v5; // r14d
  __int64 v6; // rbx
  PNPAGED_LOOKASIDE_LIST v7; // rsi
  KIRQL CurrentIrql; // di
  __int64 v9; // rdx
  __int64 Flink_low; // rcx
  bool v11; // zf
  PNPAGED_LOOKASIDE_LIST v12; // rdi
  _DWORD *v13; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+78h] [rbp+10h] BYREF
  __int64 v16; // [rsp+80h] [rbp+18h] BYREF

  v16 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v2 = FeAcquireWriteEngineLock(&LockState, 1);
  if ( v2 )
    goto LABEL_24;
  if ( *(_QWORD *)(a1 + 8) )
  {
    WfpPoolFree(a1 + 8);
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 0;
  }
  v3 = *(_DWORD *)(a1 + 120);
  WfpReleaseFastWriteLock(&gWfpGlobal[1], &LockState);
  v4 = *(unsigned int *)(*(_QWORD *)a1 + 4LL);
  if ( !(_DWORD)v4 )
    return v2;
  v2 = WfpSizeTMultiply(v4, 8, &v16);
  if ( v2 || (v2 = WfpPoolAllocNonPaged(v16, 1399875159, a1 + 8)) != 0 )
  {
LABEL_24:
    WfpReportError(v2, "SetPendingAdds");
    return v2;
  }
  v5 = 0;
  v6 = 0;
  *(_DWORD *)(a1 + 16) = *(_DWORD *)(*(_QWORD *)a1 + 4LL);
  while ( (unsigned int)v6 < *(_DWORD *)(a1 + 16) )
  {
    v7 = gWfpGlobal;
    v2 = 0;
    CurrentIrql = KeGetCurrentIrql();
    NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)v7[1].L.ListHead.Alignment, &LockState, 0);
    if ( CurrentIrql != 2 && gWfpPerProContext )
    {
      v9 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v9 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v9 = 4;
    }
    Flink_low = LODWORD(gWfpGlobal[1].L.ListEntry.Flink);
    if ( (_DWORD)Flink_low == 2 )
    {
      v2 = WfpReportSysErrorAsNtStatus(Flink_low, "FeAcquireWriteEngineLock", 3221225473LL, 1);
      if ( v2 )
      {
        WfpReleaseFastWriteLock(&gWfpGlobal[1], &LockState);
        WfpReportError(v2, "FeAcquireWriteEngineLock");
        goto LABEL_24;
      }
    }
    if ( v3 != *(_DWORD *)(a1 + 120) )
      v5 = 1;
    v11 = gWfpPerProContext == 0;
    *(_QWORD *)(8 * v6 + *(_QWORD *)(a1 + 8)) = **(_QWORD **)(8 * v6 + *(_QWORD *)(*(_QWORD *)a1 + 24LL));
    v12 = gWfpGlobal;
    if ( !v11 )
    {
      v13 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v13 == 4 )
        *v13 = 0;
    }
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v12[1].L.ListHead.Alignment, &LockState);
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"SetPendingAdds",
          1);
      }
      v2 = -1073741823;
      goto LABEL_24;
    }
    v6 = (unsigned int)(v6 + 1);
  }
  return v2;
}

```

## disassembly

```asm
0x14000a610  mov     [rsp+arg_0], rbx
0x14000a615  push    rbp
0x14000a616  push    rsi
0x14000a617  push    rdi
0x14000a618  push    r12
0x14000a61a  push    r13
0x14000a61c  push    r14
0x14000a61e  push    r15
0x14000a620  sub     rsp, 30h
0x14000a624  xor     eax, eax
0x14000a626  mov     [rsp+68h+arg_10], 0
0x14000a632  mov     r12, rcx
0x14000a635  mov     word ptr [rsp+68h+LockState.OldIrql], ax
0x14000a63a  lea     rcx, [rsp+68h+LockState]
0x14000a63f  mov     [rsp+68h+LockState.Flags], al
0x14000a643  mov     edx, 1
0x14000a648  call    FeAcquireWriteEngineLock
0x14000a64d  mov     rbp, rax
0x14000a650  test    rax, rax
0x14000a653  jnz     loc_14000A837
0x14000a659  cmp     [r12+8], rax
0x14000a65e  jnz     loc_14000A882
0x14000a664  mov     rcx, cs:gWfpGlobal
0x14000a66b  lea     rdx, [rsp+68h+LockState]
0x14000a670  mov     r13d, [r12+78h]
0x14000a675  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14000a679  call    WfpReleaseFastWriteLock
0x14000a67e  mov     rax, [r12]
0x14000a682  mov     ecx, [rax+4]
0x14000a685  test    ecx, ecx
0x14000a687  jz      loc_14000A846
0x14000a68d  lea     r8, [rsp+68h+arg_10]
0x14000a695  mov     edx, 8
0x14000a69a  call    WfpSizeTMultiply
0x14000a69f  mov     rbp, rax
0x14000a6a2  test    rax, rax
0x14000a6a5  jnz     loc_14000A837
0x14000a6ab  mov     rcx, [rsp+68h+arg_10]
0x14000a6b3  lea     r8, [r12+8]
0x14000a6b8  mov     edx, 53706657h
0x14000a6bd  call    WfpPoolAllocNonPaged
0x14000a6c2  mov     rbp, rax
0x14000a6c5  test    rax, rax
0x14000a6c8  jnz     loc_14000A837
0x14000a6ce  mov     rax, [r12]
0x14000a6d2  xor     r14d, r14d
0x14000a6d5  xor     ebx, ebx
0x14000a6d7  mov     ecx, [rax+4]
0x14000a6da  mov     [r12+10h], ecx
0x14000a6df  nop
0x14000a6e0  cmp     ebx, [r12+10h]
0x14000a6e5  jnb     loc_14000A846
0x14000a6eb  mov     rsi, cs:gWfpGlobal
0x14000a6f2  xor     ebp, ebp
0x14000a6f4  call    cs:__imp_KeGetCurrentIrql
0x14000a6fb  nop     dword ptr [rax+rax+00h]
0x14000a700  mov     rcx, [rsi+80h]; Lock
0x14000a707  lea     rdx, [rsp+68h+LockState]; LockState
0x14000a70c  xor     r8d, r8d; Flags
0x14000a70f  movzx   edi, al
0x14000a712  call    cs:__imp_NdisAcquireRWLockWrite
0x14000a719  nop     dword ptr [rax+rax+00h]
0x14000a71e  cmp     dil, 2
0x14000a722  jz      short loc_14000A763
0x14000a724  cmp     cs:gWfpPerProContext, rbp
0x14000a72b  jz      short loc_14000A763
0x14000a72d  xor     ecx, ecx; ProcNumber
0x14000a72f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000a736  nop     dword ptr [rax+rax+00h]
0x14000a73b  imul    eax, cs:gWfpPerProContextSize
0x14000a742  mov     ecx, eax
0x14000a744  mov     rax, cs:gWfpPerProContext
0x14000a74b  mov     rdx, [rcx+rax]
0x14000a74f  mov     rax, ds:0FFFFF78000000008h
0x14000a759  mov     [rdx+8], rax
0x14000a75d  mov     dword ptr [rdx], 4
0x14000a763  mov     rax, cs:gWfpGlobal
0x14000a76a  mov     ecx, [rax+0C0h]
0x14000a770  cmp     ecx, 2
0x14000a773  jnz     short loc_14000A799
0x14000a775  mov     r9d, 1
0x14000a77b  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x14000a782  mov     r8d, 0C0000001h
0x14000a788  call    WfpReportSysErrorAsNtStatus
0x14000a78d  mov     rbp, rax
0x14000a790  test    rax, rax
0x14000a793  jnz     loc_14000A8A3
0x14000a799  cmp     r13d, [r12+78h]
0x14000a79e  lea     rdx, ds:0[rbx*8]
0x14000a7a6  mov     eax, 1
0x14000a7ab  cmovnz  r14d, eax
0x14000a7af  cmp     cs:gWfpPerProContext, 0
0x14000a7b7  mov     rax, [r12]
0x14000a7bb  mov     rcx, [rax+18h]
0x14000a7bf  mov     rax, [rdx+rcx]
0x14000a7c3  mov     rcx, [r12+8]
0x14000a7c8  mov     rax, [rax]
0x14000a7cb  mov     [rdx+rcx], rax
0x14000a7cf  mov     rdi, cs:gWfpGlobal
0x14000a7d6  jz      short loc_14000A7FF
0x14000a7d8  xor     ecx, ecx; ProcNumber
0x14000a7da  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000a7e1  nop     dword ptr [rax+rax+00h]
0x14000a7e6  imul    eax, cs:gWfpPerProContextSize
0x14000a7ed  mov     ecx, eax
0x14000a7ef  mov     rax, cs:gWfpPerProContext
0x14000a7f6  mov     rdx, [rcx+rax]
0x14000a7fa  cmp     dword ptr [rdx], 4
0x14000a7fd  jz      short loc_14000A85F
0x14000a7ff  mov     rcx, [rdi+80h]; Lock
0x14000a806  lea     rdx, [rsp+68h+LockState]; LockState
0x14000a80b  call    cs:__imp_NdisReleaseRWLock
0x14000a812  nop     dword ptr [rax+rax+00h]
0x14000a817  test    r14d, r14d
0x14000a81a  jnz     short loc_14000A867
0x14000a81c  inc     ebx
0x14000a81e  jmp     loc_14000A6E0
0x14000a823  test    dword ptr [rcx+2Ch], 1000h
0x14000a82a  jnz     loc_14000A8CC
0x14000a830  mov     rbp, 0FFFFFFFFC0000001h
0x14000a837  lea     rdx, aSetpendingadds; "SetPendingAdds"
0x14000a83e  mov     rcx, rbp
0x14000a841  call    WfpReportError
0x14000a846  mov     rbx, [rsp+68h+arg_0]
0x14000a84b  mov     rax, rbp
0x14000a84e  add     rsp, 30h
0x14000a852  pop     r15
0x14000a854  pop     r14
0x14000a856  pop     r13
0x14000a858  pop     r12
0x14000a85a  pop     rdi
0x14000a85b  pop     rsi
0x14000a85c  pop     rbp
0x14000a85d  retn
0x14000a85f  mov     dword ptr [rdx], 0
0x14000a865  jmp     short loc_14000A7FF
0x14000a867  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a86e  lea     rax, WPP_GLOBAL_Control
0x14000a875  cmp     rcx, rax
0x14000a878  jz      short loc_14000A830
0x14000a87a  cmp     byte ptr [rcx+29h], 2
0x14000a87e  jb      short loc_14000A830
0x14000a880  jmp     short loc_14000A823
0x14000a882  lea     rcx, [r12+8]
0x14000a887  call    WfpPoolFree
0x14000a88c  mov     qword ptr [r12+8], 0
0x14000a895  mov     dword ptr [r12+10h], 0
0x14000a89e  jmp     loc_14000A664
0x14000a8a3  mov     rcx, cs:gWfpGlobal
0x14000a8aa  lea     rdx, [rsp+68h+LockState]
0x14000a8af  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14000a8b3  call    WfpReleaseFastWriteLock
0x14000a8b8  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x14000a8bf  mov     rcx, rbp
0x14000a8c2  call    WfpReportError
0x14000a8c7  jmp     loc_14000A837
0x14000a8cc  mov     rcx, [rcx+18h]
0x14000a8d0  lea     r9, aSetpendingadds; "SetPendingAdds"
0x14000a8d7  mov     edx, 0Ah
0x14000a8dc  mov     [rsp+68h+var_48], 0C0000001h
0x14000a8e4  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000a8eb  call    WPP_SF_sd
0x14000a8f0  jmp     loc_14000A830
```
