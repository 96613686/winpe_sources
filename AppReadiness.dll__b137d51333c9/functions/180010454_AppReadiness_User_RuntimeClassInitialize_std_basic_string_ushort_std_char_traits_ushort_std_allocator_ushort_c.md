# AppReadiness::User::RuntimeClassInitialize(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)

- ea: `0x180010454`
- end: `0x1800109d6`
- name: `?RuntimeClassInitialize@User@AppReadiness@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z`
- size: `1410`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001009c`
- `0x180037a10`

## callees

- `0x1800041e0`
- `0x18000426c`
- `0x180009d80`
- `0x180010454`
- `0x18001c718`
- `0x18001caa0`
- `0x18001e95c`
- `0x180021bd4`
- `0x180022ae0`
- `0x18002404c`
- `0x1800246e8`
- `0x1800249b4`
- `0x180027a4c`
- `0x18002eecc`
- `0x180030914`
- `0x18003235c`
- `0x180038d88`
- `0x18003e210`
- `0x18003ecb4`
- `0x1800473d8`
- `0x180049310`
- `0x18005f8a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800105ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800105ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001080f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001080f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180010545`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180010545`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800107da`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800107da`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180010636`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800106d0`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180010636`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800106d0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800107c3`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800107c3`
- `samcli!NetUserGetInfo` at `0x18001085f`
- `samcli!NetUserGetInfo` at `0x18001085f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180010961`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180010961`

## string_xrefs

