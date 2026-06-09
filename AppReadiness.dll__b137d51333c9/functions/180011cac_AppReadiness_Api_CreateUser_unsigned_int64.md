# AppReadiness::Api::CreateUser(unsigned __int64)

- ea: `0x180011cac`
- end: `0x180012021`
- name: `?CreateUser@Api@AppReadiness@@AEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@_K@Z`
- size: `885`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `7`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180027fc0`
- `0x1800454f8`
- `0x1800459f8`
- `0x180045b14`
- `0x180045e04`
- `0x180045f74`
- `0x180047640`

## callees

- `0x180002958`
- `0x1800041e0`
- `0x18000b464`
- `0x18000c000`
- `0x18000d17c`
- `0x18000e4a0`
- `0x18001009c`
- `0x180011cac`
- `0x180012124`
- `0x180012610`
- `0x180012630`
- `0x180012784`
- `0x180027a4c`
- `0x18002c40c`
- `0x18003235c`
- `0x180035f14`
- `0x18003e210`
- `0x18003ecb4`
- `0x18003eec0`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fa6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011eba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011eba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011e0b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011e0b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011fef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fd1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180011d0b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180011d0b`

## string_xrefs

- `0x180011d2f`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180011d8e`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180011d42`: `InferUserContext(userContextToken, callingUser.GetAddressOf())`
- `0x180011d3b`: `AppReadiness::Api::CreateUser`
- `0x180011d9a`: `AppReadiness::Api::CreateUser`
- `0x180011da1`: `SHGetUserSid(callingUser.Get(), &userSid)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall AppReadiness::Api::CreateUser(__int64 a1, _QWORD *a2, __int64 a3)
{
  int CallingUserToken; // eax
  __int64 v6; // rsi
  int v7; // eax
  RTL_SRWLOCK *v8; // r13
  __int64 v9; // r8
  __int128 *p_pExceptionObject; // rdx
  _QWORD *Ptr; // r12
  _QWORD *i; // rdi
  __int64 v13; // rdi
  __int64 v14; // rax
  RTL_SRWLOCK *v15; // rcx
  int LastError; // eax
  void **v18; // [rsp+38h] [rbp-81h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-79h] BYREF
  RTL_SRWLOCK *v20; // [rsp+48h] [rbp-71h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-69h] BYREF
  __int64 v22; // [rsp+58h] [rbp-61h]
  __int64 v23; // [rsp+60h] [rbp-59h]
  _QWORD v24[2]; // [rsp+68h] [rbp-51h] BYREF
  __int64 (__fastcall *v25)(); // [rsp+78h] [rbp-41h] BYREF
  __int128 v26; // [rsp+88h] [rbp-31h] BYREF
  __int64 v27; // [rsp+98h] [rbp-21h]
  __int64 v28; // [rsp+A0h] [rbp-19h]
  _QWORD *v29; // [rsp+A8h] [rbp-11h]
  __int128 pExceptionObject; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v31; // [rsp+C0h] [rbp+7h]

  v29 = a2;
  v18 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  TokenHandle = 0;
  if ( a3 )
  {
    if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
      CallingUserToken = UMgrQueryUserToken(a3, &TokenHandle);
    else
      CallingUserToken = -2147467263;
  }
  else
  {
    CallingUserToken = AppReadiness::GetCallingUserToken(a1, &TokenHandle);
  }
  if ( CallingUserToken < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      CallingUserToken,
      "InferUserContext(userContextToken, callingUser.GetAddressOf())",
      "AppReadiness::Api::CreateUser",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      403);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  pv = 0;
  v6 = -1;
  v22 = -1;
  v23 = -1;
  v7 = SHGetUserSid(TokenHandle, (LPWSTR *)&pv);
  if ( v7 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      v7,
      "SHGetUserSid(callingUser.Get(), &userSid)",
      "AppReadiness::Api::CreateUser",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      406);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  v8 = (RTL_SRWLOCK *)AppReadiness::Service::Get();
  pExceptionObject = 0;
  v31 = 0;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)pv + v9) );
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject);
  *a2 = 0;
  AcquireSRWLockShared(v8 + 19);
  v20 = v8 + 19;
  v25 = AppReadiness::IsUserEqual;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  p_pExceptionObject = &pExceptionObject;
  if ( *((_QWORD *)&v31 + 1) > 7u )
    p_pExceptionObject = (__int128 *)pExceptionObject;
  std::wstring::_Construct<2,unsigned short const *>(&v26, p_pExceptionObject, v31);
  v24[0] = &v25;
  Ptr = v8[21].Ptr;
  for ( i = v8[20].Ptr; i != Ptr && !((unsigned __int8 (__fastcall *)(__int128 *, _QWORD *))v25)(&v26, i); ++i )
    ;
  std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(&v26);
  if ( i != v8[21].Ptr )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
    Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(i);
    *a2 = *i;
  }
  if ( v8 != (RTL_SRWLOCK *)-152LL )
    ReleaseSRWLockShared(v8 + 19);
  if ( *((_QWORD *)&v31 + 1) > 7u )
    std::_Deallocate<16>(pExceptionObject, 2LL * *((_QWORD *)&v31 + 1) + 2);
  if ( !*a2 )
  {
    v13 = AppReadiness::CreateUserTokenUsingWts(v24, &v18, a3);
    pExceptionObject = 0;
    v31 = 0;
    do
      ++v6;
    while ( *((_WORD *)pv + v6) );
    std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject);
    v14 = AppReadiness::Service::CreateUser(v8, &v20, &pExceptionObject, v13);
    Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(a2, v14);
    v15 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*((void (__fastcall **)(RTL_SRWLOCK *))v15->Ptr + 2))(v15);
    }
    if ( *((_QWORD *)&v31 + 1) > 7u )
      std::_Deallocate<16>(pExceptionObject, 2LL * *((_QWORD *)&v31 + 1) + 2);
    v24[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v24);
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v22 = 0;
  v23 = 0;
  v18 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( TokenHandle
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits>::InternalClose(&v18) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  return a2;
}

```

