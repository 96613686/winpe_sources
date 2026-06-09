# CHitObj::PostViperAsyncCall(void)

- ea: `0x18000a160`
- end: `0x18000a44a`
- name: `?PostViperAsyncCall@CHitObj@@QEAAJXZ`
- size: `746`
- prototype: `__int64 __fastcall(CHitObj *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18000bcb0`
- `0x18000fce0`
- `0x180031358`
- `0x180031488`

## callees

- `0x18000a160`
- `0x180012628`
- `0x18001a600`
- `0x180062868`
- `0x1800629b0`
- `0x180062b00`
- `0x180064010`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x18000a304`
- `ADVAPI32!RevertToSelf` at `0x18002738c`
- `ADVAPI32!RevertToSelf` at `0x18000a304`
- `ADVAPI32!RevertToSelf` at `0x18002738c`
- `KERNEL32!LeaveCriticalSection` at `0x18000a38c`
- `KERNEL32!LeaveCriticalSection` at `0x18000a3d3`
- `KERNEL32!LeaveCriticalSection` at `0x18000a38c`
- `KERNEL32!LeaveCriticalSection` at `0x18000a3d3`
- `KERNEL32!SetEvent` at `0x18002734e`
- `KERNEL32!SetEvent` at `0x18002734e`
- `KERNEL32!EnterCriticalSection` at `0x18000a311`
- `KERNEL32!EnterCriticalSection` at `0x18000a338`
- `KERNEL32!EnterCriticalSection` at `0x18000a311`
- `KERNEL32!EnterCriticalSection` at `0x18000a338`
- `KERNEL32!GetTickCount` at `0x18000a1bd`
- `KERNEL32!GetTickCount` at `0x18000a2c5`
- `KERNEL32!GetTickCount` at `0x180027329`
- `KERNEL32!GetTickCount` at `0x18000a1bd`
- `KERNEL32!GetTickCount` at `0x18000a2c5`
- `KERNEL32!GetTickCount` at `0x180027329`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000a442`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000a442`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000a22c`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000a22c`

## pseudocode

```c
__int64 __fastcall CHitObj::PostViperAsyncCall(CHitObj *this)
{
  CIsapiReqInfo *v2; // rsi
  int v3; // ebp
  volatile signed __int32 *v4; // rax
  volatile signed __int32 *v5; // rax
  __int64 v6; // rax
  CViperActivity *v7; // rcx
  __int64 v8; // r14
  __int64 v9; // r14
  int v10; // eax
  char *v11; // rax
  char *v12; // rbx
  _QWORD *v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  int v16; // ecx
  __int16 v17; // ax
  __int16 v18; // cx
  int v19; // edi
  CPerfData *v20; // rcx
  int v22; // eax
  __int64 v23; // rax

  v2 = 0;
  v3 = 0;
  if ( (*((_DWORD *)this + 2) & 0xF0000) == 0x10000 )
  {
    if ( (dword_18007CB28 & 1) != 0 )
      v4 = (volatile signed __int32 *)(qword_18007CB88 + 60);
    else
      v4 = (volatile signed __int32 *)&qword_18007CBD0;
    _InterlockedIncrement(v4);
    v3 = 1;
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 8);
  if ( v5 )
  {
    _InterlockedIncrement(v5);
    v2 = (CIsapiReqInfo *)*((_QWORD *)this + 8);
  }
  *((_DWORD *)this + 48) = GetTickCount();
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
    v7 = *(CViperActivity **)(v6 + 184);
  else
    v7 = 0;
  v8 = *((_QWORD *)this + 2);
  if ( v8 )
    v9 = v8 + 736;
  else
    v9 = 0;
  v10 = *((_DWORD *)this + 2) & 0xFFFFFFF;
  if ( v7 )
  {
    *((_DWORD *)this + 2) = v10 | 0x10000000;
    v22 = CViperActivity::PostAsyncRequest(v7, this);
LABEL_49:
    v19 = v22;
    goto LABEL_27;
  }
  if ( !v9 )
  {
    *((_DWORD *)this + 2) = v10 | 0x40000000;
    v22 = CViperActivity::PostGlobalAsyncRequest(this);
    goto LABEL_49;
  }
  *((_DWORD *)this + 2) = v10 | 0x20000000;
  (**(void (__fastcall ***)(__int64))v9)(v9);
  v11 = (char *)ALLOC_CACHE_HANDLER::Alloc(CViperAsyncRequest::sm_pach);
  v12 = v11;
  if ( v11 )
  {
    v13 = v11 + 16;
    v12[70] = 0;
    *((_DWORD *)v12 + 17) &= 0xF9FFFFFF;
    *(_QWORD *)v12 = &CViperAsyncRequest::`vftable'{for `IServiceCall'};
    *((_QWORD *)v12 + 1) = &CViperAsyncRequest::`vftable'{for `IAsyncErrorNotify'};
    *v13 = &CViperAsyncRequest::`vftable'{for `CDblLink'};
    v13[2] = v13;
    v13[1] = v13;
    *((_DWORD *)v12 + 10) = 1;
    *((_QWORD *)v12 + 6) = 0;
    *((_QWORD *)v12 + 7) = 0;
    *((_DWORD *)v12 + 16) = 0;
    _InterlockedIncrement(&g_nViperRequests);
    *((_QWORD *)v12 + 7) = *(_QWORD *)(v9 + 8);
    v14 = 0;
    *((_QWORD *)v12 + 6) = this;
    if ( (*((_DWORD *)this + 2) & 0xF0000) == 0x10000 )
      v14 = 0x1000000;
    *((_DWORD *)v12 + 17) &= ~0x1000000u;
    *((_DWORD *)v12 + 17) |= v14;
    *((_DWORD *)v12 + 18) = GetTickCount();
    v15 = *((_QWORD *)this + 29);
    if ( !v15 )
      v15 = *(_QWORD *)(*((_QWORD *)this + 3) + 152LL);
    v16 = *(_DWORD *)(v15 + 84);
    if ( v16 )
    {
      v17 = 2;
      if ( g_fOOP )
        v17 = 4;
      v18 = v17 * v16;
    }
    else
    {
      v18 = 6;
      if ( g_fOOP )
        v18 = 12;
    }
    *((_WORD *)v12 + 34) = v18;
    RevertToSelf();
    EnterCriticalSection(&stru_18007D2E8);
    if ( (dword_18007D2BC & 8) == 0 && (*((_DWORD *)v12 + 17) & 0x1000000) != 0 )
    {
      EnterCriticalSection(&stru_18007D2C0);
      *(_QWORD *)(*((_QWORD *)v12 + 4) + 8LL) = *((_QWORD *)v12 + 3);
      *(_QWORD *)(*((_QWORD *)v12 + 3) + 16LL) = *((_QWORD *)v12 + 4);
      *((_QWORD *)v12 + 4) = v12 + 16;
      *((_QWORD *)v12 + 3) = &g_ViperReqMgr;
      *((_QWORD *)v12 + 4) = qword_18007D2B0;
      *(_QWORD *)(qword_18007D2B0 + 8) = v12 + 16;
      ++dword_18007D2B8;
      qword_18007D2B0 = (__int64)(v12 + 16);
      LeaveCriticalSection(&stru_18007D2C0);
      if ( dword_18007D2B8 >= (unsigned int)dword_18007D32C
        || dword_18007D2B8 >= (unsigned int)dword_18007D310 && GetTickCount() / 0x3E8 > dword_18007D328 )
      {
        SetEvent(hEvent);
      }
    }
    *((_DWORD *)v12 + 17) |= 0x4000000u;
    v19 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(v9 + 8) + 32LL))(*(_QWORD *)(v9 + 8), v12);
    LeaveCriticalSection(&stru_18007D2E8);
    if ( v19 < 0
      && (unsigned int)CViperReqManager::RemoveReqObj(
                         (CViperReqManager *)&g_ViperReqMgr,
                         (struct CViperAsyncRequest *)v12,
                         0) )
    {
      v23 = *(_QWORD *)v12;
      *((_DWORD *)v12 + 17) &= ~0x4000000u;
      (*(void (__fastcall **)(char *))(v23 + 16))(v12);
    }
  }
  else
  {
    RevertToSelf();
    v19 = -2147024882;
  }
