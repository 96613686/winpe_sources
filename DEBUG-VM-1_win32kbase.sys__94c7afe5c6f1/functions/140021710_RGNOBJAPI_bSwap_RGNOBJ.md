# RGNOBJAPI::bSwap(RGNOBJ *)

- ea: `0x140021710`
- end: `0x140021b92`
- name: `?bSwap@RGNOBJAPI@@QEAAHPEAVRGNOBJ@@@Z`
- size: `1154`
- prototype: `__int64 __fastcall(RGNOBJAPI *__hidden this, struct RGNOBJ *)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x14000e800`
- `0x140018d20`
- `0x140019670`
- `0x14001fb00`
- `0x14002a160`

## callees

- `0x140006cf8`
- `0x14001c2d0`
- `0x14001d250`
- `0x140021710`
- `0x140028974`
- `0x14003bf24`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400218f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021ad1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400218f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021ad1`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140021b54`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140021b54`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140021b45`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140021b45`
- `ntoskrnl!KeIsAttachedProcess` at `0x14002177b`
- `ntoskrnl!KeIsAttachedProcess` at `0x14002177b`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14002176c`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14002176c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002199a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400219de`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140021a44`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002199a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400219de`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140021a44`
- `WIN32K!W32GetSessionState` at `0x14002173e`
- `WIN32K!W32GetSessionState` at `0x140021883`
- `WIN32K!W32GetSessionState` at `0x14002173e`
- `WIN32K!W32GetSessionState` at `0x140021883`

## pseudocode

