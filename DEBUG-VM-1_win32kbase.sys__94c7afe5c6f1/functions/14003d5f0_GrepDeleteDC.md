# GrepDeleteDC

- ea: `0x14003d5f0`
- end: `0x14003dc62`
- name: `GrepDeleteDC`
- size: `1650`
- prototype: `__int64 __fastcall(HDC, unsigned int)`
- caller_count: `8`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000e260`
- `0x1400332c8`
- `0x140036210`
- `0x14003764c`
- `0x14003bf50`
- `0x1400b00d0`
- `0x1400b401c`
- `0x1401109b0`

## callees

- `0x140006cf8`
- `0x140008160`
- `0x14000f680`
- `0x140016500`
- `0x140019fd0`
- `0x14001d250`
- `0x14001fa50`
- `0x140028974`
- `0x14003bf24`
- `0x14003c120`
- `0x14003c1a0`
- `0x14003c6e4`
- `0x14003cef4`
- `0x14003d5f0`
- `0x14003f390`
- `0x140040150`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d922`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003db11`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d922`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003db11`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14003d6bb`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14003d6bb`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003d963`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003d963`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003dbd1`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003dbd1`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14003dc31`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14003dc31`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003dbc2`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003dbc2`
- `ntoskrnl!KeIsAttachedProcess` at `0x14003d7ef`
- `ntoskrnl!KeIsAttachedProcess` at `0x14003d7ef`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x14003dbfa`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x14003dbfa`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14003d7e0`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14003d7e0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003d643`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003d643`
- `WIN32K!W32GetSessionState` at `0x14003d615`
- `WIN32K!W32GetSessionState` at `0x14003d615`

## pseudocode

