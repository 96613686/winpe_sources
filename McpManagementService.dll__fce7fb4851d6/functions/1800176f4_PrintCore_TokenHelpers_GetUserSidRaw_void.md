# PrintCore::TokenHelpers::GetUserSidRaw(void * *)

- ea: `0x1800176f4`
- end: `0x180017903`
- name: `?GetUserSidRaw@TokenHelpers@PrintCore@@SAJPEAPEAX@Z`
- size: `527`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180017614`
- `0x180023f1c`

## callees

- `0x180010d28`
- `0x180012684`
- `0x1800126c8`
- `0x1800176f4`
- `0x18001790c`
- `0x18001db04`
- `0x18001e418`
- `0x18001e470`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001775f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800177d4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001775f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800177d4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017828`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017828`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800177ef`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180017803`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180017817`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800177ef`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180017803`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180017817`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001788e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001788e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017835`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017835`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall PrintCore::TokenHelpers::GetUserSidRaw(void **a1)
{
  bool v2; // dl
  bool v3; // cl
  int UserToken; // eax
  signed int v5; // ebx
  signed int LastError; // eax
  PSID *v7; // rdi
  DWORD LengthSid; // r14d
  HLOCAL v9; // rax
  PSID v10; // rsi
  const char *v11; // r9
  __int64 result; // rax
  signed int v13; // eax
  LPVOID TokenInformation[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+88h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+90h] [rbp+18h] BYREF
  PSID pDestinationSid; // [rsp+98h] [rbp+20h] BYREF

  TokenHandle = 0;
  pDestinationSid = 0;
  TokenInformationLength = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  UserToken = PrintCore::TokenHelpers::GetUserToken(v3, v2, &TokenHandle);
  try
  {
    v5 = UserToken;
    if ( UserToken < 0 )
      goto LABEL_21;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
      {
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        else
          v5 = LastError;
      }
    }
    if ( v5 < 0 )
      goto LABEL_21;
    *(_OWORD *)TokenInformation = 0;
    v15 = 0;
    std::vector<unsigned char>::_Construct_n<>(TokenInformation, TokenInformationLength);
    if ( GetTokenInformation(
           TokenHandle,
           TokenUser,
           TokenInformation[0],
           TokenInformationLength,
           &TokenInformationLength) )
    {
      v7 = (PSID *)TokenInformation[0];
      if ( IsWellKnownSid(*(PSID *)TokenInformation[0], WinLocalSystemSid)
        || IsWellKnownSid(*v7, WinLocalServiceSid)
        || IsWellKnownSid(*v7, WinNetworkServiceSid) )
      {
        v5 = -2147417811;
        goto LABEL_20;
      }
      LengthSid = GetLengthSid(*v7);
      v9 = LocalAlloc(0, LengthSid);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &pDestinationSid,
        v9);
      v10 = pDestinationSid;
      if ( !pDestinationSid )
      {
        std::vector<unsigned char>::_Tidy(TokenInformation);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pDestinationSid);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return 2147942414LL;
      }
      if ( CopySid(LengthSid, pDestinationSid, *v7) )
      {
        pDestinationSid = 0;
        *a1 = v10;
LABEL_20:
        std::vector<unsigned char>::_Tidy(TokenInformation);
LABEL_21:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pDestinationSid);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return (unsigned int)v5;
      }
    }
    v13 = GetLastError();
    v5 = v13;
    if ( v13 > 0 )
      v5 = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_20;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x85,
                           (unsigned int)"onecoreuap\\internal\\printscan\\inc\\TokenHelpers.h",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x1800176f4  mov     rax, rsp
0x1800176f7  push    rbx
0x1800176f8  push    rsi
0x1800176f9  push    rdi
0x1800176fa  push    r14
0x1800176fc  push    r15
0x1800176fe  sub     rsp, 50h
0x180017702  mov     r15, rcx
0x180017705  mov     qword ptr [rax+18h], 0
0x18001770d  mov     qword ptr [rax+20h], 0
0x180017715  mov     dword ptr [rax+10h], 0
0x18001771c  xor     edx, edx
0x18001771e  lea     rcx, [rax+18h]
0x180017722  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180017727  lea     r8, [rsp+78h+TokenHandle]; void **
0x18001772f  call    ?GetUserToken@TokenHelpers@PrintCore@@SAJ_N0PEAPEAX@Z; PrintCore::TokenHelpers::GetUserToken(bool,bool,void * *)
0x180017734  mov     ebx, eax
0x180017736  test    eax, eax
0x180017738  js      loc_1800178D0
0x18001773e  lea     rax, [rsp+78h+TokenInformationLength]
0x180017746  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18001774b  xor     r9d, r9d; TokenInformationLength
0x18001774e  xor     r8d, r8d; TokenInformation
0x180017751  lea     edi, [r9+1]
0x180017755  mov     edx, edi; TokenInformationClass
0x180017757  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x18001775f  call    cs:__imp_GetTokenInformation
0x180017765  test    eax, eax
0x180017767  jnz     short loc_180017785
0x180017769  call    cs:__imp_GetLastError
0x18001776f  cmp     eax, 7Ah ; 'z'
0x180017772  jz      short loc_180017785
0x180017774  test    eax, eax
0x180017776  jg      short loc_18001777C
0x180017778  mov     ebx, eax
0x18001777a  jmp     short loc_180017785
0x18001777c  movzx   ebx, ax
0x18001777f  or      ebx, 80070000h
0x180017785  test    ebx, ebx
0x180017787  js      loc_1800178D0
0x18001778d  xorps   xmm0, xmm0
0x180017790  movdqu  xmmword ptr [rsp+78h+TokenInformation], xmm0
0x180017796  mov     [rsp+78h+var_38], 0
0x18001779f  mov     edx, [rsp+78h+TokenInformationLength]
0x1800177a6  lea     rcx, [rsp+78h+TokenInformation]
0x1800177ab  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x1800177b0  lea     rax, [rsp+78h+TokenInformationLength]
0x1800177b8  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1800177bd  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x1800177c5  mov     r8, [rsp+78h+TokenInformation]; TokenInformation
0x1800177ca  mov     edx, edi; TokenInformationClass
0x1800177cc  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x1800177d4  call    cs:__imp_GetTokenInformation
0x1800177da  test    eax, eax
0x1800177dc  jz      loc_1800178B0
0x1800177e2  mov     rdi, [rsp+78h+TokenInformation]
0x1800177e7  mov     edx, 16h; WellKnownSidType
0x1800177ec  mov     rcx, [rdi]; pSid
0x1800177ef  call    cs:__imp_IsWellKnownSid
0x1800177f5  test    eax, eax
0x1800177f7  jnz     loc_1800178A9
0x1800177fd  lea     edx, [rax+17h]; WellKnownSidType
0x180017800  mov     rcx, [rdi]; pSid
0x180017803  call    cs:__imp_IsWellKnownSid
0x180017809  test    eax, eax
0x18001780b  jnz     loc_1800178A9
0x180017811  lea     edx, [rax+18h]; WellKnownSidType
0x180017814  mov     rcx, [rdi]; pSid
0x180017817  call    cs:__imp_IsWellKnownSid
0x18001781d  test    eax, eax
0x18001781f  jnz     loc_1800178A9
0x180017825  mov     rcx, [rdi]; pSid
0x180017828  call    cs:__imp_GetLengthSid
0x18001782e  mov     r14d, eax
0x180017831  mov     edx, eax; uBytes
0x180017833  xor     ecx, ecx; uFlags
0x180017835  call    cs:__imp_LocalAlloc
0x18001783b  mov     rdx, rax
0x18001783e  lea     rcx, [rsp+78h+pDestinationSid]
0x180017846  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001784b  mov     rsi, [rsp+78h+pDestinationSid]
0x180017853  test    rsi, rsi
0x180017856  jnz     short loc_180017885
0x180017858  lea     rcx, [rsp+78h+TokenInformation]
0x18001785d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180017862  nop
0x180017863  lea     rcx, [rsp+78h+pDestinationSid]
0x18001786b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017870  nop
0x180017871  lea     rcx, [rsp+78h+TokenHandle]
0x180017879  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001787e  mov     eax, 8007000Eh
0x180017883  jmp     short loc_1800178F6
0x180017885  mov     r8, [rdi]; pSourceSid
0x180017888  mov     rdx, rsi; pDestinationSid
0x18001788b  mov     ecx, r14d; nDestinationSidLength
0x18001788e  call    cs:__imp_CopySid
0x180017894  test    eax, eax
0x180017896  jz      short loc_1800178B0
0x180017898  mov     [rsp+78h+pDestinationSid], 0
0x1800178a4  mov     [r15], rsi
0x1800178a7  jmp     short loc_1800178C5
0x1800178a9  mov     ebx, 8001012Dh
0x1800178ae  jmp     short loc_1800178C5
0x1800178b0  call    cs:__imp_GetLastError
0x1800178b6  test    eax, eax
0x1800178b8  mov     ebx, eax
0x1800178ba  jle     short loc_1800178C5
0x1800178bc  movzx   ebx, ax
0x1800178bf  or      ebx, 80070000h
0x1800178c5  lea     rcx, [rsp+78h+TokenInformation]
0x1800178ca  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800178cf  nop
0x1800178d0  lea     rcx, [rsp+78h+pDestinationSid]
0x1800178d8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800178dd  nop
0x1800178de  lea     rcx, [rsp+78h+TokenHandle]
0x1800178e6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800178eb  mov     eax, ebx
0x1800178ed  jmp     short loc_1800178F6
0x1800178ef  mov     eax, [rsp+78h+TokenInformationLength]
0x1800178f6  add     rsp, 50h
0x1800178fa  pop     r15
0x1800178fc  pop     r14
0x1800178fe  pop     rdi
0x1800178ff  pop     rsi
0x180017900  pop     rbx
0x180017901  retn
```
