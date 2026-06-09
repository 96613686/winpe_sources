# Microsoft::Diagnostics::Utils::FileSystem::SetTokenAclOnFile(void *,void *,ulong,bool,_ACCESS_MODE)

- ea: `0x1801d23a0`
- end: `0x1801d26ab`
- name: `?SetTokenAclOnFile@FileSystem@Utils@Diagnostics@Microsoft@@SAJPEAX0K_NW4_ACCESS_MODE@@@Z`
- size: `779`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HANDLE handle, unsigned int, bool, enum _ACCESS_MODE)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18016add0`
- `0x1801d2344`

## callees

- `0x18001b510`
- `0x180064e6c`
- `0x180064e8c`
- `0x18008abf4`
- `0x18009c78c`
- `0x1800f7b34`
- `0x1800f9c3c`
- `0x180105ad8`
- `0x1801d23a0`
- `0x1802b7da0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d2475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d2475`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801d2438`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801d2438`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801d246b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801d2509`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801d246b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801d2509`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1801d2406`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1801d2406`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1801d25aa`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1801d25aa`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1801d261a`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1801d261a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Diagnostics::Utils::FileSystem::SetTokenAclOnFile(
        HANDLE TokenHandle,
        HANDLE handle,
        __int64 a3,
        char a4)
{
  DWORD SecurityInfo; // eax
  unsigned int v7; // ebx
  __int64 result; // rax
  BOOL v9; // eax
  DWORD v10; // eax
  const struct std::nothrow_t *v11; // rdx
  __int64 v12; // rax
  const struct std::nothrow_t *v13; // rdx
  LPWCH *v14; // rbx
  const char *v15; // r9
  unsigned int LastError; // ebx
  const struct std::nothrow_t *v17; // rdx
  const char *v18; // r9
  DWORD v19; // eax
  unsigned int v20; // ebx
  const struct std::nothrow_t *v21; // rdx
  DWORD v22; // eax
  unsigned int v23; // ebx
  const struct std::nothrow_t *v24; // rdx
  const struct std::nothrow_t *v25; // rdx
  unsigned int ppsidGroup; // [rsp+20h] [rbp-98h]
  int ppsidGroupa; // [rsp+20h] [rbp-98h]
  unsigned int ppsidGroupb; // [rsp+20h] [rbp-98h]
  unsigned int ppsidGroupc; // [rsp+20h] [rbp-98h]
  PSECURITY_DESCRIPTOR hMem; // [rsp+40h] [rbp-78h] BYREF
  LPVOID TokenInformation; // [rsp+48h] [rbp-70h] BYREF
  PACL NewAcl; // [rsp+50h] [rbp-68h] BYREF
  PACL OldAcl; // [rsp+58h] [rbp-60h] BYREF
  void *v34; // [rsp+60h] [rbp-58h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  DWORD ReturnLength; // [rsp+D8h] [rbp+20h] BYREF

  LOBYTE(ReturnLength) = a4;
  hMem = 0;
  OldAcl = 0;
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
    &hMem,
    0);
  SecurityInfo = GetSecurityInfo(handle, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
  if ( SecurityInfo )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x5F2,
           (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
           (const char *)SecurityInfo,
           ppsidGroup);
    if ( hMem )
      LocalFree(hMem);
    return v7;
  }
  else
  {
    ReturnLength = 0;
    TokenInformation = 0;
    v9 = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &ReturnLength);
    if ( v9 || (v10 = GetLastError(), v10 == 122) )
    {
      try
      {
        v12 = std::make_unique<unsigned char [0],0>(&v34, ReturnLength);
        std::unique_ptr<enum gsl::byte [0]>::operator=<std::default_delete<enum gsl::byte [0]>,0>(
          &TokenInformation,
          v12);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v34, v13);
        v14 = (LPWCH *)TokenInformation;
        if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, ReturnLength, &ReturnLength) )
        {
          *(_QWORD *)&pListOfExplicitEntries.grfInheritance = 3;
          pListOfExplicitEntries.Trustee.ptstrName = 0;
          pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
          pListOfExplicitEntries.grfAccessMode = REVOKE_ACCESS;
          pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
          *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
          *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 1;
          pListOfExplicitEntries.Trustee.ptstrName = *v14;
          NewAcl = 0;
          v19 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
          if ( v19 )
          {
            v20 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x617,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                    (const char *)v19,
                    ppsidGroupb);
            wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&NewAcl);
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&TokenInformation, v21);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&hMem);
            result = v20;
          }
          else
          {
            v22 = SetSecurityInfo(handle, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
            if ( v22 )
            {
              v23 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x61A,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                      (const char *)v22,
                      ppsidGroupc);
              wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&NewAcl);
              std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&TokenInformation, v24);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&hMem);
              result = v23;
            }
            else
            {
              wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&NewAcl);
              std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&TokenInformation, v25);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&hMem);
              result = 0;
            }
          }
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x601,
                        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                        v15);
          std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&TokenInformation, v17);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&hMem);
          result = LastError;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x61E,
                               (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                               v18);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5FC,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
        (const char *)0x80004005LL,
        ppsidGroupa);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&TokenInformation, v11);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&hMem);
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1801d23a0  mov     rax, rsp
0x1801d23a3  mov     [rax+8], rbx
0x1801d23a7  mov     [rax+10h], rsi
0x1801d23ab  mov     [rax+20h], r9b
0x1801d23af  push    rdi
0x1801d23b0  push    r14
0x1801d23b2  push    r15
0x1801d23b4  sub     rsp, 0A0h
0x1801d23bb  mov     rdi, rdx
0x1801d23be  mov     rsi, rcx
0x1801d23c1  xor     r14d, r14d
0x1801d23c4  mov     [rax-78h], r14
0x1801d23c8  mov     [rax-60h], r14
0x1801d23cc  xor     edx, edx
0x1801d23ce  lea     rcx, [rax-78h]
0x1801d23d2  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x1801d23d7  lea     rax, [rsp+0B8h+hMem]
0x1801d23dc  mov     [rsp+0B8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1801d23e1  mov     [rsp+0B8h+ppSacl], r14; ppSacl
0x1801d23e6  lea     rax, [rsp+0B8h+OldAcl]
0x1801d23eb  mov     [rsp+0B8h+ppDacl], rax; ppDacl
0x1801d23f0  mov     [rsp+0B8h+ppsidGroup], r14; unsigned int
0x1801d23f5  xor     r9d, r9d; ppsidOwner
0x1801d23f8  lea     r8d, [r14+4]; SecurityInfo
0x1801d23fc  lea     r15d, [r14+1]
0x1801d2400  mov     edx, r15d; ObjectType
0x1801d2403  mov     rcx, rdi; handle
0x1801d2406  call    cs:__imp_GetSecurityInfo
0x1801d240c  test    eax, eax
0x1801d240e  jz      short loc_1801D2445
0x1801d2410  mov     rcx, [rsp+0B8h]; this
0x1801d2418  mov     r9d, eax; char *
0x1801d241b  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1801d2422  mov     edx, 5F2h; void *
0x1801d2427  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801d242c  mov     ebx, eax
0x1801d242e  mov     rcx, [rsp+0B8h+hMem]; hMem
0x1801d2433  test    rcx, rcx
0x1801d2436  jz      short loc_1801D243E
0x1801d2438  call    cs:__imp_LocalFree
0x1801d243e  mov     eax, ebx
0x1801d2440  jmp     loc_1801D2691
0x1801d2445  mov     [rsp+0B8h+ReturnLength], r14d
0x1801d244d  mov     [rsp+0B8h+TokenInformation], r14
0x1801d2452  lea     rax, [rsp+0B8h+ReturnLength]
0x1801d245a  mov     [rsp+0B8h+ppsidGroup], rax; int
0x1801d245f  xor     r9d, r9d; TokenInformationLength
0x1801d2462  xor     r8d, r8d; TokenInformation
0x1801d2465  mov     edx, r15d; TokenInformationClass
0x1801d2468  mov     rcx, rsi; TokenHandle
0x1801d246b  call    cs:__imp_GetTokenInformation
0x1801d2471  test    eax, eax
0x1801d2473  jnz     short loc_1801D24BE
0x1801d2475  call    cs:__imp_GetLastError
0x1801d247b  cmp     eax, 7Ah ; 'z'
0x1801d247e  jz      short loc_1801D24BE
0x1801d2480  mov     rcx, [rsp+0B8h]; this
0x1801d2488  mov     ebx, 80004005h
0x1801d248d  mov     r9d, ebx; char *
0x1801d2490  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1801d2497  mov     edx, 5FCh; void *
0x1801d249c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d24a1  nop
0x1801d24a2  lea     rcx, [rsp+0B8h+TokenInformation]
0x1801d24a7  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1801d24ac  nop
0x1801d24ad  lea     rcx, [rsp+0B8h+hMem]
0x1801d24b2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1801d24b7  mov     eax, ebx
0x1801d24b9  jmp     loc_1801D2691
0x1801d24be  mov     edx, [rsp+0B8h+ReturnLength]
0x1801d24c5  lea     rcx, [rsp+0B8h+var_58]
0x1801d24ca  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x1801d24cf  mov     rdx, rax
0x1801d24d2  lea     rcx, [rsp+0B8h+TokenInformation]
0x1801d24d7  call    ??$?4U?$default_delete@$$BY0A@W4byte@gsl@@@std@@$0A@@?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<gsl::byte [0]>::operator=<std::default_delete<gsl::byte [0]>,0>(std::unique_ptr<gsl::byte [0]> &&)
0x1801d24dc  lea     rcx, [rsp+0B8h+var_58]
0x1801d24e1  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1801d24e6  lea     rax, [rsp+0B8h+ReturnLength]
0x1801d24ee  mov     [rsp+0B8h+ppsidGroup], rax; unsigned int
0x1801d24f3  mov     r9d, [rsp+0B8h+ReturnLength]; TokenInformationLength
0x1801d24fb  mov     rbx, [rsp+0B8h+TokenInformation]
0x1801d2500  mov     r8, rbx; TokenInformation
0x1801d2503  mov     edx, r15d; TokenInformationClass
0x1801d2506  mov     rcx, rsi; TokenHandle
0x1801d2509  call    cs:__imp_GetTokenInformation
0x1801d250f  test    eax, eax
0x1801d2511  jnz     short loc_1801D254A
0x1801d2513  mov     rcx, [rsp+0B8h]; this
0x1801d251b  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1801d2522  mov     edx, 601h; void *
0x1801d2527  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d252c  mov     ebx, eax
0x1801d252e  lea     rcx, [rsp+0B8h+TokenInformation]
0x1801d2533  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1801d2538  nop
0x1801d2539  lea     rcx, [rsp+0B8h+hMem]
0x1801d253e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1801d2543  mov     eax, ebx
0x1801d2545  jmp     loc_1801D2691
0x1801d254a  mov     qword ptr [rsp+0B8h+pListOfExplicitEntries.grfInheritance], 3
0x1801d2553  mov     qword ptr [rsp+0B8h+pListOfExplicitEntries.Trustee+14h], r14
0x1801d255b  mov     dword ptr [rsp+0B8h+pListOfExplicitEntries.Trustee.ptstrName+4], r14d
0x1801d2563  mov     [rsp+0B8h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x1801d256b  mov     [rsp+0B8h+pListOfExplicitEntries.grfAccessMode], 4
0x1801d2573  mov     [rsp+0B8h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x1801d2578  mov     qword ptr [rsp+0B8h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x1801d2580  mov     [rsp+0B8h+pListOfExplicitEntries.Trustee.TrusteeType], r15d
0x1801d2588  mov     rax, [rbx]
0x1801d258b  mov     [rsp+0B8h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1801d2593  mov     [rsp+0B8h+NewAcl], r14
0x1801d2598  lea     r9, [rsp+0B8h+NewAcl]; NewAcl
0x1801d259d  mov     r8, [rsp+0B8h+OldAcl]; OldAcl
0x1801d25a2  lea     rdx, [rsp+0B8h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1801d25a7  mov     ecx, r15d; cCountOfExplicitEntries
0x1801d25aa  call    cs:__imp_SetEntriesInAclW
0x1801d25b0  test    eax, eax
0x1801d25b2  jz      short loc_1801D25F9
0x1801d25b4  mov     rcx, [rsp+0B8h]; this
0x1801d25bc  mov     r9d, eax; char *
0x1801d25bf  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1801d25c6  mov     edx, 617h; void *
0x1801d25cb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801d25d0  mov     ebx, eax
0x1801d25d2  lea     rcx, [rsp+0B8h+NewAcl]
0x1801d25d7  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(void)
0x1801d25dc  nop
0x1801d25dd  lea     rcx, [rsp+0B8h+TokenInformation]
0x1801d25e2  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1801d25e7  nop
0x1801d25e8  lea     rcx, [rsp+0B8h+hMem]
0x1801d25ed  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1801d25f2  mov     eax, ebx
0x1801d25f4  jmp     loc_1801D2691
0x1801d25f9  mov     [rsp+0B8h+ppSacl], r14; pSacl
0x1801d25fe  mov     rax, [rsp+0B8h+NewAcl]
0x1801d2603  mov     [rsp+0B8h+ppDacl], rax; pDacl
0x1801d2608  mov     [rsp+0B8h+ppsidGroup], r14; unsigned int
0x1801d260d  xor     r9d, r9d; psidOwner
0x1801d2610  lea     r8d, [r9+4]; SecurityInfo
0x1801d2614  mov     edx, r15d; ObjectType
0x1801d2617  mov     rcx, rdi; handle
0x1801d261a  call    cs:__imp_SetSecurityInfo
0x1801d2620  test    eax, eax
0x1801d2622  jz      short loc_1801D2666
0x1801d2624  mov     rcx, [rsp+0B8h]; this
0x1801d262c  mov     r9d, eax; char *
0x1801d262f  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1801d2636  mov     edx, 61Ah; void *
0x1801d263b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801d2640  mov     ebx, eax
0x1801d2642  lea     rcx, [rsp+0B8h+NewAcl]
0x1801d2647  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(void)
0x1801d264c  nop
0x1801d264d  lea     rcx, [rsp+0B8h+TokenInformation]
0x1801d2652  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1801d2657  nop
0x1801d2658  lea     rcx, [rsp+0B8h+hMem]
0x1801d265d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1801d2662  mov     eax, ebx
0x1801d2664  jmp     short loc_1801D2691
0x1801d2666  lea     rcx, [rsp+0B8h+NewAcl]
0x1801d266b  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(void)
0x1801d2670  nop
0x1801d2671  lea     rcx, [rsp+0B8h+TokenInformation]
0x1801d2676  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1801d267b  nop
0x1801d267c  lea     rcx, [rsp+0B8h+hMem]
0x1801d2681  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1801d2686  xor     eax, eax
0x1801d2688  jmp     short loc_1801D2691
0x1801d268a  mov     eax, [rsp+0B8h+ReturnLength]
0x1801d2691  lea     r11, [rsp+0B8h+var_18]
0x1801d2699  mov     rbx, [r11+20h]
0x1801d269d  mov     rsi, [r11+28h]
0x1801d26a1  mov     rsp, r11
0x1801d26a4  pop     r15
0x1801d26a6  pop     r14
0x1801d26a8  pop     rdi
0x1801d26a9  retn
```