```c
_BOOL8 __fastcall GrepDeleteDC(HDC a1, unsigned int a2)
{
  HDC v3; // rdi
  __int64 v4; // rbx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  _QWORD *CurrentProcessWin32Process; // rax
  DC *v10; // rsi
  char v11; // bl
  DC *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  struct Gre::Base::SESSION_GLOBALS *v16; // r13
  unsigned int v17; // r12d
  __int64 v18; // rdi
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // r14
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rbx
  int v23; // edi
  __int64 v24; // rax
  unsigned int *v25; // r14
  unsigned int v26; // r13d
  struct _KTHREAD *CurrentThread; // rbx
  __int64 v28; // rax
  __int64 *v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rax
  unsigned int CurrentProcessId; // eax
  DC *v33; // rdx
  unsigned int v34; // ebx
  char *v35; // rax
  struct _ENTRY *v36; // rax
  struct _DC_ATTR *v37; // rax
  __int64 v38; // rdx
  int v39; // ecx
  int v40; // ecx
  DC *v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rcx
  ThreadRestrictNewHandlesRegion *v44; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  struct Gre::Base::SESSION_GLOBALS *v47; // [rsp+20h] [rbp-60h]
  unsigned int *v48; // [rsp+28h] [rbp-58h] BYREF
  int v49; // [rsp+30h] [rbp-50h]
  __int16 v50; // [rsp+34h] [rbp-4Ch]
  struct Gre::Base::SESSION_GLOBALS *v51; // [rsp+38h] [rbp-48h]
  DC *v52; // [rsp+40h] [rbp-40h] BYREF
  int v53; // [rsp+48h] [rbp-38h]
  struct Gre::Base::SESSION_GLOBALS *v54; // [rsp+50h] [rbp-30h]
  __int64 v55; // [rsp+58h] [rbp-28h]
  __int128 v56; // [rsp+60h] [rbp-20h] BYREF
  __int128 v57; // [rsp+70h] [rbp-10h]
  __int64 v59; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v60; // [rsp+D8h] [rbp+58h]

  v3 = a1;
  v4 = *(_QWORD *)(W32GetSessionState(a1) + 88);
  v54 = (struct Gre::Base::SESSION_GLOBALS *)v4;
  v55 = 0;
  v52 = 0;
  v53 = 0;
  v56 = 0;
  v57 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
  if ( CurrentThreadWin32Thread )
    v6 = *CurrentThreadWin32Thread;
  else
    v6 = 0;
  v7 = (v6 + 8) & -(__int64)(v6 != 0);
  *(_QWORD *)&v57 = &v52;
  *((_QWORD *)&v57 + 1) = UnexpectedThreadTerminationHandler<HmgLockResult<DRVOBJ>>::OnUnexpectedThreadTerminationStatic;
  if ( v7 )
  {
    v8 = *(_QWORD *)(((v6 + 8) & -(__int64)(v6 != 0)) + 0x58);
    if ( *(_QWORD *)(v8 + 8) != v7 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v56 = *(_QWORD *)(v7 + 88);
    *((_QWORD *)&v56 + 1) = v7 + 88;
    *(_QWORD *)(v8 + 8) = &v56;
    *(_QWORD *)(v7 + 88) = &v56;
  }
  else
  {
    *((_QWORD *)&v56 + 1) = &v56;
    *(_QWORD *)&v56 = &v56;
  }
  if ( *(_DWORD *)(v4 + 3112)
    || (CurrentProcessWin32Process = (_QWORD *)PsGetCurrentProcessWin32Process()) == 0
    || !*CurrentProcessWin32Process )
  {
    DCOBJ::vLockIgnoreAttributes((DCOBJ *)&v52, v3);
LABEL_11:
    v10 = v52;
    goto LABEL_12;
  }
  v16 = v54;
  v10 = 0;
  v50 = 0;
  v17 = (unsigned __int16)v3 | ((unsigned int)v3 >> 8) & 0xFF0000;
  v47 = v54;
  v51 = v54;
  v18 = 0;
  v59 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v59);
  if ( !(unsigned __int8)KeIsAttachedProcess()
    || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
        CurrentThreadProcess = PsGetCurrentThreadProcess(),
        CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
  {
    if ( CurrentThreadWin32ThreadAndEnterCriticalRegion )
      v18 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  }
  v20 = v18 + 8;
  v21 = -v18;
  v22 = v20 & -(__int64)(v21 != 0);
  if ( v22 )
  {
    v60 = *(_QWORD *)((v20 & -(__int64)(v21 != 0)) + 0x40);
    v16 = v47;
  }
  else
  {
    v60 = 0;
  }
  v23 = 1;
  v49 = 1;
  v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v16 + 1) + 40LL))(*((_QWORD *)v16 + 1), v17);
  v48 = (unsigned int *)v24;
  v25 = (unsigned int *)v24;
  if ( !v24 )
  {
    v23 = 0;
    KeLeaveCriticalRegion();
    goto LABEL_34;
  }
  _m_prefetchw((const void *)(v24 + 8));
  v26 = *(_DWORD *)(v24 + 8) & 0xFFFFFFFE;
  if ( v26 != (v59 & 0xFFFFFFFC) && v26 && (!v60 || v26 != (unsigned int)UMPDGetThreadClientPID(v22)) )
    goto LABEL_82;
  v16 = v47;
  if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v47 + 1) + 96LL))(
                     *((_QWORD *)v47 + 1),
                     *v25)
                 + 14)
      & 0x20) != 0
    && (!v22
     || (v44 = *(ThreadRestrictNewHandlesRegion **)(v22 + 328)) == 0
     || !*((_BYTE *)v44 + 80)
     || !ThreadRestrictNewHandlesRegion::InRegion(v44, v17)) )
  {
    LOBYTE(v50) = 1;
LABEL_82:
    HANDLELOCK::vUnlock((HANDLELOCK *)&v48);
    v25 = v48;
    v23 = v49;
    v16 = v51;
  }
LABEL_34:
  if ( v23 )
  {
    if ( *((_BYTE *)v25 + 14) == 1 && *((_WORD *)v25 + 6) == WORD1(a1) )
    {
      CurrentThread = KeGetCurrentThread();
      v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v16 + 1) + 96LL))(*((_QWORD *)v16 + 1), *v25);
      v10 = (DC *)v28;
      if ( !*(_WORD *)(v28 + 12) || *(struct _KTHREAD **)(v28 + 16) == CurrentThread )
      {
        _InterlockedAdd16((volatile signed __int16 *)(v28 + 12), 1u);
        *(_QWORD *)(v28 + 16) = CurrentThread;
      }
      else
      {
        v10 = 0;
      }
    }
    v29 = (__int64 *)*((_QWORD *)v16 + 1);
    v30 = *v29;
    v31 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v29 + 96))(v29, *v25);
    (*(void (__fastcall **)(__int64 *, __int64))(v30 + 48))(v29, v31);
    KeLeaveCriticalRegion();
  }
  v52 = v10;
  if ( v10 )
  {
    if ( *((_DWORD *)v10 + 534) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)v10 + 6);
      v10 = 0;
      v52 = 0;
    }
  }
  else
  {
    if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction() != 1
      && (unsigned __int8)PsIsWin32KFilterAuditEnabled() )
    {
      PsGetWin32KFilterSet();
    }
    v10 = v52;
  }
  if ( !v10 )
    goto LABEL_56;
  if ( (*((_DWORD *)v10 + 11) & 2) == 0 )
  {
    CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
    v33 = v52;
    v34 = CurrentProcessId & 0xFFFFFFFC;
    if ( *(_QWORD *)v52 )
    {
      v35 = (char *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v54 + 1) + 8LL))(*((_QWORD *)v54 + 1));
    }
    else
    {
      v35 = (char *)v52 + 2152;
      *(_OWORD *)((char *)v52 + 2152) = 0;
      *((_QWORD *)v33 + 271) = 0;
      *((_DWORD *)v33 + 540) = -2147483630;
      *((_QWORD *)v33 + 271) = 0;
    }
    if ( v34 == (*((_DWORD *)v35 + 2) & 0xFFFFFFFE) )
    {
      v36 = DC::PentryFromPobj(v52, v54);
      if ( v36 )
      {
        v37 = (struct _DC_ATTR *)GreDecodeUserModePointer(*((void **)v36 + 2));
        if ( v37 )
        {
          if ( !(unsigned int)DC::SaveAttributes(v52, v37) )
          {
            _InterlockedDecrement16((volatile signed __int16 *)v52 + 6);
            v52 = 0;
            goto LABEL_56;
          }
        }
      }
    }
    *((_DWORD *)v52 + 11) |= 2u;
    v10 = v52;
    v53 = 1;
  }
  v3 = a1;
  if ( (*((_DWORD *)v10 + 130) & 4) != 0 )
  {
    *((_DWORD *)v10 + 130) &= ~4u;
    v38 = *((_QWORD *)v10 + 122);
    v39 = *(_DWORD *)(v38 + 340);
    if ( (*((_DWORD *)v10 + 130) & 1) != 0 )
      v40 = v39 | 0x16090;
    else
      v40 = v39 | 0x6090;
    *(_DWORD *)(v38 + 340) = v40;
    goto LABEL_11;
  }
LABEL_12:
  if ( !v10 )
  {
LABEL_56:
    EngSetLastError(0xAAu);
    v41 = v52;
    if ( v52 )
    {
      if ( v53 && (*((_DWORD *)v52 + 11) & 2) != 0 )
      {
        DCOBJ::RestoreAttributesHelper((DCOBJ *)&v52);
        *((_DWORD *)v52 + 11) &= ~2u;
        v41 = v52;
        v53 = 0;
      }
      _InterlockedDecrement16((volatile signed __int16 *)v41 + 6);
      v52 = 0;
    }
    v42 = v56;
    if ( *(__int128 **)(v56 + 8) != &v56 || (v43 = *((_QWORD *)&v56 + 1), **((__int128 ***)&v56 + 1) != &v56) )
LABEL_5:
      __fastfail(3u);
    **((_QWORD **)&v56 + 1) = v56;
    *(_QWORD *)(v42 + 8) = v43;
    return 0;
  }
  if ( (a2 & 0x400000) != 0 )
  {
    *((_BYTE *)v10 + 2090) = 0;
    v10 = v52;
  }
  if ( !*((_BYTE *)v10 + 2090) )
  {
    v11 = 0;
    if ( XDCOBJ::bDelete((XDCOBJ *)&v52, a2) )
      goto LABEL_17;
    EngSetLastError(0xAAu);
    DCOBJ::~DCOBJ((DCOBJ *)&v52);
    return 0;
  }
  v11 = 1;
  XDCOBJ::bCleanDC((XDCOBJ *)&v52, a2 & 0x1000000);
LABEL_17:
  v12 = v52;
  if ( v52 )
  {
    if ( v53 && (*((_DWORD *)v52 + 11) & 2) != 0 )
    {
      DCOBJ::RestoreAttributesHelper((DCOBJ *)&v52);
      *((_DWORD *)v52 + 11) &= ~2u;
      v12 = v52;
      v53 = 0;
    }
    _InterlockedDecrement16((volatile signed __int16 *)v12 + 6);
    v52 = 0;
  }
  v13 = v56;
  if ( *(__int128 **)(v56 + 8) != &v56 )
    goto LABEL_5;
  v14 = *((_QWORD *)&v56 + 1);
  if ( **((__int128 ***)&v56 + 1) != &v56 )
    goto LABEL_5;
  **((_QWORD **)&v56 + 1) = v56;
  *(_QWORD *)(v13 + 8) = v14;
  return !v11 || (unsigned int)UserReleaseDC(v3) != 0;
}

```

