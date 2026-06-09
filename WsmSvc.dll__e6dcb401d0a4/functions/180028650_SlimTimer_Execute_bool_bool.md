# SlimTimer::Execute(bool,bool)

- ea: `0x180028650`
- end: `0x180028ac7`
- name: `?Execute@SlimTimer@@AEAAX_N0@Z`
- size: `1143`
- prototype: `void __fastcall(SlimTimer *__hidden this, bool, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180028070`
- `0x1800282b0`

## callees

- `0x180005d10`
- `0x180028650`
- `0x1800cc3dc`
- `0x18011a6d4`
- `0x18012cda0`
- `0x18012cdf4`
- `0x18012cf3c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288ce`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800286c0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800286c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800286fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800287f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800286fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800287f1`
- `miutils!RtlInterlockedWakeAll` at `0x180028794`
- `miutils!RtlInterlockedWakeAll` at `0x180028794`

## pseudocode

```c
void __fastcall SlimTimer::Execute(SlimTimer *this, char a2, unsigned __int8 a3)
{
  __int64 v3; // rdi
  PVOID *v6; // rax
  void *v7; // rdx
  _QWORD *v8; // rsi
  _QWORD *v9; // rdi
  void (__fastcall ***v10)(_QWORD); // rcx
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD LastError; // eax
  __int64 v15; // r8
  char v16; // [rsp+88h] [rbp+10h] BYREF

  v3 = a3;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)&WPP_64b650ca867e315a0ce984f86f0460b9_Traceguids,
      (_DWORD)this,
      (__int64)(&SlimTimer::stateStrings)[*((int *)this + 4)]);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = (void *)*((_QWORD *)this + 3);
  if ( !v7 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\timer.cpp", 140, L"140", 0x54Fu, 0);
    v7 = (void *)*((_QWORD *)this + 3);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x800) != 0 )
  {
    WPP_SF_qqs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v7,
      a3,
      (_DWORD)this,
      *((_QWORD *)this + 3),
      (__int64)(&SlimTimer::stateStrings)[*((int *)this + 4)]);
    v7 = (void *)*((_QWORD *)this + 3);
  }
  if ( !DeleteTimerQueueTimer(0, v7, (HANDLE)((v3 ^ 1) - 1)) && GetLastError() != 997 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_DL(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v15, LastError, LastError);
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\timer.cpp", 149, L"149", 0x54Fu, 0);
  }
  *((_QWORD *)this + 3) = 0;
  v8 = (_QWORD *)((char *)this + 32);
  v16 = 0;
  if ( !a2 )
  {
    if ( *((_DWORD *)this + 5) != GetCurrentThreadId() )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\timer.cpp", 177, L"177", 0x54Fu, 0);
    if ( !*v8 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\timer.cpp", 178, L"178", 0x54Fu, 0);
    goto LABEL_13;
  }
  v9 = (_QWORD *)((char *)this + 32);
  while ( 1 )
  {
    if ( *((_DWORD *)this + 5) )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\timer.cpp", 169, L"169", 0x54Fu, 0);
      v9 = (_QWORD *)((char *)this + 32);
    }
    if ( *v9 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\timer.cpp", 170, L"170", 0x54Fu, 0);
    *((_DWORD *)this + 5) = GetCurrentThreadId();
    *v9 = &v16;
LABEL_13:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_64b650ca867e315a0ce984f86f0460b9_Traceguids,
        (_DWORD)this,
        (__int64)(&SlimTimer::stateStrings)[*((int *)this + 4)]);
    v10 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = 0;
    (**v10)(v10);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_64b650ca867e315a0ce984f86f0460b9_Traceguids, this);
    if ( !a2 || v16 )
      break;
    *v8 = 0;
    *((_DWORD *)this + 5) = 0;
    while ( 1 )
    {
      v11 = *((int *)this + 4);
      if ( (_DWORD)v11 == 3 && _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 0, 3) == 3 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          v13 = 24;
LABEL_34:
          WPP_SF_q(v12[2], v13, &WPP_64b650ca867e315a0ce984f86f0460b9_Traceguids, this);
        }
        goto LABEL_21;
      }
      if ( (_DWORD)v11 == 5 && _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 2, 5) == 5 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          v13 = 25;
          goto LABEL_34;
        }
LABEL_21:
        RtlInterlockedWakeAll(0, this);
        return;
      }
      if ( (_DWORD)v11 == 6 )
        break;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        WPP_SF_qs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)&WPP_64b650ca867e315a0ce984f86f0460b9_Traceguids,
          (_DWORD)this,
          (__int64)(&SlimTimer::stateStrings)[v11]);
    }
    v9 = (_QWORD *)((char *)this + 32);
    SlimTimer::DeleteCurrentTimer(this, 1);
    *((_DWORD *)this + 4) = 3;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_64b650ca867e315a0ce984f86f0460b9_Traceguids, this);
  }
}

