# AppReadiness::Service::CreateUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)

- ea: `0x18001009c`
- end: `0x18001044e`
- name: `?CreateUser@Service@AppReadiness@@QEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@45@@Z`
- size: `946`
- prototype: `AppReadiness::User **__fastcall(__int64, AppReadiness::User **, _QWORD *, __int64)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180011cac`
- `0x180026c10`
- `0x180047f34`

## callees

- `0x180002958`
- `0x18000b464`
- `0x18000d17c`
- `0x18000e1d8`
- `0x18000e4a0`
- `0x18001009c`
- `0x180010454`
- `0x180027a4c`
- `0x18002c40c`
- `0x18002eb00`
- `0x180033ff8`
- `0x180035720`
- `0x180037c20`
- `0x18003ecb4`
- `0x18003eec0`
- `0x180040338`
- `0x1800473d8`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800103e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800103e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800100d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800100d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800101b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800101b5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18001021b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18001021b`

## string_xrefs

- `0x1800101d0`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x18001022d`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x1800102f2`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x180010415`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x1800101dc`: `AppReadiness::Service::CreateUser`
- `0x180010239`: `AppReadiness::Service::CreateUser`
- `0x1800102fe`: `AppReadiness::Service::CreateUser`
- `0x180010421`: `AppReadiness::Service::CreateUser`
- `0x180010305`: `MakeAndInitialize<User>(user.GetAddressOf(), userSid, userContextToken, userToken)`
- `0x1800101e3`: `GetTokenInformation(userToken.Get(), TokenSessionId, &userSessionId, sizeof(userSessionId), &userSessionIdLen)`
- `0x180010240`: `UMgrQueryUserContext(userToken.Get(), &userContextToken)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
AppReadiness::User **__fastcall AppReadiness::Service::CreateUser(
        __int64 a1,
        AppReadiness::User **a2,
        _QWORD *a3,
        __int64 a4)
{
  RTL_SRWLOCK *v8; // r12
  _QWORD *v9; // rdx
  AppReadiness::User **v10; // rax
  _QWORD *v11; // rsi
  AppReadiness::User **v12; // rdi
  AppReadiness::User **v13; // r12
  __int64 v14; // rcx
  int Error; // eax
  int v16; // eax
  AppReadiness::User *v17; // rax
  int v18; // edi
  AppReadiness::User *v19; // r14
  AppReadiness::User *v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // r8
  __int64 v23; // r8
  AppReadiness::User *v25; // [rsp+30h] [rbp-49h] BYREF
  int v26; // [rsp+38h] [rbp-41h]
  _QWORD *v27; // [rsp+40h] [rbp-39h] BYREF
  char v28[8]; // [rsp+48h] [rbp-31h] BYREF
  int TokenInformation; // [rsp+50h] [rbp-29h] BYREF
  __int64 v30; // [rsp+58h] [rbp-21h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v32; // [rsp+70h] [rbp-9h] BYREF
  __int64 v33; // [rsp+80h] [rbp+7h]
  __int64 v34; // [rsp+88h] [rbp+Fh]
  RTL_SRWLOCK *v35; // [rsp+90h] [rbp+17h]
  AppReadiness::User **ReturnLength; // [rsp+E0h] [rbp+67h] BYREF
  AppReadiness::User **v37; // [rsp+E8h] [rbp+6Fh]

  v37 = a2;
  v26 = 0;
  v8 = (RTL_SRWLOCK *)(a1 + 152);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 152));
  v35 = v8;
  if ( *(_BYTE *)(a1 + 272) )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      -2147019873,
      "!m_shuttingDown",
      "AppReadiness::Service::CreateUser",
      "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
      382);
    throw (Windows::HResultException *)pExceptionObject;
  }
  *a2 = 0;
  v26 = 1;
  pExceptionObject[0] = AppReadiness::IsUserEqual;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( a3[3] <= 7u )
    v9 = a3;
  else
    v9 = (_QWORD *)*a3;
  std::wstring::_Construct<2,unsigned short const *>(&v32, v9, a3[2]);
  v26 = 3;
  v27 = pExceptionObject;
  v10 = *(AppReadiness::User ***)(a1 + 168);
  ReturnLength = v10;
  v11 = (_QWORD *)(a1 + 160);
  v12 = *(AppReadiness::User ***)(a1 + 160);
  if ( v12 != v10 )
  {
    v13 = v10;
    do
    {
      if ( ((unsigned __int8 (__fastcall *)(__int128 *, AppReadiness::User **))pExceptionObject[0])(&v32, v12) )
        break;
      ++v12;
    }
    while ( v12 != v13 );
    v8 = (RTL_SRWLOCK *)(a1 + 152);
  }
  std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(&v32);
  if ( v12 == *(AppReadiness::User ***)(a1 + 168) )
  {
    LODWORD(ReturnLength) = 0;
    TokenInformation = 0;
    if ( !GetTokenInformation(*(HANDLE *)(a4 + 8), TokenSessionId, &TokenInformation, 4u, (PDWORD)&ReturnLength) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          Error,
          "GetTokenInformation(userToken.Get(), TokenSessionId, &userSessionId, sizeof(userSessionId), &userSessionIdLen)",
          "AppReadiness::Service::CreateUser",
          "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
          395);
        throw (Windows::HResultException *)pExceptionObject;
      }
    }
    v30 = 0;
    if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent(v14) )
    {
      v16 = UMgrQueryUserContext(*(_QWORD *)(a4 + 8), &v30);
      if ( v16 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          v16,
          "UMgrQueryUserContext(userToken.Get(), &userContextToken)",
          "AppReadiness::Service::CreateUser",
          "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
          400);
        throw (Windows::HResultException *)pExceptionObject;
      }
    }
    *a2 = 0;
    v17 = (AppReadiness::User *)operator new(0x1C0u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v17 )
    {
      v18 = -2147024882;
      goto LABEL_25;
    }
    v19 = (AppReadiness::User *)AppReadiness::User::User(v17);
    v25 = v19;
    v27 = 0;
    v18 = AppReadiness::User::RuntimeClassInitialize(v19);
    if ( v18 >= 0 )
    {
      Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(&v25);
      *a2 = v19;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      Microsoft::WRL::Details::MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>::~MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>(&v27);
      v18 = 0;
    }
    else if ( v19 )
    {
      (*(void (__fastcall **)(AppReadiness::User *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    if ( v18 < 0 )
    {
LABEL_25:
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v18,
        "MakeAndInitialize<User>(user.GetAddressOf(), userSid, userContextToken, userToken)",
        "AppReadiness::Service::CreateUser",
        "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
        403);
      throw (Windows::HResultException *)pExceptionObject;
    }
    v20 = *a2;
    v25 = v20;
    if ( v20 )
      (*(void (__fastcall **)(AppReadiness::User *))(*(_QWORD *)v20 + 8LL))(v20);
    v21 = *v11;
    v22 = v11[1];
    if ( v22 == v11[2] )
    {
      std::vector<Microsoft::WRL::ComPtr<AppReadiness::User>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<AppReadiness::User>>(
        v11,
        *v11,
        &v25);
    }
    else if ( v21 == v22 )
    {
      Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(v11[1], &v25);
      v11[1] += 8LL;
    }
    else
    {
      v27 = v11;
      Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(v28, &v25);
      Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(v23, v23 - 8);
      v11[1] += 8LL;
      std::_Move_backward_unchecked<Microsoft::WRL::ComPtr<AppReadiness::User> *,Microsoft::WRL::ComPtr<AppReadiness::User> *>(v21);
      Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(v21, v28);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v28);
    }
    if ( v25 )
      (*(void (__fastcall **)(AppReadiness::User *))(*(_QWORD *)v25 + 16LL))(v25);
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
    Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(v12);
    *a2 = *v12;
  }
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  return a2;
}