## disassembly

```asm
0x14003d5f0  mov     [rsp-38h+arg_8], rbx
0x14003d5f5  mov     [rsp-38h+arg_0], rcx
0x14003d5fa  push    rbp
0x14003d5fb  push    rsi
0x14003d5fc  push    rdi
0x14003d5fd  push    r12
0x14003d5ff  push    r13
0x14003d601  push    r14
0x14003d603  push    r15
0x14003d605  mov     rbp, rsp
0x14003d608  sub     rsp, 80h
0x14003d60f  mov     r15d, edx
0x14003d612  mov     rdi, rcx
0x14003d615  call    cs:__imp_W32GetSessionState
0x14003d61c  nop     dword ptr [rax+rax+00h]
0x14003d621  xor     r14d, r14d
0x14003d624  xorps   xmm0, xmm0
0x14003d627  mov     rbx, [rax+58h]
0x14003d62b  mov     [rbp+var_30], rbx
0x14003d62f  mov     [rbp+var_28], r14
0x14003d633  mov     [rbp+var_40], r14
0x14003d637  mov     [rbp+var_38], r14d
0x14003d63b  movups  [rbp+var_20], xmm0
0x14003d63f  movups  [rbp+var_10], xmm0
0x14003d643  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14003d64a  nop     dword ptr [rax+rax+00h]
0x14003d64f  test    rax, rax
0x14003d652  jz      loc_14003DBB3
0x14003d658  mov     rcx, [rax]
0x14003d65b  lea     rax, [rcx+8]
0x14003d65f  neg     rcx
0x14003d662  sbb     rdx, rdx
0x14003d665  and     rdx, rax
0x14003d668  lea     rax, [rbp+var_40]
0x14003d66c  mov     qword ptr [rbp+var_10], rax
0x14003d670  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VDRVOBJ@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<DRVOBJ>>::OnUnexpectedThreadTerminationStatic(void *)
0x14003d677  mov     qword ptr [rbp+var_10+8], rax
0x14003d67b  jz      loc_14003DC1C
0x14003d681  lea     rax, [rdx+58h]
0x14003d685  mov     rcx, [rax]
0x14003d688  cmp     [rcx+8], rax
0x14003d68c  jz      short loc_14003D695
0x14003d68e  mov     ecx, 3
0x14003d693  int     29h; Win8: RtlFailFast(ecx)
0x14003d695  mov     qword ptr [rbp+var_20], rcx
0x14003d699  lea     rdx, [rbp+var_20]
0x14003d69d  mov     qword ptr [rbp+var_20+8], rax
0x14003d6a1  mov     [rcx+8], rdx
0x14003d6a5  lea     rcx, [rbp+var_20]
0x14003d6a9  mov     [rax], rcx
0x14003d6ac  mov     r12d, 1
0x14003d6b2  cmp     [rbx+0C28h], r14d
0x14003d6b9  jnz     short loc_14003D6D5
0x14003d6bb  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14003d6c2  nop     dword ptr [rax+rax+00h]
0x14003d6c7  test    rax, rax
0x14003d6ca  jz      short loc_14003D6D5
0x14003d6cc  cmp     [rax], r14
0x14003d6cf  jnz     loc_14003D7AD
0x14003d6d5  mov     rdx, rdi; HDC
0x14003d6d8  lea     rcx, [rbp+var_40]; this
0x14003d6dc  call    ?vLockIgnoreAttributes@DCOBJ@@QEAAXPEAUHDC__@@@Z; DCOBJ::vLockIgnoreAttributes(HDC__ *)
0x14003d6e1  mov     rsi, [rbp+var_40]
0x14003d6e5  test    rsi, rsi
0x14003d6e8  jz      loc_14003DA3A
0x14003d6ee  bt      r15d, 16h
0x14003d6f3  jnb     short loc_14003D700
0x14003d6f5  mov     [rsi+82Ah], r14b
0x14003d6fc  mov     rsi, [rbp+var_40]
0x14003d700  lea     rcx, [rbp+var_40]; this
0x14003d704  cmp     [rsi+82Ah], r14b
0x14003d70b  jnz     loc_14003DA9B
0x14003d711  mov     edx, r15d; unsigned int
0x14003d714  mov     bl, r14b
0x14003d717  call    ?bDelete@XDCOBJ@@QEAA_NK@Z; XDCOBJ::bDelete(ulong)
0x14003d71c  test    al, al
0x14003d71e  jz      loc_14003DB22
0x14003d724  mov     rcx, [rbp+var_40]
0x14003d728  test    rcx, rcx
0x14003d72b  jz      short loc_14003D75C
0x14003d72d  cmp     [rbp+var_38], r14d
0x14003d731  jz      short loc_14003D753
0x14003d733  mov     eax, [rcx+2Ch]
0x14003d736  test    al, 2
0x14003d738  jz      short loc_14003D753
0x14003d73a  lea     rcx, [rbp+var_40]; this
0x14003d73e  call    ?RestoreAttributesHelper@DCOBJ@@AEAAXXZ; DCOBJ::RestoreAttributesHelper(void)
0x14003d743  mov     rax, [rbp+var_40]
0x14003d747  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x14003d74b  mov     rcx, [rbp+var_40]
0x14003d74f  mov     [rbp+var_38], r14d
0x14003d753  lock dec word ptr [rcx+0Ch]
0x14003d758  mov     [rbp+var_40], r14
0x14003d75c  mov     rax, qword ptr [rbp+var_20]
0x14003d760  lea     rcx, [rbp+var_20]
0x14003d764  cmp     [rax+8], rcx
0x14003d768  jnz     loc_14003D68E
0x14003d76e  mov     rcx, qword ptr [rbp+var_20+8]
0x14003d772  lea     rdx, [rbp+var_20]
0x14003d776  cmp     [rcx], rdx
0x14003d779  jnz     loc_14003D68E
0x14003d77f  mov     [rcx], rax
0x14003d782  mov     [rax+8], rcx
0x14003d786  test    bl, bl
0x14003d788  jnz     loc_14003DB57
0x14003d78e  mov     eax, r12d
0x14003d791  mov     rbx, [rsp+80h+arg_8]
0x14003d799  add     rsp, 80h
0x14003d7a0  pop     r15
0x14003d7a2  pop     r14
0x14003d7a4  pop     r13
0x14003d7a6  pop     r12
0x14003d7a8  pop     rdi
0x14003d7a9  pop     rsi
0x14003d7aa  pop     rbp
0x14003d7ab  retn
0x14003d7ad  mov     r13, [rbp+var_30]
0x14003d7b1  lea     rcx, [rbp+arg_10]
0x14003d7b5  movzx   eax, di
0x14003d7b8  mov     r12d, edi
0x14003d7bb  shr     r12d, 8
0x14003d7bf  mov     rsi, r14
0x14003d7c2  and     r12d, 0FF0000h
0x14003d7c9  mov     [rbp+var_4C], r14w
0x14003d7ce  or      r12d, eax
0x14003d7d1  mov     [rbp+var_60], r13
0x14003d7d5  mov     [rbp+var_48], r13
0x14003d7d9  mov     rdi, r14
0x14003d7dc  mov     [rbp+arg_10], r14
0x14003d7e0  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x14003d7e7  nop     dword ptr [rax+rax+00h]
0x14003d7ec  mov     r14, rax
0x14003d7ef  call    cs:__imp_KeIsAttachedProcess
0x14003d7f6  nop     dword ptr [rax+rax+00h]
0x14003d7fb  test    al, al
0x14003d7fd  jnz     loc_14003DBBB
0x14003d803  test    r14, r14
0x14003d806  jz      short loc_14003D80B
0x14003d808  mov     rdi, [r14]
0x14003d80b  lea     rax, [rdi+8]
0x14003d80f  neg     rdi
0x14003d812  sbb     rbx, rbx
0x14003d815  and     rbx, rax
0x14003d818  jz      loc_14003DC13
0x14003d81e  mov     r13, [rbx+40h]
0x14003d822  mov     [rbp+arg_18], r13
0x14003d826  mov     r13, [rbp+var_60]
0x14003d82a  mov     ecx, 1
0x14003d82f  mov     edx, r12d
0x14003d832  mov     edi, ecx
0x14003d834  mov     [rbp+var_50], ecx
0x14003d837  mov     rcx, [r13+8]
0x14003d83b  mov     rax, [rcx]
0x14003d83e  mov     rax, [rax+28h]
0x14003d842  call    _guard_dispatch_icall
0x14003d847  xor     ecx, ecx
0x14003d849  mov     [rbp+var_58], rax
0x14003d84d  mov     r14, rax
0x14003d850  test    rax, rax
0x14003d853  jz      loc_14003DB0F
0x14003d859  prefetchw byte ptr [rax+8]
0x14003d85d  mov     r13d, [rax+8]
0x14003d861  mov     eax, dword ptr [rbp+arg_10]
0x14003d864  and     r13d, 0FFFFFFFEh
0x14003d868  and     eax, 0FFFFFFFCh
0x14003d86b  cmp     r13d, eax
0x14003d86e  jnz     loc_14003DAB2
0x14003d874  mov     r13, [rbp+var_60]
0x14003d878  mov     edx, [r14]
0x14003d87b  mov     rcx, [r13+8]
0x14003d87f  mov     rax, [rcx]
0x14003d882  mov     rax, [rax+60h]
0x14003d886  call    _guard_dispatch_icall
0x14003d88b  test    byte ptr [rax+0Eh], 20h
0x14003d88f  jnz     loc_14003DB6E
0x14003d895  xor     r12d, r12d
0x14003d898  test    edi, edi
0x14003d89a  jz      loc_14003D92E
0x14003d8a0  cmp     byte ptr [r14+0Eh], 1
0x14003d8a5  jnz     short loc_14003D8FD
0x14003d8a7  movzx   eax, byte ptr [r14+0Ch]
0x14003d8ac  movzx   ecx, byte ptr [r14+0Dh]
0x14003d8b1  shl     cx, 8
0x14003d8b5  or      cx, ax
0x14003d8b8  mov     eax, dword ptr [rbp+arg_0]
0x14003d8bb  shr     eax, 10h
0x14003d8be  cmp     cx, ax
0x14003d8c1  jnz     short loc_14003D8FD
0x14003d8c3  mov     rbx, gs:188h
0x14003d8cc  mov     rcx, [r13+8]
0x14003d8d0  mov     edx, [r14]
0x14003d8d3  mov     rax, [rcx]
0x14003d8d6  mov     rax, [rax+60h]
0x14003d8da  call    _guard_dispatch_icall
0x14003d8df  mov     rsi, rax
0x14003d8e2  movzx   ecx, word ptr [rax+0Ch]
0x14003d8e6  test    cx, cx
0x14003d8e9  jnz     loc_14003DB3A
0x14003d8ef  mov     ecx, 1
0x14003d8f4  lock add [rax+0Ch], cx
0x14003d8f9  mov     [rax+10h], rbx
0x14003d8fd  mov     rdi, [r13+8]
0x14003d901  mov     edx, [r14]
0x14003d904  mov     rcx, rdi
0x14003d907  mov     rbx, [rdi]
0x14003d90a  mov     rax, [rbx+60h]
0x14003d90e  call    _guard_dispatch_icall
0x14003d913  mov     rdx, rax
0x14003d916  mov     rcx, rdi
0x14003d919  mov     rax, [rbx+30h]
0x14003d91d  call    _guard_dispatch_icall
0x14003d922  call    cs:__imp_KeLeaveCriticalRegion
0x14003d929  nop     dword ptr [rax+rax+00h]
0x14003d92e  xor     r14d, r14d
0x14003d931  mov     [rbp+var_40], rsi
0x14003d935  test    rsi, rsi
0x14003d938  jz      loc_14003DBEA
0x14003d93e  lea     r12d, [r14+1]
0x14003d942  cmp     [rsi+858h], r14d
0x14003d949  jnz     loc_14003DC3F
0x14003d94f  test    rsi, rsi
0x14003d952  jz      loc_14003DA3A
0x14003d958  mov     eax, [rsi+2Ch]
0x14003d95b  test    al, 2
0x14003d95d  jnz     loc_14003D9F4
0x14003d963  call    cs:__imp_PsGetCurrentProcessId
0x14003d96a  nop     dword ptr [rax+rax+00h]
0x14003d96f  mov     rdx, [rbp+var_40]
0x14003d973  mov     rbx, rax
0x14003d976  and     ebx, 0FFFFFFFCh
0x14003d979  cmp     [rdx], r14
0x14003d97c  jnz     loc_14003DA82
0x14003d982  lea     rax, [rdx+868h]
0x14003d989  xorps   xmm0, xmm0
0x14003d98c  movups  xmmword ptr [rax], xmm0
0x14003d98f  xor     ecx, ecx
0x14003d991  mov     [rax+10h], rcx
0x14003d995  mov     dword ptr [rdx+870h], 80000012h
0x14003d99f  mov     [rdx+878h], r14
0x14003d9a6  mov     eax, [rax+8]
0x14003d9a9  and     eax, 0FFFFFFFEh
0x14003d9ac  cmp     ebx, eax
0x14003d9ae  jnz     short loc_14003D9E4
0x14003d9b0  mov     rdx, [rbp+var_30]; struct Gre::Base::SESSION_GLOBALS *
0x14003d9b4  mov     rcx, [rbp+var_40]; this
0x14003d9b8  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x14003d9bd  test    rax, rax
0x14003d9c0  jz      short loc_14003D9E4
0x14003d9c2  mov     rcx, [rax+10h]; void *
0x14003d9c6  call    ?GreDecodeUserModePointer@@YAPEAXPEAX@Z; GreDecodeUserModePointer(void *)
0x14003d9cb  test    rax, rax
0x14003d9ce  jz      short loc_14003D9E4
0x14003d9d0  mov     rcx, [rbp+var_40]; this
0x14003d9d4  mov     rdx, rax; struct _DC_ATTR *
0x14003d9d7  call    ?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x14003d9dc  test    eax, eax
0x14003d9de  jz      loc_14003DC50
0x14003d9e4  mov     rax, [rbp+var_40]
0x14003d9e8  or      dword ptr [rax+2Ch], 2
0x14003d9ec  mov     rsi, [rbp+var_40]
0x14003d9f0  mov     [rbp+var_38], r12d
0x14003d9f4  mov     eax, [rsi+208h]
0x14003d9fa  mov     rdi, [rbp+arg_0]
0x14003d9fe  test    al, 4
0x14003da00  jz      loc_14003D6E5
0x14003da06  and     dword ptr [rsi+208h], 0FFFFFFFBh
0x14003da0d  mov     rdx, [rsi+3D0h]
0x14003da14  mov     eax, [rsi+208h]
0x14003da1a  mov     ecx, [rdx+154h]
0x14003da20  test    r12b, al
0x14003da23  jz      loc_14003DB4C
0x14003da29  or      ecx, 16090h
0x14003da2f  mov     [rdx+154h], ecx
0x14003da35  jmp     loc_14003D6E1
0x14003da3a  mov     ecx, 0AAh; iError
0x14003da3f  call    EngSetLastError
0x14003da44  mov     rcx, [rbp+var_40]
0x14003da48  test    rcx, rcx
0x14003da4b  jnz     loc_14003DADB
0x14003da51  mov     rax, qword ptr [rbp+var_20]
0x14003da55  lea     rcx, [rbp+var_20]
0x14003da59  cmp     [rax+8], rcx
0x14003da5d  jnz     loc_14003D68E
0x14003da63  mov     rcx, qword ptr [rbp+var_20+8]
0x14003da67  lea     rdx, [rbp+var_20]
0x14003da6b  cmp     [rcx], rdx
0x14003da6e  jnz     loc_14003D68E
0x14003da74  mov     [rcx], rax
0x14003da77  mov     [rax+8], rcx
0x14003da7b  xor     eax, eax
0x14003da7d  jmp     loc_14003D791
0x14003da82  mov     rax, [rbp+var_30]
0x14003da86  mov     rcx, [rax+8]
0x14003da8a  mov     rax, [rcx]
0x14003da8d  mov     rax, [rax+8]
0x14003da91  call    _guard_dispatch_icall
0x14003da96  jmp     loc_14003D9A6
0x14003da9b  shr     r15d, 18h
0x14003da9f  mov     bl, r12b
0x14003daa2  and     r15b, r12b
  ... truncated ...
```
