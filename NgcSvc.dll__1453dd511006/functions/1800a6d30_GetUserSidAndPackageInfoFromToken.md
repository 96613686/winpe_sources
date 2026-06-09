# GetUserSidAndPackageInfoFromToken

- ea: `0x1800a6d30`
- end: `0x1800a701c`
- name: `GetUserSidAndPackageInfoFromToken`
- size: `748`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `12`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008b00`
- `0x180047cf4`
- `0x18004fe40`
- `0x180054074`
- `0x180058114`
- `0x18005b5e0`
- `0x180099cc8`
- `0x1800a2ba0`
- `0x1800a3cb0`
- `0x1800a3edc`
- `0x1800a44a8`
- `0x1800a4c30`

## callees

- `0x18000782c`
- `0x180007964`
- `0x1800281e0`
- `0x180028200`
- `0x18002db44`
- `0x180048304`
- `0x1800527ac`
- `0x1800898dc`
- `0x180097c6c`
- `0x1800a6d30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6da6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a6d7a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a6e1d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a6d7a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a6e1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6df1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6fd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6df1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6fd0`
- `ntdll!RtlQueryPackageIdentity` at `0x1800a6f52`
- `ntdll!RtlQueryPackageIdentity` at `0x1800a6f52`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a6e5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a6e5d`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x1800a6ff3`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x1800a6ff3`

## string_xrefs

- `0x1800a6d92`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6db9`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6e2b`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6e76`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6eb9`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6f0a`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6f64`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a7001`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
__int64 __fastcall GetUserSidAndPackageInfoFromToken(HANDLE TokenHandle, _QWORD *a2, WCHAR **a3, const WCHAR **a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  DWORD LastError; // eax
  PSID **unique_hlocal; // rax
  PSID *v13; // rsi
  HLOCAL v14; // rcx
  const char *v15; // r9
  BOOL v16; // ebx
  const char *v17; // r9
  const char *v18; // r9
  const WCHAR *v19; // rbx
  WCHAR *v20; // rdi
  int v21; // eax
  unsigned int v22; // eax
  unsigned int ReturnLength; // [rsp+20h] [rbp-58h]
  int ReturnLengtha; // [rsp+20h] [rbp-58h]
  UINT32 packageFamilyNameLength; // [rsp+30h] [rbp-48h] BYREF
  __int64 v26; // [rsp+38h] [rbp-40h] BYREF
  PCWSTR packageFullName; // [rsp+40h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-30h] BYREF
  __int64 v29; // [rsp+50h] [rbp-28h] BYREF
  __int64 *v30; // [rsp+58h] [rbp-20h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-18h] BYREF
  char v32; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  DWORD TokenInformationLength; // [rsp+C8h] [rbp+50h] BYREF

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *a2 = 0;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( LastError != 122 && LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xF9,
               (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
               (const char *)LastError,
               ReturnLength);
    unique_hlocal = (PSID **)wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, TokenInformationLength);
    v13 = *unique_hlocal;
    *unique_hlocal = 0;
    v14 = hMem;
    hMem = 0;
    if ( v14 )
      LocalFree(v14);
    if ( !v13 )
    {
      v8 = -2147024882;
      v9 = 254;
      goto LABEL_5;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, v13, TokenInformationLength, &TokenInformationLength) )
    {
      v8 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x105,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
             v15);
LABEL_32:
      LocalFree(v13);
      return v8;
    }
    v26 = 0;
    v30 = &v26;
    StringSid = 0;
    v32 = 1;
    v16 = ConvertSidToStringSidW(*v13, &StringSid);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v30);
    if ( !v16 )
    {
      v8 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x10A,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
             v17);
LABEL_17:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
      goto LABEL_32;
    }
    v29 = 128;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &packageFullName,
      0,
      0x80u,
      v17);
    v19 = packageFullName;
    if ( !packageFullName )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10E,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
        (const char *)0x8007000ELL,
        ReturnLengtha);
LABEL_20:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&packageFullName);
      goto LABEL_17;
    }
    v29 *= 2;
    packageFamilyNameLength = 65;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &hMem,
      0,
      0x41u,
      v18);
    v20 = (WCHAR *)hMem;
    if ( !hMem )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
        (const char *)0x8007000ELL,
        ReturnLengtha);
LABEL_23:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
      goto LABEL_20;
    }
    if ( a3 )
    {
      v21 = RtlQueryPackageIdentity(TokenHandle, v19, &v29, 0);
      if ( v21 >= 0 )
      {
        v22 = PackageFamilyNameFromFullName(v19, &packageFamilyNameLength, v20);
        if ( v22 )
        {
          v8 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x121,
                 (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
                 (const char *)v22,
                 0);
          goto LABEL_23;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_NtStatus(
          retaddr,
          (void *)0x11C,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
          (const char *)(unsigned int)v21,
          0);
        *v19 = 0;
        *v20 = 0;
      }
    }
    *a2 = v26;
    v26 = 0;
    if ( a3 )
    {
      hMem = 0;
      *a3 = v20;
    }
    if ( a4 )
    {
      packageFullName = 0;
      *a4 = v19;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&packageFullName);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
    v8 = 0;
    goto LABEL_32;
  }
  v8 = -2147418113;
  v9 = 245;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
    (const char *)v8,
    ReturnLength);
  return v8;
}

```