```

## disassembly

```asm
0x180028650  push    rbx
0x180028652  push    rbp
0x180028653  push    rsi
0x180028654  push    rdi
0x180028655  push    r12
0x180028657  push    r13
0x180028659  push    r14
0x18002865b  push    r15
0x18002865d  sub     rsp, 38h
0x180028661  movzx   edi, r8b
0x180028665  mov     bpl, dl
0x180028668  mov     rbx, rcx
0x18002866b  mov     rax, cs:WPP_GLOBAL_Control
0x180028672  lea     r15, WPP_GLOBAL_Control
0x180028679  lea     rdx, ?stateStrings@SlimTimer@@0QBQEBDB; char const * const near * const SlimTimer::stateStrings
0x180028680  mov     r12d, 1000h
0x180028686  lea     r13, WPP_64b650ca867e315a0ce984f86f0460b9_Traceguids
0x18002868d  cmp     rax, r15
0x180028690  jnz     loc_18002887F
0x180028696  mov     rdx, [rbx+18h]; Timer
0x18002869a  xor     r14d, r14d
0x18002869d  mov     esi, 54Fh
0x1800286a2  test    rdx, rdx
0x1800286a5  jz      loc_18002896E
0x1800286ab  cmp     rax, r15
0x1800286ae  jnz     loc_1800287AB
0x1800286b4  mov     r8, rdi
0x1800286b7  xor     ecx, ecx; TimerQueue
0x1800286b9  xor     r8, 1
0x1800286bd  dec     r8; CompletionEvent
0x1800286c0  call    cs:__imp_DeleteTimerQueueTimer
0x1800286c6  test    eax, eax
0x1800286c8  jz      loc_1800288BD
0x1800286ce  mov     [rbx+18h], r14
0x1800286d2  lea     rsi, [rbx+20h]
0x1800286d6  mov     [rsp+78h+arg_8], r14b
0x1800286de  test    bpl, bpl
0x1800286e1  jz      loc_1800287F1
0x1800286e7  mov     rdi, rsi
0x1800286ea  mov     eax, [rbx+14h]
0x1800286ed  test    eax, eax
0x1800286ef  jnz     loc_180028A74
0x1800286f5  cmp     [rdi], r14
0x1800286f8  jnz     loc_180028A9F
0x1800286fe  call    cs:__imp_GetCurrentThreadId
0x180028704  mov     [rbx+14h], eax
0x180028707  lea     rax, [rsp+78h+arg_8]
0x18002870f  mov     [rdi], rax
0x180028712  mov     rax, cs:WPP_GLOBAL_Control
0x180028719  lea     rdi, ?stateStrings@SlimTimer@@0QBQEBDB; char const * const near * const SlimTimer::stateStrings
0x180028720  cmp     rax, r15
0x180028723  jnz     loc_180028923
0x180028729  mov     rcx, [rbx+8]
0x18002872d  mov     [rbx+8], r14
0x180028731  mov     rax, [rcx]
0x180028734  mov     rax, [rax]
0x180028737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002873c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028743  cmp     rcx, r15
0x180028746  jnz     loc_1800289C6
0x18002874c  test    bpl, bpl
0x18002874f  jz      short loc_18002879A
0x180028751  cmp     [rsp+78h+arg_8], r14b
0x180028759  jnz     short loc_18002879A
0x18002875b  mov     [rsi], r14
0x18002875e  mov     [rbx+14h], r14d
0x180028762  movsxd  rdx, dword ptr [rbx+10h]
0x180028766  cmp     edx, 3
0x180028769  jnz     loc_180028833
0x18002876f  mov     ecx, r14d
0x180028772  mov     eax, edx
0x180028774  lock cmpxchg [rbx+10h], ecx
0x180028779  jnz     loc_180028833
0x18002877f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028786  cmp     rcx, r15
0x180028789  jnz     loc_18002895A
0x18002878f  mov     rdx, rbx
0x180028792  xor     ecx, ecx
0x180028794  call    cs:__imp_RtlInterlockedWakeAll
0x18002879a  add     rsp, 38h
0x18002879e  pop     r15
0x1800287a0  pop     r14
0x1800287a2  pop     r13
0x1800287a4  pop     r12
0x1800287a6  pop     rdi
0x1800287a7  pop     rsi
0x1800287a8  pop     rbp
0x1800287a9  pop     rbx
0x1800287aa  retn
0x1800287ab  test    dword ptr [rax+1Ch], 800h
0x1800287b2  jz      loc_1800286B4
0x1800287b8  movsxd  rax, dword ptr [rbx+10h]
0x1800287bc  lea     rcx, ?stateStrings@SlimTimer@@0QBQEBDB; char const * const near * const SlimTimer::stateStrings
0x1800287c3  mov     r9, rbx
0x1800287c6  mov     rax, [rcx+rax*8]
0x1800287ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287d1  mov     [rsp+78h+var_50], rax
0x1800287d6  mov     rax, [rbx+18h]
0x1800287da  mov     [rsp+78h+var_58], rax
0x1800287df  mov     rcx, [rcx+10h]
0x1800287e3  call    WPP_SF_qqs
0x1800287e8  mov     rdx, [rbx+18h]
0x1800287ec  jmp     loc_1800286B4
0x1800287f1  call    cs:__imp_GetCurrentThreadId
0x1800287f7  mov     ecx, [rbx+14h]
0x1800287fa  cmp     ecx, eax
0x1800287fc  jnz     loc_18002899E
0x180028802  cmp     [rsi], r14
0x180028805  jnz     loc_180028712
0x18002880b  mov     r9d, 54Fh; unsigned int
0x180028811  mov     [rsp+78h+var_58], r14; struct IRequestContext *
0x180028816  lea     r8, a178; "178"
0x18002881d  mov     edx, 0B2h; unsigned int
0x180028822  lea     rcx, aOnecoreAdminWm_66; "onecore\\admin\\wmi\\wmx\\stdlib\\timer"...
0x180028829  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002882e  jmp     loc_180028712
0x180028833  cmp     edx, 5
0x180028836  jnz     loc_1800289E9
0x18002883c  lea     ecx, [rdx-3]
0x18002883f  mov     eax, edx
0x180028841  lock cmpxchg [rbx+10h], ecx
0x180028846  jnz     loc_1800289E9
0x18002884c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028853  cmp     rcx, r15
0x180028856  jz      loc_18002878F
0x18002885c  test    [rcx+1Ch], r12d
0x180028860  jz      loc_18002878F
0x180028866  mov     edx, 19h
0x18002886b  mov     rcx, [rcx+10h]
0x18002886f  mov     r9, rbx
0x180028872  mov     r8, r13
0x180028875  call    WPP_SF_q
0x18002887a  jmp     loc_18002878F
0x18002887f  test    [rax+1Ch], r12d
0x180028883  jz      loc_180028696
0x180028889  movsxd  rax, dword ptr [rcx+10h]
0x18002888d  mov     r9, rbx
0x180028890  mov     rcx, cs:WPP_GLOBAL_Control
0x180028897  mov     r8, r13
0x18002889a  mov     rax, [rdx+rax*8]
0x18002889e  mov     edx, 15h
0x1800288a3  mov     rcx, [rcx+10h]
0x1800288a7  mov     [rsp+78h+var_58], rax
0x1800288ac  call    WPP_SF_qs
0x1800288b1  mov     rax, cs:WPP_GLOBAL_Control
0x1800288b8  jmp     loc_180028696
0x1800288bd  call    cs:__imp_GetLastError
0x1800288c3  cmp     eax, 3E5h
0x1800288c8  jz      loc_1800286CE
0x1800288ce  call    cs:__imp_GetLastError
0x1800288d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288db  cmp     rcx, r15
0x1800288de  jz      short loc_1800288FE
0x1800288e0  test    dword ptr [rcx+1Ch], 800h
0x1800288e7  jz      short loc_1800288FE
0x1800288e9  mov     rcx, [rcx+10h]
0x1800288ed  mov     edx, 14h
0x1800288f2  mov     r9d, eax
0x1800288f5  mov     dword ptr [rsp+78h+var_58], eax
0x1800288f9  call    WPP_SF_DL
0x1800288fe  mov     r9d, esi; unsigned int
0x180028901  mov     [rsp+78h+var_58], r14; struct IRequestContext *
0x180028906  lea     r8, a149; "149"
0x18002890d  mov     edx, 95h; unsigned int
0x180028912  lea     rcx, aOnecoreAdminWm_66; "onecore\\admin\\wmi\\wmx\\stdlib\\timer"...
0x180028919  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002891e  jmp     loc_1800286CE
0x180028923  test    [rax+1Ch], r12d
0x180028927  jz      loc_180028729
0x18002892d  movsxd  rax, dword ptr [rbx+10h]
0x180028931  mov     edx, 16h
0x180028936  mov     rcx, cs:WPP_GLOBAL_Control
0x18002893d  mov     r9, rbx
0x180028940  mov     r8, r13
0x180028943  mov     rax, [rdi+rax*8]
0x180028947  mov     rcx, [rcx+10h]
0x18002894b  mov     [rsp+78h+var_58], rax
0x180028950  call    WPP_SF_qs
0x180028955  jmp     loc_180028729
0x18002895a  test    [rcx+1Ch], r12d
0x18002895e  jz      loc_18002878F
0x180028964  mov     edx, 18h
0x180028969  jmp     loc_18002886B
0x18002896e  mov     r9d, esi; unsigned int
0x180028971  mov     [rsp+78h+var_58], r14; struct IRequestContext *
0x180028976  lea     r8, a140; "140"
0x18002897d  mov     edx, 8Ch; unsigned int
0x180028982  lea     rcx, aOnecoreAdminWm_66; "onecore\\admin\\wmi\\wmx\\stdlib\\timer"...
0x180028989  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002898e  mov     rdx, [rbx+18h]
0x180028992  mov     rax, cs:WPP_GLOBAL_Control
0x180028999  jmp     loc_1800286AB
0x18002899e  mov     r9d, 54Fh; unsigned int
0x1800289a4  mov     [rsp+78h+var_58], r14; struct IRequestContext *
0x1800289a9  lea     r8, a177; "177"
0x1800289b0  mov     edx, 0B1h; unsigned int
0x1800289b5  lea     rcx, aOnecoreAdminWm_66; "onecore\\admin\\wmi\\wmx\\stdlib\\timer"...
0x1800289bc  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800289c1  jmp     loc_180028802
0x1800289c6  test    [rcx+1Ch], r12d
0x1800289ca  jz      loc_18002874C
0x1800289d0  mov     rcx, [rcx+10h]
0x1800289d4  mov     edx, 17h
0x1800289d9  mov     r9, rbx
0x1800289dc  mov     r8, r13
0x1800289df  call    WPP_SF_q
0x1800289e4  jmp     loc_18002874C
0x1800289e9  cmp     edx, 6
0x1800289ec  jz      short loc_180028A2D
0x1800289ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289f5  cmp     rcx, r15
0x1800289f8  jz      loc_180028762
0x1800289fe  test    dword ptr [rcx+1Ch], 800h
0x180028a05  jz      loc_180028762
0x180028a0b  mov     rax, [rdi+rdx*8]
0x180028a0f  mov     r9, rbx
0x180028a12  mov     rcx, [rcx+10h]
0x180028a16  mov     edx, 1Bh
0x180028a1b  mov     r8, r13
0x180028a1e  mov     [rsp+78h+var_58], rax
0x180028a23  call    WPP_SF_qs
0x180028a28  jmp     loc_180028762
0x180028a2d  mov     dl, 1; bool
0x180028a2f  mov     rcx, rbx; this
0x180028a32  mov     rdi, rsi
0x180028a35  call    ?DeleteCurrentTimer@SlimTimer@@AEAAX_N@Z; SlimTimer::DeleteCurrentTimer(bool)
0x180028a3a  mov     dword ptr [rbx+10h], 3
0x180028a41  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a48  cmp     rcx, r15
0x180028a4b  jz      loc_1800286EA
0x180028a51  test    [rcx+1Ch], r12d
0x180028a55  jz      loc_1800286EA
0x180028a5b  mov     rcx, [rcx+10h]
0x180028a5f  mov     edx, 1Ah
0x180028a64  mov     r9, rbx
0x180028a67  mov     r8, r13
0x180028a6a  call    WPP_SF_q
0x180028a6f  jmp     loc_1800286EA
0x180028a74  mov     r9d, 54Fh; unsigned int
0x180028a7a  mov     [rsp+78h+var_58], r14; struct IRequestContext *
0x180028a7f  lea     r8, a169; "169"
0x180028a86  mov     edx, 0A9h; unsigned int
0x180028a8b  lea     rcx, aOnecoreAdminWm_66; "onecore\\admin\\wmi\\wmx\\stdlib\\timer"...
0x180028a92  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180028a97  mov     rdi, rsi
0x180028a9a  jmp     loc_1800286F5
0x180028a9f  mov     r9d, 54Fh; unsigned int
0x180028aa5  mov     [rsp+78h+var_58], r14; struct IRequestContext *
0x180028aaa  lea     r8, a170; "170"
0x180028ab1  mov     edx, 0AAh; unsigned int
0x180028ab6  lea     rcx, aOnecoreAdminWm_66; "onecore\\admin\\wmi\\wmx\\stdlib\\timer"...
0x180028abd  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180028ac2  jmp     loc_1800286FE
```
