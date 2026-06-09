# Microsoft::Diagnostics::Utils::FileSystem::CheckAccessToPath(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,void *,ulong,bool &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> *)

- ea: `0x1802b8370`
- end: `0x1802b87c4`
- name: `?CheckAccessToPath@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAXKAEA_NPEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `1108`
- prototype: `__int64 __fastcall(__int64, void *, __int64, bool *, HANDLE *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802b8b48`
- `0x1802b95cc`

## callees

- `0x18002b7c0`
- `0x18002df00`
- `0x180064e34`
- `0x180064e6c`
- `0x180064e8c`
- `0x18008abf4`
- `0x18009c78c`
- `0x1800bc658`
- `0x1800f9c3c`
- `0x18020aac0`
- `0x1802b8370`
- `0x1802b8a90`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802b861f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802b861f`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1802b84b3`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1802b84b3`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1802b84f1`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1802b84f1`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1802b86c5`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1802b86c5`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1802b8434`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1802b8434`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::Utils::FileSystem::CheckAccessToPath(
        __int64 a1,
        void *a2,
        __int64 a3,
        bool *a4,
        HANDLE *a5)
{
  const WCHAR *v7; // rcx
  DWORD NamedSecurityInfoW; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  const char *v12; // r9
  unsigned int LastError; // ebx
  int v14; // eax
  unsigned int v15; // edi
  const WCHAR *v16; // rcx
  HANDLE FileW; // rax
  const char *v18; // r9
  unsigned int v19; // ebx
  DWORD SecurityInfo; // eax
  unsigned int v21; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  unsigned int ppsidGroup; // [rsp+20h] [rbp-B8h]
  int ppsidGroupa; // [rsp+20h] [rbp-B8h]
  unsigned int ppsidGroupb; // [rsp+20h] [rbp-B8h]
  int ppsidGroupc; // [rsp+20h] [rbp-B8h]
  PSECURITY_DESCRIPTOR ppSecurityDescriptor[2]; // [rsp+40h] [rbp-98h] BYREF
  DWORD AccessMask[4]; // [rsp+50h] [rbp-88h] BYREF
  void *phNewToken; // [rsp+60h] [rbp-78h] BYREF
  PACL ppDacl; // [rsp+68h] [rbp-70h] BYREF
  PSID v32; // [rsp+70h] [rbp-68h] BYREF
  PSID ppsidOwner; // [rsp+78h] [rbp-60h] BYREF
  LPCWSTR pObjectName[3]; // [rsp+80h] [rbp-58h] BYREF
  unsigned __int64 v35; // [rsp+98h] [rbp-40h]
  _GENERIC_MAPPING GenericMapping; // [rsp+A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    AccessMask[0] = 0x40000000;
    *a4 = 0;
    std::wstring::wstring(pObjectName, a1);
    ppSecurityDescriptor[0] = 0;
    ppsidOwner = 0;
    v32 = 0;
    ppDacl = 0;
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
      ppSecurityDescriptor,
      0);
    v7 = (const WCHAR *)pObjectName;
    if ( v35 > 7 )
      v7 = pObjectName[0];
    NamedSecurityInfoW = GetNamedSecurityInfoW(
                           v7,
                           SE_FILE_OBJECT,
                           7u,
                           &ppsidOwner,
                           &v32,
                           &ppDacl,
                           0,
                           ppSecurityDescriptor);
    if ( NamedSecurityInfoW )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x647,
             (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
             (const char *)NamedSecurityInfoW,
             ppsidGroup);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(ppSecurityDescriptor);
      std::wstring::_Tidy_deallocate(pObjectName);
      return v9;
    }
    GenericMapping.GenericRead = 1179785;
    GenericMapping.GenericWrite = 1179926;
    GenericMapping.GenericExecute = 1179808;
    GenericMapping.GenericAll = 2032127;
    MapGenericMask(AccessMask, &GenericMapping);
    phNewToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &phNewToken,
      0);
    if ( !DuplicateTokenEx(a2, 0xF01FFu, 0, SecurityIdentification, TokenImpersonation, &phNewToken) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x655,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                    v12);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(ppSecurityDescriptor);
      std::wstring::_Tidy_deallocate(pObjectName);
      return LastError;
    }
    v14 = Microsoft::Diagnostics::Utils::Os::CheckTokenAccess(
            a4,
            AccessMask[0],
            ppSecurityDescriptor[0],
            phNewToken,
            &GenericMapping);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
        (const char *)(unsigned int)v14,
        ppsidGroupa);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(ppSecurityDescriptor);
      std::wstring::_Tidy_deallocate(pObjectName);
      return v15;
    }
    if ( !*a4 || !a5 )
      goto LABEL_11;
    v16 = (const WCHAR *)pObjectName;
    if ( v35 > 7 )
      v16 = pObjectName[0];
    FileW = CreateFileW(v16, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a5,
      FileW);
    if ( (((unsigned __int64)*a5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v19 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x672,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
              v18);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(ppSecurityDescriptor);
      std::wstring::_Tidy_deallocate(pObjectName);
      return v19;
    }
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
      ppSecurityDescriptor,
      0);
    SecurityInfo = GetSecurityInfo(*a5, SE_FILE_OBJECT, 7u, &ppsidOwner, &v32, &ppDacl, 0, ppSecurityDescriptor);
    if ( SecurityInfo )
    {
      v21 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x67F,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
              (const char *)SecurityInfo,
              ppsidGroupb);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(ppSecurityDescriptor);
      std::wstring::_Tidy_deallocate(pObjectName);
      return v21;
    }
    v22 = Microsoft::Diagnostics::Utils::Os::CheckTokenAccess(
            a4,
            AccessMask[0],
            ppSecurityDescriptor[0],
            phNewToken,
            &GenericMapping);
    v23 = v22;
    if ( v22 >= 0 )
    {
LABEL_11:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(ppSecurityDescriptor);
      std::wstring::_Tidy_deallocate(pObjectName);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x685,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
      (const char *)(unsigned int)v22,
      ppsidGroupc);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(ppSecurityDescriptor);
    std::wstring::_Tidy_deallocate(pObjectName);
    result = v23;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x68B,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1802b8370  mov     r11, rsp