```

## disassembly

```asm
0x18001009c  mov     [rsp-8+arg_10], rbx
0x1800100a1  mov     [rsp-8+arg_8], rdx
0x1800100a6  push    rbp
0x1800100a7  push    rsi
0x1800100a8  push    rdi
0x1800100a9  push    r12
0x1800100ab  push    r13
0x1800100ad  push    r14
0x1800100af  push    r15
0x1800100b1  lea     rbp, [rsp-27h]
0x1800100b6  sub     rsp, 0A0h
0x1800100bd  mov     r13, r9
0x1800100c0  mov     r15, r8
0x1800100c3  mov     rbx, rdx
0x1800100c6  mov     r14, rcx
0x1800100c9  xor     edi, edi
0x1800100cb  mov     [rbp+57h+var_98], edi
0x1800100ce  lea     r12, [rcx+98h]
0x1800100d5  mov     rcx, r12; SRWLock
0x1800100d8  call    cs:__imp_AcquireSRWLockExclusive
0x1800100de  mov     [rbp+57h+var_40], r12
0x1800100e2  cmp     [r14+110h], dil
0x1800100e9  jnz     loc_18001040D
0x1800100ef  mov     [rbx], rdi
0x1800100f2  mov     [rbp+57h+var_98], 1
0x1800100f9  lea     rax, AppReadiness__IsUserEqual
0x180010100  mov     [rbp+57h+pExceptionObject], rax
0x180010104  xorps   xmm0, xmm0
0x180010107  movups  [rbp+57h+var_60], xmm0
0x18001010b  mov     [rbp+57h+var_50], rdi
0x18001010f  mov     [rbp+57h+var_48], rdi
0x180010113  cmp     qword ptr [r15+18h], 7
0x180010118  jbe     short loc_18001011F
0x18001011a  mov     rdx, [r15]
0x18001011d  jmp     short loc_180010122
0x18001011f  mov     rdx, r15
0x180010122  mov     r8, [r15+10h]
0x180010126  lea     rcx, [rbp+57h+var_60]
0x18001012a  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18001012f  mov     [rbp+57h+var_98], 3
0x180010136  lea     rax, [rbp+57h+pExceptionObject]
0x18001013a  mov     [rbp+57h+var_90], rax
0x18001013e  mov     rax, [r14+0A8h]
0x180010145  mov     [rbp+57h+arg_0], rax
0x180010149  lea     rsi, [r14+0A0h]
0x180010150  mov     rdi, [rsi]
0x180010153  cmp     rdi, rax
0x180010156  jz      short loc_18001017F
0x180010158  mov     r12, rax
0x18001015b  mov     rdx, rdi
0x18001015e  lea     rcx, [rbp+57h+var_60]
0x180010162  mov     rax, [rbp+57h+pExceptionObject]
0x180010166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001016b  test    al, al
0x18001016d  jnz     short loc_180010178
0x18001016f  add     rdi, 8
0x180010173  cmp     rdi, r12
0x180010176  jnz     short loc_18001015B
0x180010178  lea     r12, [r14+98h]
0x18001017f  lea     rcx, [rbp+57h+var_60]
0x180010183  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x180010188  cmp     rdi, [r14+0A8h]
0x18001018f  jnz     loc_1800103CB
0x180010195  xor     edi, edi
0x180010197  mov     dword ptr [rbp+57h+arg_0], edi
0x18001019a  mov     [rbp+57h+TokenInformation], edi
0x18001019d  lea     rax, [rbp+57h+arg_0]
0x1800101a1  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800101a6  lea     r9d, [rdi+4]; TokenInformationLength
0x1800101aa  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800101ae  lea     edx, [rdi+0Ch]; TokenInformationClass
0x1800101b1  mov     rcx, [r13+8]; TokenHandle
0x1800101b5  call    cs:__imp_GetTokenInformation
0x1800101bb  test    eax, eax
0x1800101bd  jnz     short loc_180010206
0x1800101bf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800101c4  test    eax, eax
0x1800101c6  jns     short loc_180010206
0x1800101c8  mov     [rsp+0D0h+var_A8], 18Bh; int
0x1800101d0  lea     rcx, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800101d7  mov     [rsp+0D0h+ReturnLength], rcx; char *
0x1800101dc  lea     r9, aAppreadinessSe_11; "AppReadiness::Service::CreateUser"
0x1800101e3  lea     r8, aGettokeninform_0; "GetTokenInformation(userToken.Get(), To"...
0x1800101ea  mov     edx, eax; int
0x1800101ec  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800101f0  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800101f5  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800101fc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180010200  call    _CxxThrowException_0
0x180010206  mov     [rbp+57h+var_78], rdi
0x18001020a  call    IsUMgrEnumerateSessionUsersPresent
0x18001020f  test    al, al
0x180010211  jz      short loc_180010263
0x180010213  lea     rdx, [rbp+57h+var_78]
0x180010217  mov     rcx, [r13+8]
0x18001021b  call    cs:__imp_UMgrQueryUserContext
0x180010221  test    eax, eax
0x180010223  jns     short loc_180010263
0x180010225  mov     [rsp+0D0h+var_A8], 190h; int
0x18001022d  lea     rcx, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180010234  mov     [rsp+0D0h+ReturnLength], rcx; char *
0x180010239  lea     r9, aAppreadinessSe_11; "AppReadiness::Service::CreateUser"
0x180010240  lea     r8, aUmgrqueryuserc_0; "UMgrQueryUserContext(userToken.Get(), &"...
0x180010247  mov     edx, eax; int
0x180010249  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001024d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180010252  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180010259  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001025d  call    _CxxThrowException_0
0x180010263  mov     [rbx], rdi
0x180010266  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001026d  mov     ecx, 1C0h; unsigned __int64
0x180010272  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010277  test    rax, rax
0x18001027a  jnz     short loc_180010283
0x18001027c  mov     edi, 8007000Eh
0x180010281  jmp     short loc_1800102EA
0x180010283  mov     rcx, rax; this
0x180010286  call    ??0User@AppReadiness@@QEAA@XZ; AppReadiness::User::User(void)
0x18001028b  mov     r14, rax
0x18001028e  mov     [rbp+57h+var_A0], rax
0x180010292  mov     [rbp+57h+var_90], rdi
0x180010296  mov     r9, r13
0x180010299  mov     r8, [rbp+57h+var_78]
0x18001029d  mov     rdx, r15
0x1800102a0  mov     rcx, rax
0x1800102a3  call    ?RuntimeClassInitialize@User@AppReadiness@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; AppReadiness::User::RuntimeClassInitialize(std::wstring const &,unsigned __int64,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x1800102a8  mov     edi, eax
0x1800102aa  test    eax, eax
0x1800102ac  jns     short loc_1800102C5
0x1800102ae  test    r14, r14
0x1800102b1  jz      short loc_1800102C3
0x1800102b3  mov     rax, [r14]
0x1800102b6  mov     rcx, r14
0x1800102b9  mov     rax, [rax+10h]
0x1800102bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102c2  nop
0x1800102c3  jmp     short loc_1800102E6
0x1800102c5  lea     rcx, [rbp+57h+var_A0]
0x1800102c9  call    ?InternalAddRef@?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(void)
0x1800102ce  mov     [rbx], r14
0x1800102d1  lea     rcx, [rbp+57h+var_A0]
0x1800102d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800102da  nop
0x1800102db  lea     rcx, [rbp+57h+var_90]
0x1800102df  call    ??1?$MakeAllocator@VResolveStoreCategories@Tasks@AppReadiness@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>::~MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>(void)
0x1800102e4  xor     edi, edi
0x1800102e6  test    edi, edi
0x1800102e8  jns     short loc_180010328
0x1800102ea  mov     [rsp+0D0h+var_A8], 193h; int
0x1800102f2  lea     rcx, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800102f9  mov     [rsp+0D0h+ReturnLength], rcx; char *
0x1800102fe  lea     r9, aAppreadinessSe_11; "AppReadiness::Service::CreateUser"
0x180010305  lea     r8, aMakeandinitial_1; "MakeAndInitialize<User>(user.GetAddress"...
0x18001030c  mov     edx, edi; int
0x18001030e  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180010312  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180010317  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18001031e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180010322  call    _CxxThrowException_0
0x180010328  mov     rcx, [rbx]
0x18001032b  mov     [rbp+57h+var_A0], rcx
0x18001032f  test    rcx, rcx
0x180010332  jz      short loc_180010341
0x180010334  mov     rax, [rcx]
0x180010337  mov     rax, [rax+8]
0x18001033b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010340  nop
0x180010341  mov     rdi, [rsi]
0x180010344  mov     r8, [rsi+8]
0x180010348  cmp     r8, [rsi+10h]
0x18001034c  jz      short loc_1800103A3
0x18001034e  lea     rdx, [rbp+57h+var_A0]
0x180010352  cmp     rdi, r8
0x180010355  jnz     short loc_180010366
0x180010357  mov     rcx, r8
0x18001035a  call    ??0?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(Microsoft::WRL::ComPtr<AppReadiness::ITask> &&)
0x18001035f  add     qword ptr [rsi+8], 8
0x180010364  jmp     short loc_1800103B3
0x180010366  mov     [rbp+57h+var_90], rsi
0x18001036a  lea     rcx, [rbp+57h+var_88]
0x18001036e  call    ??0?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(Microsoft::WRL::ComPtr<AppReadiness::ITask> &&)
0x180010373  lea     rdx, [r8-8]
0x180010377  mov     rcx, r8
0x18001037a  call    ??0?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(Microsoft::WRL::ComPtr<AppReadiness::ITask> &&)
0x18001037f  add     qword ptr [rsi+8], 8
0x180010384  mov     rcx, rdi
0x180010387  call    ??$_Move_backward_unchecked@PEAV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@PEAV123@@std@@YAPEAV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@PEAV123@00@Z; std::_Move_backward_unchecked<Microsoft::WRL::ComPtr<AppReadiness::User> *,Microsoft::WRL::ComPtr<AppReadiness::User> *>(Microsoft::WRL::ComPtr<AppReadiness::User> *,Microsoft::WRL::ComPtr<AppReadiness::User> *,Microsoft::WRL::ComPtr<AppReadiness::User> *)
0x18001038c  lea     rdx, [rbp+57h+var_88]
0x180010390  mov     rcx, rdi
0x180010393  call    ??4?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &&)
0x180010398  lea     rcx, [rbp+57h+var_88]
0x18001039c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800103a1  jmp     short loc_1800103B3
0x1800103a3  lea     r8, [rbp+57h+var_A0]
0x1800103a7  mov     rdx, rdi
0x1800103aa  mov     rcx, rsi
0x1800103ad  call    ??$_Emplace_reallocate@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@@?$vector@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@QEAV234@$$QEAV234@@Z; std::vector<Microsoft::WRL::ComPtr<AppReadiness::User>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<AppReadiness::User>>(Microsoft::WRL::ComPtr<AppReadiness::User> * const,Microsoft::WRL::ComPtr<AppReadiness::User> &&)
0x1800103b2  nop
0x1800103b3  mov     rcx, [rbp+57h+var_A0]
0x1800103b7  test    rcx, rcx
0x1800103ba  jz      short loc_1800103C9
0x1800103bc  mov     rax, [rcx]
0x1800103bf  mov     rax, [rax+10h]
0x1800103c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103c8  nop
0x1800103c9  jmp     short loc_1800103E1
0x1800103cb  mov     rcx, rbx
0x1800103ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800103d3  mov     rcx, rdi
0x1800103d6  call    ?InternalAddRef@?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(void)
0x1800103db  mov     rax, [rdi]
0x1800103de  mov     [rbx], rax
0x1800103e1  test    r12, r12
0x1800103e4  jz      short loc_1800103EF
0x1800103e6  mov     rcx, r12; SRWLock
0x1800103e9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800103ef  mov     rax, rbx
0x1800103f2  mov     rbx, [rsp+0D0h+arg_10]
0x1800103fa  add     rsp, 0A0h
0x180010401  pop     r15
0x180010403  pop     r14
0x180010405  pop     r13
0x180010407  pop     r12
0x180010409  pop     rdi
0x18001040a  pop     rsi
0x18001040b  pop     rbp
0x18001040c  retn
0x18001040d  mov     [rsp+0D0h+var_A8], 17Eh; int
0x180010415  lea     rcx, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001041c  mov     [rsp+0D0h+ReturnLength], rcx; char *
0x180010421  lea     r9, aAppreadinessSe_11; "AppReadiness::Service::CreateUser"
0x180010428  lea     r8, aMShuttingdown; "!m_shuttingDown"
0x18001042f  mov     edx, 8007139Fh; int
0x180010434  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180010438  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18001043d  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180010444  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180010448  call    _CxxThrowException_0
```
