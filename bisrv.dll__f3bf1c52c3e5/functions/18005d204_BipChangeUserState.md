# BipChangeUserState

- ea: `0x18005d204`
- end: `0x18005d5a0`
- name: `BipChangeUserState`
- size: `924`
- prototype: `__int64 __fastcall(PSID pSid)`
- caller_count: `4`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180044908`
- `0x18004dab8`
- `0x18004e078`
- `0x18007b4b0`

## callees

- `0x180004474`
- `0x180006300`
- `0x180006dc0`
- `0x18000d7c0`
- `0x18000da50`
- `0x1800121b0`
- `0x18002a770`
- `0x18004a450`
- `0x180050d38`
- `0x180053100`
- `0x18005d204`
- `0x180076918`
- `0x18007b22c`
- `0x18007b6dc`

## import_xrefs

- `ntdll!TpSetTimer` at `0x18005d3d2`
- `ntdll!TpSetTimer` at `0x18005d4aa`
- `ntdll!TpSetTimer` at `0x18005d3d2`
- `ntdll!TpSetTimer` at `0x18005d4aa`
- `ntdll!RtlWaitOnAddress` at `0x18005d508`
- `ntdll!RtlWaitOnAddress` at `0x18005d508`
- `ntdll!RtlEqualSid` at `0x18005d2fd`
- `ntdll!RtlEqualSid` at `0x18005d2fd`

## pseudocode

```c
__int64 __fastcall BipChangeUserState(__int64 *pSid, unsigned int a2, __int64 a3)
{
  __int64 *v3; // r12
  int v4; // edi
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rbx
  int v14; // r14d
  unsigned int v15; // ebx
  void *v16; // rax
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  char v20; // r9
  int v21; // r8d
  __int64 v22; // rcx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  int v29; // [rsp+50h] [rbp-19h] BYREF
  BOOL v30; // [rsp+54h] [rbp-15h] BYREF
  int v31; // [rsp+58h] [rbp-11h] BYREF
  unsigned int v32; // [rsp+5Ch] [rbp-Dh] BYREF
  __int64 *v33; // [rsp+60h] [rbp-9h] BYREF
  __int128 v34; // [rsp+68h] [rbp-1h] BYREF
  __int64 v35; // [rsp+78h] [rbp+Fh] BYREF
  __int64 *v36; // [rsp+80h] [rbp+17h] BYREF

  v29 = 0;
  v35 = 0;
  v3 = &BipTraceLoggingNullSid;
  v4 = a3;
  v34 = 0;
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, a3) )
  {
    v31 = v8;
    v32 = a2;
    v30 = v9 != 0;
    v10 = &BipTraceLoggingNullSid;
    if ( pSid )
      v10 = pSid;
    v33 = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned __int8 *)&word_1800B3D4E,
      v8,
      v9,
      (__int64)&v32,
      (__int64 *)&v33,
      (__int64)&v31,
      (__int64)&v30);
  }
  BipAcquireGlobalLock();
  BipSyncAcquireLock((struct _BI_LOCK *)BipSessionLock);
  v11 = BipUserContextInfoFind(a2, pSid);
  v13 = v11;
  if ( !v11 )
  {
    v14 = -1;
LABEL_8:
    v15 = -1073741275;
LABEL_16:
    LOBYTE(v12) = 1;
    BipSyncReleaseLock(BipSessionLock, v12);
    BipLockWatchdogContextDisarmWatchdog(v17);
    LOBYTE(v18) = 1;
    BipSyncReleaseLock(&BipGlobalLock, v18);
    goto LABEL_54;
  }
  v14 = *(_DWORD *)(v11 + 120);
  v16 = (void *)(*(_QWORD *)(v11 + 72) + 36LL);
  if ( pSid )
  {
    if ( !v16 || !RtlEqualSid(pSid, v16) )
      goto LABEL_8;
  }
  else
  {
    pSid = (__int64 *)v16;
  }
  if ( !(unsigned __int8)BipIsValidSessionStateTransition(v13, (unsigned int)v4) )
  {
    v15 = -1073700861;
    goto LABEL_16;
  }
  if ( v4 <= 5 )
  {
    if ( v4 == 5 )
    {
      *(_DWORD *)(v13 + 120) |= 0x40000000u;
      *(_DWORD *)(v13 + 88) = 6;
      v33 = (__int64 *)(-10000LL * (unsigned int)dword_1800C3D24);
      TpSetTimer(*(_QWORD *)(v13 + 80), &v33, 0, 1000);
    }
    else if ( v4 )
    {
      switch ( v4 )
      {
        case 1:
        case 2:
          *(_DWORD *)(v13 + 120) &= ~1u;
          break;
        case 3:
          *(_DWORD *)(v13 + 120) |= 0x80000000;
          break;
        case 4:
          if ( (*(_BYTE *)(v13 + 120) & 2) != 0 )
            BipCancelQuietModeCancelBgTasksTimer((struct _BI_USERCONTEXT_INFORMATION *)v13);
          *(_DWORD *)(v13 + 120) = 0;
          break;
      }
    }
    else
    {
      *(_DWORD *)(v13 + 120) |= 1u;
    }
    goto LABEL_47;
  }
  switch ( v4 )
  {
    case 6:
      *(_DWORD *)(v13 + 120) &= ~0x40000000u;
      goto LABEL_47;
    case 7:
      if ( (*(_BYTE *)(v13 + 120) & 2) == 0 )
        BipSetQuietModeCancelBgTasksTimer((struct _BI_USERCONTEXT_INFORMATION *)v13);
      *(_DWORD *)(v13 + 120) |= 6u;
      v20 = 1;
      goto LABEL_42;
    case 8:
      if ( (*(_BYTE *)(v13 + 120) & 2) == 0 )
        BipSetQuietModeCancelBgTasksTimer((struct _BI_USERCONTEXT_INFORMATION *)v13);
      *(_DWORD *)(v13 + 120) = *(_DWORD *)(v13 + 120) & 0xFFFFFFF9 | 2;
      v20 = 0;
LABEL_42:
      v21 = 0;
LABEL_37:
      BipNotifySessionQuietModeEnterExit(*(_DWORD *)(*(_QWORD *)(v13 + 48) + 56LL), pSid, v21, v20);
      goto LABEL_47;
  }
  if ( v4 != 9 )
  {
    if ( v4 != 10 )
      goto LABEL_47;
    v20 = 1;
    v21 = 2;
    goto LABEL_37;
  }
  BipCancelQuietModeCancelBgTasksTimer((struct _BI_USERCONTEXT_INFORMATION *)v13);
  *(_DWORD *)(v13 + 120) &= ~2u;
  BipNotifySessionQuietModeEnterExit(
    *(_DWORD *)(*(_QWORD *)(v13 + 48) + 56LL),
    pSid,
    1,
    (*(_DWORD *)(v13 + 120) & 4) != 0);
  *(_DWORD *)(v13 + 120) &= ~4u;