## disassembly

```asm
0x180011cac  mov     [rsp-8+arg_0], rbx
0x180011cb1  push    rbp
0x180011cb2  push    rsi
0x180011cb3  push    rdi
0x180011cb4  push    r12
0x180011cb6  push    r13
0x180011cb8  push    r14
0x180011cba  push    r15
0x180011cbc  lea     rbp, [rsp-27h]
0x180011cc1  sub     rsp, 0E0h
0x180011cc8  mov     rax, cs:__security_cookie
0x180011ccf  xor     rax, rsp
0x180011cd2  mov     [rbp+57h+var_38], rax
0x180011cd6  mov     r14, r8
0x180011cd9  mov     rbx, rdx
0x180011cdc  mov     [rbp+57h+var_68], rdx
0x180011ce0  xor     edi, edi
0x180011ce2  mov     [rsp+110h+var_E0], edi
0x180011ce6  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180011ced  mov     [rsp+110h+var_D8], rax
0x180011cf2  mov     [rbp+57h+TokenHandle], rdi
0x180011cf6  test    r8, r8
0x180011cf9  jz      short loc_180011D1A
0x180011cfb  call    IsUMgrEnumerateSessionUsersPresent
0x180011d00  test    al, al
0x180011d02  jz      short loc_180011D13
0x180011d04  lea     rdx, [rbp+57h+TokenHandle]
0x180011d08  mov     rcx, r14
0x180011d0b  call    cs:__imp_UMgrQueryUserToken
0x180011d11  jmp     short loc_180011D23
0x180011d13  mov     eax, 80004001h
0x180011d18  jmp     short loc_180011D23
0x180011d1a  lea     rdx, [rbp+57h+TokenHandle]
0x180011d1e  call    AppReadiness__GetCallingUserToken
0x180011d23  test    eax, eax
0x180011d25  jns     short loc_180011D65
0x180011d27  mov     [rsp+110h+var_E8], 193h; int
0x180011d2f  lea     rcx, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180011d36  mov     [rsp+110h+var_F0], rcx; char *
0x180011d3b  lea     r9, aAppreadinessAp; "AppReadiness::Api::CreateUser"
0x180011d42  lea     r8, aInferuserconte; "InferUserContext(userContextToken, call"...
0x180011d49  mov     edx, eax; int
0x180011d4b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180011d4f  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180011d54  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180011d5b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180011d5f  call    _CxxThrowException_0
0x180011d65  mov     [rbp+57h+pv], rdi
0x180011d69  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180011d6d  mov     [rbp+57h+var_B8], rsi
0x180011d71  mov     [rbp+57h+var_B0], rsi
0x180011d75  lea     rdx, [rbp+57h+pv]; StringSid
0x180011d79  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180011d7d  call    SHGetUserSid
0x180011d82  test    eax, eax
0x180011d84  jns     short loc_180011DC4
0x180011d86  mov     [rsp+110h+var_E8], 196h; int
0x180011d8e  lea     rcx, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180011d95  mov     [rsp+110h+var_F0], rcx; char *
0x180011d9a  lea     r9, aAppreadinessAp; "AppReadiness::Api::CreateUser"
0x180011da1  lea     r8, aShgetusersidCa; "SHGetUserSid(callingUser.Get(), &userSi"...
0x180011da8  mov     edx, eax; int
0x180011daa  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180011dae  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180011db3  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180011dba  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180011dbe  call    _CxxThrowException_0
0x180011dc4  call    ?Get@Service@AppReadiness@@SAAEAV12@XZ; AppReadiness::Service::Get(void)
0x180011dc9  mov     r13, rax
0x180011dcc  mov     rdx, [rbp+57h+pv]
0x180011dd0  xorps   xmm0, xmm0
0x180011dd3  movups  [rbp+57h+pExceptionObject], xmm0
0x180011dd7  xorps   xmm1, xmm1
0x180011dda  movdqu  [rbp+57h+var_50], xmm1
0x180011ddf  mov     r8, rsi
0x180011de2  inc     r8
0x180011de5  cmp     [rdx+r8*2], di
0x180011dea  jnz     short loc_180011DE2
0x180011dec  lea     rcx, [rbp+57h+pExceptionObject]
0x180011df0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011df5  nop
0x180011df6  mov     [rbx], rdi
0x180011df9  mov     [rsp+110h+var_E0], 2
0x180011e01  lea     r15, [r13+98h]
0x180011e08  mov     rcx, r15; SRWLock
0x180011e0b  call    cs:__imp_AcquireSRWLockShared
0x180011e11  mov     [rbp+57h+var_C8], r15
0x180011e15  lea     rax, AppReadiness__IsUserEqual
0x180011e1c  mov     [rbp+57h+var_98], rax
0x180011e20  xorps   xmm0, xmm0
0x180011e23  movups  [rbp+57h+var_88], xmm0
0x180011e27  mov     [rbp+57h+var_78], rdi
0x180011e2b  mov     [rbp+57h+var_70], rdi
0x180011e2f  lea     rdx, [rbp+57h+pExceptionObject]
0x180011e33  cmp     qword ptr [rbp+57h+var_50+8], 7
0x180011e38  cmova   rdx, qword ptr [rbp+57h+pExceptionObject]
0x180011e3d  mov     r8, qword ptr [rbp+57h+var_50]
0x180011e41  lea     rcx, [rbp+57h+var_88]
0x180011e45  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180011e4a  mov     [rsp+110h+var_E0], 6
0x180011e52  lea     rax, [rbp+57h+var_98]
0x180011e56  mov     [rbp+57h+var_A8], rax
0x180011e5a  mov     r12, [r13+0A8h]
0x180011e61  mov     rdi, [r13+0A0h]
0x180011e68  jmp     short loc_180011E82
0x180011e6a  mov     rdx, rdi
0x180011e6d  lea     rcx, [rbp+57h+var_88]
0x180011e71  mov     rax, [rbp+57h+var_98]
0x180011e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e7a  test    al, al
0x180011e7c  jnz     short loc_180011E87
0x180011e7e  add     rdi, 8
0x180011e82  cmp     rdi, r12
0x180011e85  jnz     short loc_180011E6A
0x180011e87  lea     rcx, [rbp+57h+var_88]
0x180011e8b  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x180011e90  cmp     rdi, [r13+0A8h]
0x180011e97  jz      short loc_180011EAF
0x180011e99  mov     rcx, rbx
0x180011e9c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011ea1  mov     rcx, rdi
0x180011ea4  call    ?InternalAddRef@?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(void)
0x180011ea9  mov     rax, [rdi]
0x180011eac  mov     [rbx], rax
0x180011eaf  xor     r12d, r12d
0x180011eb2  test    r15, r15
0x180011eb5  jz      short loc_180011EC1
0x180011eb7  mov     rcx, r15; SRWLock
0x180011eba  call    cs:__imp_ReleaseSRWLockShared
0x180011ec0  nop
0x180011ec1  mov     [rsp+110h+var_E0], 5
0x180011ec9  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x180011ecd  cmp     rdx, 7
0x180011ed1  jbe     short loc_180011EE4
0x180011ed3  lea     rdx, ds:2[rdx*2]
0x180011edb  mov     rcx, qword ptr [rbp+57h+pExceptionObject]
0x180011edf  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011ee4  cmp     [rbx], r12
0x180011ee7  jnz     loc_180011F96
0x180011eed  mov     r8, r14
0x180011ef0  lea     rdx, [rsp+110h+var_D8]
0x180011ef5  lea     rcx, [rbp+57h+var_A8]
0x180011ef9  call    AppReadiness__CreateUserTokenUsingWts
0x180011efe  mov     rdi, rax
0x180011f01  mov     rdx, [rbp+57h+pv]
0x180011f05  xorps   xmm0, xmm0
0x180011f08  movups  [rbp+57h+pExceptionObject], xmm0
0x180011f0c  xorps   xmm1, xmm1
0x180011f0f  movdqu  [rbp+57h+var_50], xmm1
0x180011f14  inc     rsi
0x180011f17  cmp     [rdx+rsi*2], r12w
0x180011f1c  jnz     short loc_180011F14
0x180011f1e  mov     r8, rsi
0x180011f21  lea     rcx, [rbp+57h+pExceptionObject]
0x180011f25  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011f2a  nop
0x180011f2b  mov     r9, rdi
0x180011f2e  lea     r8, [rbp+57h+pExceptionObject]
0x180011f32  lea     rdx, [rbp+57h+var_C8]
0x180011f36  mov     rcx, r13
0x180011f39  call    ?CreateUser@Service@AppReadiness@@QEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@45@@Z; AppReadiness::Service::CreateUser(std::wstring const &,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180011f3e  mov     rdx, rax
0x180011f41  mov     rcx, rbx
0x180011f44  call    ??4?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &&)
0x180011f49  nop
0x180011f4a  mov     rcx, [rbp+57h+var_C8]
0x180011f4e  test    rcx, rcx
0x180011f51  jz      short loc_180011F64
0x180011f53  mov     [rbp+57h+var_C8], r12
0x180011f57  mov     rax, [rcx]
0x180011f5a  mov     rax, [rax+10h]
0x180011f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f63  nop
0x180011f64  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x180011f68  cmp     rdx, 7
0x180011f6c  jbe     short loc_180011F80
0x180011f6e  lea     rdx, ds:2[rdx*2]
0x180011f76  mov     rcx, qword ptr [rbp+57h+pExceptionObject]
0x180011f7a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011f7f  nop
0x180011f80  lea     rdi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180011f87  mov     [rbp+57h+var_A8], rdi
0x180011f8b  lea     rcx, [rbp+57h+var_A8]
0x180011f8f  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180011f94  jmp     short loc_180011F9D
0x180011f96  lea     rdi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180011f9d  mov     rcx, [rbp+57h+pv]; pv
0x180011fa1  test    rcx, rcx
0x180011fa4  jz      short loc_180011FB0
0x180011fa6  call    cs:__imp_CoTaskMemFree
0x180011fac  mov     [rbp+57h+pv], r12
0x180011fb0  mov     [rbp+57h+var_B8], r12
0x180011fb4  mov     [rbp+57h+var_B0], r12
0x180011fb8  mov     [rsp+110h+var_D8], rdi
0x180011fbd  cmp     [rbp+57h+TokenHandle], r12
0x180011fc1  jz      short loc_180011FF6
0x180011fc3  lea     rcx, [rsp+110h+var_D8]
0x180011fc8  call    ?InternalClose@?$HandleT@USemaphoreTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits>::InternalClose(void)
0x180011fcd  test    al, al
0x180011fcf  jnz     short loc_180011FF6
0x180011fd1  call    cs:__imp_GetLastError
0x180011fd7  test    eax, eax
0x180011fd9  jle     short loc_180011FE3
0x180011fdb  movzx   eax, ax
0x180011fde  or      eax, 80070000h
0x180011fe3  xor     r9d, r9d; lpArguments
0x180011fe6  xor     r8d, r8d; nNumberOfArguments
0x180011fe9  lea     edx, [r9+1]; dwExceptionFlags
0x180011fed  mov     ecx, eax; dwExceptionCode
0x180011fef  call    cs:__imp_RaiseException
0x180011ff5  int     3; Trap to Debugger
0x180011ff6  mov     rax, rbx
0x180011ff9  mov     rcx, [rbp+57h+var_38]
0x180011ffd  xor     rcx, rsp; StackCookie
0x180012000  call    __security_check_cookie
0x180012005  mov     rbx, [rsp+110h+arg_0]
0x18001200d  add     rsp, 0E0h
0x180012014  pop     r15
0x180012016  pop     r14
0x180012018  pop     r13
0x18001201a  pop     r12
0x18001201c  pop     rdi
0x18001201d  pop     rsi
0x18001201e  pop     rbp
0x18001201f  retn
```
