# Windows::AI::IsolationEnvironment::Internal::IsolationEnvironmentInternalStatics::QueryAppIdentityOfAgentUser(Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult * *)

- ea: `0x180012140`
- end: `0x1800124fd`
- name: `?QueryAppIdentityOfAgentUser@IsolationEnvironmentInternalStatics@Internal@IsolationEnvironment@AI@Windows@@UEAAJPEAPEAUIIsolationAppIdentityQueryResult@345@@Z`
- size: `957`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::Internal::IsolationEnvironmentInternalStatics *__hidden this, struct Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x18000a464`
- `0x18000fda0`
- `0x18000fedc`
- `0x18001045c`
- `0x1800116ac`
- `0x180011e18`
- `0x180012140`
- `0x18001355c`
- `0x180035700`
- `0x180036fb4`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800121ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012248`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800123b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800124f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800121ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012248`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800123b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800124f0`

## string_xrefs

- `0x1800121a4`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentinternalstatics.cpp`
- `0x1800122ff`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentinternalstatics.cpp`
- `0x180012436`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentinternalstatics.cpp`
- `0x18001221e`: `QueryAppIdentityOfAgentUser: caller SID %s is not a known agent user`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::AI::IsolationEnvironment::Internal::IsolationEnvironmentInternalStatics::QueryAppIdentityOfAgentUser(
        Windows::AI::IsolationEnvironment::Internal::IsolationEnvironmentInternalStatics *this,
        struct Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult **a2)
{
  int CallerUserSid; // eax
  unsigned int v4; // edi
  RTL_SRWLOCK *v5; // rcx
  __int64 v7; // rbx
  __int64 v8; // rdi
  WCHAR *v9; // r8
  RTL_SRWLOCK *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // esi
  volatile signed __int32 *v15; // rdi
  volatile signed __int32 *v16; // rdi
  RTL_SRWLOCK *v17; // rcx
  volatile signed __int32 *v18; // rdi
  int v19; // eax
  struct Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult *v20; // rax
  volatile signed __int32 *v21; // rdi
  RTL_SRWLOCK *v22; // rcx
  __int64 v23; // [rsp+20h] [rbp-29h] BYREF
  int v24; // [rsp+28h] [rbp-21h] BYREF
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-19h] BYREF
  struct Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult *v26; // [rsp+38h] [rbp-11h] BYREF
  __int64 v27; // [rsp+40h] [rbp-9h] BYREF
  volatile signed __int32 *v28; // [rsp+48h] [rbp-1h]
  __int128 v29; // [rsp+50h] [rbp+7h] BYREF
  WCHAR String2[8]; // [rsp+60h] [rbp+17h] BYREF
  __m128i si128; // [rsp+70h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  checked_srwlock::lock_shared((__int64)this, &SRWLock);
  *(_OWORD *)String2 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  String2[0] = 0;
  CallerUserSid = Windows::AI::IsolationEnvironment::Internal::IsolationEnvironmentInternalStatics::GetCallerUserSid((__int64)String2);
  v4 = CallerUserSid;
  if ( CallerUserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentinternalstatics.cpp",
      (const char *)(unsigned int)CallerUserSid,
      v23);
    std::wstring::~wstring((char **)String2);
    v5 = SRWLock;
    if ( SRWLock )
    {
      _InterlockedAdd((volatile signed __int32 *)&SRWLock[1].Ptr + 1, 0xFFFFFFFF);
      ReleaseSRWLockShared(v5);
    }
    return v4;
  }
  v29 = 0;
  v7 = AgentManager::s_agentUsersInUse;
  v8 = qword_1800B9348;
  while ( 1 )
  {
    if ( v7 == v8 )
    {
      v9 = String2;
      if ( si128.m128i_i64[1] > 7uLL )
        v9 = *(WCHAR **)String2;
      Log(3u, L"QueryAppIdentityOfAgentUser: caller SID %s is not a known agent user", v9);
      std::wstring::~wstring((char **)String2);
      v10 = SRWLock;
      if ( SRWLock )
      {
        _InterlockedAdd((volatile signed __int32 *)&SRWLock[1].Ptr + 1, 0xFFFFFFFF);
        ReleaseSRWLockShared(v10);
      }
      return 2147942405LL;
    }
    if ( AreStringsEqual((const WCHAR *)(*(_QWORD *)v7 + 80LL), String2, 1) )
      break;
    v7 += 16;
  }
  std::shared_ptr<ClientIdentity>::operator=(&v29, v7);
  v24 = 2;
  v23 = 0;
  v11 = *(_QWORD *)(v29 + 48);
  if ( v11 )
  {
    v12 = *(_QWORD *)(v11 + 120);
    if ( v12 )
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
    v27 = *(_QWORD *)(v11 + 112);
    v28 = *(volatile signed __int32 **)(v11 + 120);
    v23 = 0;
    v13 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::IsolationAppIdentity,Windows::AI::IsolationEnvironment::IIsolationAppIdentity,std::shared_ptr<AppIdentity> &>(
            &v23,
            &v27);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentinternalstatics.cpp",
        (const char *)(unsigned int)v13,
        v23);
      v15 = v28;
      if ( v28 )
      {
        if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
LABEL_24:
      v16 = (volatile signed __int32 *)*((_QWORD *)&v29 + 1);
      if ( *((_QWORD *)&v29 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
      std::wstring::~wstring((char **)String2);
      v17 = SRWLock;
      if ( SRWLock )
      {
        _InterlockedAdd((volatile signed __int32 *)&SRWLock[1].Ptr + 1, 0xFFFFFFFF);
        ReleaseSRWLockShared(v17);
      }
      return v14;
    }
    v24 = 0;
    v18 = v28;
    if ( v28 )
    {
      if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
  }
  v27 = v23;
  v26 = 0;
  v19 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::IsolationAppIdentityQueryResult,Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult,Windows::AI::IsolationEnvironment::IIsolationAppIdentity *,enum Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &>(
          &v26,
          &v27,
          &v24);
  v14 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentinternalstatics.cpp",
      (const char *)(unsigned int)v19,
      v23);
    if ( v26 )
      (*(void (__fastcall **)(struct Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult *))(*(_QWORD *)v26 + 16LL))(v26);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    goto LABEL_24;
  }
  v20 = v26;
  v26 = 0;
  *a2 = v20;
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v21 = (volatile signed __int32 *)*((_QWORD *)&v29 + 1);
  if ( *((_QWORD *)&v29 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  std::wstring::~wstring((char **)String2);
  v22 = SRWLock;
  if ( SRWLock )
  {
    _InterlockedAdd((volatile signed __int32 *)&SRWLock[1].Ptr + 1, 0xFFFFFFFF);
    ReleaseSRWLockShared(v22);
  }
  return 0;
}

```

