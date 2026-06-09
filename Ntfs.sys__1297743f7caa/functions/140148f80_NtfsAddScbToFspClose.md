# NtfsAddScbToFspClose

- ea: `0x140148f80`
- end: `0x14014943e`
- name: `NtfsAddScbToFspClose`
- size: `1214`
- prototype: `__int64 __fastcall(int, int, int, int, void *)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140128a10`
- `0x140128da0`
- `0x14012a140`
- `0x14014a980`
- `0x1401a2d00`
- `0x14029c204`

## callees

- `0x1400054e8`
- `0x140023250`
- `0x1400592c0`
- `0x140059740`
- `0x140148f80`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1401492ad`
- `ntoskrnl!ExQueueWorkItem` at `0x1401492ad`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401490f1`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401490f1`
- `ntoskrnl!IoClearActivityIdThread` at `0x1401492bc`
- `ntoskrnl!IoClearActivityIdThread` at `0x1401492bc`
- `ntoskrnl!IoTransferActivityId` at `0x1401493e8`
- `ntoskrnl!IoTransferActivityId` at `0x1401493e8`
- `ntoskrnl!EtwActivityIdControl` at `0x1401493d1`
- `ntoskrnl!EtwActivityIdControl` at `0x1401493d1`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401490d6`
- `ntoskrnl!IoGetActivityIdThread` at `0x140149131`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401490d6`
- `ntoskrnl!IoGetActivityIdThread` at `0x140149131`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140148fca`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140148fca`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401491e9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14014928c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401491e9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14014928c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14014916b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14014934b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14014916b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14014934b`
- `ntoskrnl!ExAcquireFastMutex` at `0x140149044`
- `ntoskrnl!ExAcquireFastMutex` at `0x140149044`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401490b8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401490b8`

## pseudocode

```c
char __fastcall NtfsAddScbToFspClose(__int64 a1, _QWORD *a2, char a3, char a4, _QWORD *a5)
{
  _QWORD *v5; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // r15
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 *v13; // rcx
  __int64 v14; // rdx
  __int64 **v15; // rax
  __int64 v16; // rax
  __int64 **v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *ActivityIdThread; // rax
  char *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  char v23; // r12
  __int64 v24; // r13
  __int64 v25; // rsi
  _QWORD *v26; // rcx
  _QWORD *v27; // rax
  char *v28; // r12
  struct _FAST_MUTEX *v29; // rdi
  __int64 v30; // rcx
  struct _FAST_MUTEX *v31; // r14
  _QWORD *v32; // rdx
  _QWORD *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  bool v36; // zf
  _QWORD *v37; // rcx
  __int64 v38; // rax
  __int128 v41; // [rsp+38h] [rbp-48h] BYREF
  __int64 v42; // [rsp+48h] [rbp-38h]
  __int128 v43; // [rsp+50h] [rbp-30h] BYREF
  __int64 v44; // [rsp+60h] [rbp-20h]

  v5 = a5;
  v42 = 0;
  v41 = 0;
  if ( a5 || (v9 = ExAllocateFromLookasideListEx(&NtfsCloseEntryLookasideList), (v5 = v9) != 0) )
  {
    memset(v5, 0, 0x58u);
    v5[1] = v5;
    v10 = v5 + 2;
    *v5 = v5;
    v5[3] = v5 + 2;
    LOBYTE(v11) = 1;
    v5[2] = v5 + 2;
    v5[4] = a2;
    *((_BYTE *)v5 + 56) = 5;
    NtfsIncrementCloseCounts(v12, a2, v11, 0);
    if ( a4 )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2[23] + 104LL) + 8LL));
      v13 = a2 + 21;
      v14 = a2[21];
      if ( v14 != a2[23] + 64LL )
      {
        if ( *(__int64 **)(v14 + 8) != v13
          || (v15 = (__int64 **)a2[22], *v15 != v13)
          || (*v15 = (__int64 *)v14,
              *(_QWORD *)(v14 + 8) = v15,
              v16 = a2[23] + 64LL,
              v17 = *(__int64 ***)(a2[23] + 72LL),
              *v17 != (__int64 *)v16) )
        {
LABEL_8:
          __fastfail(3u);
        }
        *v13 = v16;
        a2[22] = v17;
        *v17 = v13;
        *(_QWORD *)(v16 + 8) = v13;
      }
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2[23] + 104LL) + 8LL));
    }
    if ( a1 && (v18 = *(_QWORD **)(a1 + 120)) != 0 )
    {
      *((_QWORD *)&v41 + 1) = *v18;
      v42 = v18[1];
      v20 = (char *)&v41 + 8;
    }
    else
    {
      ActivityIdThread = (_QWORD *)IoGetActivityIdThread();
      if ( ActivityIdThread )
      {
        *((_QWORD *)&v41 + 1) = *ActivityIdThread;
        v20 = (char *)&v41 + 8;
        v42 = ActivityIdThread[1];
      }
      else
      {
        v20 = 0;
      }
    }
    v21 = IoSetActivityIdThread(v20);
    v22 = v5[4];
    v23 = 0;
    v24 = v21;
    v44 = 0;
    v43 = 0;
    v25 = *(_QWORD *)(v22 + 192);
    if ( a1 )
    {
      v26 = *(_QWORD **)(a1 + 120);
      if ( v26 )
      {
        *((_QWORD *)&v43 + 1) = *v26;
        v44 = v26[1];
        *(_QWORD *)&v43 = (char *)&v43 + 8;
        v28 = (char *)&v43 + 8;
      }
      else
      {
        v27 = (_QWORD *)IoGetActivityIdThread();
        if ( v27 )
        {
          v28 = (char *)&v43 + 8;
          *((_QWORD *)&v43 + 1) = *v27;
          v44 = v27[1];
        }
        else
        {
          v28 = 0;
        }
        *(_QWORD *)&v43 = v28;
      }
      if ( v28 )
      {
        EtwActivityIdControl(3u, (LPGUID)(v5 + 9));
        v5[8] = v5 + 9;
        IoTransferActivityId(v28, v5[8]);
      }
      else
      {
        v5[8] = 0;
      }
      v29 = (struct _FAST_MUTEX *)(v25 + 8456);
      _InterlockedIncrement((volatile signed __int32 *)(v25 + 4904));
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v25 + 8456));
      if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
        McTemplateK0pq_EtwWriteTransfer(v30, WORKITEM_QUEUE, *(_QWORD *)(a1 + 120));
      v31 = (struct _FAST_MUTEX *)(v25 + 8456);
      v23 = 0;
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)(v25 + 4904));
      v29 = (struct _FAST_MUTEX *)(v25 + 8456);
      v31 = (struct _FAST_MUTEX *)(v25 + 8456);
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v25 + 8456));
    }
    if ( a3 )
    {
      v33 = *(_QWORD **)(v25 + 8448);
      if ( *v33 != v25 + 8440 )
        goto LABEL_8;
      *v5 = v25 + 8440;
      v5[1] = v33;
      *v33 = v5;
      *(_QWORD *)(v25 + 8448) = v5;
      v34 = *(_QWORD *)(v5[4] + 184LL);
      v35 = *(_QWORD *)(v34 + 272);
      if ( v35 )
      {
        v37 = *(_QWORD **)(v35 + 24);
        v38 = v35 + 16;
        if ( *v37 != v38 )
          goto LABEL_8;
        *v10 = v38;
        v5[3] = v37;
        *v37 = v10;
        *(_QWORD *)(v38 + 8) = v10;
      }
      else
      {
        *(_QWORD *)(v34 + 272) = v5;
      }
      if ( ++*(_DWORD *)(v25 + 8428) > *(_DWORD *)(v25 + 8432) )
        *(_DWORD *)(v25 + 8432) = *(_DWORD *)(v25 + 8428);
      ++*(_DWORD *)(*(_QWORD *)(v5[4] + 184LL) + 268LL);
      if ( *(_DWORD *)(v25 + 8428) > (unsigned int)NtfsMaxDelayCloseCount )
      {
        v36 = *(_BYTE *)(v25 + 8416) == 0;
        *(_BYTE *)(v25 + 8418) = 1;
        if ( v36 )
        {
          *(_BYTE *)(v25 + 8416) = 1;
          v23 = 1;
        }
      }
    }
    else
    {
      v32 = *(_QWORD **)(v25 + 8408);
      if ( *v32 != v25 + 8400 )
        goto LABEL_8;
      *v5 = v25 + 8400;
      v5[1] = v32;
      *v32 = v5;
      *(_QWORD *)(v25 + 8408) = v5;
      if ( ++*(_DWORD *)(v25 + 8420) > *(_DWORD *)(v25 + 8424) )
        *(_DWORD *)(v25 + 8424) = *(_DWORD *)(v25 + 8420);
      if ( !*(_BYTE *)(v25 + 8416) )
      {
        *(_BYTE *)(v25 + 8416) = 1;
        KeReleaseGuardedMutex(v31);
        goto LABEL_38;
      }
    }
    KeReleaseGuardedMutex(v29);
    if ( !v23 )
    {
LABEL_39:
      IoClearActivityIdThread(v24);
      LOBYTE(v9) = 1;
      return (char)v9;
    }