## disassembly

```asm
0x1800a6d30  push    rbp
0x1800a6d32  push    rbx
0x1800a6d33  push    rsi
0x1800a6d34  push    rdi
0x1800a6d35  push    r12
0x1800a6d37  push    r13
0x1800a6d39  push    r14
0x1800a6d3b  push    r15
0x1800a6d3d  mov     rbp, rsp
0x1800a6d40  sub     rsp, 78h
0x1800a6d44  xor     edi, edi
0x1800a6d46  mov     r12, r9
0x1800a6d49  mov     r14, r8
0x1800a6d4c  mov     r15, rdx
0x1800a6d4f  mov     r13, rcx
0x1800a6d52  test    rdx, rdx
0x1800a6d55  jnz     short loc_1800A6D5C
0x1800a6d57  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a6d5c  xor     r9d, r9d; TokenInformationLength
0x1800a6d5f  mov     [r15], rdi
0x1800a6d62  lea     rax, [rbp+TokenInformationLength]
0x1800a6d66  mov     [rbp+TokenInformationLength], edi
0x1800a6d69  xor     r8d, r8d; TokenInformation
0x1800a6d6c  mov     [rsp+78h+ReturnLength], rax; unsigned int
0x1800a6d71  mov     rcx, r13; TokenHandle
0x1800a6d74  lea     ebx, [r9+1]
0x1800a6d78  mov     edx, ebx; TokenInformationClass
0x1800a6d7a  call    cs:__imp_GetTokenInformation
0x1800a6d80  test    eax, eax
0x1800a6d82  jz      short loc_1800A6DA6
0x1800a6d84  mov     ebx, 8000FFFFh
0x1800a6d89  mov     edx, 0F5h; void *
0x1800a6d8e  mov     rcx, [rbp+40h]; this
0x1800a6d92  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6d99  mov     r9d, ebx; char *
0x1800a6d9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6da1  jmp     loc_1800A6FD6
0x1800a6da6  call    cs:__imp_GetLastError
0x1800a6dac  cmp     eax, 7Ah ; 'z'
0x1800a6daf  jz      short loc_1800A6DD2
0x1800a6db1  test    eax, eax
0x1800a6db3  jz      short loc_1800A6DD2
0x1800a6db5  mov     rcx, [rbp+40h]; this
0x1800a6db9  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6dc0  mov     r9d, eax; char *
0x1800a6dc3  mov     edx, 0F9h; void *
0x1800a6dc8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a6dcd  jmp     loc_1800A6FD8
0x1800a6dd2  mov     edx, [rbp+TokenInformationLength]
0x1800a6dd5  lea     rcx, [rbp+hMem]
0x1800a6dd9  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800a6dde  mov     rsi, [rax]
0x1800a6de1  mov     [rax], rdi
0x1800a6de4  mov     rcx, [rbp+hMem]; hMem
0x1800a6de8  mov     [rbp+hMem], rdi
0x1800a6dec  test    rcx, rcx
0x1800a6def  jz      short loc_1800A6DF7
0x1800a6df1  call    cs:__imp_LocalFree
0x1800a6df7  test    rsi, rsi
0x1800a6dfa  jnz     short loc_1800A6E08
0x1800a6dfc  mov     ebx, 8007000Eh
0x1800a6e01  mov     edx, 0FEh
0x1800a6e06  jmp     short loc_1800A6D8E
0x1800a6e08  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800a6e0c  lea     rax, [rbp+TokenInformationLength]
0x1800a6e10  mov     r8, rsi; TokenInformation
0x1800a6e13  mov     [rsp+78h+ReturnLength], rax; int
0x1800a6e18  mov     edx, ebx; TokenInformationClass
0x1800a6e1a  mov     rcx, r13; TokenHandle
0x1800a6e1d  call    cs:__imp_GetTokenInformation
0x1800a6e23  test    eax, eax
0x1800a6e25  jnz     short loc_1800A6E43
0x1800a6e27  mov     rcx, [rbp+40h]; this
0x1800a6e2b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6e32  mov     edx, 105h; void *
0x1800a6e37  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a6e3c  mov     ebx, eax
0x1800a6e3e  jmp     loc_1800A6FCD
0x1800a6e43  lea     rax, [rbp+var_40]
0x1800a6e47  mov     [rbp+var_40], rdi
0x1800a6e4b  mov     [rbp+var_20], rax
0x1800a6e4f  lea     rdx, [rbp+StringSid]; StringSid
0x1800a6e53  mov     [rbp+StringSid], rdi
0x1800a6e57  mov     [rbp+var_10], bl
0x1800a6e5a  mov     rcx, [rsi]; Sid
0x1800a6e5d  call    cs:__imp_ConvertSidToStringSidW
0x1800a6e63  lea     rcx, [rbp+var_20]
0x1800a6e67  mov     ebx, eax
0x1800a6e69  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a6e6e  test    ebx, ebx
0x1800a6e70  jnz     short loc_1800A6E97
0x1800a6e72  mov     rcx, [rbp+40h]; this
0x1800a6e76  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6e7d  mov     edx, 10Ah; void *
0x1800a6e82  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a6e87  mov     ebx, eax
0x1800a6e89  lea     rcx, [rbp+var_40]; void *
0x1800a6e8d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a6e92  jmp     loc_1800A6FCD
0x1800a6e97  mov     r8d, 80h
0x1800a6e9d  lea     rcx, [rbp+packageFullName]
0x1800a6ea1  xor     edx, edx
0x1800a6ea3  mov     [rbp+var_28], r8
0x1800a6ea7  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a6eac  mov     rbx, [rbp+packageFullName]
0x1800a6eb0  test    rbx, rbx
0x1800a6eb3  jnz     short loc_1800A6EDD
0x1800a6eb5  mov     rcx, [rbp+40h]; this
0x1800a6eb9  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6ec0  mov     ebx, 8007000Eh
0x1800a6ec5  mov     edx, 10Eh; void *
0x1800a6eca  mov     r9d, ebx; char *
0x1800a6ecd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6ed2  lea     rcx, [rbp+packageFullName]; void *
0x1800a6ed6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a6edb  jmp     short loc_1800A6E89
0x1800a6edd  mov     rax, [rbp+var_28]
0x1800a6ee1  lea     rcx, [rbp+hMem]
0x1800a6ee5  add     rax, rax
0x1800a6ee8  mov     r8d, 41h ; 'A'
0x1800a6eee  xor     edx, edx
0x1800a6ef0  mov     [rbp+var_28], rax
0x1800a6ef4  mov     [rbp+packageFamilyNameLength], r8d
0x1800a6ef8  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a6efd  mov     rdi, [rbp+hMem]
0x1800a6f01  test    rdi, rdi
0x1800a6f04  jnz     short loc_1800A6F2E
0x1800a6f06  mov     rcx, [rbp+40h]; this
0x1800a6f0a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6f11  mov     ebx, 8007000Eh
0x1800a6f16  mov     edx, 113h; void *
0x1800a6f1b  mov     r9d, ebx; char *
0x1800a6f1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6f23  lea     rcx, [rbp+hMem]; void *
0x1800a6f27  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a6f2c  jmp     short loc_1800A6ED2
0x1800a6f2e  test    r14, r14
0x1800a6f31  jz      short loc_1800A6F80
0x1800a6f33  mov     [rsp+78h+var_50], 0
0x1800a6f3c  lea     r8, [rbp+var_28]
0x1800a6f40  xor     r9d, r9d
0x1800a6f43  mov     [rsp+78h+ReturnLength], 0; unsigned int
0x1800a6f4c  mov     rdx, rbx
0x1800a6f4f  mov     rcx, r13
0x1800a6f52  call    cs:__imp_RtlQueryPackageIdentity
0x1800a6f58  test    eax, eax
0x1800a6f5a  jns     loc_1800A6FE9
0x1800a6f60  mov     rcx, [rbp+40h]; this
0x1800a6f64  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6f6b  mov     r9d, eax; char *
0x1800a6f6e  mov     edx, 11Ch; void *
0x1800a6f73  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800a6f78  xor     eax, eax
0x1800a6f7a  mov     [rbx], ax
0x1800a6f7d  mov     [rdi], ax
0x1800a6f80  mov     rax, [rbp+var_40]
0x1800a6f84  mov     [r15], rax
0x1800a6f87  mov     [rbp+var_40], 0
0x1800a6f8f  test    r14, r14
0x1800a6f92  jz      short loc_1800A6F9F
0x1800a6f94  mov     [rbp+hMem], 0
0x1800a6f9c  mov     [r14], rdi
0x1800a6f9f  test    r12, r12
0x1800a6fa2  jz      short loc_1800A6FB0
0x1800a6fa4  mov     [rbp+packageFullName], 0
0x1800a6fac  mov     [r12], rbx
0x1800a6fb0  lea     rcx, [rbp+hMem]; void *
0x1800a6fb4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a6fb9  lea     rcx, [rbp+packageFullName]; void *
0x1800a6fbd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a6fc2  lea     rcx, [rbp+var_40]; void *
0x1800a6fc6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a6fcb  xor     ebx, ebx
0x1800a6fcd  mov     rcx, rsi; hMem
0x1800a6fd0  call    cs:__imp_LocalFree
0x1800a6fd6  mov     eax, ebx
0x1800a6fd8  add     rsp, 78h
0x1800a6fdc  pop     r15
0x1800a6fde  pop     r14
0x1800a6fe0  pop     r13
0x1800a6fe2  pop     r12
0x1800a6fe4  pop     rdi
0x1800a6fe5  pop     rsi
0x1800a6fe6  pop     rbx
0x1800a6fe7  pop     rbp
0x1800a6fe8  retn
0x1800a6fe9  mov     r8, rdi; packageFamilyName
0x1800a6fec  lea     rdx, [rbp+packageFamilyNameLength]; packageFamilyNameLength
0x1800a6ff0  mov     rcx, rbx; packageFullName
0x1800a6ff3  call    cs:__imp_PackageFamilyNameFromFullName
0x1800a6ff9  test    eax, eax
0x1800a6ffb  jz      short loc_1800A6F80
0x1800a6ffd  mov     rcx, [rbp+40h]; this
0x1800a7001  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a7008  mov     r9d, eax; char *
0x1800a700b  mov     edx, 121h; void *
0x1800a7010  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a7015  mov     ebx, eax
0x1800a7017  jmp     loc_1800A6F23
```
