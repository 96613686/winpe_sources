# AppReadiness::Service::GetSystemUser(void)

- ea: `0x18002c0d0`
- end: `0x18002c383`
- name: `?GetSystemUser@Service@AppReadiness@@QEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@XZ`
- size: `691`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002bfbc`
- `0x180045f74`
- `0x18004630c`

## callees

- `0x180002958`
- `0x1800041e0`
- `0x18000b464`
- `0x18000e1d8`
- `0x180021bd4`
- `0x18002760c`
- `0x180027a4c`
- `0x18002c0d0`
- `0x18002c38c`
- `0x18003235c`
- `0x180037a10`
- `0x180037c20`
- `0x18003e210`
- `0x18003ecb4`
- `0x1800473d8`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c33a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c33a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c128`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c128`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002c1ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002c1ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002c1fe`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002c1fe`

## string_xrefs

- `0x18002c144`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x18002c21b`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x18002c280`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x18002c150`: `AppReadiness::Service::GetSystemUser`
- `0x18002c227`: `AppReadiness::Service::GetSystemUser`
- `0x18002c28c`: `AppReadiness::Service::GetSystemUser`
- `0x18002c22e`: `OpenProcessToken(GetCurrentProcess(), TOKEN_IMPERSONATE|TOKEN_QUERY|TOKEN_DUPLICATE, processToken.GetAddressOf())`
- `0x18002c293`: `MakeAndInitialize<User>(&systemUser, systemSid, INVALID_USERCONTEXT_TOKEN, processToken)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
AppReadiness::User **__fastcall AppReadiness::Service::GetSystemUser(__int64 a1, AppReadiness::User **a2)
{
  AppReadiness::User **v4; // r15
  HANDLE CurrentProcess; // rax
  int Error; // edx
  int v7; // eax
  AppReadiness::User *v8; // rcx
  _QWORD *v9; // rcx
  AppReadiness::User *v11; // [rsp+30h] [rbp-59h] BYREF
  int v12; // [rsp+38h] [rbp-51h]
  void **v13; // [rsp+40h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int8 (__fastcall *pExceptionObject[2])(__int64, __int64); // [rsp+50h] [rbp-39h] BYREF
  _BYTE v16[32]; // [rsp+60h] [rbp-29h] BYREF
  AppReadiness::User **v17; // [rsp+80h] [rbp-9h]
  __int64 v18; // [rsp+88h] [rbp-1h]
  void *v19[3]; // [rsp+90h] [rbp+7h] BYREF
  unsigned __int64 v20; // [rsp+A8h] [rbp+1Fh]

  v17 = a2;
  AppReadiness::User::GetWellKnownSid((__int64)v19, WinLocalSystemSid, 0);
  v12 = 2;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 152));
  v18 = a1 + 152;
  if ( *(_BYTE *)(a1 + 272) )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      -2147019873,
      "!m_shuttingDown",
      "AppReadiness::Service::GetSystemUser",
      "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
      443);
    throw (Windows::HResultException *)pExceptionObject;
  }
  pExceptionObject[0] = (unsigned __int8 (__fastcall *)(__int64, __int64))AppReadiness::IsUserEqual;
  std::wstring::wstring(v16, v19);
  v12 = 6;
  std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<AppReadiness::User>>>>,std::_Binder<std::_Unforced,bool (*)(std::wstring const &,Microsoft::WRL::ComPtr<AppReadiness::User> const &),std::wstring const &,std::_Ph<1> const &>>(
    &v11,
    *(_QWORD *)(a1 + 160),
    *(_QWORD *)(a1 + 168),
    pExceptionObject);
  *a2 = 0;
  v12 = 7;
  v4 = (AppReadiness::User **)v11;
  if ( v11 == *(AppReadiness::User **)(a1 + 168) )
  {
    v13 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          Error,
          "OpenProcessToken(GetCurrentProcess(), TOKEN_IMPERSONATE|TOKEN_QUERY|TOKEN_DUPLICATE, processToken.GetAddressOf())",
          "AppReadiness::Service::GetSystemUser",
          "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
          449);
        throw (Windows::HResultException *)pExceptionObject;
      }
    }
    LODWORD(v11) = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
    v7 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::User,AppReadiness::User,std::wstring &,int,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> &>(a2);
    if ( v7 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v7,
        "MakeAndInitialize<User>(&systemUser, systemSid, INVALID_USERCONTEXT_TOKEN, processToken)",
        "AppReadiness::Service::GetSystemUser",
        "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
        450);
      throw (Windows::HResultException *)pExceptionObject;
    }
    v8 = *a2;
    v11 = v8;
    if ( v8 )
      (*(void (__fastcall **)(AppReadiness::User *, _QWORD))(*(_QWORD *)v8 + 8LL))(v8, (unsigned int)v7);
    v9 = *(_QWORD **)(a1 + 168);
    if ( v9 == *(_QWORD **)(a1 + 176) )
    {
      std::vector<Microsoft::WRL::ComPtr<AppReadiness::User>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<AppReadiness::User>>(
        (_QWORD *)(a1 + 160),
        *(_QWORD *)(a1 + 168),
        (__int64)&v11);
    }
    else
    {
      Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(v9, &v11);
      *(_QWORD *)(a1 + 168) += 8LL;
    }
    if ( v11 )
      (*(void (__fastcall **)(AppReadiness::User *))(*(_QWORD *)v11 + 16LL))(v11);
    v13 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v13);
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
    Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(v4);
    *a2 = *v4;
  }
  if ( a1 != -152 )
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 152));
  if ( v20 > 7 )
    std::_Deallocate<16>(v19[0], 2 * v20 + 2);
  return a2;
}

```