0x1802b8373  push    rbx
0x1802b8374  push    rsi
0x1802b8375  push    rdi
0x1802b8376  sub     rsp, 0C0h
0x1802b837d  mov     rax, cs:__security_cookie
0x1802b8384  xor     rax, rsp
0x1802b8387  mov     [rsp+0D8h+var_28], rax
0x1802b838f  mov     rbx, r9
0x1802b8392  mov     rdi, rdx
0x1802b8395  mov     rsi, [rsp+0D8h+arg_20]
0x1802b839d  mov     [rsp+0D8h+AccessMask], 40000000h
0x1802b83a5  mov     byte ptr [r9], 0
0x1802b83a9  mov     rdx, rcx
0x1802b83ac  lea     rcx, [r11-58h]
0x1802b83b0  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1802b83b5  mov     [rsp+0D8h+var_98], 0
0x1802b83be  mov     [rsp+0D8h+ppsidOwner], 0
0x1802b83c7  mov     [rsp+0D8h+var_68], 0
0x1802b83d0  mov     [rsp+0D8h+var_70], 0
0x1802b83d9  xor     edx, edx
0x1802b83db  lea     rcx, [rsp+0D8h+var_98]
0x1802b83e0  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x1802b83e5  lea     rcx, [rsp+0D8h+pObjectName]
0x1802b83ed  cmp     [rsp+0D8h+var_40], 7
0x1802b83f6  cmova   rcx, [rsp+0D8h+pObjectName]; pObjectName
0x1802b83ff  lea     rax, [rsp+0D8h+var_98]
0x1802b8404  mov     [rsp+0D8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1802b8409  mov     [rsp+0D8h+ppSacl], 0; ppSacl
0x1802b8412  lea     rax, [rsp+0D8h+var_70]
0x1802b8417  mov     [rsp+0D8h+ppDacl], rax; ppDacl
0x1802b841c  lea     rax, [rsp+0D8h+var_68]
0x1802b8421  mov     [rsp+0D8h+ppsidGroup], rax; unsigned int
0x1802b8426  lea     r9, [rsp+0D8h+ppsidOwner]; ppsidOwner
0x1802b842b  mov     edx, 1; ObjectType
0x1802b8430  lea     r8d, [rdx+6]; SecurityInfo
0x1802b8434  call    cs:__imp_GetNamedSecurityInfoW
0x1802b843a  test    eax, eax
0x1802b843c  jz      short loc_1802B847A
0x1802b843e  mov     rcx, [rsp+0D8h]; this
0x1802b8446  mov     r9d, eax; char *
0x1802b8449  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1802b8450  mov     edx, 647h; void *
0x1802b8455  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802b845a  mov     ebx, eax
0x1802b845c  lea     rcx, [rsp+0D8h+var_98]
0x1802b8461  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1802b8466  lea     rcx, [rsp+0D8h+pObjectName]
0x1802b846e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b8473  mov     eax, ebx
0x1802b8475  jmp     loc_1802B87A8
0x1802b847a  mov     [rsp+0D8h+GenericMapping.GenericRead], 120089h
0x1802b8485  mov     [rsp+0D8h+GenericMapping.GenericWrite], 120116h
0x1802b8490  mov     [rsp+0D8h+GenericMapping.GenericExecute], 1200A0h
0x1802b849b  mov     [rsp+0D8h+GenericMapping.GenericAll], 1F01FFh
0x1802b84a6  lea     rdx, [rsp+0D8h+GenericMapping]; GenericMapping
0x1802b84ae  lea     rcx, [rsp+0D8h+AccessMask]; AccessMask
0x1802b84b3  call    cs:__imp_MapGenericMask
0x1802b84b9  mov     [rsp+0D8h+phNewToken], 0
0x1802b84c2  xor     edx, edx
0x1802b84c4  lea     rcx, [rsp+0D8h+phNewToken]
0x1802b84c9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802b84ce  lea     rax, [rsp+0D8h+phNewToken]
0x1802b84d3  mov     [rsp+0D8h+ppDacl], rax; phNewToken
0x1802b84d8  mov     dword ptr [rsp+0D8h+ppsidGroup], 2; TokenType
0x1802b84e0  mov     r9d, 1; ImpersonationLevel
0x1802b84e6  xor     r8d, r8d; lpTokenAttributes
0x1802b84e9  mov     edx, 0F01FFh; dwDesiredAccess
0x1802b84ee  mov     rcx, rdi; hExistingToken
0x1802b84f1  call    cs:__imp_DuplicateTokenEx
0x1802b84f7  test    eax, eax
0x1802b84f9  jnz     short loc_1802B853E
0x1802b84fb  mov     rcx, [rsp+0D8h]; this
0x1802b8503  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1802b850a  mov     edx, 655h; void *
0x1802b850f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802b8514  mov     ebx, eax
0x1802b8516  lea     rcx, [rsp+0D8h+phNewToken]
0x1802b851b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b8520  lea     rcx, [rsp+0D8h+var_98]
0x1802b8525  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1802b852a  lea     rcx, [rsp+0D8h+pObjectName]
0x1802b8532  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b8537  mov     eax, ebx
0x1802b8539  jmp     loc_1802B87A8
0x1802b853e  lea     rax, [rsp+0D8h+GenericMapping]
0x1802b8546  mov     [rsp+0D8h+ppsidGroup], rax; int
0x1802b854b  mov     r9, [rsp+0D8h+phNewToken]; void *
0x1802b8550  mov     r8, [rsp+0D8h+var_98]; void *
0x1802b8555  mov     edx, [rsp+0D8h+AccessMask]; unsigned int
0x1802b8559  mov     rcx, rbx; bool *
0x1802b855c  call    ?CheckTokenAccess@Os@Utils@Diagnostics@Microsoft@@SAJAEA_NKPEAX1AEAU_GENERIC_MAPPING@@@Z; Microsoft::Diagnostics::Utils::Os::CheckTokenAccess(bool &,ulong,void *,void *,_GENERIC_MAPPING &)
0x1802b8561  mov     edi, eax
0x1802b8563  test    eax, eax
0x1802b8565  jns     short loc_1802B85AB
0x1802b8567  mov     rcx, [rsp+0D8h]; this
0x1802b856f  mov     r9d, eax; char *
0x1802b8572  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1802b8579  mov     edx, 65Ch; void *
0x1802b857e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b8583  lea     rcx, [rsp+0D8h+phNewToken]
0x1802b8588  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b858d  lea     rcx, [rsp+0D8h+var_98]
0x1802b8592  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1802b8597  lea     rcx, [rsp+0D8h+pObjectName]
0x1802b859f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b85a4  mov     eax, edi
0x1802b85a6  jmp     loc_1802B87A8
0x1802b85ab  cmp     byte ptr [rbx], 0
0x1802b85ae  jnz     short loc_1802B85D8
0x1802b85b0  lea     rcx, [rsp+0D8h+phNewToken]
0x1802b85b5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b85ba  lea     rcx, [rsp+0D8h+var_98]
0x1802b85bf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1802b85c4  lea     rcx, [rsp+0D8h+pObjectName]
0x1802b85cc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b85d1  xor     eax, eax
0x1802b85d3  jmp     loc_1802B87A8
0x1802b85d8  test    rsi, rsi
0x1802b85db  jz      loc_1802B877F
0x1802b85e1  lea     rcx, [rsp+0D8h+pObjectName]
0x1802b85e9  cmp     [rsp+0D8h+var_40], 7
0x1802b85f2  cmova   rcx, [rsp+0D8h+pObjectName]; lpFileName
0x1802b85fb  mov     [rsp+0D8h+ppSacl], 0; hTemplateFile
0x1802b8604  mov     dword ptr [rsp+0D8h+ppDacl], 2000000h; dwFlagsAndAttributes
0x1802b860c  mov     r8d, 3; dwShareMode
0x1802b8612  mov     dword ptr [rsp+0D8h+ppsidGroup], r8d; dwCreationDisposition
0x1802b8617  xor     r9d, r9d; lpSecurityAttributes
0x1802b861a  mov     edx, 80000000h; dwDesiredAccess
0x1802b861f  call    cs:__imp_CreateFileW
0x1802b8625  mov     rdx, rax
0x1802b8628  mov     rcx, rsi
0x1802b862b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802b8630  mov     rax, [rsi]
0x1802b8633  inc     rax
0x1802b8636  test    rax, 0FFFFFFFFFFFFFFFEh
0x1802b863c  jnz     short loc_1802B8681
0x1802b863e  mov     rcx, [rsp+0D8h]; this
0x1802b8646  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1802b864d  mov     edx, 672h; void *
0x1802b8652  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802b8657  mov     ebx, eax
0x1802b8659  lea     rcx, [rsp+0D8h+phNewToken]
0x1802b865e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b8663  lea     rcx, [rsp+0D8h+var_98]
0x1802b8668  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1802b866d  lea     rcx, [rsp+0D8h+pObjectName]
0x1802b8675  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b867a  mov     eax, ebx
0x1802b867c  jmp     loc_1802B87A8
0x1802b8681  xor     edx, edx
0x1802b8683  lea     rcx, [rsp+0D8h+var_98]
0x1802b8688  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x1802b868d  lea     rax, [rsp+0D8h+var_98]
0x1802b8692  mov     [rsp+0D8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1802b8697  mov     [rsp+0D8h+ppSacl], 0; ppSacl
0x1802b86a0  lea     rax, [rsp+0D8h+var_70]
0x1802b86a5  mov     [rsp+0D8h+ppDacl], rax; ppDacl
0x1802b86aa  lea     rax, [rsp+0D8h+var_68]
0x1802b86af  mov     [rsp+0D8h+ppsidGroup], rax; unsigned int
0x1802b86b4  lea     r9, [rsp+0D8h+ppsidOwner]; ppsidOwner
0x1802b86b9  mov     edx, 1; ObjectType
0x1802b86be  lea     r8d, [rdx+6]; SecurityInfo
0x1802b86c2  mov     rcx, [rsi]; handle
0x1802b86c5  call    cs:__imp_GetSecurityInfo
0x1802b86cb  test    eax, eax
0x1802b86cd  jz      short loc_1802B8715
0x1802b86cf  mov     rcx, [rsp+0D8h]; this
0x1802b86d7  mov     r9d, eax; char *
0x1802b86da  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1802b86e1  mov     edx, 67Fh; void *
0x1802b86e6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802b86eb  mov     ebx, eax
0x1802b86ed  lea     rcx, [rsp+0D8h+phNewToken]
0x1802b86f2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b86f7  lea     rcx, [rsp+0D8h+var_98]
0x1802b86fc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1802b8701  lea     rcx, [rsp+0D8h+pObjectName]
0x1802b8709  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b870e  mov     eax, ebx
0x1802b8710  jmp     loc_1802B87A8
0x1802b8715  lea     rax, [rsp+0D8h+GenericMapping]
0x1802b871d  mov     [rsp+0D8h+ppsidGroup], rax; int
0x1802b8722  mov     r9, [rsp+0D8h+phNewToken]; void *
0x1802b8727  mov     r8, [rsp+0D8h+var_98]; void *
0x1802b872c  mov     edx, [rsp+0D8h+AccessMask]; unsigned int
0x1802b8730  mov     rcx, rbx; bool *
0x1802b8733  call    ?CheckTokenAccess@Os@Utils@Diagnostics@Microsoft@@SAJAEA_NKPEAX1AEAU_GENERIC_MAPPING@@@Z; Microsoft::Diagnostics::Utils::Os::CheckTokenAccess(bool &,ulong,void *,void *,_GENERIC_MAPPING &)
0x1802b8738  mov     ebx, eax
0x1802b873a  test    eax, eax
0x1802b873c  jns     short loc_1802B877F
0x1802b873e  mov     rcx, [rsp+0D8h]; this
0x1802b8746  mov     r9d, eax; char *
0x1802b8749  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1802b8750  mov     edx, 685h; void *
0x1802b8755  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b875a  lea     rcx, [rsp+0D8h+phNewToken]
0x1802b875f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b8764  lea     rcx, [rsp+0D8h+var_98]
0x1802b8769  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1802b876e  lea     rcx, [rsp+0D8h+pObjectName]
0x1802b8776  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b877b  mov     eax, ebx
0x1802b877d  jmp     short loc_1802B87A8
0x1802b877f  lea     rcx, [rsp+0D8h+phNewToken]
0x1802b8784  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b8789  lea     rcx, [rsp+0D8h+var_98]
0x1802b878e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1802b8793  lea     rcx, [rsp+0D8h+pObjectName]
0x1802b879b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b87a0  xor     eax, eax
0x1802b87a2  jmp     short loc_1802B87A8
0x1802b87a4  mov     eax, [rsp+0D8h+AccessMask]
0x1802b87a8  mov     rcx, [rsp+0D8h+var_28]
0x1802b87b0  xor     rcx, rsp; StackCookie
0x1802b87b3  call    __security_check_cookie
0x1802b87b8  add     rsp, 0C0h
0x1802b87bf  pop     rdi
0x1802b87c0  pop     rsi
0x1802b87c1  pop     rbx
0x1802b87c2  retn
```