LABEL_47:
  if ( *(_DWORD *)(v13 + 88) == v4 || v4 == 4 )
  {
    v22 = *(_QWORD *)(v13 + 80);
    *(_DWORD *)(v13 + 88) = 11;
    TpSetTimer(v22, 0, 0, 0);
  }
  LOBYTE(v12) = 1;
  BipSyncReleaseLock(BipSessionLock, v12);
  *(_QWORD *)&v34 = pSid;
  *((_QWORD *)&v34 + 1) = __PAIR64__(v14, a2);
  v35 = (unsigned int)v4;
  BipEnumeratePackagesWithCallback((void (__fastcall *)(__int64, __int64))BipChangeUserStateCallback, (__int64)&v34);
  BipLockWatchdogContextDisarmWatchdog(v23);
  LOBYTE(v24) = 1;
  BipSyncReleaseLock(&BipGlobalLock, v24);
  while ( 1 )
  {
    v29 = HIDWORD(v35);
    if ( !HIDWORD(v35) )
      break;
    RtlWaitOnAddress((char *)&v35 + 4, &v29, 4, 0);
  }
  v15 = 0;
LABEL_54:
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, v19) )
  {
    v32 = v15;
    v31 = v4;
    v30 = v14;
    if ( pSid )
      v3 = pSid;
    v36 = v3;
    LODWORD(v33) = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v25,
      (__int64)byte_1800B3DA1,
      v26,
      v27,
      (__int64)&v33,
      (__int64 *)&v36,
      (__int64)&v30,
      (__int64)&v31,
      (__int64)&v32);
  }
  return v15;
}