```c
__int64 __fastcall RGNOBJAPI::bSwap(__int64 **this, __int64 **a2)
{
  __int64 v2; // rsi
  __int64 *v3; // rbx
  __int64 SessionState; // rax
  __int64 v7; // r13
  unsigned int v8; // edi
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // r14
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  unsigned int *v13; // r14
  unsigned int v14; // esi
  __int64 *v15; // r10
  __int16 v16; // r8
  __int64 v17; // rdi
  unsigned __int16 v18; // cx
  int v19; // esi
  __int16 v20; // dx
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int16 v25; // ax
  __int64 *v26; // rdi
  __int64 v27; // rbx
  __int64 v28; // rax
  int v29; // r8d
  __int64 *v30; // rbx
  _QWORD *v31; // rsi
  __int64 v32; // rdi
  _QWORD *v33; // r14
  __int64 **v34; // rax
  _QWORD *v35; // rax
  __int64 v36; // rcx
  _QWORD *v37; // rdx
  __int64 *v38; // rcx
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 *v40; // rdi
  _QWORD *v41; // rbx
  __int64 *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rdx
  _QWORD *v45; // rax
  __int64 v46; // rcx
  __int64 *v47; // rdi
  _QWORD *v48; // rbx
  __int64 *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rdx
  _QWORD *v52; // rax
  __int64 v53; // rcx
  ThreadRestrictNewHandlesRegion *v55; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v58; // [rsp+20h] [rbp-28h] BYREF
  int v59; // [rsp+28h] [rbp-20h]
  int v60; // [rsp+2Ch] [rbp-1Ch]
  __int64 v61; // [rsp+30h] [rbp-18h]
  __int64 *v62; // [rsp+90h] [rbp+48h]
  __int64 v63; // [rsp+98h] [rbp+50h] BYREF
  __int64 v64; // [rsp+A0h] [rbp+58h]
  __int64 *v65; // [rsp+A8h] [rbp+60h]

  v2 = 0;
  v3 = *this;
  v65 = *a2;
  v62 = v3;
  LOWORD(v60) = 0;
  SessionState = W32GetSessionState(this);
  v63 = 0;
  v7 = *(_QWORD *)(SessionState + 88);
  v8 = (unsigned __int16)*(_DWORD *)v3 | (*(_DWORD *)v3 >> 8) & 0xFF0000;
  v61 = v7;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v63);
  if ( !(unsigned __int8)KeIsAttachedProcess()
    || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
        CurrentThreadProcess = PsGetCurrentThreadProcess(),
        CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
  {
    if ( CurrentThreadWin32ThreadAndEnterCriticalRegion )
      v2 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  }
  v10 = (v2 + 8) & -(__int64)(v2 != 0);
  if ( v10 )
    v64 = *(_QWORD *)(((v2 + 8) & -(__int64)(v2 != 0)) + 0x40);
  else
    v64 = 0;
  v11 = *(_QWORD *)(v7 + 8);
  v59 = 1;
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, v8);
  v58 = (unsigned int *)v12;
  v13 = (unsigned int *)v12;
  if ( v12 )
  {
    _m_prefetchw((const void *)(v12 + 8));
    v14 = *(_DWORD *)(v12 + 8) & 0xFFFFFFFE;
    if ( v14 == (v63 & 0xFFFFFFFC) || !v14 || v64 && v14 == (unsigned int)UMPDGetThreadClientPID(v10) )
    {
      if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v7 + 8) + 96LL))(
                         *(_QWORD *)(v7 + 8),
                         *v13)
                     + 14)
          & 0x20) == 0
        || v10
        && (v55 = *(ThreadRestrictNewHandlesRegion **)(v10 + 328)) != 0
        && *((_BYTE *)v55 + 80)
        && ThreadRestrictNewHandlesRegion::InRegion(v55, v8) )
      {
LABEL_9:
        v15 = v65;
        v16 = *((_WORD *)v65 + 7);
        v17 = *v65;
        v18 = *((_WORD *)v62 + 7) & 0x70;
        v19 = *((_DWORD *)v65 + 2);
        v20 = *((_WORD *)v62 + 7) & 0x80;
        v21 = v65[2];
        v60 = *((_DWORD *)v65 + 3);
        v22 = v16 & 0x80u | v18;
        *((_WORD *)v65 + 7) = v22;
        v23 = *(_QWORD *)v62;
        *((_WORD *)v62 + 7) = v16 & 0x70 | v20;
        *v15 = v23;
        *((_WORD *)v15 + 6) = *((_WORD *)v62 + 6);
        *((_DWORD *)v15 + 2) = v62[2];
        v15[2] = *((_QWORD *)v62 + 2);
        v24 = W32GetSessionState(v22);
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(*(_QWORD *)(v24 + 88) + 8LL) + 104LL))(
          *(_QWORD *)(*(_QWORD *)(v24 + 88) + 8LL),
          (unsigned __int16)*v62 | (*v62 >> 8) & 0xFF0000u,
          v65);
        v25 = v60;
        *(_QWORD *)v62 = v17;
        *((_WORD *)v62 + 6) = v25;
        v62[2] = v19;
        *((_QWORD *)v62 + 2) = v21;
        v26 = *(__int64 **)(v7 + 8);
        v27 = *v26;
        v28 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v26 + 96))(v26, *v13);
        (*(void (__fastcall **)(__int64 *, __int64))(v27 + 48))(v26, v28);
        KeLeaveCriticalRegion();
        v29 = *((_DWORD *)*this + 19);
        *((_DWORD *)*this + 19) = *((_DWORD *)*a2 + 19);
        *((_DWORD *)*a2 + 19) = v29;
        v30 = *this + 10;
        v31 = *a2 + 10;
        v32 = *v30;
        v33 = (_QWORD *)*v31;
        if ( *this != (__int64 *)-80LL )
        {
          if ( *(__int64 **)(v32 + 8) != v30 )
            goto LABEL_25;
          v34 = (__int64 **)(*this)[11];
          if ( *v34 != v30 )
            goto LABEL_25;
          *v34 = (__int64 *)v32;
          *(_QWORD *)(v32 + 8) = v34;
          v30[1] = (__int64)v30;
          *v30 = (__int64)v30;
        }
        v35 = *a2 + 10;
        if ( *a2 != (__int64 *)-80LL )
        {
          v36 = *v35;
          if ( *(_QWORD **)(*v35 + 8LL) != v35 )
            goto LABEL_25;
          v37 = (_QWORD *)(*a2)[11];
          if ( (_QWORD *)*v37 != v35 )
            goto LABEL_25;
          *v37 = v36;
          *(_QWORD *)(v36 + 8) = v37;
          v35[1] = v35;
          *v35 = v35;
        }
        v38 = *this;
        *this = *a2;
        *a2 = v38;
        CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread();
        if ( !CurrentThreadWin32Thread
          || (-(__int64)(*CurrentThreadWin32Thread != 0) & (*CurrentThreadWin32Thread + 8LL)) == 0 )
        {
          return 1;
        }
        if ( (__int64 *)v32 != v30 )
        {
          v40 = *this;
          v41 = *this + 10;
          if ( *this != (__int64 *)-80LL )
          {
            v42 = (__int64 *)PsGetCurrentThreadWin32Thread();
            if ( v42 )
              v43 = *v42;
            else
              v43 = 0;
            v41[2] = v40;
            v41[3] = CleanUpRegion;
            v44 = (v43 + 8) & -(__int64)(v43 != 0);
            if ( v44 )
            {
              v45 = (_QWORD *)(v44 + 88);
              v46 = *(_QWORD *)(((v43 + 8) & -(__int64)(v43 != 0)) + 0x58);
              if ( *(_QWORD *)(v46 + 8) != v44 + 88 )
                goto LABEL_25;
              *v41 = v46;
              v41[1] = v45;
              *(_QWORD *)(v46 + 8) = v41;
              *v45 = v41;
            }
            else
            {
              v41[1] = v41;
              *v41 = v41;
            }
          }
        }
        if ( v33 == v31 )
          return 1;
        v47 = *a2;
        v48 = *a2 + 10;
        if ( *a2 == (__int64 *)-80LL )
          return 1;
        v49 = (__int64 *)PsGetCurrentThreadWin32Thread();
        if ( v49 )
          v50 = *v49;
        else
          v50 = 0;
        v48[2] = v47;
        v48[3] = CleanUpRegion;
        v51 = (v50 + 8) & -(__int64)(v50 != 0);
        if ( !v51 )
        {
          v48[1] = v48;
          *v48 = v48;
          return 1;
        }
        v52 = (_QWORD *)(v51 + 88);
        v53 = *(_QWORD *)(((v50 + 8) & -(__int64)(v50 != 0)) + 0x58);
        if ( *(_QWORD *)(v53 + 8) == v51 + 88 )
        {
          *v48 = v53;
          v48[1] = v52;
          *(_QWORD *)(v53 + 8) = v48;
          *v52 = v48;
          return 1;
        }
LABEL_25:
        __fastfail(3u);
      }
      LOBYTE(v60) = 1;
    }
    HANDLELOCK::vUnlock((HANDLELOCK *)&v58);
    if ( v59 )
    {
      v7 = v61;
      v13 = v58;
      goto LABEL_9;
    }
  }
  else
  {
    v59 = 0;
    KeLeaveCriticalRegion();
  }
  HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v58);
  return 0;
}

```