## disassembly

```asm
0x180012140  mov     [rsp-8+arg_0], rbx
0x180012145  mov     [rsp-8+arg_10], rsi
0x18001214a  push    rbp
0x18001214b  push    rdi
0x18001214c  push    r14
0x18001214e  lea     rbp, [rsp-47h]
0x180012153  sub     rsp, 90h
0x18001215a  mov     rax, cs:__security_cookie
0x180012161  xor     rax, rsp
0x180012164  mov     [rbp+57h+var_20], rax
0x180012168  mov     r14, rdx
0x18001216b  lea     rdx, [rbp+57h+SRWLock]
0x18001216f  call    ?lock_shared@checked_srwlock@@QEAA?AV?$holder@USharedTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_shared(void)
0x180012174  xorps   xmm0, xmm0
0x180012177  movups  xmmword ptr [rbp+57h+String2], xmm0
0x18001217b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180012183  movdqu  [rbp+57h+var_30], xmm1
0x180012188  xor     eax, eax
0x18001218a  mov     [rbp+57h+String2], ax
0x18001218e  lea     rcx, [rbp+57h+String2]
0x180012192  call    ?GetCallerUserSid@IsolationEnvironmentInternalStatics@Internal@IsolationEnvironment@AI@Windows@@CAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Windows::AI::IsolationEnvironment::Internal::IsolationEnvironmentInternalStatics::GetCallerUserSid(std::wstring &)
0x180012197  mov     edi, eax
0x180012199  test    eax, eax
0x18001219b  jns     short loc_1800121D8
0x18001219d  mov     rcx, [rbp+5Fh]; this
0x1800121a1  mov     r9d, eax; char *
0x1800121a4  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800121ab  mov     edx, 35h ; '5'; void *
0x1800121b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800121b5  lea     rcx, [rbp+57h+String2]
0x1800121b9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800121be  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800121c2  test    rcx, rcx
0x1800121c5  jz      short loc_1800121D4
0x1800121c7  or      ebx, 0FFFFFFFFh
0x1800121ca  lock add [rcx+0Ch], ebx
0x1800121ce  call    cs:__imp_ReleaseSRWLockShared
0x1800121d4  mov     eax, edi
0x1800121d6  jmp     short loc_180012253
0x1800121d8  xorps   xmm0, xmm0
0x1800121db  movdqu  [rbp+57h+var_50], xmm0
0x1800121e0  mov     rbx, cs:?s_agentUsersInUse@AgentManager@@0V?$vector@V?$shared_ptr@VAgentUser@@@std@@V?$allocator@V?$shared_ptr@VAgentUser@@@std@@@2@@std@@A; std::vector<std::shared_ptr<AgentUser>> AgentManager::s_agentUsersInUse
0x1800121e7  mov     rdi, cs:qword_1800B9348
0x1800121ee  jmp     short loc_18001220B
0x1800121f0  mov     rcx, [rbx]
0x1800121f3  add     rcx, 50h ; 'P'; lpString1
0x1800121f7  mov     r8b, 1
0x1800121fa  lea     rdx, [rbp+57h+String2]; lpString2
0x1800121fe  call    ?AreStringsEqual@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z; AreStringsEqual(std::wstring const &,std::wstring const &,bool)
0x180012203  test    al, al
0x180012205  jnz     short loc_180012277
0x180012207  add     rbx, 10h
0x18001220b  cmp     rbx, rdi
0x18001220e  jnz     short loc_1800121F0
0x180012210  lea     r8, [rbp+57h+String2]
0x180012214  cmp     qword ptr [rbp+57h+var_30+8], 7
0x180012219  cmova   r8, qword ptr [rbp+57h+String2]
0x18001221e  lea     rdx, aQueryappidenti_23; "QueryAppIdentityOfAgentUser: caller SID"...
0x180012225  mov     ecx, 3; unsigned __int8
0x18001222a  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18001222f  lea     rcx, [rbp+57h+String2]
0x180012233  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012238  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001223c  test    rcx, rcx
0x18001223f  jz      short loc_18001224E
0x180012241  or      ebx, 0FFFFFFFFh
0x180012244  lock add [rcx+0Ch], ebx
0x180012248  call    cs:__imp_ReleaseSRWLockShared
0x18001224e  mov     eax, 80070005h
0x180012253  mov     rcx, [rbp+57h+var_20]
0x180012257  xor     rcx, rsp; StackCookie
0x18001225a  call    __security_check_cookie
0x18001225f  lea     r11, [rsp+0A0h+var_10]
0x180012267  mov     rbx, [r11+20h]
0x18001226b  mov     rsi, [r11+30h]
0x18001226f  mov     rsp, r11
0x180012272  pop     r14
0x180012274  pop     rdi
0x180012275  pop     rbp
0x180012276  retn
0x180012277  mov     rdx, rbx
0x18001227a  lea     rcx, [rbp+57h+var_50]
0x18001227e  call    ??4?$shared_ptr@VClientIdentity@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClientIdentity>::operator=(std::shared_ptr<ClientIdentity> const &)
0x180012283  mov     [rbp+57h+var_78], 2
0x18001228a  mov     [rbp+57h+var_80], 0
0x180012292  mov     rax, qword ptr [rbp+57h+var_50]
0x180012296  mov     rcx, [rax+30h]
0x18001229a  or      ebx, 0FFFFFFFFh
0x18001229d  test    rcx, rcx
0x1800122a0  jz      loc_180012408
0x1800122a6  mov     rax, [rcx+78h]
0x1800122aa  test    rax, rax
0x1800122ad  jz      short loc_1800122B3
0x1800122af  lock inc dword ptr [rax+8]
0x1800122b3  mov     rax, [rcx+70h]
0x1800122b7  mov     [rbp+57h+var_60], rax
0x1800122bb  mov     rax, [rcx+78h]
0x1800122bf  mov     [rbp+57h+var_58], rax
0x1800122c3  mov     rcx, [rbp+57h+var_80]
0x1800122c7  mov     [rbp+57h+var_80], 0
0x1800122cf  test    rcx, rcx
0x1800122d2  jz      short loc_1800122E1
0x1800122d4  mov     rax, [rcx]
0x1800122d7  mov     rax, [rax+10h]
0x1800122db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122e0  nop
0x1800122e1  lea     rdx, [rbp+57h+var_60]
0x1800122e5  lea     rcx, [rbp+57h+var_80]
0x1800122e9  call    ??$MakeAndInitialize@VIsolationAppIdentity@IsolationEnvironment@AI@Windows@@UIIsolationAppIdentity@234@AEAV?$shared_ptr@VAppIdentity@@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationAppIdentity@IsolationEnvironment@AI@Windows@@AEAV?$shared_ptr@VAppIdentity@@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::IsolationAppIdentity,Windows::AI::IsolationEnvironment::IIsolationAppIdentity,std::shared_ptr<AppIdentity> &>(Windows::AI::IsolationEnvironment::IIsolationAppIdentity * *,std::shared_ptr<AppIdentity> &)
0x1800122ee  mov     esi, eax
0x1800122f0  test    eax, eax
0x1800122f2  jns     loc_1800123C5
0x1800122f8  mov     rcx, [rbp+5Fh]; this
0x1800122fc  mov     r9d, eax; char *
0x1800122ff  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180012306  mov     edx, 4Dh ; 'M'; void *
0x18001230b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012310  or      ebx, 0FFFFFFFFh
0x180012313  mov     rdi, [rbp+57h+var_58]
0x180012317  test    rdi, rdi
0x18001231a  jz      short loc_180012350
0x18001231c  mov     eax, ebx
0x18001231e  lock xadd [rdi+8], eax
0x180012323  add     eax, ebx
0x180012325  jnz     short loc_180012350
0x180012327  mov     rax, [rdi]
0x18001232a  mov     rcx, rdi
0x18001232d  mov     rax, [rax]
0x180012330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012335  mov     eax, ebx
0x180012337  lock xadd [rdi+0Ch], eax
0x18001233c  add     eax, ebx
0x18001233e  jnz     short loc_180012350
0x180012340  mov     rax, [rdi]
0x180012343  mov     rcx, rdi
0x180012346  mov     rax, [rax+8]
0x18001234a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001234f  nop
0x180012350  mov     rcx, [rbp+57h+var_80]
0x180012354  test    rcx, rcx
0x180012357  jz      short loc_180012366
0x180012359  mov     rax, [rcx]
0x18001235c  mov     rax, [rax+10h]
0x180012360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012365  nop
0x180012366  mov     rdi, qword ptr [rbp+57h+var_50+8]
0x18001236a  test    rdi, rdi
0x18001236d  jz      short loc_1800123A2
0x18001236f  mov     eax, ebx
0x180012371  lock xadd [rdi+8], eax
0x180012376  add     eax, ebx
0x180012378  jnz     short loc_1800123A2
0x18001237a  mov     rax, [rdi]
0x18001237d  mov     rcx, rdi
0x180012380  mov     rax, [rax]
0x180012383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012388  mov     eax, ebx
0x18001238a  lock xadd [rdi+0Ch], eax
0x18001238f  add     eax, ebx
0x180012391  jnz     short loc_1800123A2
0x180012393  mov     rax, [rdi]
0x180012396  mov     rcx, rdi
0x180012399  mov     rax, [rax+8]
0x18001239d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123a2  lea     rcx, [rbp+57h+String2]
0x1800123a6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800123ab  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800123af  test    rcx, rcx
0x1800123b2  jz      short loc_1800123BE
0x1800123b4  lock add [rcx+0Ch], ebx
0x1800123b8  call    cs:__imp_ReleaseSRWLockShared
0x1800123be  mov     eax, esi
0x1800123c0  jmp     loc_180012253
0x1800123c5  mov     [rbp+57h+var_78], 0
0x1800123cc  mov     rdi, [rbp+57h+var_58]
0x1800123d0  test    rdi, rdi
0x1800123d3  jz      short loc_180012408
0x1800123d5  mov     eax, ebx
0x1800123d7  lock xadd [rdi+8], eax
0x1800123dc  add     eax, ebx
0x1800123de  jnz     short loc_180012408
0x1800123e0  mov     rax, [rdi]
0x1800123e3  mov     rcx, rdi
0x1800123e6  mov     rax, [rax]
0x1800123e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123ee  mov     eax, ebx
0x1800123f0  lock xadd [rdi+0Ch], eax
0x1800123f5  add     eax, ebx
0x1800123f7  jnz     short loc_180012408
0x1800123f9  mov     rax, [rdi]
0x1800123fc  mov     rcx, rdi
0x1800123ff  mov     rax, [rax+8]
0x180012403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012408  mov     rax, [rbp+57h+var_80]
0x18001240c  mov     [rbp+57h+var_60], rax
0x180012410  mov     [rbp+57h+var_68], 0
0x180012418  lea     r8, [rbp+57h+var_78]
0x18001241c  lea     rdx, [rbp+57h+var_60]
0x180012420  lea     rcx, [rbp+57h+var_68]
0x180012424  call    ??$MakeAndInitialize@VIsolationAppIdentityQueryResult@IsolationEnvironment@AI@Windows@@UIIsolationAppIdentityQueryResult@234@PEAUIIsolationAppIdentity@234@AEAW4IsolationQueryAppIdentityStatus@234@@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationAppIdentityQueryResult@IsolationEnvironment@AI@Windows@@$$QEAPEAUIIsolationAppIdentity@456@AEAW4IsolationQueryAppIdentityStatus@456@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::IsolationAppIdentityQueryResult,Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult,Windows::AI::IsolationEnvironment::IIsolationAppIdentity *,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &>(Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult * *,Windows::AI::IsolationEnvironment::IIsolationAppIdentity * &&,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &)
0x180012429  mov     esi, eax
0x18001242b  test    eax, eax
0x18001242d  jns     short loc_180012479
0x18001242f  mov     rcx, [rbp+5Fh]; this
0x180012433  mov     r9d, eax; char *
0x180012436  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18001243d  mov     edx, 56h ; 'V'; void *
0x180012442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012447  nop
0x180012448  mov     rcx, [rbp+57h+var_68]
0x18001244c  test    rcx, rcx
0x18001244f  jz      short loc_18001245E
0x180012451  mov     rax, [rcx]
0x180012454  mov     rax, [rax+10h]
0x180012458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001245d  nop
0x18001245e  mov     rcx, [rbp+57h+var_80]
0x180012462  test    rcx, rcx
0x180012465  jz      short loc_180012474
0x180012467  mov     rax, [rcx]
0x18001246a  mov     rax, [rax+10h]
0x18001246e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012473  nop
0x180012474  jmp     loc_180012366
0x180012479  mov     rax, [rbp+57h+var_68]
0x18001247d  mov     [rbp+57h+var_68], 0
0x180012485  mov     [r14], rax
0x180012488  mov     rcx, [rbp+57h+var_80]
0x18001248c  test    rcx, rcx
0x18001248f  jz      short loc_18001249E
0x180012491  mov     rax, [rcx]
0x180012494  mov     rax, [rax+10h]
0x180012498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001249d  nop
0x18001249e  mov     rdi, qword ptr [rbp+57h+var_50+8]
0x1800124a2  test    rdi, rdi
0x1800124a5  jz      short loc_1800124DA
0x1800124a7  mov     eax, ebx
0x1800124a9  lock xadd [rdi+8], eax
0x1800124ae  add     eax, ebx
0x1800124b0  jnz     short loc_1800124DA
0x1800124b2  mov     rax, [rdi]
0x1800124b5  mov     rcx, rdi
0x1800124b8  mov     rax, [rax]
0x1800124bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124c0  mov     eax, ebx
0x1800124c2  lock xadd [rdi+0Ch], eax
0x1800124c7  add     eax, ebx
0x1800124c9  jnz     short loc_1800124DA
0x1800124cb  mov     rax, [rdi]
0x1800124ce  mov     rcx, rdi
0x1800124d1  mov     rax, [rax+8]
0x1800124d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124da  lea     rcx, [rbp+57h+String2]
0x1800124de  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800124e3  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800124e7  test    rcx, rcx
0x1800124ea  jz      short loc_1800124F6
0x1800124ec  lock add [rcx+0Ch], ebx
0x1800124f0  call    cs:__imp_ReleaseSRWLockShared
0x1800124f6  xor     eax, eax
0x1800124f8  jmp     loc_180012253
```
