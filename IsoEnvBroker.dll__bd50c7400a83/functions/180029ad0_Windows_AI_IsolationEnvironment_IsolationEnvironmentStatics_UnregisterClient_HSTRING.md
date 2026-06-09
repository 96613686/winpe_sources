# Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::UnregisterClient(HSTRING__ *)

- ea: `0x180029ad0`
- end: `0x180029dd4`
- name: `?UnregisterClient@IsolationEnvironmentStatics@IsolationEnvironment@AI@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `772`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180002520`
- `0x18000a464`
- `0x18001045c`
- `0x180011e18`
- `0x180013230`
- `0x1800134e8`
- `0x180014c04`
- `0x180029ad0`
- `0x180032e60`
- `0x180035700`
- `0x1800357a0`
- `0x180036488`
- `0x180039b3c`
- `0x18003a8f8`
- `0x18003af58`
- `0x18003b1ac`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029bc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029db4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029bc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029db4`

## string_xrefs

- `0x180029b25`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x180029b63`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x180029c1f`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::UnregisterClient(
        Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics *this,
        HSTRING a2)
{
  __int64 v3; // rcx
  int v4; // ebx
  int AppIdentity; // eax
  int v7; // esi
  volatile signed __int32 *v8; // rdi
  RTL_SRWLOCK *v9; // rcx
  __int64 v10; // rdx
  volatile signed __int32 *v11; // rdi
  __int64 String; // rax
  _QWORD *v13; // rbx
  __int64 v14; // rsi
  __int64 v15; // rdi
  __int64 v16; // r9
  volatile signed __int32 *v17; // rdi
  volatile signed __int32 *v18; // rdi
  RTL_SRWLOCK *v19; // rcx
  int v20; // [rsp+20h] [rbp-59h]
  const char *v21; // [rsp+28h] [rbp-51h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-49h] BYREF
  __int128 v23; // [rsp+38h] [rbp-41h] BYREF
  __int128 v24; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v25[8]; // [rsp+58h] [rbp-21h] BYREF
  WCHAR String2[8]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v27; // [rsp+70h] [rbp-9h]
  char *v28[4]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  Log(4u, L"IsolationEnvironment::UnregisterClient called.");
  v4 = CheckCallingProcessCohort(1, 0);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v4,
      (int)"Calling user is not in a supported cohort",
      v21);
    return (unsigned int)v4;
  }
  checked_srwlock::lock_exclusive(v3, &SRWLock);
  v23 = 0;
  AppIdentity = AppIdentity::QueryAppIdentity((__int64)&v23, 0);
  v7 = AppIdentity;
  if ( AppIdentity < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x174,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)AppIdentity,
      v20);
    v8 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
    if ( !*((_QWORD *)&v23 + 1) )
    {
LABEL_8:
      v9 = SRWLock;
      if ( SRWLock )
      {
        LODWORD(SRWLock[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v9);
      }
      return (unsigned int)v7;
    }
LABEL_5:
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
    goto LABEL_8;
  }
  v24 = 0;
  *(_OWORD *)String2 = 0;
  v27 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)String2, &word_180096C4C, 0);
  v7 = OwningUser::GetForUser((char *)String2, (__int64)&v24);
  std::wstring::~wstring((char **)String2);
  if ( v7 < 0 )
  {
    v10 = 377;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v7,
      v20);
    v11 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    if ( *((_QWORD *)&v24 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    v8 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
    if ( !*((_QWORD *)&v23 + 1) )
      goto LABEL_8;
    goto LABEL_5;
  }
  String = GetString(v28, a2);
  v13 = ClientIdentity::s_instances;
  v14 = String;
  while ( 1 )
  {
    if ( v13 == (_QWORD *)qword_1800B9370 )
    {
      v7 = ClientIdentity::ReportNotFound(&v24, &v23, v14);
      goto LABEL_27;
    }
    v15 = *v13;
    ClientIdentity::GenerateIdentityKey(String2, &v24, &v23, v14);
    LOBYTE(v15) = AreStringsEqual((const WCHAR *)(v15 + 8), String2, 1);
    std::wstring::~wstring((char **)String2);
    if ( (_BYTE)v15 )
      break;
    v13 += 2;
  }
  *(_BYTE *)(*v13 + 1LL) = 1;
  if ( *(_QWORD *)(*v13 + 56LL) == *(_QWORD *)(*v13 + 64LL) )
    std::vector<std::shared_ptr<ClientIdentity>>::erase(*v13, v25, v13, v16);
  v7 = 0;
LABEL_27:
  std::wstring::~wstring(v28);
  if ( v7 < 0 )
  {
    v10 = 383;
    goto LABEL_13;
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
  v18 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
  if ( *((_QWORD *)&v23 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v23 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  v19 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x180029ad0  push    rbp
0x180029ad2  push    rbx
0x180029ad3  push    rsi
0x180029ad4  push    rdi
0x180029ad5  lea     rbp, [rsp-3Fh]
0x180029ada  sub     rsp, 0B8h
0x180029ae1  mov     rax, cs:__security_cookie
0x180029ae8  xor     rax, rsp
0x180029aeb  mov     [rbp+57h+var_30], rax
0x180029aef  mov     rdi, rdx
0x180029af2  mov     ecx, 4; unsigned __int8
0x180029af7  lea     rdx, aIsolationenvir_12; "IsolationEnvironment::UnregisterClient "...
0x180029afe  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180029b03  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x180029b05  mov     cl, 1; bool
0x180029b07  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x180029b0c  mov     ebx, eax
0x180029b0e  test    eax, eax
0x180029b10  jns     short loc_180029B3D
0x180029b12  mov     rcx, [rbp+5Fh]; this
0x180029b16  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x180029b1d  mov     r9d, ebx; char *
0x180029b20  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180029b25  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180029b2c  mov     edx, 16Fh; void *
0x180029b31  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180029b36  mov     eax, ebx
0x180029b38  jmp     loc_180029DBC
0x180029b3d  lea     rdx, [rbp+57h+SRWLock]
0x180029b41  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x180029b46  xorps   xmm0, xmm0
0x180029b49  lea     rcx, [rbp+57h+var_98]
0x180029b4d  xor     edx, edx
0x180029b4f  movdqu  [rbp+57h+var_98], xmm0
0x180029b54  call    ?QueryAppIdentity@AppIdentity@@SAJAEAV?$shared_ptr@VAppIdentity@@@std@@PEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@@Z; AppIdentity::QueryAppIdentity(std::shared_ptr<AppIdentity> &,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *)
0x180029b59  mov     esi, eax
0x180029b5b  test    eax, eax
0x180029b5d  jns     short loc_180029BD3
0x180029b5f  mov     rcx, [rbp+5Fh]; this
0x180029b63  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180029b6a  mov     r9d, eax; char *
0x180029b6d  mov     edx, 174h; void *
0x180029b72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029b77  mov     rdi, qword ptr [rbp+57h+var_98+8]
0x180029b7b  test    rdi, rdi
0x180029b7e  jz      short loc_180029BB6
0x180029b80  or      ebx, 0FFFFFFFFh
0x180029b83  mov     eax, ebx
0x180029b85  lock xadd [rdi+8], eax
0x180029b8a  add     eax, ebx
0x180029b8c  jnz     short loc_180029BB6
0x180029b8e  mov     rax, [rdi]
0x180029b91  mov     rcx, rdi
0x180029b94  mov     rax, [rax]
0x180029b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b9c  mov     eax, ebx
0x180029b9e  lock xadd [rdi+0Ch], eax
0x180029ba3  add     eax, ebx
0x180029ba5  jnz     short loc_180029BB6
0x180029ba7  mov     rax, [rdi]
0x180029baa  mov     rcx, rdi
0x180029bad  mov     rax, [rax+8]
0x180029bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bb6  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180029bba  test    rcx, rcx
0x180029bbd  jz      short loc_180029BCC
0x180029bbf  mov     dword ptr [rcx+8], 0
0x180029bc6  call    cs:__imp_ReleaseSRWLockExclusive
0x180029bcc  mov     eax, esi
0x180029bce  jmp     loc_180029DBC
0x180029bd3  xorps   xmm0, xmm0
0x180029bd6  lea     rdx, word_180096C4C
0x180029bdd  xorps   xmm1, xmm1
0x180029be0  lea     rcx, [rbp+57h+String2]
0x180029be4  xor     r8d, r8d
0x180029be7  movdqu  [rbp+57h+var_88], xmm0
0x180029bec  movups  xmmword ptr [rbp+57h+String2], xmm0
0x180029bf0  movdqu  [rbp+57h+var_60], xmm1
0x180029bf5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180029bfa  lea     rdx, [rbp+57h+var_88]
0x180029bfe  lea     rcx, [rbp+57h+String2]
0x180029c02  call    ?GetForUser@OwningUser@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@VOwningUser@@@3@@Z; OwningUser::GetForUser(std::wstring const &,std::shared_ptr<OwningUser> &)
0x180029c07  lea     rcx, [rbp+57h+String2]
0x180029c0b  mov     esi, eax
0x180029c0d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029c12  test    esi, esi
0x180029c14  jns     short loc_180029C7F
0x180029c16  mov     edx, 179h; void *
0x180029c1b  mov     rcx, [rbp+5Fh]; this
0x180029c1f  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180029c26  mov     r9d, esi; char *
0x180029c29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029c2e  mov     rdi, qword ptr [rbp+57h+var_88+8]
0x180029c32  or      ebx, 0FFFFFFFFh
0x180029c35  test    rdi, rdi
0x180029c38  jz      short loc_180029C6D
0x180029c3a  mov     eax, ebx
0x180029c3c  lock xadd [rdi+8], eax
0x180029c41  add     eax, ebx
0x180029c43  jnz     short loc_180029C6D
0x180029c45  mov     rax, [rdi]
0x180029c48  mov     rcx, rdi
0x180029c4b  mov     rax, [rax]
0x180029c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c53  mov     eax, ebx
0x180029c55  lock xadd [rdi+0Ch], eax
0x180029c5a  add     eax, ebx
0x180029c5c  jnz     short loc_180029C6D
0x180029c5e  mov     rax, [rdi]
0x180029c61  mov     rcx, rdi
0x180029c64  mov     rax, [rax+8]
0x180029c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c6d  mov     rdi, qword ptr [rbp+57h+var_98+8]
0x180029c71  test    rdi, rdi
0x180029c74  jz      loc_180029BB6
0x180029c7a  jmp     loc_180029B83
0x180029c7f  mov     rdx, rdi
0x180029c82  lea     rcx, [rbp+57h+var_50]
0x180029c86  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x180029c8b  mov     rbx, cs:?s_instances@ClientIdentity@@0V?$vector@V?$shared_ptr@VClientIdentity@@@std@@V?$allocator@V?$shared_ptr@VClientIdentity@@@std@@@2@@std@@A; std::vector<std::shared_ptr<ClientIdentity>> ClientIdentity::s_instances
0x180029c92  mov     rsi, rax
0x180029c95  cmp     rbx, cs:qword_1800B9370
0x180029c9c  jz      short loc_180029D00
0x180029c9e  mov     rdi, [rbx]
0x180029ca1  lea     r8, [rbp+57h+var_98]
0x180029ca5  mov     r9, rsi
0x180029ca8  lea     rdx, [rbp+57h+var_88]
0x180029cac  lea     rcx, [rbp+57h+String2]
0x180029cb0  call    ?GenerateIdentityKey@ClientIdentity@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$shared_ptr@VOwningUser@@@3@AEBV?$shared_ptr@VAppIdentity@@@3@AEBV23@@Z; ClientIdentity::GenerateIdentityKey(std::shared_ptr<OwningUser> const &,std::shared_ptr<AppIdentity> const &,std::wstring const &)
0x180029cb5  lea     rcx, [rdi+8]; lpString1
0x180029cb9  mov     r8b, 1
0x180029cbc  lea     rdx, [rbp+57h+String2]; lpString2
0x180029cc0  call    ?AreStringsEqual@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z; AreStringsEqual(std::wstring const &,std::wstring const &,bool)
0x180029cc5  lea     rcx, [rbp+57h+String2]
0x180029cc9  mov     dil, al
0x180029ccc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029cd1  test    dil, dil
0x180029cd4  jnz     short loc_180029CDC
0x180029cd6  add     rbx, 10h
0x180029cda  jmp     short loc_180029C95
0x180029cdc  mov     rax, [rbx]
0x180029cdf  mov     byte ptr [rax+1], 1
0x180029ce3  mov     rcx, [rbx]
0x180029ce6  mov     rax, [rcx+40h]
0x180029cea  cmp     [rcx+38h], rax
0x180029cee  jnz     short loc_180029CFC
0x180029cf0  mov     r8, rbx
0x180029cf3  lea     rdx, [rbp+57h+var_78]
0x180029cf7  call    ?erase@?$vector@V?$shared_ptr@VClientIdentity@@@std@@V?$allocator@V?$shared_ptr@VClientIdentity@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VClientIdentity@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VClientIdentity@@@std@@@std@@@std@@@2@@Z; std::vector<std::shared_ptr<ClientIdentity>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<ClientIdentity>>>>)
0x180029cfc  xor     esi, esi
0x180029cfe  jmp     short loc_180029D12
0x180029d00  mov     r8, rsi
0x180029d03  lea     rdx, [rbp+57h+var_98]
0x180029d07  lea     rcx, [rbp+57h+var_88]
0x180029d0b  call    ?ReportNotFound@ClientIdentity@@CAJAEAV?$shared_ptr@VOwningUser@@@std@@AEBV?$shared_ptr@VAppIdentity@@@3@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; ClientIdentity::ReportNotFound(std::shared_ptr<OwningUser> &,std::shared_ptr<AppIdentity> const &,std::wstring const &)
0x180029d10  mov     esi, eax
0x180029d12  lea     rcx, [rbp+57h+var_50]
0x180029d16  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029d1b  test    esi, esi
0x180029d1d  jns     short loc_180029D29
0x180029d1f  mov     edx, 17Fh
0x180029d24  jmp     loc_180029C1B
0x180029d29  mov     rdi, qword ptr [rbp+57h+var_88+8]
0x180029d2d  or      ebx, 0FFFFFFFFh
0x180029d30  test    rdi, rdi
0x180029d33  jz      short loc_180029D68
0x180029d35  mov     eax, ebx
0x180029d37  lock xadd [rdi+8], eax
0x180029d3c  add     eax, ebx
0x180029d3e  jnz     short loc_180029D68
0x180029d40  mov     rax, [rdi]
0x180029d43  mov     rcx, rdi
0x180029d46  mov     rax, [rax]
0x180029d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d4e  mov     eax, ebx
0x180029d50  lock xadd [rdi+0Ch], eax
0x180029d55  add     eax, ebx
0x180029d57  jnz     short loc_180029D68
0x180029d59  mov     rax, [rdi]
0x180029d5c  mov     rcx, rdi
0x180029d5f  mov     rax, [rax+8]
0x180029d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d68  mov     rdi, qword ptr [rbp+57h+var_98+8]
0x180029d6c  test    rdi, rdi
0x180029d6f  jz      short loc_180029DA4
0x180029d71  mov     eax, ebx
0x180029d73  lock xadd [rdi+8], eax
0x180029d78  add     eax, ebx
0x180029d7a  jnz     short loc_180029DA4
0x180029d7c  mov     rax, [rdi]
0x180029d7f  mov     rcx, rdi
0x180029d82  mov     rax, [rax]
0x180029d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d8a  mov     eax, ebx
0x180029d8c  lock xadd [rdi+0Ch], eax
0x180029d91  add     eax, ebx
0x180029d93  jnz     short loc_180029DA4
0x180029d95  mov     rax, [rdi]
0x180029d98  mov     rcx, rdi
0x180029d9b  mov     rax, [rax+8]
0x180029d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029da4  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180029da8  test    rcx, rcx
0x180029dab  jz      short loc_180029DBA
0x180029dad  mov     dword ptr [rcx+8], 0
0x180029db4  call    cs:__imp_ReleaseSRWLockExclusive
0x180029dba  xor     eax, eax
0x180029dbc  mov     rcx, [rbp+57h+var_30]
0x180029dc0  xor     rcx, rsp; StackCookie
0x180029dc3  call    __security_check_cookie
0x180029dc8  add     rsp, 0B8h
0x180029dcf  pop     rdi
0x180029dd0  pop     rsi
0x180029dd1  pop     rbx
0x180029dd2  pop     rbp
0x180029dd3  retn
```
