# Windows::AI::IsolationEnvironment::Internal::IsolationEnvironmentInternalStatics::DestroyAgentsForApp(HSTRING__ *)

- ea: `0x180010b00`
- end: `0x180010cc9`
- name: `?DestroyAgentsForApp@IsolationEnvironmentInternalStatics@Internal@IsolationEnvironment@AI@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::Internal::IsolationEnvironmentInternalStatics *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x18000a464`
- `0x18001045c`
- `0x180010b00`
- `0x180011e18`
- `0x180013230`
- `0x1800134e8`
- `0x180032e60`
- `0x1800357a0`
- `0x180036178`
- `0x180037924`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010b69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010c09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010cac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010b69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010c09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010cac`

## string_xrefs

- `0x180010b48`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentinternalstatics.cpp`
- `0x180010b9d`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentinternalstatics.cpp`
- `0x180010c36`: `IsolationEnvironment::DestroyAgentsForApp called for user %s, app identity: %s`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::Internal::IsolationEnvironmentInternalStatics::DestroyAgentsForApp(
        Windows::AI::IsolationEnvironment::Internal::IsolationEnvironmentInternalStatics *this,
        HSTRING a2)
{
  int v3; // ebx
  RTL_SRWLOCK *v4; // rcx
  int v6; // eax
  unsigned int v7; // esi
  volatile signed __int32 *v8; // rdi
  RTL_SRWLOCK *v9; // rcx
  char **v10; // r9
  _QWORD *v11; // r8
  volatile signed __int32 *v12; // rdi
  RTL_SRWLOCK *v13; // rcx
  int v14; // [rsp+20h] [rbp-58h]
  const char *v15; // [rsp+28h] [rbp-50h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-48h] BYREF
  __int128 v17; // [rsp+38h] [rbp-40h] BYREF
  char *v18[4]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  checked_srwlock::lock_exclusive((__int64)this, &SRWLock);
  v3 = CheckCallingProcessCohort(0, 0);
  if ( v3 >= 0 )
  {
    GetString(v18, a2);
    v17 = 0;
    v6 = OwningUser::GetForCallingProcess();
    v7 = v6;
    if ( v6 >= 0 )
    {
      v10 = v18;
      if ( v18[3] > (char *)7 )
        v10 = (char **)v18[0];
      v11 = (_QWORD *)(v17 + 48);
      if ( *(_QWORD *)(v17 + 72) > 7u )
        v11 = (_QWORD *)*v11;
      Log(4u, L"IsolationEnvironment::DestroyAgentsForApp called for user %s, app identity: %s", v11, v10);
      AgentManager::RevokeAgentUsersForClientIdentity_DropsLock(&v17, v18);
      v12 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
      if ( *((_QWORD *)&v17 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      std::wstring::~wstring(v18);
      v13 = SRWLock;
      if ( SRWLock )
      {
        LODWORD(SRWLock[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v13);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentinternalstatics.cpp",
        (const char *)(unsigned int)v6,
        v14);
      v8 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
      if ( *((_QWORD *)&v17 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
          if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
        }
      }
      std::wstring::~wstring(v18);
      v9 = SRWLock;
      if ( SRWLock )
      {
        LODWORD(SRWLock[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v9);
      }
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentinternalstatics.cpp",
      (const char *)(unsigned int)v3,
      (int)"Calling user is not in a supported cohort",
      v15);
    v4 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v4);
    }
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x180010b00  push    rbp
0x180010b02  push    rbx
0x180010b03  push    rsi
0x180010b04  push    rdi
0x180010b05  mov     rbp, rsp
0x180010b08  sub     rsp, 78h
0x180010b0c  mov     rax, cs:__security_cookie
0x180010b13  xor     rax, rsp
0x180010b16  mov     [rbp+var_10], rax
0x180010b1a  mov     rdi, rdx
0x180010b1d  lea     rdx, [rbp+SRWLock]
0x180010b21  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x180010b26  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x180010b28  xor     ecx, ecx; bool
0x180010b2a  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x180010b2f  mov     ebx, eax
0x180010b31  test    eax, eax
0x180010b33  jns     short loc_180010B76
0x180010b35  mov     rcx, [rbp+20h]; this
0x180010b39  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x180010b40  mov     r9d, ebx; char *
0x180010b43  mov     qword ptr [rsp+78h+var_58], rax; int
0x180010b48  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180010b4f  mov     edx, 15h; void *
0x180010b54  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180010b59  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010b5d  test    rcx, rcx
0x180010b60  jz      short loc_180010B6F
0x180010b62  mov     dword ptr [rcx+8], 0
0x180010b69  call    cs:__imp_ReleaseSRWLockExclusive
0x180010b6f  mov     eax, ebx
0x180010b71  jmp     loc_180010CB4
0x180010b76  mov     rdx, rdi
0x180010b79  lea     rcx, [rbp+var_30]
0x180010b7d  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x180010b82  xorps   xmm0, xmm0
0x180010b85  lea     rcx, [rbp+var_40]
0x180010b89  movdqu  [rbp+var_40], xmm0
0x180010b8e  call    ?GetForCallingProcess@OwningUser@@SAJAEAV?$shared_ptr@VOwningUser@@@std@@@Z; OwningUser::GetForCallingProcess(std::shared_ptr<OwningUser> &)
0x180010b93  mov     esi, eax
0x180010b95  test    eax, eax
0x180010b97  jns     short loc_180010C16
0x180010b99  mov     rcx, [rbp+20h]; this
0x180010b9d  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180010ba4  mov     r9d, eax; char *
0x180010ba7  mov     edx, 1Ah; void *
0x180010bac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010bb1  mov     rdi, qword ptr [rbp+var_40+8]
0x180010bb5  test    rdi, rdi
0x180010bb8  jz      short loc_180010BF0
0x180010bba  or      ebx, 0FFFFFFFFh
0x180010bbd  mov     eax, ebx
0x180010bbf  lock xadd [rdi+8], eax
0x180010bc4  add     eax, ebx
0x180010bc6  jnz     short loc_180010BF0
0x180010bc8  mov     rax, [rdi]
0x180010bcb  mov     rcx, rdi
0x180010bce  mov     rax, [rax]
0x180010bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bd6  mov     eax, ebx
0x180010bd8  lock xadd [rdi+0Ch], eax
0x180010bdd  add     eax, ebx
0x180010bdf  jnz     short loc_180010BF0
0x180010be1  mov     rax, [rdi]
0x180010be4  mov     rcx, rdi
0x180010be7  mov     rax, [rax+8]
0x180010beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bf0  lea     rcx, [rbp+var_30]
0x180010bf4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010bf9  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010bfd  test    rcx, rcx
0x180010c00  jz      short loc_180010C0F
0x180010c02  mov     dword ptr [rcx+8], 0
0x180010c09  call    cs:__imp_ReleaseSRWLockExclusive
0x180010c0f  mov     eax, esi
0x180010c11  jmp     loc_180010CB4
0x180010c16  cmp     [rbp+var_18], 7
0x180010c1b  lea     r9, [rbp+var_30]
0x180010c1f  mov     r8, qword ptr [rbp+var_40]
0x180010c23  cmova   r9, [rbp+var_30]
0x180010c28  add     r8, 30h ; '0'
0x180010c2c  cmp     qword ptr [r8+18h], 7
0x180010c31  jbe     short loc_180010C36
0x180010c33  mov     r8, [r8]
0x180010c36  lea     rdx, aIsolationenvir_18; "IsolationEnvironment::DestroyAgentsForA"...
0x180010c3d  mov     ecx, 4; unsigned __int8
0x180010c42  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180010c47  lea     rdx, [rbp+var_30]
0x180010c4b  lea     rcx, [rbp+var_40]
0x180010c4f  call    ?RevokeAgentUsersForClientIdentity_DropsLock@AgentManager@@SAXAEBV?$shared_ptr@VOwningUser@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; AgentManager::RevokeAgentUsersForClientIdentity_DropsLock(std::shared_ptr<OwningUser> const &,std::wstring const &)
0x180010c54  mov     rdi, qword ptr [rbp+var_40+8]
0x180010c58  test    rdi, rdi
0x180010c5b  jz      short loc_180010C93
0x180010c5d  or      ebx, 0FFFFFFFFh
0x180010c60  mov     eax, ebx
0x180010c62  lock xadd [rdi+8], eax
0x180010c67  add     eax, ebx
0x180010c69  jnz     short loc_180010C93
0x180010c6b  mov     rax, [rdi]
0x180010c6e  mov     rcx, rdi
0x180010c71  mov     rax, [rax]
0x180010c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c79  mov     eax, ebx
0x180010c7b  lock xadd [rdi+0Ch], eax
0x180010c80  add     eax, ebx
0x180010c82  jnz     short loc_180010C93
0x180010c84  mov     rax, [rdi]
0x180010c87  mov     rcx, rdi
0x180010c8a  mov     rax, [rax+8]
0x180010c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c93  lea     rcx, [rbp+var_30]
0x180010c97  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010c9c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010ca0  test    rcx, rcx
0x180010ca3  jz      short loc_180010CB2
0x180010ca5  mov     dword ptr [rcx+8], 0
0x180010cac  call    cs:__imp_ReleaseSRWLockExclusive
0x180010cb2  xor     eax, eax
0x180010cb4  mov     rcx, [rbp+var_10]
0x180010cb8  xor     rcx, rsp; StackCookie
0x180010cbb  call    __security_check_cookie
0x180010cc0  add     rsp, 78h
0x180010cc4  pop     rdi
0x180010cc5  pop     rsi
0x180010cc6  pop     rbx
0x180010cc7  pop     rbp
0x180010cc8  retn
```