```

## disassembly

```asm
0x18005d204  push    rbp
0x18005d206  push    rbx
0x18005d207  push    rsi
0x18005d208  push    rdi
0x18005d209  push    r12
0x18005d20b  push    r14
0x18005d20d  push    r15
0x18005d20f  lea     rbp, [rsp-27h]
0x18005d214  sub     rsp, 90h
0x18005d21b  xor     eax, eax
0x18005d21d  mov     [rbp+57h+var_70], 0
0x18005d224  mov     [rbp+57h+var_48], rax
0x18005d228  lea     r12, BipTraceLoggingNullSid
0x18005d22f  mov     eax, cs:dword_1800C3098
0x18005d235  xorps   xmm0, xmm0
0x18005d238  mov     edi, r8d
0x18005d23b  mov     r15d, edx
0x18005d23e  mov     rsi, rcx
0x18005d241  movups  [rbp+57h+var_58], xmm0
0x18005d245  cmp     eax, 5
0x18005d248  jbe     short loc_18005D2B0
0x18005d24a  mov     edx, 2
0x18005d24f  lea     rcx, dword_1800C3098
0x18005d256  call    _tlgKeywordOn
0x18005d25b  test    al, al
0x18005d25d  jz      short loc_18005D2B0
0x18005d25f  xor     eax, eax
0x18005d261  mov     [rbp+57h+var_68], r8d
0x18005d265  test    r9, r9
0x18005d268  mov     [rbp+57h+var_64], r15d
0x18005d26c  lea     rdx, word_1800B3D4E
0x18005d273  setnz   al
0x18005d276  test    rsi, rsi
0x18005d279  mov     [rbp+57h+var_6C], eax
0x18005d27c  mov     rax, r12
0x18005d27f  cmovnz  rax, rsi
0x18005d283  mov     [rbp+57h+var_60], rax
0x18005d287  lea     rax, [rbp+57h+var_6C]
0x18005d28b  mov     [rsp+0C0h+var_88], rax
0x18005d290  lea     rax, [rbp+57h+var_68]
0x18005d294  mov     [rsp+0C0h+var_90], rax
0x18005d299  lea     rax, [rbp+57h+var_60]
0x18005d29d  mov     [rsp+0C0h+var_98], rax
0x18005d2a2  lea     rax, [rbp+57h+var_64]
0x18005d2a6  mov     [rsp+0C0h+var_A0], rax
0x18005d2ab  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSid@U_SID@@@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSid@U_SID@@@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSid<_SID> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005d2b0  call    BipAcquireGlobalLock
0x18005d2b5  mov     dl, 1
0x18005d2b7  lea     rcx, BipSessionLock; struct _BI_LOCK *
0x18005d2be  call    BipSyncAcquireLock
0x18005d2c3  mov     rdx, rsi
0x18005d2c6  mov     ecx, r15d
0x18005d2c9  call    BipUserContextInfoFind
0x18005d2ce  mov     rbx, rax
0x18005d2d1  test    rax, rax
0x18005d2d4  jnz     short loc_18005D2E1
0x18005d2d6  or      r14d, 0FFFFFFFFh
0x18005d2da  mov     ebx, 0C0000225h
0x18005d2df  jmp     short loc_18005D31F
0x18005d2e1  mov     r14d, [rax+78h]
0x18005d2e5  mov     rax, [rax+48h]
0x18005d2e9  add     rax, 24h ; '$'
0x18005d2ed  test    rsi, rsi
0x18005d2f0  jz      short loc_18005D309
0x18005d2f2  test    rax, rax
0x18005d2f5  jz      short loc_18005D2DA
0x18005d2f7  mov     rdx, rax; Sid2
0x18005d2fa  mov     rcx, rsi; Sid1
0x18005d2fd  call    cs:__imp_RtlEqualSid
0x18005d303  test    al, al
0x18005d305  jnz     short loc_18005D30C
0x18005d307  jmp     short loc_18005D2DA
0x18005d309  mov     rsi, rax
0x18005d30c  mov     edx, edi
0x18005d30e  mov     rcx, rbx
0x18005d311  call    ?BipIsValidSessionStateTransition@@YAEPEAU_BI_USERCONTEXT_INFORMATION@@W4_BI_SESSION_STATE_TRANSITION@@@Z; BipIsValidSessionStateTransition(_BI_USERCONTEXT_INFORMATION *,_BI_SESSION_STATE_TRANSITION)
0x18005d316  test    al, al
0x18005d318  jnz     short loc_18005D345
0x18005d31a  mov     ebx, 0C000A003h
0x18005d31f  mov     dl, 1
0x18005d321  lea     rcx, BipSessionLock
0x18005d328  call    BipSyncReleaseLock
0x18005d32d  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18005d332  mov     dl, 1
0x18005d334  lea     rcx, BipGlobalLock
0x18005d33b  call    BipSyncReleaseLock
0x18005d340  jmp     loc_18005D51A
0x18005d345  cmp     edi, 5
0x18005d348  jg      loc_18005D3DD
0x18005d34e  jz      short loc_18005D3A4
0x18005d350  mov     ecx, edi
0x18005d352  test    edi, edi
0x18005d354  jz      short loc_18005D39B
0x18005d356  sub     ecx, 1
0x18005d359  jz      short loc_18005D392
0x18005d35b  sub     ecx, 1
0x18005d35e  jz      short loc_18005D392
0x18005d360  sub     ecx, 1
0x18005d363  jz      short loc_18005D388
0x18005d365  cmp     ecx, 1
0x18005d368  jnz     loc_18005D48D
0x18005d36e  test    byte ptr [rbx+78h], 2
0x18005d372  jz      short loc_18005D37C
0x18005d374  mov     rcx, rbx; struct _BI_USERCONTEXT_INFORMATION *
0x18005d377  call    ?BipCancelQuietModeCancelBgTasksTimer@@YAXPEAU_BI_USERCONTEXT_INFORMATION@@@Z; BipCancelQuietModeCancelBgTasksTimer(_BI_USERCONTEXT_INFORMATION *)
0x18005d37c  mov     dword ptr [rbx+78h], 0
0x18005d383  jmp     loc_18005D48D
0x18005d388  bts     dword ptr [rbx+78h], 1Fh
0x18005d38d  jmp     loc_18005D48D
0x18005d392  and     dword ptr [rbx+78h], 0FFFFFFFEh
0x18005d396  jmp     loc_18005D48D
0x18005d39b  or      dword ptr [rbx+78h], 1
0x18005d39f  jmp     loc_18005D48D
0x18005d3a4  bts     dword ptr [rbx+78h], 1Eh
0x18005d3a9  lea     rdx, [rbp+57h+var_60]
0x18005d3ad  mov     dword ptr [rbx+58h], 6
0x18005d3b4  mov     r9d, 3E8h
0x18005d3ba  mov     eax, cs:dword_1800C3D24
0x18005d3c0  xor     r8d, r8d
0x18005d3c3  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18005d3ca  mov     [rbp+57h+var_60], rcx
0x18005d3ce  mov     rcx, [rbx+50h]
0x18005d3d2  call    cs:__imp_TpSetTimer
0x18005d3d8  jmp     loc_18005D48D
0x18005d3dd  mov     ecx, edi
0x18005d3df  sub     ecx, 6
0x18005d3e2  jz      loc_18005D488
0x18005d3e8  sub     ecx, 1
0x18005d3eb  jz      loc_18005D471
0x18005d3f1  sub     ecx, 1
0x18005d3f4  jz      short loc_18005D44F
0x18005d3f6  sub     ecx, 1
0x18005d3f9  jz      short loc_18005D41C
0x18005d3fb  cmp     ecx, 1
0x18005d3fe  jnz     loc_18005D48D
0x18005d404  mov     r9b, cl
0x18005d407  lea     r8d, [rcx+1]
0x18005d40b  mov     rcx, [rbx+30h]
0x18005d40f  mov     rdx, rsi; pSid
0x18005d412  mov     ecx, [rcx+38h]; char
0x18005d415  call    BipNotifySessionQuietModeEnterExit
0x18005d41a  jmp     short loc_18005D48D
0x18005d41c  mov     rcx, rbx; struct _BI_USERCONTEXT_INFORMATION *
0x18005d41f  call    ?BipCancelQuietModeCancelBgTasksTimer@@YAXPEAU_BI_USERCONTEXT_INFORMATION@@@Z; BipCancelQuietModeCancelBgTasksTimer(_BI_USERCONTEXT_INFORMATION *)
0x18005d424  and     dword ptr [rbx+78h], 0FFFFFFFDh
0x18005d428  mov     r8d, 1
0x18005d42e  mov     rcx, [rbx+30h]
0x18005d432  mov     rdx, rsi; pSid
0x18005d435  mov     r9d, [rbx+78h]
0x18005d439  shr     r9d, 2
0x18005d43d  and     r9b, 1
0x18005d441  mov     ecx, [rcx+38h]; char
0x18005d444  call    BipNotifySessionQuietModeEnterExit
0x18005d449  and     dword ptr [rbx+78h], 0FFFFFFFBh
0x18005d44d  jmp     short loc_18005D48D
0x18005d44f  test    byte ptr [rbx+78h], 2
0x18005d453  jnz     short loc_18005D45D
0x18005d455  mov     rcx, rbx; struct _BI_USERCONTEXT_INFORMATION *
0x18005d458  call    ?BipSetQuietModeCancelBgTasksTimer@@YAJPEAU_BI_USERCONTEXT_INFORMATION@@@Z; BipSetQuietModeCancelBgTasksTimer(_BI_USERCONTEXT_INFORMATION *)
0x18005d45d  mov     eax, [rbx+78h]
0x18005d460  and     eax, 0FFFFFFFBh
0x18005d463  or      eax, 2
0x18005d466  mov     [rbx+78h], eax
0x18005d469  xor     r9d, r9d
0x18005d46c  xor     r8d, r8d
0x18005d46f  jmp     short loc_18005D40B
0x18005d471  test    byte ptr [rbx+78h], 2
0x18005d475  jnz     short loc_18005D47F
0x18005d477  mov     rcx, rbx; struct _BI_USERCONTEXT_INFORMATION *
0x18005d47a  call    ?BipSetQuietModeCancelBgTasksTimer@@YAJPEAU_BI_USERCONTEXT_INFORMATION@@@Z; BipSetQuietModeCancelBgTasksTimer(_BI_USERCONTEXT_INFORMATION *)
0x18005d47f  or      dword ptr [rbx+78h], 6
0x18005d483  mov     r9b, 1
0x18005d486  jmp     short loc_18005D46C
0x18005d488  btr     dword ptr [rbx+78h], 1Eh
0x18005d48d  cmp     [rbx+58h], edi
0x18005d490  jz      short loc_18005D497
0x18005d492  cmp     edi, 4
0x18005d495  jnz     short loc_18005D4B0
0x18005d497  mov     rcx, [rbx+50h]
0x18005d49b  xor     r9d, r9d
0x18005d49e  xor     r8d, r8d
0x18005d4a1  mov     dword ptr [rbx+58h], 0Bh
0x18005d4a8  xor     edx, edx
0x18005d4aa  call    cs:__imp_TpSetTimer
0x18005d4b0  mov     dl, 1
0x18005d4b2  lea     rcx, BipSessionLock
0x18005d4b9  call    BipSyncReleaseLock
0x18005d4be  mov     qword ptr [rbp+57h+var_58], rsi
0x18005d4c2  lea     rdx, [rbp+57h+var_58]
0x18005d4c6  mov     dword ptr [rbp+57h+var_58+8], r15d
0x18005d4ca  lea     rcx, ?BipChangeUserStateCallback@@YAXPEAU_BI_PACKAGE@@PEAX@Z; BipChangeUserStateCallback(_BI_PACKAGE *,void *)
0x18005d4d1  mov     dword ptr [rbp+57h+var_58+0Ch], r14d
0x18005d4d5  mov     dword ptr [rbp+57h+var_48], edi
0x18005d4d8  mov     dword ptr [rbp+57h+var_48+4], 0
0x18005d4df  call    BipEnumeratePackagesWithCallback
0x18005d4e4  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18005d4e9  mov     dl, 1
0x18005d4eb  lea     rcx, BipGlobalLock
0x18005d4f2  call    BipSyncReleaseLock
0x18005d4f7  jmp     short loc_18005D50E
0x18005d4f9  xor     r9d, r9d
0x18005d4fc  lea     rdx, [rbp+57h+var_70]
0x18005d500  lea     rcx, [rbp+57h+var_48+4]
0x18005d504  lea     r8d, [r9+4]
0x18005d508  call    cs:__imp_RtlWaitOnAddress
0x18005d50e  mov     eax, dword ptr [rbp+57h+var_48+4]
0x18005d511  mov     [rbp+57h+var_70], eax
0x18005d514  test    eax, eax
0x18005d516  jnz     short loc_18005D4F9
0x18005d518  xor     ebx, ebx
0x18005d51a  mov     eax, cs:dword_1800C3098
0x18005d520  cmp     eax, 5
0x18005d523  jbe     short loc_18005D58C
0x18005d525  mov     edx, 2
0x18005d52a  lea     rcx, dword_1800C3098
0x18005d531  call    _tlgKeywordOn
0x18005d536  test    al, al
0x18005d538  jz      short loc_18005D58C
0x18005d53a  lea     rax, [rbp+57h+var_64]
0x18005d53e  mov     [rbp+57h+var_64], ebx
0x18005d541  mov     [rsp+0C0h+var_80], rax
0x18005d546  lea     rdx, byte_1800B3DA1
0x18005d54d  lea     rax, [rbp+57h+var_68]
0x18005d551  mov     [rbp+57h+var_68], edi
0x18005d554  mov     [rsp+0C0h+var_88], rax
0x18005d559  test    rsi, rsi
0x18005d55c  lea     rax, [rbp+57h+var_6C]
0x18005d560  mov     [rbp+57h+var_6C], r14d
0x18005d564  mov     [rsp+0C0h+var_90], rax
0x18005d569  cmovnz  r12, rsi
0x18005d56d  lea     rax, [rbp+57h+var_40]
0x18005d571  mov     [rbp+57h+var_40], r12
0x18005d575  mov     [rsp+0C0h+var_98], rax
0x18005d57a  lea     rax, [rbp+57h+var_60]
0x18005d57e  mov     [rsp+0C0h+var_A0], rax
0x18005d583  mov     dword ptr [rbp+57h+var_60], r15d
0x18005d587  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSid@U_SID@@@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSid@U_SID@@@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSid<_SID> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005d58c  mov     eax, ebx
0x18005d58e  add     rsp, 90h
0x18005d595  pop     r15
0x18005d597  pop     r14
0x18005d599  pop     r12
0x18005d59b  pop     rdi
0x18005d59c  pop     rsi
0x18005d59d  pop     rbx
0x18005d59e  pop     rbp
0x18005d59f  retn
```