- `0x1800104ed`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180010560`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x1800105f1`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18001068f`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18001071b`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18001099c`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180010981`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x1800104f9`: `AppReadiness::User::RuntimeClassInitialize`
- `0x18001056c`: `AppReadiness::User::RuntimeClassInitialize`
- `0x1800105fd`: `AppReadiness::User::RuntimeClassInitialize`
- `0x18001069b`: `AppReadiness::User::RuntimeClassInitialize`
- `0x180010727`: `AppReadiness::User::RuntimeClassInitialize`
- `0x180010573`: `ResultFromWin32Bool(DuplicateTokenEx(userToken.Get(), TOKEN_IMPERSONATE|TOKEN_DUPLICATE|TOKEN_QUERY, nullptr, SecurityImpersonation, TokenImpersonation, m_userToken.GetAddressOf()))`
- `0x1800106a2`: `m_taskGate.IsValid()`
- `0x180010604`: `m_runningTasksEvent.IsValid()`
- `0x18001072e`: `m_futureTaskGate.IsValid()`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppReadiness::User::RuntimeClassInitialize(
        AppReadiness::User *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned __int16 *v7; // rsi
  int IsFSLogixUser; // eax
  int Error; // eax
  HANDLE Event; // rbx
  int v11; // eax
  int v12; // eax
  int v13; // edx
  DWORD v14; // r8d
  int v15; // eax
  unsigned __int16 *v16; // rdx
  DWORD Info; // eax
  LPBYTE v18; // rdx
  WCHAR *v19; // rdx
  _QWORD *v20; // rbx
  int v21; // r8d
  const char *v22; // rax
  PSID *v23; // rdi
  int v24; // ebx
  WCHAR *TokenType; // [rsp+20h] [rbp-E0h]
  int TokenTypea; // [rsp+20h] [rbp-E0h]
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nSize[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-ACh] BYREF
  LPBYTE bufptr; // [rsp+58h] [rbp-A8h] BYREF
  LPBYTE v33; // [rsp+60h] [rbp-A0h] BYREF
  PSID *v34; // [rsp+68h] [rbp-98h] BYREF
  HANDLE SemaphoreW; // [rsp+70h] [rbp-90h] BYREF
  char v36; // [rsp+78h] [rbp-88h]
  unsigned __int64 v37; // [rsp+80h] [rbp-80h]
  WCHAR pExceptionObject[20]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ReferencedDomainName[16]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Name[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v41[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  v7 = (unsigned __int16 *)((char *)this + 64);
  std::wstring::operator=((char *)this + 64, a2);
  *((_QWORD *)this + 12) = a3;
  AppReadiness::User::GetWellKnownSid(&v34, 22);
  *((_BYTE *)this + 176) = AppReadiness::User::IsUser(this, &v34);
  if ( v37 > 7 )
    std::_Deallocate<16>(v34, 2 * v37 + 2);
  IsFSLogixUser = AppReadiness::User::SetIsFSLogixUser(this);
  if ( IsFSLogixUser < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      IsFSLogixUser,
      "SetIsFSLogixUser()",
      "AppReadiness::User::RuntimeClassInitialize",
      "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
      101);
    throw (Windows::HResultException *)pExceptionObject;
  }
  if ( !DuplicateTokenEx(*(HANDLE *)(a4 + 8), 0xEu, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)this + 14) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        Error,
        "ResultFromWin32Bool(DuplicateTokenEx(userToken.Get(), TOKEN_IMPERSONATE|TOKEN_DUPLICATE|TOKEN_QUERY, nullptr, Se"
        "curityImpersonation, TokenImpersonation, m_userToken.GetAddressOf()))",
        "AppReadiness::User::RuntimeClassInitialize",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        102);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  *((_BYTE *)this + 177) = AppReadiness::User::IsMemberOfDefaultSystemManagedGroup((char *)this + 104);
  Event = CreateEventExW(0, 0, 3u, 0x100002u);
  if ( Event == *((HANDLE *)this + 30) )
  {
    Event = (HANDLE)*((_QWORD *)this + 30);
  }
  else
  {
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close((char *)this + 232);
    *((_QWORD *)this + 30) = Event;
  }
  if ( !Event )
  {
    v11 = ResultFromKnownLastError();
    if ( v11 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v11,
        "m_runningTasksEvent.IsValid()",
        "AppReadiness::User::RuntimeClassInitialize",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        105);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  SemaphoreW = CreateSemaphoreW(0, 1, 1, 0);
  v34 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::Semaphore::operator=((char *)this + 144, &v34);
  v34 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v34);
  if ( !*((_QWORD *)this + 19) )
  {
    v12 = ResultFromKnownLastError();
    if ( v12 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v12,
        "m_taskGate.IsValid()",
        "AppReadiness::User::RuntimeClassInitialize",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        108);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  SemaphoreW = CreateSemaphoreW(0, 1, 1, 0);
  v34 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::Semaphore::operator=((char *)this + 160, &v34);
  v34 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v34);
  if ( !*((_QWORD *)this + 21) )
  {
    v15 = ResultFromKnownLastError();
    if ( v15 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v15,
        "m_futureTaskGate.IsValid()",
        "AppReadiness::User::RuntimeClassInitialize",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        111);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  *(_QWORD *)nSize = 0;
  if ( SHQueryToken<_TOKEN_USER>(*((HANDLE *)this + 14), v13, v14, nSize) >= 0 )
  {
    v34 = *(PSID **)nSize;
    cchName = 260;
    cchReferencedDomainName = 16;
    nSize[0] = 16;
    peUse = 0;
    if ( LookupAccountSidW(0, *v34, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse)
      && GetComputerNameW(pExceptionObject, nSize)
      && peUse == SidTypeUser )
    {
      if ( !*((_BYTE *)this + 176) || CompareStringOrdinal(pExceptionObject, -1, ReferencedDomainName, -1, 1) == 2 )
      {
        bufptr = 0;
        Info = NetUserGetInfo(0, Name, 0x18u, &bufptr);
        v18 = bufptr;
        v33 = bufptr;
        if ( Info || !*(_DWORD *)bufptr )
        {
          v19 = Name;
        }
        else
        {
          *((_BYTE *)this + 218) = 1;
          v19 = (WCHAR *)*((_QWORD *)v18 + 2);
        }
        std::wstring::assign((char *)this + 184, v19);
        std::unique_ptr<_USER_INFO_24,LocalMem_Deleter<_USER_INFO_24>>::~unique_ptr<_USER_INFO_24,LocalMem_Deleter<_USER_INFO_24>>(&v33);
        v20 = (_QWORD *)((char *)this + 184);
        goto LABEL_36;
      }
      TokenType = ReferencedDomainName;
      StringCchPrintfW(v41, 0x104u, L"%ls\\%ls", Name);
      v16 = v41;
    }
    else
    {
      if ( *((_QWORD *)v7 + 3) > 7u )
        v7 = *(unsigned __int16 **)v7;
      v16 = v7;
    }
    v20 = (_QWORD *)((char *)this + 184);
    std::wstring::assign((char *)this + 184, v16);
LABEL_36:
    std::unique_ptr<_USER_INFO_24,LocalMem_Deleter<_USER_INFO_24>>::~unique_ptr<_USER_INFO_24,LocalMem_Deleter<_USER_INFO_24>>(&v34);
    goto LABEL_40;
  }
  if ( *((_QWORD *)v7 + 3) > 7u )
    v7 = *(unsigned __int16 **)v7;
  v20 = (_QWORD *)((char *)this + 184);
  std::wstring::assign((char *)this + 184, v7);
LABEL_40:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v22 = "is";
    if ( !*((_BYTE *)this + 218) )
      v22 = "is not";
    if ( v20[3] > 7u )
      v20 = (_QWORD *)*v20;
    WPP_SF_Ss(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)"is not", v21, (_DWORD)v20, (__int64)v22);
  }
  v23 = (PSID *)((char *)this + 440);
  if ( !*v23 )
  {
    v34 = v23;
    SemaphoreW = 0;
    v36 = 1;
    v24 = SRCacheManager_Open(0, &SemaphoreW);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v34);
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
        (const char *)(unsigned int)v24,
        (int)TokenType);
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        (const char *)(unsigned int)v24,
        TokenTypea);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180010454  mov     [rsp-8+arg_10], rbx
0x180010459  push    rbp
0x18001045a  push    rsi
0x18001045b  push    rdi
0x18001045c  push    r13
0x18001045e  push    r14
0x180010460  lea     rbp, [rsp-400h]
0x180010468  sub     rsp, 500h
0x18001046f  mov     rax, cs:__security_cookie
0x180010476  xor     rax, rsp
0x180010479  mov     [rbp+420h+var_30], rax
0x180010480  mov     r14, r9
0x180010483  mov     rbx, r8
0x180010486  mov     rdi, rcx
0x180010489  lea     rsi, [rcx+40h]
0x18001048d  mov     rcx, rsi
0x180010490  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180010495  mov     [rdi+60h], rbx
0x180010499  xor     r8d, r8d
0x18001049c  lea     edx, [r8+16h]
0x1800104a0  lea     rcx, [rsp+520h+var_4B8]
0x1800104a5  call    ?GetWellKnownSid@User@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; AppReadiness::User::GetWellKnownSid(WELL_KNOWN_SID_TYPE,void *)
0x1800104aa  lea     rdx, [rsp+520h+var_4B8]
0x1800104af  mov     rcx, rdi
0x1800104b2  call    ?IsUser@User@AppReadiness@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppReadiness::User::IsUser(std::wstring const &)
0x1800104b7  mov     [rdi+0B0h], al
0x1800104bd  mov     rdx, [rbp+420h+var_4A0]
0x1800104c1  cmp     rdx, 7
0x1800104c5  jbe     short loc_1800104D9
0x1800104c7  lea     rdx, ds:2[rdx*2]
0x1800104cf  mov     rcx, [rsp+520h+var_4B8]
0x1800104d4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800104d9  mov     rcx, rdi; this
0x1800104dc  call    ?SetIsFSLogixUser@User@AppReadiness@@IEAAJXZ; AppReadiness::User::SetIsFSLogixUser(void)
0x1800104e1  test    eax, eax
0x1800104e3  jns     short loc_180010523
0x1800104e5  mov     dword ptr [rsp+520h+phNewToken], 65h ; 'e'; int
0x1800104ed  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800104f4  mov     qword ptr [rsp+520h+TokenType], r8; char *
0x1800104f9  lea     r9, aAppreadinessUs_7; "AppReadiness::User::RuntimeClassInitial"...
0x180010500  lea     r8, aSetisfslogixus; "SetIsFSLogixUser()"
0x180010507  mov     edx, eax; int
0x180010509  lea     rcx, [rbp+420h+pExceptionObject]; this
0x18001050d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180010512  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180010519  lea     rcx, [rbp+420h+pExceptionObject]; pExceptionObject
0x18001051d  call    _CxxThrowException_0
0x180010523  lea     rax, [rdi+70h]
0x180010527  mov     [rsp+520h+phNewToken], rax; phNewToken
0x18001052c  mov     [rsp+520h+TokenType], 2; TokenType
0x180010534  mov     r9d, 2; ImpersonationLevel
0x18001053a  xor     r8d, r8d; lpTokenAttributes
0x18001053d  lea     edx, [r9+0Ch]; dwDesiredAccess
0x180010541  mov     rcx, [r14+8]; hExistingToken
0x180010545  call    cs:__imp_DuplicateTokenEx
0x18001054b  test    eax, eax
0x18001054d  jnz     short loc_180010596
0x18001054f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180010554  test    eax, eax
0x180010556  jns     short loc_180010596
0x180010558  mov     dword ptr [rsp+520h+phNewToken], 66h ; 'f'; int
0x180010560  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180010567  mov     qword ptr [rsp+520h+TokenType], r8; char *
0x18001056c  lea     r9, aAppreadinessUs_7; "AppReadiness::User::RuntimeClassInitial"...
0x180010573  lea     r8, aResultfromwin3_3; "ResultFromWin32Bool(DuplicateTokenEx(us"...
0x18001057a  mov     edx, eax; int
0x18001057c  lea     rcx, [rbp+420h+pExceptionObject]; this
0x180010580  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180010585  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18001058c  lea     rcx, [rbp+420h+pExceptionObject]; pExceptionObject
0x180010590  call    _CxxThrowException_0
0x180010596  lea     rcx, [rdi+68h]
0x18001059a  call    ?IsMemberOfDefaultSystemManagedGroup@User@AppReadiness@@KA_NAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; AppReadiness::User::IsMemberOfDefaultSystemManagedGroup(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x18001059f  mov     [rdi+0B1h], al
0x1800105a5  lea     r14, [rdi+0E8h]
0x1800105ac  xor     edx, edx; lpName
0x1800105ae  xor     ecx, ecx; lpEventAttributes
0x1800105b0  mov     r9d, 100002h; dwDesiredAccess
0x1800105b6  lea     r8d, [rdx+3]; dwFlags
0x1800105ba  call    cs:__imp_CreateEventExW
0x1800105c0  mov     rbx, rax
0x1800105c3  cmp     rax, [r14+8]
0x1800105c7  jz      short loc_1800105D7
0x1800105c9  mov     rcx, r14
0x1800105cc  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x1800105d1  mov     [r14+8], rbx
0x1800105d5  jmp     short loc_1800105DB
0x1800105d7  mov     rbx, [r14+8]
0x1800105db  test    rbx, rbx
0x1800105de  jnz     short loc_180010627
0x1800105e0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800105e5  test    eax, eax
0x1800105e7  jns     short loc_180010627
0x1800105e9  mov     dword ptr [rsp+520h+phNewToken], 69h ; 'i'; int
0x1800105f1  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800105f8  mov     qword ptr [rsp+520h+TokenType], r8; char *
0x1800105fd  lea     r9, aAppreadinessUs_7; "AppReadiness::User::RuntimeClassInitial"...
0x180010604  lea     r8, aMRunningtaskse; "m_runningTasksEvent.IsValid()"
0x18001060b  mov     edx, eax; int
0x18001060d  lea     rcx, [rbp+420h+pExceptionObject]; this
0x180010611  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180010616  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18001061d  lea     rcx, [rbp+420h+pExceptionObject]; pExceptionObject
0x180010621  call    _CxxThrowException_0
0x180010627  xor     r9d, r9d; lpName
0x18001062a  lea     r14d, [r9+1]
0x18001062e  mov     r8d, r14d; lMaximumCount
0x180010631  mov     edx, r14d; lInitialCount
0x180010634  xor     ecx, ecx; lpSemaphoreAttributes
0x180010636  call    cs:__imp_CreateSemaphoreW
0x18001063c  mov     [rsp+520h+var_4B0], rax
0x180010641  lea     rbx, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180010648  mov     [rsp+520h+var_4B8], rbx
0x18001064d  lea     rcx, [rdi+90h]
0x180010654  lea     rdx, [rsp+520h+var_4B8]
0x180010659  call    ??4Semaphore@Wrappers@WRL@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z; Microsoft::WRL::Wrappers::Semaphore::operator=(Microsoft::WRL::Wrappers::Semaphore &&)
0x18001065e  lea     r13, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180010665  mov     [rsp+520h+var_4B8], r13
0x18001066a  lea     rcx, [rsp+520h+var_4B8]
0x18001066f  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180010674  cmp     qword ptr [rdi+98h], 0
0x18001067c  jnz     short loc_1800106C5
0x18001067e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180010683  test    eax, eax
0x180010685  jns     short loc_1800106C5
0x180010687  mov     dword ptr [rsp+520h+phNewToken], 6Ch ; 'l'; int
0x18001068f  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180010696  mov     qword ptr [rsp+520h+TokenType], r8; char *
0x18001069b  lea     r9, aAppreadinessUs_7; "AppReadiness::User::RuntimeClassInitial"...
0x1800106a2  lea     r8, aMTaskgateIsval; "m_taskGate.IsValid()"
0x1800106a9  mov     edx, eax; int
0x1800106ab  lea     rcx, [rbp+420h+pExceptionObject]; this
0x1800106af  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800106b4  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800106bb  lea     rcx, [rbp+420h+pExceptionObject]; pExceptionObject
0x1800106bf  call    _CxxThrowException_0
0x1800106c5  xor     r9d, r9d; lpName
0x1800106c8  mov     r8d, r14d; lMaximumCount
0x1800106cb  mov     edx, r14d; lInitialCount
0x1800106ce  xor     ecx, ecx; lpSemaphoreAttributes
0x1800106d0  call    cs:__imp_CreateSemaphoreW
0x1800106d6  mov     [rsp+520h+var_4B0], rax
0x1800106db  mov     [rsp+520h+var_4B8], rbx
0x1800106e0  lea     rcx, [rdi+0A0h]
0x1800106e7  lea     rdx, [rsp+520h+var_4B8]
0x1800106ec  call    ??4Semaphore@Wrappers@WRL@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z; Microsoft::WRL::Wrappers::Semaphore::operator=(Microsoft::WRL::Wrappers::Semaphore &&)
0x1800106f1  mov     [rsp+520h+var_4B8], r13
0x1800106f6  lea     rcx, [rsp+520h+var_4B8]
0x1800106fb  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180010700  cmp     qword ptr [rdi+0A8h], 0
0x180010708  jnz     short loc_180010751
0x18001070a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001070f  test    eax, eax
0x180010711  jns     short loc_180010751
0x180010713  mov     dword ptr [rsp+520h+phNewToken], 6Fh ; 'o'; int
0x18001071b  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180010722  mov     qword ptr [rsp+520h+TokenType], r8; char *
0x180010727  lea     r9, aAppreadinessUs_7; "AppReadiness::User::RuntimeClassInitial"...
0x18001072e  lea     r8, aMFuturetaskgat; "m_futureTaskGate.IsValid()"
0x180010735  mov     edx, eax; int
0x180010737  lea     rcx, [rbp+420h+pExceptionObject]; this
0x18001073b  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180010740  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180010747  lea     rcx, [rbp+420h+pExceptionObject]; pExceptionObject
0x18001074b  call    _CxxThrowException_0
0x180010751  mov     qword ptr [rsp+520h+nSize], 0
0x18001075a  lea     r9, [rsp+520h+nSize]
0x18001075f  mov     rcx, [rdi+70h]; TokenHandle
0x180010763  call    ??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z; SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)
0x180010768  test    eax, eax
0x18001076a  js      loc_1800108D1
0x180010770  mov     rdx, qword ptr [rsp+520h+nSize]
0x180010775  mov     [rsp+520h+var_4B8], rdx
0x18001077a  mov     ebx, 104h
0x18001077f  mov     [rsp+520h+cchName], ebx
0x180010783  mov     eax, 10h
0x180010788  mov     [rsp+520h+cchReferencedDomainName], eax
0x18001078c  mov     [rsp+520h+nSize], eax
0x180010790  mov     [rsp+520h+var_4E0], 0
0x180010798  lea     rax, [rsp+520h+var_4E0]
0x18001079d  mov     [rsp+520h+peUse], rax; peUse
0x1800107a2  lea     rax, [rsp+520h+cchReferencedDomainName]
0x1800107a7  mov     [rsp+520h+phNewToken], rax; cchReferencedDomainName
0x1800107ac  lea     rax, [rbp+420h+ReferencedDomainName]
0x1800107b0  mov     qword ptr [rsp+520h+TokenType], rax; ReferencedDomainName
0x1800107b5  lea     r9, [rsp+520h+cchName]; cchName
0x1800107ba  lea     r8, [rbp+420h+Name]; Name
0x1800107be  mov     rdx, [rdx]; Sid
0x1800107c1  xor     ecx, ecx; lpSystemName
0x1800107c3  call    cs:__imp_LookupAccountSidW
0x1800107c9  test    eax, eax
0x1800107cb  jz      loc_1800108A8
0x1800107d1  lea     rdx, [rsp+520h+nSize]; nSize
0x1800107d6  lea     rcx, [rbp+420h+pExceptionObject]; lpBuffer
0x1800107da  call    cs:__imp_GetComputerNameW
0x1800107e0  test    eax, eax
0x1800107e2  jz      loc_1800108A8
0x1800107e8  cmp     [rsp+520h+var_4E0], r14d
0x1800107ed  jnz     loc_1800108A8
0x1800107f3  cmp     byte ptr [rdi+0B0h], 0
0x1800107fa  jz      short loc_180010845
0x1800107fc  mov     [rsp+520h+TokenType], r14d; bIgnoreCase
0x180010801  or      edx, 0FFFFFFFFh; cchCount1
0x180010804  mov     r9d, edx; cchCount2
0x180010807  lea     r8, [rbp+420h+ReferencedDomainName]; lpString2
0x18001080b  lea     rcx, [rbp+420h+pExceptionObject]; lpString1
0x18001080f  call    cs:__imp_CompareStringOrdinal
0x180010815  cmp     eax, 2
0x180010818  jz      short loc_180010845
0x18001081a  lea     rax, [rbp+420h+ReferencedDomainName]
0x18001081e  mov     qword ptr [rsp+520h+TokenType], rax
0x180010823  lea     r9, [rbp+420h+Name]
0x180010827  lea     r8, aLsLs; "%ls\\%ls"
0x18001082e  mov     edx, ebx; unsigned __int64
0x180010830  lea     rcx, [rbp+420h+var_240]; unsigned __int16 *
0x180010837  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001083c  lea     rdx, [rbp+420h+var_240]
0x180010843  jmp     short loc_1800108B5
0x180010845  mov     [rsp+520h+bufptr], 0
0x18001084e  lea     r9, [rsp+520h+bufptr]; bufptr
0x180010853  mov     r8d, 18h; level
0x180010859  lea     rdx, [rbp+420h+Name]; username
0x18001085d  xor     ecx, ecx; servername
0x18001085f  call    cs:__imp_NetUserGetInfo
0x180010865  mov     rdx, [rsp+520h+bufptr]
0x18001086a  mov     [rsp+520h+var_4C0], rdx
0x18001086f  test    eax, eax
0x180010871  jnz     short loc_180010884
0x180010873  cmp     [rdx], eax
0x180010875  jz      short loc_180010884
0x180010877  mov     [rdi+0DAh], r14b
0x18001087e  mov     rdx, [rdx+10h]
0x180010882  jmp     short loc_180010888
0x180010884  lea     rdx, [rbp+420h+Name]
0x180010888  lea     rcx, [rdi+0B8h]
0x18001088f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180010894  nop
0x180010895  lea     rcx, [rsp+520h+var_4C0]
0x18001089a  call    ??1?$unique_ptr@U_USER_INFO_24@@U?$LocalMem_Deleter@U_USER_INFO_24@@@@@std@@QEAA@XZ; std::unique_ptr<_USER_INFO_24,LocalMem_Deleter<_USER_INFO_24>>::~unique_ptr<_USER_INFO_24,LocalMem_Deleter<_USER_INFO_24>>(void)
0x18001089f  lea     rbx, [rdi+0B8h]
0x1800108a6  jmp     short loc_1800108C5
0x1800108a8  cmp     qword ptr [rsi+18h], 7
0x1800108ad  jbe     short loc_1800108B2
0x1800108af  mov     rsi, [rsi]
0x1800108b2  mov     rdx, rsi
0x1800108b5  lea     rbx, [rdi+0B8h]
0x1800108bc  mov     rcx, rbx
0x1800108bf  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800108c4  nop
0x1800108c5  lea     rcx, [rsp+520h+var_4B8]
0x1800108ca  call    ??1?$unique_ptr@U_USER_INFO_24@@U?$LocalMem_Deleter@U_USER_INFO_24@@@@@std@@QEAA@XZ; std::unique_ptr<_USER_INFO_24,LocalMem_Deleter<_USER_INFO_24>>::~unique_ptr<_USER_INFO_24,LocalMem_Deleter<_USER_INFO_24>>(void)
0x1800108cf  jmp     short loc_1800108ED
0x1800108d1  cmp     qword ptr [rsi+18h], 7
0x1800108d6  jbe     short loc_1800108DB
0x1800108d8  mov     rsi, [rsi]
0x1800108db  lea     rbx, [rdi+0B8h]
0x1800108e2  mov     rdx, rsi
0x1800108e5  mov     rcx, rbx
0x1800108e8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800108ed  lea     rax, WPP_GLOBAL_Control
0x1800108f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108fb  cmp     rcx, rax
0x1800108fe  jz      short loc_18001093A
0x180010900  test    byte ptr [rcx+1Ch], 4
0x180010904  jz      short loc_18001093A
0x180010906  lea     rdx, aIsNot; "is not"
0x18001090d  lea     rax, aIs; "is"
0x180010914  cmp     byte ptr [rdi+0DAh], 0
0x18001091b  cmovz   rax, rdx
0x18001091f  cmp     qword ptr [rbx+18h], 7
0x180010924  jbe     short loc_180010929
0x180010926  mov     rbx, [rbx]
0x180010929  mov     qword ptr [rsp+520h+TokenType], rax; int
0x18001092e  mov     r9, rbx
0x180010931  mov     rcx, [rcx+10h]
0x180010935  call    WPP_SF_Ss
0x18001093a  add     rdi, 1B8h
0x180010941  cmp     qword ptr [rdi], 0
0x180010945  jnz     short loc_1800109AE
0x180010947  mov     [rsp+520h+var_4B8], rdi
0x18001094c  mov     [rsp+520h+var_4B0], 0
0x180010955  mov     [rsp+520h+var_4A8], r14b
0x18001095a  lea     rdx, [rsp+520h+var_4B0]
0x18001095f  xor     ecx, ecx
0x180010961  call    cs:__imp_SRCacheManager_Open
0x180010967  mov     ebx, eax
0x180010969  lea     rcx, [rsp+520h+var_4B8]
0x18001096e  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x180010973  test    ebx, ebx
0x180010975  jns     short loc_1800109AE
0x180010977  mov     rcx, [rbp+428h]; this
0x18001097e  mov     r9d, ebx; char *
0x180010981  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180010988  mov     edx, 0A5h; void *
0x18001098d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010992  mov     rcx, [rbp+428h]; this
0x180010999  mov     r9d, ebx; char *
0x18001099c  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800109a3  mov     edx, 0A1h; void *
0x1800109a8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
