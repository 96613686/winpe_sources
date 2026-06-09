# DoReleaseContext

- ea: `0x180010ab0`
- end: `0x180010f1d`
- name: `DoReleaseContext`
- size: `1133`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `14`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001be0`
- `0x18000fcd0`
- `0x1800105c0`
- `0x180010620`
- `0x180010a00`
- `0x180011430`
- `0x1800117c0`
- `0x1800118c0`
- `0x180012130`
- `0x1800123e0`
- `0x180012610`
- `0x18004f410`
- `0x18004f4a0`
- `0x180062ba0`

## callees

- `0x180010400`
- `0x180010ab0`
- `0x18001bb10`
- `0x180020080`
- `0x1800248e0`
- `0x180024c40`
- `0x18005dcc0`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x180010ca3`
- `ntoskrnl!ExQueueWorkItem` at `0x180010ca3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010c0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010c0a`
- `ntoskrnl!KeBugCheckEx` at `0x180010ecc`
- `ntoskrnl!KeBugCheckEx` at `0x180010ecc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x180010c58`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x180010c58`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x180010c8e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x180010e5d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x180010c8e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x180010e5d`
- `ntoskrnl!ObfDereferenceObject` at `0x180010d7b`
- `ntoskrnl!ObfDereferenceObject` at `0x180010eea`
- `ntoskrnl!ObfDereferenceObject` at `0x180010d7b`
- `ntoskrnl!ObfDereferenceObject` at `0x180010eea`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180010bed`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180010daf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180010e92`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180010bed`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180010daf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180010e92`
- `ntoskrnl!KeGetCurrentIrql` at `0x180010ae4`
- `ntoskrnl!KeGetCurrentIrql` at `0x180010ae4`
- `ntoskrnl!ZwClose` at `0x180010efc`
- `ntoskrnl!ZwClose` at `0x180010efc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180010b79`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180010b79`
- `ntoskrnl!ExReleaseRundownProtection` at `0x180010b8c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x180010b8c`
- `ntoskrnl!RtlWalkFrameChain` at `0x180010e32`
- `ntoskrnl!RtlWalkFrameChain` at `0x180010e32`

## pseudocode

```c
void __fastcall DoReleaseContext(HANDLE **BugCheckParameter3)
{
  KIRQL CurrentIrql; // al
  int v3; // edi
  int v4; // edi
  struct _EX_RUNDOWN_REF **v5; // r14
  __int16 v6; // ax
  struct _EX_RUNDOWN_REF *v7; // rax
  HANDLE *v8; // rsi
  __int16 v9; // ax
  int v10; // ecx
  int v11; // eax
  struct _EX_RUNDOWN_REF *v12; // rsi
  int v13; // ecx
  ULONG v14; // edx
  int v15; // ecx
  _QWORD *v16; // rcx
  HANDLE v17; // rcx
  HANDLE v18; // rsi
  volatile signed __int32 *Count; // rcx
  unsigned __int64 v20; // rbx
  HANDLE v21; // rcx
  signed __int64 v22; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-28h] BYREF

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)BugCheckParameter3 + 20, 0xFFFFFFFF) != 1 )
    return;
  if ( ((_DWORD)BugCheckParameter3[9] & 0x10000) != 0 )
    KeBugCheckEx(0xF5u, 0x6Du, (ULONG_PTR)(BugCheckParameter3 + 12), (ULONG_PTR)BugCheckParameter3, 0);
  CurrentIrql = KeGetCurrentIrql();
  v3 = *((_DWORD *)BugCheckParameter3 + 18);
  if ( CurrentIrql < 2u )
  {
    v4 = (_DWORD)BugCheckParameter3[9] & 2;
    v5 = (struct _EX_RUNDOWN_REF **)BugCheckParameter3[1];
    v6 = *((_WORD *)v5 + 12);
    if ( v6 == 32 )
    {
      v21 = (*BugCheckParameter3)[1];
      if ( v21 != (HANDLE)-1LL )
      {
        ObfDereferenceObject(v21);
        ZwClose(**BugCheckParameter3);
      }
      if ( ((_DWORD)BugCheckParameter3[9] & 4) != 0 )
      {
        v22 = _InterlockedCompareExchange64(
                (volatile signed __int64 *)BugCheckParameter3 + 2,
                0,
                (signed __int64)BugCheckParameter3[2]);
        if ( v22 )
          FltpObjectPointerDereference(v22);
      }
    }
    else if ( v6 == 64 )
    {
      v17 = **BugCheckParameter3;
      v18 = (*BugCheckParameter3)[1];
      if ( v17 )
        FltObjectDereference(v17);
      if ( v18 )
        ObfDereferenceObject(v18);
      memset(*BugCheckParameter3, 0, 0x58u);
    }
    v7 = v5[1];
    if ( v7 )
      ((void (__fastcall *)(HANDLE **, _QWORD))v7)(BugCheckParameter3 + 12, *((unsigned __int16 *)v5 + 12));
    v8 = BugCheckParameter3[1];
    v9 = *((_WORD *)v8 + 12);
    if ( v9 == 32 )
    {
      if ( *BugCheckParameter3 )
        ExFreeToNPagedLookasideList(&stru_18003F5C0, *BugCheckParameter3);
    }
    else if ( v9 == 64 && *BugCheckParameter3 )
    {
      ExFreeToNPagedLookasideList(&stru_18003F7C0, *BugCheckParameter3);
    }
    v10 = *((unsigned __int8 *)v8 + 27);
    if ( v10 == 1 )
    {
      v11 = *((_DWORD *)BugCheckParameter3 + 18);
      if ( (v11 & 1) != 0 )
      {
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v8 + 24), BugCheckParameter3);
LABEL_13:
        v12 = *v5;
        ExReleaseRundownProtection(*v5 + 1);
        if ( (FltGlobals[0] & 0x2000) != 0 && (v12->Count & 0x2000000) != 0
          || (FltGlobals[0] & 0x4000) != 0 && (v12->Count & 0x4000000) != 0
          || (FltGlobals[0] & 0x8000) != 0 && (v12->Count & 0x1000000) != 0 )
        {
          Count = (volatile signed __int32 *)v12[4].Count;
          if ( Count )
          {
            v20 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(Count, 1u) + 1) & 0x3FF) << 7;
            *(_DWORD *)(v20 + v12[4].Count + 8) = -1;
            *(struct _EX_RUNDOWN_REF *)(v20 + v12[4].Count + 16) = v12[1];
            memset((void *)(v20 + v12[4].Count + 24), 0, 0x70u);
            RtlWalkFrameChain((PVOID *)(v20 + v12[4].Count + 24), 0xEu, 0);
          }
        }
        if ( v4 )
          FltpDequeueThrottledWorkItem(1);
        return;
      }
      if ( (v11 & 8) == 0 )
      {
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v8 + 8), BugCheckParameter3);
        goto LABEL_13;
      }
      v14 = *((_DWORD *)v8 + 58);
    }
    else
    {
      v13 = v10 - 2;
      if ( v13 )
      {
        if ( v13 == 1 )
          ((void (__fastcall *)(HANDLE **, _QWORD))v8[5])(BugCheckParameter3, *((unsigned __int16 *)v8 + 12));
        goto LABEL_13;
      }
      v14 = *((_DWORD *)v8 + 8);
    }
    ExFreePoolWithTag(BugCheckParameter3, v14);
    goto LABEL_13;
  }
  *((_DWORD *)BugCheckParameter3 + 6) = 2683172;
  *((_DWORD *)BugCheckParameter3 + 18) = v3 | 2;
  BugCheckParameter3[6] = (HANDLE *)DoFreeContext;
  BugCheckParameter3[4] = 0;
  *(_QWORD *)&LockHandle.OldIrql = 0;
  BugCheckParameter3[7] = (HANDLE *)BugCheckParameter3;
  LockHandle.LockQueue = 0;
  KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
  if ( dword_1800402D0 >= (unsigned int)dword_1800402D4 )
  {
    if ( (byte_180040A44 & 1) != 0 )
      McTemplateU0spddd_EtwWriteTransfer(
        dword_1800402D0,
        (unsigned int)WorkSup_c214,
        (unsigned int)"FltpQueueThrottledWorkItem",
        (_DWORD)BugCheckParameter3 + 24,
        1,
        dword_1800402D0,
        dword_1800402D4);
    v16 = (_QWORD *)qword_1800402C8;
    if ( *(__int64 **)qword_1800402C8 != &qword_1800402C0 )
      __fastfail(3u);
    BugCheckParameter3[5] = (HANDLE *)qword_1800402C8;
    BugCheckParameter3[4] = (HANDLE *)&qword_1800402C0;
    *v16 = BugCheckParameter3 + 4;
    qword_1800402C8 = (__int64)(BugCheckParameter3 + 4);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  else
  {
    v15 = ++dword_1800402D0;
    if ( (byte_180040A44 & 1) != 0 )
      McTemplateU0spddd_EtwWriteTransfer(
        v15,
        (unsigned int)WorkSup_c193,
        (unsigned int)"FltpQueueThrottledWorkItem",
        (_DWORD)BugCheckParameter3 + 24,
        1,
        v15,
        dword_1800402D4);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    ExQueueWorkItem((PWORK_QUEUE_ITEM)BugCheckParameter3 + 1, DelayedWorkQueue);
  }
}