LABEL_27:
  if ( v19 >= 0 )
  {
    if ( !v2 )
      return (unsigned int)v19;
    *((_DWORD *)v2 + 306) = 3;
    goto LABEL_30;
  }
  if ( v3 )
    _InterlockedDecrement((volatile signed __int32 *)CPerfData::PDWCounter(v20, 14));
  if ( v2 )
  {
LABEL_30:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2, 0xFFFFFFFF) == 1 )
    {
      CIsapiReqInfo::~CIsapiReqInfo(v2);
      if ( CIsapiReqInfo::sm_pach )
        ALLOC_CACHE_HANDLER::Free(CIsapiReqInfo::sm_pach, v2);
    }
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18000a160  push    rbp
0x18000a162  push    rsi
0x18000a163  push    rdi
0x18000a164  sub     rsp, 30h
0x18000a168  mov     eax, [rcx+8]
0x18000a16b  mov     rdi, rcx
0x18000a16e  mov     [rsp+48h+var_20], r14
0x18000a173  and     eax, 0F0000h
0x18000a178  mov     [rsp+48h+var_28], r15
0x18000a17d  xor     r15d, r15d
0x18000a180  mov     esi, r15d
0x18000a183  mov     ebp, r15d
0x18000a186  cmp     eax, 10000h
0x18000a18b  jnz     short loc_18000A1AD
0x18000a18d  test    byte ptr cs:dword_18007CB28, 1
0x18000a194  jz      loc_1800272D0
0x18000a19a  mov     rax, cs:qword_18007CB88
0x18000a1a1  add     rax, 3Ch ; '<'
0x18000a1a5  lock inc dword ptr [rax]
0x18000a1a8  mov     ebp, 1
0x18000a1ad  mov     rax, [rcx+40h]
0x18000a1b1  test    rax, rax
0x18000a1b4  jz      short loc_18000A1BD
0x18000a1b6  lock inc dword ptr [rax]
0x18000a1b9  mov     rsi, [rcx+40h]
0x18000a1bd  call    cs:__imp_GetTickCount
0x18000a1c3  mov     [rdi+0C0h], eax
0x18000a1c9  mov     rax, [rdi+18h]
0x18000a1cd  test    rax, rax
0x18000a1d0  jz      loc_1800272DC
0x18000a1d6  mov     rcx, [rax+0B8h]; this
0x18000a1dd  mov     r14, [rdi+10h]
0x18000a1e1  test    r14, r14
0x18000a1e4  jz      loc_1800272E4
0x18000a1ea  add     r14, 2E0h
0x18000a1f1  mov     eax, [rdi+8]
0x18000a1f4  and     eax, 0FFFFFFFh
0x18000a1f9  test    rcx, rcx
0x18000a1fc  jnz     loc_1800272EC
0x18000a202  test    r14, r14
0x18000a205  jz      loc_18002739C
0x18000a20b  bts     eax, 1Dh
0x18000a20f  mov     [rsp+48h+arg_8], rbx
0x18000a214  mov     [rdi+8], eax
0x18000a217  mov     rcx, r14
0x18000a21a  mov     rax, [r14]
0x18000a21d  mov     rax, [rax]
0x18000a220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a225  mov     rcx, cs:?sm_pach@CViperAsyncRequest@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CViperAsyncRequest::sm_pach
0x18000a22c  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000a232  mov     rbx, rax
0x18000a235  test    rax, rax
0x18000a238  jz      loc_18002738C
0x18000a23e  add     rax, 10h
0x18000a242  mov     [rbx+46h], r15b
0x18000a246  and     dword ptr [rbx+44h], 0F9FFFFFFh
0x18000a24d  lea     rcx, ??_7CViperAsyncRequest@@6BIServiceCall@@@; const CViperAsyncRequest::`vftable'{for `IServiceCall'}
0x18000a254  mov     [rbx], rcx
0x18000a257  lea     rcx, ??_7CViperAsyncRequest@@6BIAsyncErrorNotify@@@; const CViperAsyncRequest::`vftable'{for `IAsyncErrorNotify'}
0x18000a25e  mov     [rbx+8], rcx
0x18000a262  lea     rcx, ??_7CViperAsyncRequest@@6BCDblLink@@@; const CViperAsyncRequest::`vftable'{for `CDblLink'}
0x18000a269  mov     [rax], rcx
0x18000a26c  mov     [rsp+48h+arg_10], r12
0x18000a271  mov     [rax+10h], rax
0x18000a275  mov     [rax+8], rax
0x18000a279  mov     dword ptr [rbx+28h], 1
0x18000a280  mov     [rbx+30h], r15
0x18000a284  mov     [rbx+38h], r15
0x18000a288  mov     [rbx+40h], r15d
0x18000a28c  lock inc cs:?g_nViperRequests@@3JC; long volatile g_nViperRequests
0x18000a293  mov     rax, [r14+8]
0x18000a297  mov     r12d, 1000000h
0x18000a29d  mov     [rbx+38h], rax
0x18000a2a1  mov     eax, r15d
0x18000a2a4  mov     [rbx+30h], rdi
0x18000a2a8  mov     ecx, [rdi+8]
0x18000a2ab  and     ecx, 0F0000h
0x18000a2b1  cmp     ecx, 10000h
0x18000a2b7  cmovz   eax, r12d
0x18000a2bb  and     dword ptr [rbx+44h], 0FEFFFFFFh
0x18000a2c2  or      [rbx+44h], eax
0x18000a2c5  call    cs:__imp_GetTickCount
0x18000a2cb  mov     [rbx+48h], eax
0x18000a2ce  mov     rcx, [rdi+0E8h]
0x18000a2d5  test    rcx, rcx
0x18000a2d8  jz      loc_180027300
0x18000a2de  mov     ecx, [rcx+54h]
0x18000a2e1  test    ecx, ecx
0x18000a2e3  jz      loc_180027310
0x18000a2e9  cmp     cs:?g_fOOP@@3HA, r15d; int g_fOOP
0x18000a2f0  mov     edx, 4
0x18000a2f5  mov     eax, 2
0x18000a2fa  cmovnz  eax, edx
0x18000a2fd  imul    ecx, eax
0x18000a300  mov     [rbx+44h], cx
0x18000a304  call    cs:__imp_RevertToSelf
0x18000a30a  lea     rcx, stru_18007D2E8; lpCriticalSection
0x18000a311  call    cs:__imp_EnterCriticalSection
0x18000a317  test    byte ptr cs:dword_18007D2BC, 8
0x18000a31e  lea     r15, ?g_ViperReqMgr@@3VCViperReqManager@@A; CViperReqManager g_ViperReqMgr
0x18000a325  jnz     loc_18000A3B0
0x18000a32b  test    [rbx+44h], r12d
0x18000a32f  jz      short loc_18000A3B0
0x18000a331  lea     rcx, stru_18007D2C0; lpCriticalSection
0x18000a338  call    cs:__imp_EnterCriticalSection
0x18000a33e  mov     rdx, [rbx+20h]
0x18000a342  lea     r8, [rbx+10h]
0x18000a346  mov     rax, [r8+8]
0x18000a34a  lea     rcx, stru_18007D2C0; lpCriticalSection
0x18000a351  mov     [rdx+8], rax
0x18000a355  mov     rax, [r8+10h]
0x18000a359  mov     rdx, [r8+8]
0x18000a35d  mov     [rdx+10h], rax
0x18000a361  mov     [r8+10h], r8
0x18000a365  mov     [r8+8], r15
0x18000a369  mov     rax, cs:qword_18007D2B0
0x18000a370  mov     [r8+10h], rax
0x18000a374  mov     rax, cs:qword_18007D2B0
0x18000a37b  mov     [rax+8], r8
0x18000a37f  inc     cs:dword_18007D2B8
0x18000a385  mov     cs:qword_18007D2B0, r8
0x18000a38c  call    cs:__imp_LeaveCriticalSection
0x18000a392  mov     eax, cs:dword_18007D2B8
0x18000a398  cmp     eax, cs:dword_18007D32C
0x18000a39e  jnb     loc_180027347
0x18000a3a4  cmp     eax, cs:dword_18007D310
0x18000a3aa  jnb     loc_180027329
0x18000a3b0  or      dword ptr [rbx+44h], 4000000h
0x18000a3b7  mov     rdx, rbx
0x18000a3ba  mov     rcx, [r14+8]
0x18000a3be  mov     rax, [rcx]
0x18000a3c1  mov     rax, [rax+20h]
0x18000a3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3ca  lea     rcx, stru_18007D2E8; lpCriticalSection
0x18000a3d1  mov     edi, eax
0x18000a3d3  call    cs:__imp_LeaveCriticalSection
0x18000a3d9  mov     r12, [rsp+48h+arg_10]
0x18000a3de  test    edi, edi
0x18000a3e0  js      loc_18002735A
0x18000a3e6  mov     rbx, [rsp+48h+arg_8]
0x18000a3eb  mov     r15, [rsp+48h+var_28]
0x18000a3f0  mov     r14, [rsp+48h+var_20]
0x18000a3f5  test    edi, edi
0x18000a3f7  js      loc_1800273B2
0x18000a3fd  test    rsi, rsi
0x18000a400  jz      short loc_18000A41A
0x18000a402  mov     dword ptr [rsi+4C8h], 3
0x18000a40c  mov     eax, 0FFFFFFFFh
0x18000a411  lock xadd [rsi], eax
0x18000a415  cmp     eax, 1
0x18000a418  jz      short loc_18000A42B
0x18000a41a  mov     eax, edi
0x18000a41c  add     rsp, 30h
0x18000a420  pop     rdi
0x18000a421  pop     rsi
0x18000a422  pop     rbp
0x18000a423  retn
0x18000a424  test    rsi, rsi
0x18000a427  jnz     short loc_18000A40C
0x18000a429  jmp     short loc_18000A41A
0x18000a42b  mov     rcx, rsi; this
0x18000a42e  call    ??1CIsapiReqInfo@@QEAA@XZ; CIsapiReqInfo::~CIsapiReqInfo(void)
0x18000a433  mov     rcx, cs:?sm_pach@CIsapiReqInfo@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CIsapiReqInfo::sm_pach
0x18000a43a  test    rcx, rcx
0x18000a43d  jz      short loc_18000A41A
0x18000a43f  mov     rdx, rsi
0x18000a442  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000a448  jmp     short loc_18000A41A
0x1800272d0  lea     rax, qword_18007CBD0
0x1800272d7  jmp     loc_18000A1A5
0x1800272dc  mov     rcx, r15
0x1800272df  jmp     loc_18000A1DD
0x1800272e4  mov     r14, r15
0x1800272e7  jmp     loc_18000A1F1
0x1800272ec  bts     eax, 1Ch
0x1800272f0  mov     rdx, rdi; struct CHitObj *
0x1800272f3  mov     [rdi+8], eax
0x1800272f6  call    ?PostAsyncRequest@CViperActivity@@QEAAJPEAVCHitObj@@@Z; CViperActivity::PostAsyncRequest(CHitObj *)
0x1800272fb  jmp     loc_1800273AB
0x180027300  mov     rax, [rdi+18h]
0x180027304  mov     rcx, [rax+98h]
0x18002730b  jmp     loc_18000A2DE
0x180027310  cmp     cs:?g_fOOP@@3HA, r15d; int g_fOOP
0x180027317  mov     ecx, 6
0x18002731c  mov     eax, 0Ch
0x180027321  cmovnz  ecx, eax
0x180027324  jmp     loc_18000A300
0x180027329  call    cs:__imp_GetTickCount
0x18002732f  mov     ecx, eax
0x180027331  mov     eax, 10624DD3h
0x180027336  mul     ecx
0x180027338  shr     edx, 6
0x18002733b  cmp     edx, cs:dword_18007D328
0x180027341  jbe     loc_18000A3B0
0x180027347  mov     rcx, cs:hEvent; hEvent
0x18002734e  call    cs:__imp_SetEvent
0x180027354  nop
0x180027355  jmp     loc_18000A3B0
0x18002735a  xor     r8d, r8d; int
0x18002735d  mov     rdx, rbx; struct CViperAsyncRequest *
0x180027360  mov     rcx, r15; this
0x180027363  call    ?RemoveReqObj@CViperReqManager@@QEAAHPEAVCViperAsyncRequest@@H@Z; CViperReqManager::RemoveReqObj(CViperAsyncRequest *,int)
0x180027368  test    eax, eax
0x18002736a  jz      loc_18000A3E6
0x180027370  mov     rax, [rbx]
0x180027373  mov     rcx, rbx
0x180027376  and     dword ptr [rbx+44h], 0FBFFFFFFh
0x18002737d  mov     rax, [rax+10h]
0x180027381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027386  nop
0x180027387  jmp     loc_18000A3E6
0x18002738c  call    cs:__imp_RevertToSelf
0x180027392  mov     edi, 8007000Eh
0x180027397  jmp     loc_18000A3E6
0x18002739c  bts     eax, 1Eh
0x1800273a0  mov     rcx, rdi; struct CHitObj *
0x1800273a3  mov     [rdi+8], eax
0x1800273a6  call    ?PostGlobalAsyncRequest@CViperActivity@@SAJPEAVCHitObj@@@Z; CViperActivity::PostGlobalAsyncRequest(CHitObj *)
0x1800273ab  mov     edi, eax
0x1800273ad  jmp     loc_18000A3EB
0x1800273b2  test    ebp, ebp
0x1800273b4  jz      loc_18000A424
0x1800273ba  mov     edx, 0Eh; int
0x1800273bf  call    ?PDWCounter@CPerfData@@QEAAPEAKH@Z; CPerfData::PDWCounter(int)
0x1800273c4  lock dec dword ptr [rax]
0x1800273c7  jmp     loc_18000A424
```