LABEL_38:
    _InterlockedIncrement((volatile signed __int32 *)(v25 + 284));
    ExQueueWorkItem((PWORK_QUEUE_ITEM)(v25 + 8368), CriticalWorkQueue);
    goto LABEL_39;
  }
  return (char)v9;
}

```

## disassembly

```asm
0x140148f80  push    rbp
0x140148f82  push    rbx
0x140148f83  push    rsi
0x140148f84  push    rdi
0x140148f85  push    r14
0x140148f87  mov     rbp, rsp
0x140148f8a  sub     rsp, 80h
0x140148f91  mov     rax, cs:__security_cookie
0x140148f98  xor     rax, rsp
0x140148f9b  mov     [rbp+var_18], rax
0x140148f9f  mov     rbx, [rbp+arg_20]
0x140148fa3  xor     eax, eax
0x140148fa5  mov     [rbp+var_50], r8b
0x140148fa9  xorps   xmm0, xmm0
0x140148fac  mov     [rbp+var_38], rax
0x140148fb0  movzx   esi, r9b
0x140148fb4  mov     rdi, rdx
0x140148fb7  mov     r14, rcx
0x140148fba  movups  [rbp+var_48], xmm0
0x140148fbe  test    rbx, rbx
0x140148fc1  jnz     short loc_140148FE2
0x140148fc3  lea     rcx, NtfsCloseEntryLookasideList; Lookaside
0x140148fca  call    cs:__imp_ExAllocateFromLookasideListEx
0x140148fd1  nop     dword ptr [rax+rax+00h]
0x140148fd6  mov     rbx, rax
0x140148fd9  test    rax, rax
0x140148fdc  jz      loc_1401493C0
0x140148fe2  mov     [rsp+80h+arg_10], r12
0x140148fea  xor     edx, edx; Val
0x140148fec  mov     [rsp+80h+var_8], r13
0x140148ff1  mov     r8d, 58h ; 'X'; Size
0x140148ff7  mov     rcx, rbx; void *
0x140148ffa  mov     [rsp+80h+var_10], r15
0x140148fff  call    memset
0x140149004  mov     [rbx+8], rbx
0x140149008  lea     r15, [rbx+10h]
0x14014900c  mov     [rbx], rbx
0x14014900f  xor     r9d, r9d
0x140149012  mov     [r15+8], r15
0x140149016  mov     r8b, 1
0x140149019  mov     [r15], r15
0x14014901c  mov     rdx, rdi
0x14014901f  mov     [rbx+20h], rdi
0x140149023  mov     byte ptr [rbx+38h], 5
0x140149027  call    NtfsIncrementCloseCounts
0x14014902c  test    sil, sil
0x14014902f  jz      loc_1401490C4
0x140149035  mov     rax, [rdi+0B8h]
0x14014903c  mov     rcx, [rax+68h]
0x140149040  add     rcx, 8; FastMutex
0x140149044  call    cs:__imp_ExAcquireFastMutex
0x14014904b  nop     dword ptr [rax+rax+00h]
0x140149050  mov     rax, [rdi+0B8h]
0x140149057  lea     rcx, [rdi+0A8h]
0x14014905e  mov     rdx, [rcx]
0x140149061  add     rax, 40h ; '@'
0x140149065  cmp     rdx, rax
0x140149068  jz      short loc_1401490A9
0x14014906a  cmp     [rdx+8], rcx
0x14014906e  jnz     short loc_140149094
0x140149070  mov     rax, [rcx+8]
0x140149074  cmp     [rax], rcx
0x140149077  jnz     short loc_140149094
0x140149079  mov     [rax], rdx
0x14014907c  mov     [rdx+8], rax
0x140149080  mov     rax, [rdi+0B8h]
0x140149087  add     rax, 40h ; '@'
0x14014908b  mov     rdx, [rax+8]
0x14014908f  cmp     [rdx], rax
0x140149092  jz      short loc_14014909B
0x140149094  mov     ecx, 3
0x140149099  int     29h; Win8: RtlFailFast(ecx)
0x14014909b  mov     [rcx], rax
0x14014909e  mov     [rcx+8], rdx
0x1401490a2  mov     [rdx], rcx
0x1401490a5  mov     [rax+8], rcx
0x1401490a9  mov     rax, [rdi+0B8h]
0x1401490b0  mov     rcx, [rax+68h]
0x1401490b4  add     rcx, 8; FastMutex
0x1401490b8  call    cs:__imp_ExReleaseFastMutex
0x1401490bf  nop     dword ptr [rax+rax+00h]
0x1401490c4  test    r14, r14
0x1401490c7  jz      short loc_1401490D6
0x1401490c9  mov     rcx, [r14+78h]
0x1401490cd  test    rcx, rcx
0x1401490d0  jnz     loc_1401492F7
0x1401490d6  call    cs:__imp_IoGetActivityIdThread
0x1401490dd  nop     dword ptr [rax+rax+00h]
0x1401490e2  test    rax, rax
0x1401490e5  jnz     loc_14014935C
0x1401490eb  xor     ecx, ecx
0x1401490ed  mov     qword ptr [rbp+var_48], rcx
0x1401490f1  call    cs:__imp_IoSetActivityIdThread
0x1401490f8  nop     dword ptr [rax+rax+00h]
0x1401490fd  mov     rcx, [rbx+20h]
0x140149101  xor     r12b, r12b
0x140149104  mov     r13, rax
0x140149107  xorps   xmm0, xmm0
0x14014910a  xor     eax, eax
0x14014910c  mov     [rbp+var_20], rax
0x140149110  movups  [rbp+var_30], xmm0
0x140149114  mov     rsi, [rcx+0C0h]
0x14014911b  test    r14, r14
0x14014911e  jz      loc_140149337
0x140149124  mov     rcx, [r14+78h]
0x140149128  test    rcx, rcx
0x14014912b  jnz     loc_140149317
0x140149131  call    cs:__imp_IoGetActivityIdThread
0x140149138  nop     dword ptr [rax+rax+00h]
0x14014913d  test    rax, rax
0x140149140  jnz     loc_140149374
0x140149146  xor     r12d, r12d
0x140149149  mov     qword ptr [rbp+var_30], r12
0x14014914d  test    r12, r12
0x140149150  jnz     loc_1401493C5
0x140149156  mov     [rbx+40h], r12
0x14014915a  lea     rdi, [rsi+2108h]
0x140149161  lock inc dword ptr [rsi+1328h]
0x140149168  mov     rcx, rdi; Mutex
0x14014916b  call    cs:__imp_KeAcquireGuardedMutex
0x140149172  nop     dword ptr [rax+rax+00h]
0x140149177  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14014917e  jnz     loc_1401493FD
0x140149184  mov     r14, rdi
0x140149187  xor     r12b, r12b
0x14014918a  cmp     [rbp+var_50], 0
0x14014918e  jnz     short loc_1401491FA
0x140149190  lea     rax, [rsi+20D0h]
0x140149197  mov     rdx, [rax+8]
0x14014919b  cmp     [rdx], rax
0x14014919e  jnz     loc_140149094
0x1401491a4  mov     [rbx], rax
0x1401491a7  mov     [rbx+8], rdx
0x1401491ab  mov     [rdx], rbx
0x1401491ae  mov     [rax+8], rbx
0x1401491b2  mov     eax, [rsi+20E4h]
0x1401491b8  inc     eax
0x1401491ba  mov     [rsi+20E4h], eax
0x1401491c0  mov     eax, [rsi+20E4h]
0x1401491c6  cmp     eax, [rsi+20E8h]
0x1401491cc  ja      loc_14014938C
0x1401491d2  cmp     byte ptr [rsi+20E0h], 0
0x1401491d9  jnz     loc_140149289
0x1401491df  mov     rcx, r14; Mutex
0x1401491e2  mov     byte ptr [rsi+20E0h], 1
0x1401491e9  call    cs:__imp_KeReleaseGuardedMutex
0x1401491f0  nop     dword ptr [rax+rax+00h]
0x1401491f5  jmp     loc_14014929D
0x1401491fa  lea     rax, [rsi+20F8h]
0x140149201  mov     rcx, [rax+8]
0x140149205  cmp     [rcx], rax
0x140149208  jnz     loc_140149094
0x14014920e  mov     [rbx], rax
0x140149211  mov     [rbx+8], rcx
0x140149215  mov     [rcx], rbx
0x140149218  mov     [rax+8], rbx
0x14014921c  mov     rax, [rbx+20h]
0x140149220  mov     rcx, [rax+0B8h]
0x140149227  mov     rax, [rcx+110h]
0x14014922e  test    rax, rax
0x140149231  jnz     loc_14014941A
0x140149237  mov     [rcx+110h], rbx
0x14014923e  mov     eax, [rsi+20ECh]
0x140149244  inc     eax
0x140149246  mov     [rsi+20ECh], eax
0x14014924c  mov     eax, [rsi+20ECh]
0x140149252  cmp     eax, [rsi+20F0h]
0x140149258  jbe     short loc_140149266
0x14014925a  mov     eax, [rsi+20ECh]
0x140149260  mov     [rsi+20F0h], eax
0x140149266  mov     rax, [rbx+20h]
0x14014926a  mov     rcx, [rax+0B8h]
0x140149271  inc     dword ptr [rcx+10Ch]
0x140149277  mov     eax, [rsi+20ECh]
0x14014927d  cmp     eax, cs:NtfsMaxDelayCloseCount
0x140149283  ja      loc_14014939D
0x140149289  mov     rcx, rdi; Mutex
0x14014928c  call    cs:__imp_KeReleaseGuardedMutex
0x140149293  nop     dword ptr [rax+rax+00h]
0x140149298  test    r12b, r12b
0x14014929b  jz      short loc_1401492B9
0x14014929d  lock inc dword ptr [rsi+11Ch]
0x1401492a4  lea     rcx, [rsi+20B0h]; WorkItem
0x1401492ab  xor     edx, edx; QueueType
0x1401492ad  call    cs:__imp_ExQueueWorkItem
0x1401492b4  nop     dword ptr [rax+rax+00h]
0x1401492b9  mov     rcx, r13
0x1401492bc  call    cs:__imp_IoClearActivityIdThread
0x1401492c3  nop     dword ptr [rax+rax+00h]
0x1401492c8  mov     r13, [rsp+80h+var_8]
0x1401492cd  mov     al, 1
0x1401492cf  mov     r12, [rsp+80h+arg_10]
0x1401492d7  mov     r15, [rsp+80h+var_10]
0x1401492dc  mov     rcx, [rbp+var_18]
0x1401492e0  xor     rcx, rsp; StackCookie
0x1401492e3  call    __security_check_cookie
0x1401492e8  add     rsp, 80h
0x1401492ef  pop     r14
0x1401492f1  pop     rdi
0x1401492f2  pop     rsi
0x1401492f3  pop     rbx
0x1401492f4  pop     rbp
0x1401492f5  retn
0x1401492f7  mov     rax, [rcx]
0x1401492fa  mov     qword ptr [rbp+var_48+8], rax
0x1401492fe  mov     rax, [rcx+8]
0x140149302  mov     [rbp+var_38], rax
0x140149306  lea     rax, [rbp+var_48+8]
0x14014930a  mov     qword ptr [rbp+var_48], rax
0x14014930e  mov     rcx, qword ptr [rbp+var_48]
0x140149312  jmp     loc_1401490F1
0x140149317  mov     rax, [rcx]
0x14014931a  mov     qword ptr [rbp+var_30+8], rax
0x14014931e  mov     rax, [rcx+8]
0x140149322  mov     [rbp+var_20], rax
0x140149326  lea     rax, [rbp+var_30+8]
0x14014932a  mov     qword ptr [rbp+var_30], rax
0x14014932e  mov     r12, qword ptr [rbp+var_30]
0x140149332  jmp     loc_14014914D
0x140149337  lock inc dword ptr [rsi+1328h]
0x14014933e  lea     rdi, [rsi+2108h]
0x140149345  mov     rcx, rdi; Mutex
0x140149348  mov     r14, rdi
0x14014934b  call    cs:__imp_KeAcquireGuardedMutex
0x140149352  nop     dword ptr [rax+rax+00h]
0x140149357  jmp     loc_14014918A
0x14014935c  mov     rcx, [rax]
0x14014935f  mov     qword ptr [rbp+var_48+8], rcx
0x140149363  lea     rcx, [rbp+var_48+8]
0x140149367  mov     rax, [rax+8]
0x14014936b  mov     [rbp+var_38], rax
0x14014936f  jmp     loc_1401490ED
0x140149374  mov     rcx, [rax]
0x140149377  lea     r12, [rbp+var_30+8]
0x14014937b  mov     qword ptr [rbp+var_30+8], rcx
0x14014937f  mov     rax, [rax+8]
0x140149383  mov     [rbp+var_20], rax
0x140149387  jmp     loc_140149149
0x14014938c  mov     eax, [rsi+20E4h]
0x140149392  mov     [rsi+20E8h], eax
0x140149398  jmp     loc_1401491D2
0x14014939d  cmp     byte ptr [rsi+20E0h], 0
0x1401493a4  mov     byte ptr [rsi+20E2h], 1
0x1401493ab  jnz     loc_140149289
0x1401493b1  mov     byte ptr [rsi+20E0h], 1
0x1401493b8  mov     r12b, 1
0x1401493bb  jmp     loc_140149289
0x1401493c0  jmp     loc_1401492DC
0x1401493c5  lea     rdi, [rbx+48h]
0x1401493c9  mov     ecx, 3; ControlCode
0x1401493ce  mov     rdx, rdi; ActivityId
0x1401493d1  call    cs:__imp_EtwActivityIdControl
0x1401493d8  nop     dword ptr [rax+rax+00h]
0x1401493dd  mov     [rbx+40h], rdi
0x1401493e1  mov     rcx, r12
0x1401493e4  mov     rdx, [rbx+40h]
0x1401493e8  call    cs:__imp_IoTransferActivityId
0x1401493ef  nop     dword ptr [rax+rax+00h]
0x1401493f4  mov     rax, [rbx+40h]
0x1401493f8  jmp     loc_14014915A
0x1401493fd  mov     r8, [r14+78h]
0x140149401  lea     rdx, WORKITEM_QUEUE
0x140149408  mov     [rsp+80h+var_60], 2
0x140149410  call    McTemplateK0pq_EtwWriteTransfer
0x140149415  jmp     loc_140149184
0x14014941a  mov     rcx, [rax+18h]
0x14014941e  add     rax, 10h
0x140149422  cmp     [rcx], rax
0x140149425  jnz     loc_140149094
0x14014942b  mov     [r15], rax
0x14014942e  mov     [r15+8], rcx
0x140149432  mov     [rcx], r15
0x140149435  mov     [rax+8], r15
0x140149439  jmp     loc_14014923E
```
