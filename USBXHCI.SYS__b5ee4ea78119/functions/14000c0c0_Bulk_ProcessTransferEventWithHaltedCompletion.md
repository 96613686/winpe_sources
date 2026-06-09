# Bulk_ProcessTransferEventWithHaltedCompletion

- ea: `0x14000c0c0`
- end: `0x14000c25d`
- name: `Bulk_ProcessTransferEventWithHaltedCompletion`
- size: `413`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140009ea4`
- `0x14000a43c`

## callees

- `0x1400095a0`
- `0x14000c0c0`
- `0x14000c264`
- `0x14000c9b0`
- `0x14000d190`
- `0x14002792c`
- `0x140059a80`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000c105`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c211`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c105`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c211`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c0e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c1b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c0e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c1b1`

## string_xrefs

- `0x14000c133`: `Received duplicate Transfer Event TRB with Halted Completion Code`

## pseudocode

```c
void __fastcall Bulk_ProcessTransferEventWithHaltedCompletion(__int64 a1, __int64 *a2, int a3, unsigned int a4)
{
  KSPIN_LOCK *v4; // rbp
  size_t v5; // r14
  KIRQL v9; // al
  volatile signed __int32 *v10; // r10
  __int64 v11; // rbx
  __int64 v12; // rax
  int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rdx

  v4 = (KSPIN_LOCK *)(a1 + 96);
  v5 = a4;
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  *(_DWORD *)(a1 + 332) |= 4u;
  *(_BYTE *)(a1 + 104) = v9;
  *(_DWORD *)(a1 + 360) = 1;
  KeReleaseSpinLock(v4, v9);
  v10 = *(volatile signed __int32 **)(a1 + 56);
  _m_prefetchw((const void *)(v10 + 8));
  if ( (_InterlockedOr(v10 + 8, 0x20u) & 0x20) != 0 )
    Controller_HwVerifierBreakIfEnabled(
      *(_QWORD *)v10,
      *((_QWORD *)v10 + 1),
      *((_QWORD *)v10 + 3),
      0x2000000,
      (__int64)"Received duplicate Transfer Event TRB with Halted Completion Code",
      0,
      0);
  else
    ESM_AddEsmEvent(v10, 154);
  v11 = *a2;
  *(_DWORD *)(v11 + 108) += v5;
  v12 = *(_QWORD *)(v11 + 48);
  *(_DWORD *)(v11 + 68) = a3;
  if ( (*(_DWORD *)(v12 + 32) & 1) != 0 && *(_DWORD *)(v11 + 76) == 2 )
    memmove((void *)a2[8], *(const void **)(a2[9] + 16), v5);
  Bulk_Stage_FreeScatterGatherList(a1, a2);
  *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc(v4);
  Bulk_Stage_Release(a1, a2);
  ++*(_DWORD *)(v11 + 116);
  Bulk_Transfer_CompleteCancelable(a1, v11, 0xFFFFFFFFLL, 0);
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 40) + 1044LL) == 1 )
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 356));
  else
    --*(_DWORD *)(a1 + 356);
  --*(_DWORD *)(a1 + 360);
  v13 = *(_DWORD *)(a1 + 332);
  KeReleaseSpinLock(v4, *(_BYTE *)(a1 + 104));
  if ( (v13 & 2) != 0 )
  {
    v14 = *(_QWORD *)(a1 + 56);
    if ( !*(_BYTE *)(v14 + 37)
      || (v15 = *(_QWORD *)(v14 + 144),
          _InterlockedIncrement((volatile signed __int32 *)(v15 + 20)) == *(_DWORD *)(v15 + 8)) )
    {
      ESM_AddEsmEvent(v14, 150);
    }
  }
}

```

## disassembly