```

## disassembly

```asm
0x180010ab0  push    rbx
0x180010ab2  sub     rsp, 60h
0x180010ab6  mov     rbx, rcx
0x180010ab9  mov     eax, 0FFFFFFFFh
0x180010abe  lock xadd [rcx+50h], eax
0x180010ac3  cmp     eax, 1
0x180010ac6  jz      short loc_180010ACF
0x180010ac8  add     rsp, 60h
0x180010acc  pop     rbx
0x180010acd  retn
0x180010acf  test    dword ptr [rcx+48h], 10000h
0x180010ad6  jnz     loc_180010EB4
0x180010adc  mov     [rsp+68h+arg_10], rdi
0x180010ae4  call    cs:__imp_KeGetCurrentIrql
0x180010aeb  nop     dword ptr [rax+rax+00h]
0x180010af0  mov     edi, [rbx+48h]
0x180010af3  cmp     al, 2
0x180010af5  jnb     loc_180010C1B
0x180010afb  mov     [rsp+68h+arg_8], rsi
0x180010b00  and     edi, 2
0x180010b03  mov     [rsp+68h+arg_18], r14
0x180010b0b  mov     r14, [rbx+8]
0x180010b0f  movzx   eax, word ptr [r14+18h]
0x180010b14  cmp     ax, 20h ; ' '
0x180010b18  jz      loc_180010ED9
0x180010b1e  cmp     ax, 40h ; '@'
0x180010b22  jz      loc_180010D5F
0x180010b28  mov     rax, [r14+8]
0x180010b2c  test    rax, rax
0x180010b2f  jz      short loc_180010B3F
0x180010b31  movzx   edx, word ptr [r14+18h]
0x180010b36  lea     rcx, [rbx+60h]
0x180010b3a  call    _guard_dispatch_icall
0x180010b3f  mov     rsi, [rbx+8]
0x180010b43  movzx   eax, word ptr [rsi+18h]
0x180010b47  cmp     ax, 20h ; ' '
0x180010b4b  jz      loc_180010E7F
0x180010b51  cmp     ax, 40h ; '@'
0x180010b55  jz      loc_180010D9C
0x180010b5b  movzx   ecx, byte ptr [rsi+1Bh]
0x180010b5f  cmp     ecx, 1
0x180010b62  jnz     loc_180010BFB
0x180010b68  mov     eax, [rbx+48h]
0x180010b6b  test    cl, al
0x180010b6d  jz      short loc_180010BDE
0x180010b6f  lea     rcx, [rsi+0C0h]; Lookaside
0x180010b76  mov     rdx, rbx; Entry
0x180010b79  call    cs:__imp_ExFreeToPagedLookasideList
0x180010b80  nop     dword ptr [rax+rax+00h]
0x180010b85  mov     rsi, [r14]
0x180010b88  lea     rcx, [rsi+8]; RunRef
0x180010b8c  call    cs:__imp_ExReleaseRundownProtection
0x180010b93  nop     dword ptr [rax+rax+00h]
0x180010b98  mov     ecx, cs:FltGlobals
0x180010b9e  bt      ecx, 0Dh
0x180010ba2  jb      loc_180010E6E
0x180010ba8  bt      ecx, 0Eh
0x180010bac  jb      loc_180010DC0
0x180010bb2  bt      ecx, 0Fh
0x180010bb6  jb      loc_180010EA3
0x180010bbc  mov     r14, [rsp+68h+arg_18]
0x180010bc4  mov     rsi, [rsp+68h+arg_8]
0x180010bc9  test    edi, edi
0x180010bcb  jnz     loc_180010F0E
0x180010bd1  mov     rdi, [rsp+68h+arg_10]
0x180010bd9  jmp     loc_180010AC8
0x180010bde  test    al, 8
0x180010be0  jnz     loc_180010CDA
0x180010be6  lea     rcx, [rsi+40h]; Lookaside
0x180010bea  mov     rdx, rbx; Entry
0x180010bed  call    cs:__imp_ExFreeToNPagedLookasideList
0x180010bf4  nop     dword ptr [rax+rax+00h]
0x180010bf9  jmp     short loc_180010B85
0x180010bfb  sub     ecx, 2
0x180010bfe  jnz     loc_180010CBC
0x180010c04  mov     edx, [rsi+20h]; Tag
0x180010c07  mov     rcx, rbx; P
0x180010c0a  call    cs:__imp_ExFreePoolWithTag
0x180010c11  nop     dword ptr [rax+rax+00h]
0x180010c16  jmp     loc_180010B85
0x180010c1b  mov     dword ptr [rbx+18h], 28F124h
0x180010c22  lea     rax, DoFreeContext
0x180010c29  xor     ecx, ecx
0x180010c2b  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x180010c30  xorps   xmm0, xmm0
0x180010c33  or      edi, 2
0x180010c36  mov     [rbx+48h], edi
0x180010c39  mov     [rbx+30h], rax
0x180010c3d  xor     eax, eax
0x180010c3f  mov     [rbx+20h], rcx
0x180010c43  lea     rcx, SpinLock; SpinLock
0x180010c4a  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x180010c4f  mov     [rbx+38h], rbx
0x180010c53  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x180010c58  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x180010c5f  nop     dword ptr [rax+rax+00h]
0x180010c64  mov     ecx, cs:dword_1800402D0
0x180010c6a  mov     edx, cs:dword_1800402D4
0x180010c70  cmp     ecx, edx
0x180010c72  jnb     short loc_180010CE5
0x180010c74  inc     ecx
0x180010c76  test    cs:byte_180040A44, 1
0x180010c7d  mov     cs:dword_1800402D0, ecx
0x180010c83  jnz     loc_180010D33
0x180010c89  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x180010c8e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x180010c95  nop     dword ptr [rax+rax+00h]
0x180010c9a  lea     rcx, [rbx+20h]; WorkItem
0x180010c9e  mov     edx, 1; QueueType
0x180010ca3  call    cs:__imp_ExQueueWorkItem
0x180010caa  nop     dword ptr [rax+rax+00h]
0x180010caf  mov     rdi, [rsp+68h+arg_10]
0x180010cb7  jmp     loc_180010AC8
0x180010cbc  cmp     ecx, 1
0x180010cbf  jnz     loc_180010B85
0x180010cc5  mov     rax, [rsi+28h]
0x180010cc9  mov     rcx, rbx
0x180010ccc  movzx   edx, word ptr [rsi+18h]
0x180010cd0  call    _guard_dispatch_icall
0x180010cd5  jmp     loc_180010B85
0x180010cda  mov     edx, [rsi+0E8h]
0x180010ce0  jmp     loc_180010C07
0x180010ce5  test    cs:byte_180040A44, 1
0x180010cec  jz      short loc_180010D15
0x180010cee  mov     [rsp+68h+var_38], edx
0x180010cf2  lea     r9, [rbx+18h]
0x180010cf6  mov     [rsp+68h+var_40], ecx
0x180010cfa  lea     rdx, WorkSup_c214
0x180010d01  lea     r8, aFltpqueuethrot; "FltpQueueThrottledWorkItem"
0x180010d08  mov     dword ptr [rsp+68h+BugCheckParameter4], 1
0x180010d10  call    McTemplateU0spddd_EtwWriteTransfer
0x180010d15  mov     rcx, cs:qword_1800402C8
0x180010d1c  lea     rdx, qword_1800402C0
0x180010d23  cmp     [rcx], rdx
0x180010d26  jz      loc_180010E43
0x180010d2c  mov     ecx, 3
0x180010d31  int     29h; Win8: RtlFailFast(ecx)
0x180010d33  mov     [rsp+68h+var_38], edx
0x180010d37  lea     r9, [rbx+18h]
0x180010d3b  mov     [rsp+68h+var_40], ecx
0x180010d3f  lea     rdx, WorkSup_c193
0x180010d46  lea     r8, aFltpqueuethrot; "FltpQueueThrottledWorkItem"
0x180010d4d  mov     dword ptr [rsp+68h+BugCheckParameter4], 1
0x180010d55  call    McTemplateU0spddd_EtwWriteTransfer
0x180010d5a  jmp     loc_180010C89
0x180010d5f  mov     rax, [rbx]
0x180010d62  mov     rcx, [rax]; FltObject
0x180010d65  mov     rsi, [rax+8]
0x180010d69  test    rcx, rcx
0x180010d6c  jz      short loc_180010D73
0x180010d6e  call    FltObjectDereference
0x180010d73  test    rsi, rsi
0x180010d76  jz      short loc_180010D87
0x180010d78  mov     rcx, rsi; Object
0x180010d7b  call    cs:__imp_ObfDereferenceObject
0x180010d82  nop     dword ptr [rax+rax+00h]
0x180010d87  mov     rcx, [rbx]; void *
0x180010d8a  xor     edx, edx; Val
0x180010d8c  mov     r8d, 58h ; 'X'; Size
0x180010d92  call    memset
0x180010d97  jmp     loc_180010B28
0x180010d9c  mov     rdx, [rbx]; Entry
0x180010d9f  test    rdx, rdx
0x180010da2  jz      loc_180010B5B
0x180010da8  lea     rcx, stru_18003F7C0; Lookaside
0x180010daf  call    cs:__imp_ExFreeToNPagedLookasideList
0x180010db6  nop     dword ptr [rax+rax+00h]
0x180010dbb  jmp     loc_180010B5B
0x180010dc0  test    dword ptr [rsi], 4000000h
0x180010dc6  jz      loc_180010BB2
0x180010dcc  mov     rcx, [rsi+20h]
0x180010dd0  test    rcx, rcx
0x180010dd3  jz      loc_180010BBC
0x180010dd9  mov     ebx, 1
0x180010dde  lock xadd [rcx], ebx
0x180010de2  mov     rax, [rsi+20h]
0x180010de6  inc     ebx
0x180010de8  and     ebx, 3FFh
0x180010dee  xor     edx, edx; Val
0x180010df0  shl     rbx, 7
0x180010df4  mov     r8d, 70h ; 'p'; Size
0x180010dfa  mov     dword ptr [rbx+rax+8], 0FFFFFFFFh
0x180010e02  mov     rcx, [rsi+20h]
0x180010e06  mov     rax, [rsi+8]
0x180010e0a  mov     [rbx+rcx+10h], rax
0x180010e0f  mov     rcx, [rsi+20h]
0x180010e13  add     rcx, 18h
0x180010e17  add     rcx, rbx; void *
0x180010e1a  call    memset
0x180010e1f  mov     rcx, [rsi+20h]
0x180010e23  xor     r8d, r8d; Flags
0x180010e26  add     rcx, 18h
0x180010e2a  mov     edx, 0Eh; Count
0x180010e2f  add     rcx, rbx; Callers
0x180010e32  call    cs:__imp_RtlWalkFrameChain
0x180010e39  nop     dword ptr [rax+rax+00h]
0x180010e3e  jmp     loc_180010BBC
0x180010e43  lea     rax, [rbx+20h]
0x180010e47  mov     [rax+8], rcx
0x180010e4b  mov     [rax], rdx
0x180010e4e  mov     [rcx], rax
0x180010e51  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x180010e56  mov     cs:qword_1800402C8, rax
0x180010e5d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x180010e64  nop     dword ptr [rax+rax+00h]
0x180010e69  jmp     loc_180010BD1
0x180010e6e  test    dword ptr [rsi], 2000000h
0x180010e74  jnz     loc_180010DCC
0x180010e7a  jmp     loc_180010BA8
0x180010e7f  mov     rdx, [rbx]; Entry
0x180010e82  test    rdx, rdx
0x180010e85  jz      loc_180010B5B
0x180010e8b  lea     rcx, stru_18003F5C0; Lookaside
0x180010e92  call    cs:__imp_ExFreeToNPagedLookasideList
0x180010e99  nop     dword ptr [rax+rax+00h]
0x180010e9e  jmp     loc_180010B5B
0x180010ea3  test    dword ptr [rsi], 1000000h
0x180010ea9  jz      loc_180010BBC
0x180010eaf  jmp     loc_180010DCC
0x180010eb4  lea     r8, [rcx+60h]; BugCheckParameter2
0x180010eb8  mov     r9, rbx; BugCheckParameter3
0x180010ebb  xor     ecx, ecx
0x180010ebd  mov     edx, 6Dh ; 'm'; BugCheckParameter1
0x180010ec2  mov     [rsp+68h+BugCheckParameter4], rcx; BugCheckParameter4
0x180010ec7  mov     ecx, 0F5h; BugCheckCode
0x180010ecc  call    cs:__imp_KeBugCheckEx
0x180010ed9  mov     rax, [rbx]
0x180010edc  mov     rcx, [rax+8]; Object
0x180010ee0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010ee4  jz      loc_180025D62
0x180010eea  call    cs:__imp_ObfDereferenceObject
0x180010ef1  nop     dword ptr [rax+rax+00h]
0x180010ef6  mov     rcx, [rbx]
0x180010ef9  mov     rcx, [rcx]; Handle
0x180010efc  call    cs:__imp_ZwClose
0x180010f03  nop     dword ptr [rax+rax+00h]
0x180010f08  nop
0x180010f09  jmp     loc_180025D62
0x180010f0e  mov     ecx, 1
0x180010f13  call    FltpDequeueThrottledWorkItem
0x180010f18  jmp     loc_180010BD1
0x180025d62  mov     eax, [rbx+48h]
0x180025d65  test    al, 4
0x180025d67  jz      loc_180010B28
0x180025d6d  mov     rax, [rbx+10h]
0x180025d71  xor     ecx, ecx
0x180025d73  lock cmpxchg [rbx+10h], rcx
0x180025d79  test    rax, rax
0x180025d7c  jz      loc_180010B28
0x180025d82  mov     rcx, rax
0x180025d85  call    FltpObjectPointerDereference
0x180025d8a  nop
0x180025d8b  jmp     loc_180010B28
```
