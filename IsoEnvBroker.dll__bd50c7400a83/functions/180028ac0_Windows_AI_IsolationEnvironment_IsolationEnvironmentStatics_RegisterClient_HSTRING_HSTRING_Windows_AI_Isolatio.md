# Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::RegisterClient(HSTRING__ *,HSTRING__ *,Windows::AI::IsolationEnvironment::IsolationEnviromentRegistrationStatus *)

- ea: `0x180028ac0`
- end: `0x180028dce`
- name: `?RegisterClient@IsolationEnvironmentStatics@IsolationEnvironment@AI@Windows@@UEAAJPEAUHSTRING__@@0PEAW4IsolationEnviromentRegistrationStatus@234@@Z`
- size: `782`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics *this, HSTRING, HSTRING, enum Windows::AI::IsolationEnvironment::IsolationEnviromentRegistrationStatus *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002520`
- `0x18000a464`
- `0x18001045c`
- `0x180011e18`
- `0x180013230`
- `0x1800134e8`
- `0x180014c04`
- `0x180028ac0`
- `0x180032e60`
- `0x1800357a0`
- `0x180036488`
- `0x180039b3c`
- `0x18003abe4`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028b1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028b1e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028b2c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028b64`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028b2c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028b64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028c96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028d85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028c96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028d85`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180028b06`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180028b06`

## string_xrefs

- `0x180028b90`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x180028c38`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x180028aff`: `wtsapi32.dll`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::RegisterClient(
        Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics *this,
        HSTRING a2,
        HSTRING a3,
        enum Windows::AI::IsolationEnvironment::IsolationEnviromentRegistrationStatus *a4)
{
  HMODULE LibraryW; // rax
  HMODULE v8; // rbx
  FARPROC ProcAddress; // rax
  int v11; // edi
  int v12; // ebx
  __int64 v13; // rcx
  volatile signed __int32 *v14; // rdi
  int v15; // esi
  __int64 v16; // rdx
  volatile signed __int32 *v17; // rdi
  RTL_SRWLOCK *v18; // rcx
  volatile signed __int32 *v19; // rdi
  const WCHAR *String; // rbx
  int v21; // eax
  int v22; // ecx
  volatile signed __int32 *v23; // rdi
  RTL_SRWLOCK *v24; // rcx
  int lpString2; // [rsp+20h] [rbp-59h]
  const char *v26; // [rsp+28h] [rbp-51h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-49h] BYREF
  int v28[4]; // [rsp+38h] [rbp-41h] BYREF
  int v29[4]; // [rsp+48h] [rbp-31h] BYREF
  _OWORD v30[2]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v31[32]; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  Log(4u, L"IsolationEnvironment::RegisterClient called.");
  LibraryW = LoadLibraryW(L"wtsapi32.dll");
  v8 = LibraryW;
  if ( !LibraryW )
    return 2147549183LL;
  ProcAddress = GetProcAddress(LibraryW, "WTSEnableChildSessions");
  if ( !ProcAddress )
  {
    FreeLibrary(v8);
    return 2147549183LL;
  }
  v11 = ((__int64 (__fastcall *)(__int64))ProcAddress)(1);
  FreeLibrary(v8);
  if ( !v11 )
    return 2147549183LL;
  v12 = CheckCallingProcessCohort(1, 0);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v12,
      (int)"Calling user is not in a supported cohort",
      v26);
    return (unsigned int)v12;
  }
  *(_OWORD *)v28 = 0;
  if ( (int)AppIdentity::QueryAppIdentity(v28, 0) < 0 )
  {
    v14 = *(volatile signed __int32 **)&v28[2];
    *(_DWORD *)a4 = 3;
    if ( !v14 )
      return 0;
LABEL_33:
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
    return 0;
  }
  checked_srwlock::lock_exclusive(v13, &SRWLock);
  *(_DWORD *)a4 = 0;
  *(_OWORD *)v29 = 0;
  memset(v30, 0, sizeof(v30));
  std::wstring::_Construct<1,wchar_t const *>(v30, &word_180096C4C);
  v15 = OwningUser::GetForUser((char *)v30);
  std::wstring::~wstring(v30);
  if ( v15 >= 0 )
  {
    String = (const WCHAR *)GetString(v31, a3);
    v21 = GetString(v30, a2);
    v15 = ClientIdentity::RegisterClient(v22, (int)v28, (int)v29, v21, String, (__int64)a4);
    std::wstring::~wstring(v30);
    std::wstring::~wstring(v31);
    if ( v15 >= 0 )
    {
      v23 = *(volatile signed __int32 **)&v29[2];
      if ( *(_QWORD *)&v29[2] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v29[2] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
          if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        }
      }
      v24 = SRWLock;
      if ( SRWLock )
      {
        LODWORD(SRWLock[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v24);
      }
      v14 = *(volatile signed __int32 **)&v28[2];
      if ( !*(_QWORD *)&v28[2] )
        return 0;
      goto LABEL_33;
    }
    v16 = 338;
  }
  else
  {
    v16 = 330;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
    (const char *)(unsigned int)v15,
    lpString2);
  v17 = *(volatile signed __int32 **)&v29[2];
  if ( *(_QWORD *)&v29[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v29[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  v18 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v18);
  }
  v19 = *(volatile signed __int32 **)&v28[2];
  if ( *(_QWORD *)&v28[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v28[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180028ac0  push    rbp
0x180028ac2  push    rbx
0x180028ac3  push    rsi
0x180028ac4  push    rdi
0x180028ac5  push    r12
0x180028ac7  push    r14
0x180028ac9  push    r15
0x180028acb  lea     rbp, [rsp-27h]
0x180028ad0  sub     rsp, 0A0h
0x180028ad7  mov     rax, cs:__security_cookie
0x180028ade  xor     rax, rsp
0x180028ae1  mov     [rbp+57h+var_38], rax
0x180028ae5  mov     r15, rdx
0x180028ae8  mov     ecx, 4; unsigned __int8
0x180028aed  lea     rdx, aIsolationenvir_16; "IsolationEnvironment::RegisterClient ca"...
0x180028af4  mov     r14, r9
0x180028af7  mov     r12, r8
0x180028afa  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180028aff  lea     rcx, LibFileName; "wtsapi32.dll"
0x180028b06  call    cs:__imp_LoadLibraryW
0x180028b0c  mov     rbx, rax
0x180028b0f  test    rax, rax
0x180028b12  jz      short loc_180028B32
0x180028b14  lea     rdx, aWtsenablechild; "WTSEnableChildSessions"
0x180028b1b  mov     rcx, rax; hModule
0x180028b1e  call    cs:__imp_GetProcAddress
0x180028b24  test    rax, rax
0x180028b27  jnz     short loc_180028B55
0x180028b29  mov     rcx, rbx; hLibModule
0x180028b2c  call    cs:__imp_FreeLibrary
0x180028b32  mov     eax, 8000FFFFh
0x180028b37  mov     rcx, [rbp+57h+var_38]
0x180028b3b  xor     rcx, rsp; StackCookie
0x180028b3e  call    __security_check_cookie
0x180028b43  add     rsp, 0A0h
0x180028b4a  pop     r15
0x180028b4c  pop     r14
0x180028b4e  pop     r12
0x180028b50  pop     rdi
0x180028b51  pop     rsi
0x180028b52  pop     rbx
0x180028b53  pop     rbp
0x180028b54  retn
0x180028b55  mov     ecx, 1
0x180028b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b5f  mov     rcx, rbx; hLibModule
0x180028b62  mov     edi, eax
0x180028b64  call    cs:__imp_FreeLibrary
0x180028b6a  test    edi, edi
0x180028b6c  jz      short loc_180028B32
0x180028b6e  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x180028b70  mov     cl, 1; bool
0x180028b72  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x180028b77  mov     ebx, eax
0x180028b79  test    eax, eax
0x180028b7b  jns     short loc_180028BA5
0x180028b7d  mov     rcx, [rbp+5Fh]; this
0x180028b81  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x180028b88  mov     r9d, ebx; char *
0x180028b8b  mov     [rsp+0D0h+lpString2], rax; int
0x180028b90  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180028b97  mov     edx, 137h; void *
0x180028b9c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180028ba1  mov     eax, ebx
0x180028ba3  jmp     short loc_180028B37
0x180028ba5  xorps   xmm0, xmm0
0x180028ba8  lea     rcx, [rbp+57h+var_98]
0x180028bac  xor     edx, edx
0x180028bae  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x180028bb3  call    ?QueryAppIdentity@AppIdentity@@SAJAEAV?$shared_ptr@VAppIdentity@@@std@@PEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@@Z; AppIdentity::QueryAppIdentity(std::shared_ptr<AppIdentity> &,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *)
0x180028bb8  test    eax, eax
0x180028bba  jns     short loc_180028BD8
0x180028bbc  mov     rdi, qword ptr [rbp+57h+var_98+8]
0x180028bc0  mov     dword ptr [r14], 3
0x180028bc7  test    rdi, rdi
0x180028bca  jz      loc_180028DC7
0x180028bd0  or      ebx, 0FFFFFFFFh
0x180028bd3  jmp     loc_180028D94
0x180028bd8  lea     rdx, [rbp+57h+SRWLock]
0x180028bdc  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x180028be1  xorps   xmm0, xmm0
0x180028be4  mov     dword ptr [r14], 0
0x180028beb  xorps   xmm1, xmm1
0x180028bee  lea     rdx, word_180096C4C
0x180028bf5  xor     r8d, r8d
0x180028bf8  lea     rcx, [rbp+57h+var_78]
0x180028bfc  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x180028c01  movups  [rbp+57h+var_78], xmm0
0x180028c05  movdqu  [rbp+57h+var_68], xmm1
0x180028c0a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180028c0f  lea     rdx, [rbp+57h+var_88]
0x180028c13  lea     rcx, [rbp+57h+var_78]
0x180028c17  call    ?GetForUser@OwningUser@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@VOwningUser@@@3@@Z; OwningUser::GetForUser(std::wstring const &,std::shared_ptr<OwningUser> &)
0x180028c1c  lea     rcx, [rbp+57h+var_78]
0x180028c20  mov     esi, eax
0x180028c22  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028c27  test    esi, esi
0x180028c29  jns     loc_180028CDF
0x180028c2f  mov     edx, 14Ah; void *
0x180028c34  mov     rcx, [rbp+5Fh]; this
0x180028c38  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180028c3f  mov     r9d, esi; char *
0x180028c42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028c47  mov     rdi, qword ptr [rbp+57h+var_88+8]
0x180028c4b  or      ebx, 0FFFFFFFFh
0x180028c4e  test    rdi, rdi
0x180028c51  jz      short loc_180028C86
0x180028c53  mov     eax, ebx
0x180028c55  lock xadd [rdi+8], eax
0x180028c5a  add     eax, ebx
0x180028c5c  jnz     short loc_180028C86
0x180028c5e  mov     rax, [rdi]
0x180028c61  mov     rcx, rdi
0x180028c64  mov     rax, [rax]
0x180028c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c6c  mov     eax, ebx
0x180028c6e  lock xadd [rdi+0Ch], eax
0x180028c73  add     eax, ebx
0x180028c75  jnz     short loc_180028C86
0x180028c77  mov     rax, [rdi]
0x180028c7a  mov     rcx, rdi
0x180028c7d  mov     rax, [rax+8]
0x180028c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c86  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180028c8a  test    rcx, rcx
0x180028c8d  jz      short loc_180028C9C
0x180028c8f  mov     dword ptr [rcx+8], 0
0x180028c96  call    cs:__imp_ReleaseSRWLockExclusive
0x180028c9c  mov     rdi, qword ptr [rbp+57h+var_98+8]
0x180028ca0  test    rdi, rdi
0x180028ca3  jz      short loc_180028CD8
0x180028ca5  mov     eax, ebx
0x180028ca7  lock xadd [rdi+8], eax
0x180028cac  add     eax, ebx
0x180028cae  jnz     short loc_180028CD8
0x180028cb0  mov     rax, [rdi]
0x180028cb3  mov     rcx, rdi
0x180028cb6  mov     rax, [rax]
0x180028cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cbe  mov     eax, ebx
0x180028cc0  lock xadd [rdi+0Ch], eax
0x180028cc5  add     eax, ebx
0x180028cc7  jnz     short loc_180028CD8
0x180028cc9  mov     rax, [rdi]
0x180028ccc  mov     rcx, rdi
0x180028ccf  mov     rax, [rax+8]
0x180028cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cd8  mov     eax, esi
0x180028cda  jmp     loc_180028B37
0x180028cdf  mov     rdx, r12
0x180028ce2  lea     rcx, [rbp+57h+var_58]
0x180028ce6  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x180028ceb  mov     rdx, r15
0x180028cee  lea     rcx, [rbp+57h+var_78]
0x180028cf2  mov     rbx, rax
0x180028cf5  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x180028cfa  mov     r9, rax; int
0x180028cfd  mov     [rsp+0D0h+var_A8], r14; __int64
0x180028d02  lea     r8, [rbp+57h+var_88]; int
0x180028d06  mov     [rsp+0D0h+lpString2], rbx; lpString2
0x180028d0b  lea     rdx, [rbp+57h+var_98]; int
0x180028d0f  call    ?RegisterClient@ClientIdentity@@SAJPEAUIUnknown@@AEAV?$shared_ptr@VAppIdentity@@@std@@AEAV?$shared_ptr@VOwningUser@@@4@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@3PEAW4IsolationEnviromentRegistrationStatus@IsolationEnvironment@AI@Windows@@@Z; ClientIdentity::RegisterClient(IUnknown *,std::shared_ptr<AppIdentity> &,std::shared_ptr<OwningUser> &,std::wstring const &,std::wstring const &,Windows::AI::IsolationEnvironment::IsolationEnviromentRegistrationStatus *)
0x180028d14  lea     rcx, [rbp+57h+var_78]
0x180028d18  mov     esi, eax
0x180028d1a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028d1f  lea     rcx, [rbp+57h+var_58]
0x180028d23  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028d28  test    esi, esi
0x180028d2a  jns     short loc_180028D36
0x180028d2c  mov     edx, 152h
0x180028d31  jmp     loc_180028C34
0x180028d36  mov     rdi, qword ptr [rbp+57h+var_88+8]
0x180028d3a  or      ebx, 0FFFFFFFFh
0x180028d3d  test    rdi, rdi
0x180028d40  jz      short loc_180028D75
0x180028d42  mov     eax, ebx
0x180028d44  lock xadd [rdi+8], eax
0x180028d49  add     eax, ebx
0x180028d4b  jnz     short loc_180028D75
0x180028d4d  mov     rax, [rdi]
0x180028d50  mov     rcx, rdi
0x180028d53  mov     rax, [rax]
0x180028d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d5b  mov     eax, ebx
0x180028d5d  lock xadd [rdi+0Ch], eax
0x180028d62  add     eax, ebx
0x180028d64  jnz     short loc_180028D75
0x180028d66  mov     rax, [rdi]
0x180028d69  mov     rcx, rdi
0x180028d6c  mov     rax, [rax+8]
0x180028d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d75  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180028d79  test    rcx, rcx
0x180028d7c  jz      short loc_180028D8B
0x180028d7e  mov     dword ptr [rcx+8], 0
0x180028d85  call    cs:__imp_ReleaseSRWLockExclusive
0x180028d8b  mov     rdi, qword ptr [rbp+57h+var_98+8]
0x180028d8f  test    rdi, rdi
0x180028d92  jz      short loc_180028DC7
0x180028d94  mov     eax, ebx
0x180028d96  lock xadd [rdi+8], eax
0x180028d9b  add     eax, ebx
0x180028d9d  jnz     short loc_180028DC7
0x180028d9f  mov     rax, [rdi]
0x180028da2  mov     rcx, rdi
0x180028da5  mov     rax, [rax]
0x180028da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028dad  mov     eax, ebx
0x180028daf  lock xadd [rdi+0Ch], eax
0x180028db4  add     eax, ebx
0x180028db6  jnz     short loc_180028DC7
0x180028db8  mov     rax, [rdi]
0x180028dbb  mov     rcx, rdi
0x180028dbe  mov     rax, [rax+8]
0x180028dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028dc7  xor     eax, eax
0x180028dc9  jmp     loc_180028B37
```