```asm
0x14000c0c0  push    rbx
0x14000c0c2  push    rbp
0x14000c0c3  push    rsi
0x14000c0c4  push    rdi
0x14000c0c5  push    r14
0x14000c0c7  push    r15
0x14000c0c9  sub     rsp, 48h
0x14000c0cd  lea     rbp, [rcx+60h]
0x14000c0d1  mov     r14d, r9d
0x14000c0d4  mov     rdi, rcx
0x14000c0d7  mov     r15d, r8d
0x14000c0da  mov     rcx, rbp; SpinLock
0x14000c0dd  mov     rsi, rdx
0x14000c0e0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c0e7  nop     dword ptr [rax+rax+00h]
0x14000c0ec  or      dword ptr [rdi+14Ch], 4
0x14000c0f3  mov     rcx, rbp; SpinLock
0x14000c0f6  mov     dl, al; NewIrql
0x14000c0f8  mov     [rdi+68h], al
0x14000c0fb  mov     dword ptr [rdi+168h], 1
0x14000c105  call    cs:__imp_KeReleaseSpinLock
0x14000c10c  nop     dword ptr [rax+rax+00h]
0x14000c111  mov     r10, [rdi+38h]
0x14000c115  prefetchw byte ptr [r10+20h]
0x14000c11a  mov     eax, [r10+20h]
0x14000c11e  mov     ecx, eax
0x14000c120  or      ecx, 20h
0x14000c123  lock cmpxchg [r10+20h], ecx
0x14000c129  jnz     short loc_14000C11E
0x14000c12b  test    al, 20h
0x14000c12d  jz      short loc_14000C165
0x14000c12f  mov     r8, [r10+18h]
0x14000c133  lea     rax, aReceivedDuplic; "Received duplicate Transfer Event TRB w"...
0x14000c13a  mov     rdx, [r10+8]
0x14000c13e  mov     r9d, 2000000h
0x14000c144  mov     rcx, [r10]
0x14000c147  mov     [rsp+78h+var_48], 0
0x14000c150  mov     [rsp+78h+var_50], 0
0x14000c159  mov     [rsp+78h+var_58], rax
0x14000c15e  call    Controller_HwVerifierBreakIfEnabled
0x14000c163  jmp     short loc_14000C172
0x14000c165  mov     edx, 9Ah
0x14000c16a  mov     rcx, r10
0x14000c16d  call    ESM_AddEsmEvent
0x14000c172  mov     rbx, [rsi]
0x14000c175  add     [rbx+6Ch], r14d
0x14000c179  mov     rax, [rbx+30h]
0x14000c17d  mov     [rbx+44h], r15d
0x14000c181  mov     ecx, [rax+20h]
0x14000c184  test    cl, 1
0x14000c187  jz      short loc_14000C1A3
0x14000c189  cmp     dword ptr [rbx+4Ch], 2
0x14000c18d  jnz     short loc_14000C1A3
0x14000c18f  mov     rdx, [rsi+48h]
0x14000c193  mov     r8, r14; Size
0x14000c196  mov     rcx, [rsi+40h]; void *
0x14000c19a  mov     rdx, [rdx+10h]; Src
0x14000c19e  call    memmove
0x14000c1a3  mov     rdx, rsi
0x14000c1a6  mov     rcx, rdi
0x14000c1a9  call    Bulk_Stage_FreeScatterGatherList
0x14000c1ae  mov     rcx, rbp; SpinLock
0x14000c1b1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c1b8  nop     dword ptr [rax+rax+00h]
0x14000c1bd  mov     rdx, rsi
0x14000c1c0  mov     rcx, rdi
0x14000c1c3  mov     [rdi+68h], al
0x14000c1c6  call    Bulk_Stage_Release
0x14000c1cb  inc     dword ptr [rbx+74h]
0x14000c1ce  xor     r9d, r9d
0x14000c1d1  or      r8d, 0FFFFFFFFh
0x14000c1d5  mov     rdx, rbx
0x14000c1d8  mov     rcx, rdi
0x14000c1db  call    Bulk_Transfer_CompleteCancelable
0x14000c1e0  mov     rax, [rdi+28h]
0x14000c1e4  or      ecx, 0FFFFFFFFh
0x14000c1e7  cmp     byte ptr [rax+414h], 1
0x14000c1ee  jnz     short loc_14000C1F9
0x14000c1f0  lock dec dword ptr [rdi+164h]
0x14000c1f7  jmp     short loc_14000C1FF
0x14000c1f9  add     [rdi+164h], ecx
0x14000c1ff  add     [rdi+168h], ecx
0x14000c205  mov     rcx, rbp; SpinLock
0x14000c208  mov     dl, [rdi+68h]; NewIrql
0x14000c20b  mov     ebx, [rdi+14Ch]
0x14000c211  call    cs:__imp_KeReleaseSpinLock
0x14000c218  nop     dword ptr [rax+rax+00h]
0x14000c21d  bt      ebx, 1
0x14000c221  jnb     short loc_14000C24F
0x14000c223  mov     rcx, [rdi+38h]
0x14000c227  cmp     byte ptr [rcx+25h], 0
0x14000c22b  jz      short loc_14000C245
0x14000c22d  mov     rdx, [rcx+90h]
0x14000c234  mov     eax, 1
0x14000c239  lock xadd [rdx+14h], eax
0x14000c23e  inc     eax
0x14000c240  cmp     eax, [rdx+8]
0x14000c243  jnz     short loc_14000C24F
0x14000c245  mov     edx, 96h
0x14000c24a  call    ESM_AddEsmEvent
0x14000c24f  add     rsp, 48h
0x14000c253  pop     r15
0x14000c255  pop     r14
0x14000c257  pop     rdi
0x14000c258  pop     rsi
0x14000c259  pop     rbp
0x14000c25a  pop     rbx
0x14000c25b  retn
```