## disassembly

```asm
0x140021710  push    rbp
0x140021712  push    rbx
0x140021713  push    rsi
0x140021714  push    rdi
0x140021715  push    r12
0x140021717  push    r13
0x140021719  push    r14
0x14002171b  push    r15
0x14002171d  mov     rbp, rsp
0x140021720  sub     rsp, 48h
0x140021724  mov     r8, [rdx]
0x140021727  xor     esi, esi
0x140021729  mov     rbx, [rcx]
0x14002172c  mov     r15, rdx
0x14002172f  mov     [rbp+arg_18], r8
0x140021733  mov     r12, rcx
0x140021736  mov     [rbp+arg_0], rbx
0x14002173a  mov     word ptr [rbp+var_1C], si
0x14002173e  call    cs:__imp_W32GetSessionState
0x140021745  nop     dword ptr [rax+rax+00h]
0x14002174a  lea     rcx, [rbp+arg_8]
0x14002174e  mov     [rbp+arg_8], rsi
0x140021752  mov     r13, [rax+58h]
0x140021756  mov     eax, [rbx]
0x140021758  mov     edi, eax
0x14002175a  shr     edi, 8
0x14002175d  movzx   eax, ax
0x140021760  and     edi, 0FF0000h
0x140021766  or      edi, eax
0x140021768  mov     [rbp+var_18], r13
0x14002176c  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x140021773  nop     dword ptr [rax+rax+00h]
0x140021778  mov     r14, rax
0x14002177b  call    cs:__imp_KeIsAttachedProcess
0x140021782  nop     dword ptr [rax+rax+00h]
0x140021787  test    al, al
0x140021789  jnz     loc_140021B3E
0x14002178f  test    r14, r14
0x140021792  jz      short loc_140021797
0x140021794  mov     rsi, [r14]
0x140021797  lea     rax, [rsi+8]
0x14002179b  neg     rsi
0x14002179e  sbb     rbx, rbx
0x1400217a1  and     rbx, rax
0x1400217a4  jz      loc_140021B6D
0x1400217aa  mov     rsi, [rbx+40h]
0x1400217ae  mov     [rbp+arg_10], rsi
0x1400217b2  mov     rcx, [r13+8]
0x1400217b6  mov     edx, edi
0x1400217b8  mov     [rbp+var_20], 1
0x1400217bf  mov     rax, [rcx]
0x1400217c2  mov     rax, [rax+28h]
0x1400217c6  call    _guard_dispatch_icall
0x1400217cb  mov     [rbp+var_28], rax
0x1400217cf  mov     r14, rax
0x1400217d2  test    rax, rax
0x1400217d5  jz      loc_140021ACA
0x1400217db  prefetchw byte ptr [rax+8]
0x1400217df  mov     esi, [rax+8]
0x1400217e2  mov     eax, dword ptr [rbp+arg_8]
0x1400217e5  and     esi, 0FFFFFFFEh
0x1400217e8  and     eax, 0FFFFFFFCh
0x1400217eb  cmp     esi, eax
0x1400217ed  jnz     loc_140021AA9
0x1400217f3  mov     rcx, [r13+8]
0x1400217f7  mov     edx, [r14]
0x1400217fa  mov     rax, [rcx]
0x1400217fd  mov     rax, [rax+60h]
0x140021801  call    _guard_dispatch_icall
0x140021806  test    byte ptr [rax+0Eh], 20h
0x14002180a  jnz     loc_140021AEA
0x140021810  mov     r10, [rbp+arg_18]
0x140021814  mov     r11d, 80h
0x14002181a  mov     r9, [rbp+arg_0]
0x14002181e  mov     eax, [r10+0Ch]
0x140021822  movzx   edx, word ptr [r9+0Eh]
0x140021827  movzx   r8d, word ptr [r10+0Eh]
0x14002182c  movzx   ecx, dx
0x14002182f  mov     rdi, [r10]
0x140021832  and     cx, 70h
0x140021836  mov     esi, [r10+8]
0x14002183a  and     dx, r11w
0x14002183e  mov     rbx, [r10+10h]
0x140021842  mov     [rbp+var_1C], eax
0x140021845  movzx   eax, r8w
0x140021849  and     ax, r11w
0x14002184d  and     r8w, 70h
0x140021852  or      cx, ax
0x140021855  or      dx, r8w
0x140021859  mov     [r10+0Eh], cx
0x14002185e  mov     rax, [r9]
0x140021861  mov     [r9+0Eh], dx
0x140021866  mov     [r10], rax
0x140021869  movzx   eax, word ptr [r9+0Ch]
0x14002186e  xchg    ax, [r10+0Ch]
0x140021873  mov     eax, [r9+8]
0x140021877  mov     [r10+8], eax
0x14002187b  mov     rax, [r9+10h]
0x14002187f  mov     [r10+10h], rax
0x140021883  call    cs:__imp_W32GetSessionState
0x14002188a  nop     dword ptr [rax+rax+00h]
0x14002188f  mov     r8, [rbp+arg_18]
0x140021893  mov     rcx, [rax+58h]
0x140021897  mov     rax, [rbp+arg_0]
0x14002189b  mov     rcx, [rcx+8]
0x14002189f  mov     eax, [rax]
0x1400218a1  mov     edx, eax
0x1400218a3  shr     edx, 8
0x1400218a6  movzx   eax, ax
0x1400218a9  and     edx, 0FF0000h
0x1400218af  mov     r9, [rcx]
0x1400218b2  or      edx, eax
0x1400218b4  mov     rax, [r9+68h]
0x1400218b8  call    _guard_dispatch_icall
0x1400218bd  movzx   eax, word ptr [rbp+var_1C]
0x1400218c1  mov     rcx, [rbp+arg_0]
0x1400218c5  mov     [rcx], rdi
0x1400218c8  xchg    ax, [rcx+0Ch]
0x1400218cc  mov     [rcx+8], esi
0x1400218cf  mov     [rcx+10h], rbx
0x1400218d3  mov     rdi, [r13+8]
0x1400218d7  mov     edx, [r14]
0x1400218da  mov     rcx, rdi
0x1400218dd  mov     rbx, [rdi]
0x1400218e0  mov     rax, [rbx+60h]
0x1400218e4  call    _guard_dispatch_icall
0x1400218e9  mov     rdx, rax
0x1400218ec  mov     rcx, rdi
0x1400218ef  mov     rax, [rbx+30h]
0x1400218f3  call    _guard_dispatch_icall
0x1400218f8  call    cs:__imp_KeLeaveCriticalRegion
0x1400218ff  nop     dword ptr [rax+rax+00h]
0x140021904  mov     rax, [r15]
0x140021907  mov     rdx, [r12]
0x14002190b  mov     ecx, [rax+4Ch]
0x14002190e  mov     r8d, [rdx+4Ch]
0x140021912  mov     [rdx+4Ch], ecx
0x140021915  mov     rax, [r15]
0x140021918  mov     [rax+4Ch], r8d
0x14002191c  mov     rbx, [r12]
0x140021920  mov     rsi, [r15]
0x140021923  add     rbx, 50h ; 'P'
0x140021927  add     rsi, 50h ; 'P'
0x14002192b  mov     rdi, [rbx]
0x14002192e  mov     r14, [rsi]
0x140021931  test    rbx, rbx
0x140021934  jz      short loc_14002195B
0x140021936  cmp     [rdi+8], rbx
0x14002193a  jnz     loc_140021A1E
0x140021940  mov     rax, [rbx+8]
0x140021944  cmp     [rax], rbx
0x140021947  jnz     loc_140021A1E
0x14002194d  mov     [rax], rdi
0x140021950  mov     [rdi+8], rax
0x140021954  mov     [rbx+8], rbx
0x140021958  mov     [rbx], rbx
0x14002195b  mov     rax, [r15]
0x14002195e  add     rax, 50h ; 'P'
0x140021962  jz      short loc_14002198C
0x140021964  mov     rcx, [rax]
0x140021967  cmp     [rcx+8], rax
0x14002196b  jnz     loc_140021A1E
0x140021971  mov     rdx, [rax+8]
0x140021975  cmp     [rdx], rax
0x140021978  jnz     loc_140021A1E
0x14002197e  mov     [rdx], rcx
0x140021981  mov     [rcx+8], rdx
0x140021985  mov     [rax+8], rax
0x140021989  mov     [rax], rax
0x14002198c  mov     rax, [r15]
0x14002198f  mov     rcx, [r12]
0x140021993  mov     [r12], rax
0x140021997  mov     [r15], rcx
0x14002199a  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400219a1  nop     dword ptr [rax+rax+00h]
0x1400219a6  test    rax, rax
0x1400219a9  jz      loc_140021A92
0x1400219af  mov     rax, [rax]
0x1400219b2  lea     rcx, [rax+8]
0x1400219b6  neg     rax
0x1400219b9  sbb     rax, rax
0x1400219bc  test    rcx, rax
0x1400219bf  jz      loc_140021A92
0x1400219c5  lea     r13, ?CleanUpRegion@@YAXPEAVREGION@@@Z; CleanUpRegion(REGION *)
0x1400219cc  cmp     rdi, rbx
0x1400219cf  jz      short loc_140021A33
0x1400219d1  mov     rdi, [r12]
0x1400219d5  lea     rbx, [rdi+50h]
0x1400219d9  test    rbx, rbx
0x1400219dc  jz      short loc_140021A33
0x1400219de  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400219e5  nop     dword ptr [rax+rax+00h]
0x1400219ea  test    rax, rax
0x1400219ed  jz      loc_140021B30
0x1400219f3  mov     rcx, [rax]
0x1400219f6  lea     rax, [rcx+8]
0x1400219fa  mov     [rbx+10h], rdi
0x1400219fe  neg     rcx
0x140021a01  mov     [rbx+18h], r13
0x140021a05  sbb     rdx, rdx
0x140021a08  and     rdx, rax
0x140021a0b  jz      loc_140021B7A
0x140021a11  lea     rax, [rdx+58h]
0x140021a15  mov     rcx, [rax]
0x140021a18  cmp     [rcx+8], rax
0x140021a1c  jz      short loc_140021A25
0x140021a1e  mov     ecx, 3
0x140021a23  int     29h; Win8: RtlFailFast(ecx)
0x140021a25  mov     [rbx], rcx
0x140021a28  mov     [rbx+8], rax
0x140021a2c  mov     [rcx+8], rbx
0x140021a30  mov     [rax], rbx
0x140021a33  cmp     r14, rsi
0x140021a36  jz      short loc_140021A92
0x140021a38  mov     rdi, [r15]
0x140021a3b  lea     rbx, [rdi+50h]
0x140021a3f  test    rbx, rbx
0x140021a42  jz      short loc_140021A92
0x140021a44  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140021a4b  nop     dword ptr [rax+rax+00h]
0x140021a50  test    rax, rax
0x140021a53  jz      loc_140021B37
0x140021a59  mov     rcx, [rax]
0x140021a5c  lea     rax, [rcx+8]
0x140021a60  mov     [rbx+10h], rdi
0x140021a64  neg     rcx
0x140021a67  mov     [rbx+18h], r13
0x140021a6b  sbb     rdx, rdx
0x140021a6e  and     rdx, rax
0x140021a71  jz      loc_140021B86
0x140021a77  lea     rax, [rdx+58h]
0x140021a7b  mov     rcx, [rax]
0x140021a7e  cmp     [rcx+8], rax
0x140021a82  jnz     short loc_140021A1E
0x140021a84  mov     [rbx], rcx
0x140021a87  mov     [rbx+8], rax
0x140021a8b  mov     [rcx+8], rbx
0x140021a8f  mov     [rax], rbx
0x140021a92  mov     eax, 1
0x140021a97  add     rsp, 48h
0x140021a9b  pop     r15
0x140021a9d  pop     r14
0x140021a9f  pop     r13
0x140021aa1  pop     r12
0x140021aa3  pop     rdi
0x140021aa4  pop     rsi
0x140021aa5  pop     rbx
0x140021aa6  pop     rbp
0x140021aa7  retn
0x140021aa9  test    esi, esi
0x140021aab  jz      loc_1400217F3
0x140021ab1  cmp     [rbp+arg_10], 0
0x140021ab6  jz      short loc_140021B14
0x140021ab8  mov     rcx, rbx
0x140021abb  call    UMPDGetThreadClientPID
0x140021ac0  cmp     esi, eax
0x140021ac2  jz      loc_1400217F3
0x140021ac8  jmp     short loc_140021B14
0x140021aca  mov     [rbp+var_20], 0
0x140021ad1  call    cs:__imp_KeLeaveCriticalRegion
0x140021ad8  nop     dword ptr [rax+rax+00h]
0x140021add  lea     rcx, [rbp+var_28]; this
0x140021ae1  call    ??1HANDLELOCK@@QEAA@XZ; HANDLELOCK::~HANDLELOCK(void)
0x140021ae6  xor     eax, eax
0x140021ae8  jmp     short loc_140021A97
0x140021aea  test    rbx, rbx
0x140021aed  jz      short loc_140021B10
0x140021aef  mov     rcx, [rbx+148h]; this
0x140021af6  test    rcx, rcx
0x140021af9  jz      short loc_140021B10
0x140021afb  cmp     byte ptr [rcx+50h], 0
0x140021aff  jz      short loc_140021B10
0x140021b01  mov     edx, edi; unsigned int
0x140021b03  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x140021b08  test    al, al
0x140021b0a  jnz     loc_140021810
0x140021b10  mov     byte ptr [rbp+var_1C], 1
0x140021b14  lea     rcx, [rbp+var_28]; this
0x140021b18  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x140021b1d  cmp     [rbp+var_20], 0
0x140021b21  jz      short loc_140021ADD
0x140021b23  mov     r13, [rbp+var_18]
0x140021b27  mov     r14, [rbp+var_28]
0x140021b2b  jmp     loc_140021810
0x140021b30  xor     ecx, ecx
0x140021b32  jmp     loc_1400219F6
0x140021b37  xor     ecx, ecx
0x140021b39  jmp     loc_140021A5C
0x140021b3e  call    W32GetCurrentWin32kSessionId
0x140021b43  mov     ebx, eax
0x140021b45  call    cs:__imp_PsGetCurrentThreadProcess
0x140021b4c  nop     dword ptr [rax+rax+00h]
0x140021b51  mov     rcx, rax
0x140021b54  call    cs:__imp_PsGetProcessSessionIdEx
0x140021b5b  nop     dword ptr [rax+rax+00h]
0x140021b60  cmp     ebx, eax
0x140021b62  jz      loc_14002178F
0x140021b68  jmp     loc_140021797
0x140021b6d  mov     [rbp+arg_10], 0
0x140021b75  jmp     loc_1400217B2
  ... truncated ...
```
