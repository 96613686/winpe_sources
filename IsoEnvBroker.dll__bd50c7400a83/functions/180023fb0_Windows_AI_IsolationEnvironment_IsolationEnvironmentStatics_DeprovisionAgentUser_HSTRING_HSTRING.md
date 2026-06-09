# Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::DeprovisionAgentUser(HSTRING__ *,HSTRING__ *)

- ea: `0x180023fb0`
- end: `0x180024298`
- name: `?DeprovisionAgentUser@IsolationEnvironmentStatics@IsolationEnvironment@AI@Windows@@UEAAJPEAUHSTRING__@@0@Z`
- size: `744`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics *__hidden this, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x18000a464`
- `0x18001045c`
- `0x180011e18`
- `0x180013230`
- `0x1800134e8`
- `0x180014c04`
- `0x180023fb0`
- `0x180032e60`
- `0x1800357a0`
- `0x180037470`
- `0x18003783c`
- `0x180039b3c`
- `0x18003a79c`
- `0x18003dd8c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024243`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024243`

## string_xrefs

- `0x180024011`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x18002404f`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x1800240e1`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x180024134`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x180023fe0`: `IsolationEnvironment::DeprovisionAgentUser called.`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::DeprovisionAgentUser(
        Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics *this,
        HSTRING a2,
        HSTRING a3)
{
  __int64 v5; // rcx
  int v6; // ebx
  int AppIdentity; // eax
  int ActiveAgentUserByProvisionId; // esi
  volatile signed __int32 *v10; // rdi
  __int64 String; // rbx
  __int64 v12; // rax
  __int64 v13; // rdi
  _QWORD *v14; // rbx
  __int64 i; // r8
  volatile signed __int32 *v16; // rdi
  volatile signed __int32 *v17; // rdi
  RTL_SRWLOCK *v18; // rcx
  const char *v19; // r9
  int v20; // [rsp+20h] [rbp-49h]
  const char *v21; // [rsp+28h] [rbp-41h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-39h] BYREF
  __int128 v23; // [rsp+38h] [rbp-31h] BYREF
  __int128 v24; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v25[8]; // [rsp+58h] [rbp-11h] BYREF
  _OWORD v26[2]; // [rsp+60h] [rbp-9h] BYREF
  char *v27[4]; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  Log(4u, L"IsolationEnvironment::DeprovisionAgentUser called.");
  v6 = CheckCallingProcessCohort(1, 0);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x25E,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v6,
      (int)"Calling user is not in a supported cohort",
      v21);
    return (unsigned int)v6;
  }
  checked_srwlock::lock_exclusive(v5, &SRWLock);
  v23 = 0;
  AppIdentity = AppIdentity::QueryAppIdentity((__int64)&v23, 0);
  ActiveAgentUserByProvisionId = AppIdentity;
  if ( AppIdentity >= 0 )
  {
    v24 = 0;
    String = GetString(v27, a2);
    memset(v26, 0, sizeof(v26));
    std::wstring::_Construct<1,wchar_t const *>((char **)v26, &word_180096C4C, 0);
    ActiveAgentUserByProvisionId = ClientIdentity::Find(v26, &v23, String, &v24);
    std::wstring::~wstring((char **)v26);
    std::wstring::~wstring(v27);
    if ( ActiveAgentUserByProvisionId >= 0 )
    {
      v26[0] = 0;
      v12 = GetString(v27, a3);
      ActiveAgentUserByProvisionId = AgentManager::FindActiveAgentUserByProvisionId(v24, v12, v26);
      std::wstring::~wstring(v27);
      if ( ActiveAgentUserByProvisionId >= 0 )
      {
        v13 = *(_QWORD *)&v26[0];
        v14 = (_QWORD *)(*(_QWORD *)&v26[0] + 24LL);
        for ( i = *(_QWORD *)(*(_QWORD *)&v26[0] + 24LL); ; i += 16 )
        {
          if ( i == *(_QWORD *)(*(_QWORD *)&v26[0] + 32LL) )
          {
            ActiveAgentUserByProvisionId = -2147023728;
            goto LABEL_15;
          }
          if ( *(_DWORD *)(*(_QWORD *)i + 64LL) == *(_DWORD *)(v23 + 200) )
            break;
        }
        std::vector<std::shared_ptr<ClientConnection>>::erase(*(_QWORD *)&v26[0] + 24LL, v25);
        if ( *v14 == v14[1] )
          AgentManager::DeallocateAgentUser_DropsLock(v13, 0, 0, v19);
        ActiveAgentUserByProvisionId = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x271,
          (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
          (const char *)(unsigned int)ActiveAgentUserByProvisionId,
          v20);
      }
LABEL_15:
      v16 = (volatile signed __int32 *)*((_QWORD *)&v26[0] + 1);
      if ( *((_QWORD *)&v26[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v26[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26B,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
        (const char *)(unsigned int)ActiveAgentUserByProvisionId,
        v20);
    }
    v17 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    if ( *((_QWORD *)&v24 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    v10 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
    if ( !*((_QWORD *)&v23 + 1) )
      goto LABEL_27;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x263,
    (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
    (const char *)(unsigned int)AppIdentity,
    v20);
  v10 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
  if ( *((_QWORD *)&v23 + 1) )
  {
LABEL_24:
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
LABEL_27:
  v18 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v18);
  }
  return (unsigned int)ActiveAgentUserByProvisionId;
}

```

## disassembly

```asm
0x180023fb0  mov     [rsp-8+arg_0], rbx
0x180023fb5  mov     [rsp-8+arg_18], rsi
0x180023fba  push    rbp
0x180023fbb  push    rdi
0x180023fbc  push    r14
0x180023fbe  lea     rbp, [rsp-47h]
0x180023fc3  sub     rsp, 0B0h
0x180023fca  mov     rax, cs:__security_cookie
0x180023fd1  xor     rax, rsp
0x180023fd4  mov     [rbp+57h+var_20], rax
0x180023fd8  mov     r14, rdx
0x180023fdb  mov     ecx, 4; unsigned __int8
0x180023fe0  lea     rdx, aIsolationenvir_2; "IsolationEnvironment::DeprovisionAgentU"...
0x180023fe7  mov     rdi, r8
0x180023fea  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180023fef  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x180023ff1  mov     cl, 1; bool
0x180023ff3  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x180023ff8  mov     ebx, eax
0x180023ffa  test    eax, eax
0x180023ffc  jns     short loc_180024029
0x180023ffe  mov     rcx, [rbp+5Fh]; this
0x180024002  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x180024009  mov     r9d, ebx; char *
0x18002400c  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180024011  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180024018  mov     edx, 25Eh; void *
0x18002401d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024022  mov     eax, ebx
0x180024024  jmp     loc_18002424B
0x180024029  lea     rdx, [rbp+57h+SRWLock]
0x18002402d  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x180024032  xorps   xmm0, xmm0
0x180024035  lea     rcx, [rbp+57h+var_88]
0x180024039  xor     edx, edx
0x18002403b  movdqu  [rbp+57h+var_88], xmm0
0x180024040  call    ?QueryAppIdentity@AppIdentity@@SAJAEAV?$shared_ptr@VAppIdentity@@@std@@PEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@@Z; AppIdentity::QueryAppIdentity(std::shared_ptr<AppIdentity> &,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *)
0x180024045  mov     esi, eax
0x180024047  test    eax, eax
0x180024049  jns     short loc_180024078
0x18002404b  mov     rcx, [rbp+5Fh]; this
0x18002404f  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180024056  mov     r9d, eax; char *
0x180024059  mov     edx, 263h; void *
0x18002405e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024063  mov     rdi, qword ptr [rbp+57h+var_88+8]
0x180024067  test    rdi, rdi
0x18002406a  jz      loc_180024233
0x180024070  or      ebx, 0FFFFFFFFh
0x180024073  jmp     loc_180024200
0x180024078  xorps   xmm0, xmm0
0x18002407b  lea     rcx, [rbp+57h+var_40]
0x18002407f  mov     rdx, r14
0x180024082  movdqu  [rbp+57h+var_78], xmm0
0x180024087  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x18002408c  xorps   xmm0, xmm0
0x18002408f  lea     rdx, word_180096C4C
0x180024096  xorps   xmm1, xmm1
0x180024099  lea     rcx, [rbp+57h+var_60]
0x18002409d  xor     r8d, r8d
0x1800240a0  mov     rbx, rax
0x1800240a3  movups  [rbp+57h+var_60], xmm0
0x1800240a7  movdqu  [rbp+57h+var_50], xmm1
0x1800240ac  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800240b1  lea     r9, [rbp+57h+var_78]
0x1800240b5  mov     r8, rbx
0x1800240b8  lea     rdx, [rbp+57h+var_88]
0x1800240bc  lea     rcx, [rbp+57h+var_60]
0x1800240c0  call    ?Find@ClientIdentity@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$shared_ptr@VAppIdentity@@@3@0AEAV?$shared_ptr@VClientIdentity@@@3@@Z; ClientIdentity::Find(std::wstring const &,std::shared_ptr<AppIdentity> const &,std::wstring const &,std::shared_ptr<ClientIdentity> &)
0x1800240c5  lea     rcx, [rbp+57h+var_60]
0x1800240c9  mov     esi, eax
0x1800240cb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800240d0  lea     rcx, [rbp+57h+var_40]
0x1800240d4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800240d9  test    esi, esi
0x1800240db  jns     short loc_1800240FD
0x1800240dd  mov     rcx, [rbp+5Fh]; this
0x1800240e1  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800240e8  mov     r9d, esi; char *
0x1800240eb  mov     edx, 26Bh; void *
0x1800240f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800240f5  or      ebx, 0FFFFFFFFh
0x1800240f8  jmp     loc_1800241BB
0x1800240fd  xorps   xmm0, xmm0
0x180024100  lea     rcx, [rbp+57h+var_40]
0x180024104  mov     rdx, rdi
0x180024107  movdqu  [rbp+57h+var_60], xmm0
0x18002410c  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x180024111  mov     rcx, qword ptr [rbp+57h+var_78]
0x180024115  lea     r8, [rbp+57h+var_60]
0x180024119  mov     rdx, rax
0x18002411c  call    ?FindActiveAgentUserByProvisionId@AgentManager@@SAJPEBVClientIdentity@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@VAgentUser@@@4@@Z; AgentManager::FindActiveAgentUserByProvisionId(ClientIdentity const *,std::wstring const &,std::shared_ptr<AgentUser> &)
0x180024121  lea     rcx, [rbp+57h+var_40]
0x180024125  mov     esi, eax
0x180024127  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002412c  test    esi, esi
0x18002412e  jns     short loc_18002414A
0x180024130  mov     rcx, [rbp+5Fh]; this
0x180024134  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18002413b  mov     r9d, esi; char *
0x18002413e  mov     edx, 271h; void *
0x180024143  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024148  jmp     short loc_18002417C
0x18002414a  mov     rdi, qword ptr [rbp+57h+var_60]
0x18002414e  mov     rax, qword ptr [rbp+57h+var_88]
0x180024152  lea     rbx, [rdi+18h]
0x180024156  mov     r8, [rbx]
0x180024159  mov     eax, [rax+0C8h]
0x18002415f  jmp     short loc_180024171
0x180024161  mov     rcx, [r8]
0x180024164  cmp     [rcx+40h], eax
0x180024167  jz      loc_18002426F
0x18002416d  add     r8, 10h
0x180024171  cmp     r8, [rbx+8]
0x180024175  jnz     short loc_180024161
0x180024177  mov     esi, 80070490h
0x18002417c  mov     rdi, qword ptr [rbp+57h+var_60+8]
0x180024180  or      ebx, 0FFFFFFFFh
0x180024183  test    rdi, rdi
0x180024186  jz      short loc_1800241BB
0x180024188  mov     eax, ebx
0x18002418a  lock xadd [rdi+8], eax
0x18002418f  add     eax, ebx
0x180024191  jnz     short loc_1800241BB
0x180024193  mov     rax, [rdi]
0x180024196  mov     rcx, rdi
0x180024199  mov     rax, [rax]
0x18002419c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241a1  mov     eax, ebx
0x1800241a3  lock xadd [rdi+0Ch], eax
0x1800241a8  add     eax, ebx
0x1800241aa  jnz     short loc_1800241BB
0x1800241ac  mov     rax, [rdi]
0x1800241af  mov     rcx, rdi
0x1800241b2  mov     rax, [rax+8]
0x1800241b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241bb  mov     rdi, qword ptr [rbp+57h+var_78+8]
0x1800241bf  test    rdi, rdi
0x1800241c2  jz      short loc_1800241F7
0x1800241c4  mov     eax, ebx
0x1800241c6  lock xadd [rdi+8], eax
0x1800241cb  add     eax, ebx
0x1800241cd  jnz     short loc_1800241F7
0x1800241cf  mov     rax, [rdi]
0x1800241d2  mov     rcx, rdi
0x1800241d5  mov     rax, [rax]
0x1800241d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241dd  mov     eax, ebx
0x1800241df  lock xadd [rdi+0Ch], eax
0x1800241e4  add     eax, ebx
0x1800241e6  jnz     short loc_1800241F7
0x1800241e8  mov     rax, [rdi]
0x1800241eb  mov     rcx, rdi
0x1800241ee  mov     rax, [rax+8]
0x1800241f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241f7  mov     rdi, qword ptr [rbp+57h+var_88+8]
0x1800241fb  test    rdi, rdi
0x1800241fe  jz      short loc_180024233
0x180024200  mov     eax, ebx
0x180024202  lock xadd [rdi+8], eax
0x180024207  add     eax, ebx
0x180024209  jnz     short loc_180024233
0x18002420b  mov     rax, [rdi]
0x18002420e  mov     rcx, rdi
0x180024211  mov     rax, [rax]
0x180024214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024219  mov     eax, ebx
0x18002421b  lock xadd [rdi+0Ch], eax
0x180024220  add     eax, ebx
0x180024222  jnz     short loc_180024233
0x180024224  mov     rax, [rdi]
0x180024227  mov     rcx, rdi
0x18002422a  mov     rax, [rax+8]
0x18002422e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024233  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180024237  test    rcx, rcx
0x18002423a  jz      short loc_180024249
0x18002423c  mov     dword ptr [rcx+8], 0
0x180024243  call    cs:__imp_ReleaseSRWLockExclusive
0x180024249  mov     eax, esi
0x18002424b  mov     rcx, [rbp+57h+var_20]
0x18002424f  xor     rcx, rsp; StackCookie
0x180024252  call    __security_check_cookie
0x180024257  lea     r11, [rsp+0C0h+var_10]
0x18002425f  mov     rbx, [r11+20h]
0x180024263  mov     rsi, [r11+38h]
0x180024267  mov     rsp, r11
0x18002426a  pop     r14
0x18002426c  pop     rdi
0x18002426d  pop     rbp
0x18002426e  retn
0x18002426f  lea     rdx, [rbp+57h+var_68]
0x180024273  mov     rcx, rbx
0x180024276  call    ?erase@?$vector@V?$shared_ptr@VClientConnection@@@std@@V?$allocator@V?$shared_ptr@VClientConnection@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VClientConnection@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VClientConnection@@@std@@@std@@@std@@@2@@Z; std::vector<std::shared_ptr<ClientConnection>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<ClientConnection>>>>)
0x18002427b  mov     rax, [rbx+8]
0x18002427f  cmp     [rbx], rax
0x180024282  jnz     short loc_180024291
0x180024284  xor     r8d, r8d
0x180024287  xor     edx, edx
0x180024289  mov     rcx, rdi
0x18002428c  call    ?DeallocateAgentUser_DropsLock@AgentManager@@SAXPEAVAgentUser@@W4IsolationProvisionLostReason@IsolationEnvironment@AI@Windows@@_N@Z; AgentManager::DeallocateAgentUser_DropsLock(AgentUser *,Windows::AI::IsolationEnvironment::IsolationProvisionLostReason,bool)
0x180024291  xor     esi, esi
0x180024293  jmp     loc_18002417C
```