## disassembly

```asm
0x18002c0d0  mov     [rsp-8+arg_10], rbx
0x18002c0d5  push    rbp
0x18002c0d6  push    rsi
0x18002c0d7  push    rdi
0x18002c0d8  push    r14
0x18002c0da  push    r15
0x18002c0dc  lea     rbp, [rsp-37h]
0x18002c0e1  sub     rsp, 0C0h
0x18002c0e8  mov     rax, cs:__security_cookie
0x18002c0ef  xor     rax, rsp
0x18002c0f2  mov     [rbp+57h+var_30], rax
0x18002c0f6  mov     rbx, rdx
0x18002c0f9  mov     r14, rcx
0x18002c0fc  mov     [rbp+57h+var_60], rdx
0x18002c100  mov     [rbp+57h+var_A8], 0
0x18002c107  xor     r8d, r8d
0x18002c10a  lea     edx, [r8+16h]
0x18002c10e  lea     rcx, [rbp+57h+var_50]
0x18002c112  call    ?GetWellKnownSid@User@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; AppReadiness::User::GetWellKnownSid(WELL_KNOWN_SID_TYPE,void *)
0x18002c117  mov     [rbp+57h+var_A8], 2
0x18002c11e  lea     rsi, [r14+98h]
0x18002c125  mov     rcx, rsi; SRWLock
0x18002c128  call    cs:__imp_AcquireSRWLockExclusive
0x18002c12e  mov     [rbp+57h+var_58], rsi
0x18002c132  cmp     byte ptr [r14+110h], 0
0x18002c13a  jz      short loc_18002C17D
0x18002c13c  mov     [rsp+0E0h+var_B8], 1BBh; int
0x18002c144  lea     rax, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002c14b  mov     [rsp+0E0h+var_C0], rax; char *
0x18002c150  lea     r9, aAppreadinessSe_4; "AppReadiness::Service::GetSystemUser"
0x18002c157  lea     r8, aMShuttingdown; "!m_shuttingDown"
0x18002c15e  mov     edx, 8007139Fh; int
0x18002c163  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002c167  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002c16c  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002c173  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002c177  call    _CxxThrowException_0
0x18002c17d  lea     rax, AppReadiness__IsUserEqual
0x18002c184  mov     [rbp+57h+pExceptionObject], rax
0x18002c188  lea     rdx, [rbp+57h+var_50]
0x18002c18c  lea     rcx, [rbp+57h+var_80]
0x18002c190  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c195  mov     [rbp+57h+var_A8], 6
0x18002c19c  lea     rdi, [r14+0A0h]
0x18002c1a3  lea     r9, [rbp+57h+pExceptionObject]
0x18002c1a7  mov     r8, [r14+0A8h]
0x18002c1ae  mov     rdx, [rdi]
0x18002c1b1  lea     rcx, [rbp+57h+var_B0]
0x18002c1b5  call    ??$find_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@@std@@@std@@@std@@V?$_Binder@U_Unforced@std@@P6A_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEBV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@@ZAEBV32@AEBU?$_Ph@$00@2@@2@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@@std@@@std@@@0@V10@V10@V?$_Binder@U_Unforced@std@@P6A_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEBV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@@ZAEBV32@AEBU?$_Ph@$00@2@@0@@Z; std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<AppReadiness::User>>>>,std::_Binder<std::_Unforced,bool (*)(std::wstring const &,Microsoft::WRL::ComPtr<AppReadiness::User> const &),std::wstring const &,std::_Ph<1> const &>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<AppReadiness::User>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<AppReadiness::User>>>>,std::_Binder<std::_Unforced,bool (*)(std::wstring const &,Microsoft::WRL::ComPtr<AppReadiness::User> const &),std::wstring const &,std::_Ph<1> const &>)
0x18002c1ba  mov     qword ptr [rbx], 0
0x18002c1c1  mov     [rbp+57h+var_A8], 7
0x18002c1c8  mov     r15, [rbp+57h+var_B0]
0x18002c1cc  cmp     r15, [r14+0A8h]
0x18002c1d3  jnz     loc_18002C31C
0x18002c1d9  lea     r14, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18002c1e0  mov     [rbp+57h+var_A0], r14
0x18002c1e4  mov     [rbp+57h+TokenHandle], 0
0x18002c1ec  call    cs:__imp_GetCurrentProcess
0x18002c1f2  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18002c1f6  mov     edx, 0Eh; DesiredAccess
0x18002c1fb  mov     rcx, rax; ProcessHandle
0x18002c1fe  call    cs:__imp_OpenProcessToken
0x18002c204  test    eax, eax
0x18002c206  jnz     short loc_18002C24F
0x18002c208  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002c20d  mov     edx, eax; int
0x18002c20f  test    eax, eax
0x18002c211  jns     short loc_18002C24F
0x18002c213  mov     [rsp+0E0h+var_B8], 1C1h; int
0x18002c21b  lea     rax, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002c222  mov     [rsp+0E0h+var_C0], rax; char *
0x18002c227  lea     r9, aAppreadinessSe_4; "AppReadiness::Service::GetSystemUser"
0x18002c22e  lea     r8, aOpenprocesstok; "OpenProcessToken(GetCurrentProcess(), T"...
0x18002c235  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002c239  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002c23e  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002c245  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002c249  call    _CxxThrowException_0
0x18002c24f  mov     dword ptr [rbp+57h+var_B0], 0
0x18002c256  mov     rcx, rbx
0x18002c259  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c25e  lea     r9, [rbp+57h+var_A0]
0x18002c262  lea     r8, [rbp+57h+var_B0]
0x18002c266  lea     rdx, [rbp+57h+var_50]
0x18002c26a  mov     rcx, rbx
0x18002c26d  call    ??$MakeAndInitialize@VUser@AppReadiness@@V12@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HAEAV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAVUser@AppReadiness@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEAHAEAV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::User,AppReadiness::User,std::wstring &,int,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> &>(AppReadiness::User * *,std::wstring &,int &&,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> &)
0x18002c272  mov     edx, eax; int
0x18002c274  test    eax, eax
0x18002c276  jns     short loc_18002C2B4
0x18002c278  mov     [rsp+0E0h+var_B8], 1C2h; int
0x18002c280  lea     rax, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002c287  mov     [rsp+0E0h+var_C0], rax; char *
0x18002c28c  lea     r9, aAppreadinessSe_4; "AppReadiness::Service::GetSystemUser"
0x18002c293  lea     r8, aMakeandinitial_9; "MakeAndInitialize<User>(&systemUser, sy"...
0x18002c29a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002c29e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002c2a3  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002c2aa  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002c2ae  call    _CxxThrowException_0
0x18002c2b4  mov     rcx, [rbx]
0x18002c2b7  mov     [rbp+57h+var_B0], rcx
0x18002c2bb  test    rcx, rcx
0x18002c2be  jz      short loc_18002C2CD
0x18002c2c0  mov     rax, [rcx]
0x18002c2c3  mov     rax, [rax+8]
0x18002c2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2cc  nop
0x18002c2cd  mov     rcx, [rdi+8]
0x18002c2d1  cmp     rcx, [rdi+10h]
0x18002c2d5  jz      short loc_18002C2E7
0x18002c2d7  lea     rdx, [rbp+57h+var_B0]
0x18002c2db  call    ??0?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(Microsoft::WRL::ComPtr<AppReadiness::ITask> &&)
0x18002c2e0  add     qword ptr [rdi+8], 8
0x18002c2e5  jmp     short loc_18002C2F7
0x18002c2e7  lea     r8, [rbp+57h+var_B0]
0x18002c2eb  mov     rdx, rcx
0x18002c2ee  mov     rcx, rdi
0x18002c2f1  call    ??$_Emplace_reallocate@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@@?$vector@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@QEAV234@$$QEAV234@@Z; std::vector<Microsoft::WRL::ComPtr<AppReadiness::User>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<AppReadiness::User>>(Microsoft::WRL::ComPtr<AppReadiness::User> * const,Microsoft::WRL::ComPtr<AppReadiness::User> &&)
0x18002c2f6  nop
0x18002c2f7  mov     rcx, [rbp+57h+var_B0]
0x18002c2fb  test    rcx, rcx
0x18002c2fe  jz      short loc_18002C30D
0x18002c300  mov     rax, [rcx]
0x18002c303  mov     rax, [rax+10h]
0x18002c307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c30c  nop
0x18002c30d  mov     [rbp+57h+var_A0], r14
0x18002c311  lea     rcx, [rbp+57h+var_A0]
0x18002c315  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18002c31a  jmp     short loc_18002C332
0x18002c31c  mov     rcx, rbx
0x18002c31f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c324  mov     rcx, r15
0x18002c327  call    ?InternalAddRef@?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(void)
0x18002c32c  mov     rax, [r15]
0x18002c32f  mov     [rbx], rax
0x18002c332  test    rsi, rsi
0x18002c335  jz      short loc_18002C341
0x18002c337  mov     rcx, rsi; SRWLock
0x18002c33a  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c340  nop
0x18002c341  mov     rdx, [rbp+57h+var_38]
0x18002c345  cmp     rdx, 7
0x18002c349  jbe     short loc_18002C35C
0x18002c34b  lea     rdx, ds:2[rdx*2]
0x18002c353  mov     rcx, [rbp+57h+var_50]
0x18002c357  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002c35c  mov     rax, rbx
0x18002c35f  mov     rcx, [rbp+57h+var_30]
0x18002c363  xor     rcx, rsp; StackCookie
0x18002c366  call    __security_check_cookie
0x18002c36b  mov     rbx, [rsp+0E0h+arg_10]
0x18002c373  add     rsp, 0C0h
0x18002c37a  pop     r15
0x18002c37c  pop     r14
0x18002c37e  pop     rdi
0x18002c37f  pop     rsi
0x18002c380  pop     rbp
0x18002c381  retn
```
