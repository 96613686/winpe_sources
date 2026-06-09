# PrintCore::TokenHelpers::GetUserSidRaw(void * *)

- ea: `0x1800317bc`
- end: `0x1800319b9`
- name: `?GetUserSidRaw@TokenHelpers@PrintCore@@SAJPEAPEAX@Z`
- size: `509`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003161c`

## callees

- `0x18001255c`
- `0x1800230fc`
- `0x180023264`
- `0x1800264dc`
- `0x180027020`
- `0x1800317bc`
- `0x1800319c0`
- `0x1800328d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031966`
- `KERNELBASE!LocalAlloc` at `0x1800318eb`
- `KERNELBASE!LocalAlloc` at `0x1800318eb`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800318a5`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800318b9`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800318cd`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800318a5`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800318b9`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800318cd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180031944`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180031944`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800318de`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800318de`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031827`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003188a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031827`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003188a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintCore::TokenHelpers::GetUserSidRaw(void **a1)
{
  bool v2; // dl
  bool v3; // cl
  int UserToken; // eax
  signed int v5; // ebx
  signed int LastError; // eax
  PSID *v7; // rdi
  SIZE_T LengthSid; // r14
  HLOCAL v9; // rax
  PSID v10; // rsi
  const char *v11; // r9
  __int64 result; // rax
  signed int v13; // eax
  LPVOID TokenInformation[9]; // [rsp+30h] [rbp-48h] BYREF
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
    std::vector<unsigned char>::vector<unsigned char>(TokenInformation, TokenInformationLength);
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
                           (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\TokenHelpers.h",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x1800317bc  mov     rax, rsp
0x1800317bf  push    rbx
0x1800317c0  push    rsi
0x1800317c1  push    rdi
0x1800317c2  push    r14
0x1800317c4  push    r15
0x1800317c6  sub     rsp, 50h
0x1800317ca  mov     r15, rcx
0x1800317cd  mov     qword ptr [rax+18h], 0
0x1800317d5  mov     qword ptr [rax+20h], 0
0x1800317dd  mov     dword ptr [rax+10h], 0
0x1800317e4  xor     edx, edx
0x1800317e6  lea     rcx, [rax+18h]
0x1800317ea  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800317ef  lea     r8, [rsp+78h+TokenHandle]; void **
0x1800317f7  call    ?GetUserToken@TokenHelpers@PrintCore@@SAJ_N0PEAPEAX@Z; PrintCore::TokenHelpers::GetUserToken(bool,bool,void * *)
0x1800317fc  mov     ebx, eax
0x1800317fe  test    eax, eax
0x180031800  js      loc_180031986
0x180031806  lea     rax, [rsp+78h+TokenInformationLength]
0x18003180e  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180031813  xor     r9d, r9d; TokenInformationLength
0x180031816  xor     r8d, r8d; TokenInformation
0x180031819  lea     edi, [r9+1]
0x18003181d  mov     edx, edi; TokenInformationClass
0x18003181f  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x180031827  call    cs:__imp_GetTokenInformation
0x18003182d  test    eax, eax
0x18003182f  jnz     short loc_18003184D
0x180031831  call    cs:__imp_GetLastError
0x180031837  cmp     eax, 7Ah ; 'z'
0x18003183a  jz      short loc_18003184D
0x18003183c  test    eax, eax
0x18003183e  jg      short loc_180031844
0x180031840  mov     ebx, eax
0x180031842  jmp     short loc_18003184D
0x180031844  movzx   ebx, ax
0x180031847  or      ebx, 80070000h
0x18003184d  test    ebx, ebx
0x18003184f  js      loc_180031986
0x180031855  mov     edx, [rsp+78h+TokenInformationLength]
0x18003185c  lea     rcx, [rsp+78h+TokenInformation]
0x180031861  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180031866  lea     rax, [rsp+78h+TokenInformationLength]
0x18003186e  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180031873  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x18003187b  mov     r8, [rsp+78h+TokenInformation]; TokenInformation
0x180031880  mov     edx, edi; TokenInformationClass
0x180031882  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x18003188a  call    cs:__imp_GetTokenInformation
0x180031890  test    eax, eax
0x180031892  jz      loc_180031966
0x180031898  mov     rdi, [rsp+78h+TokenInformation]
0x18003189d  mov     edx, 16h; WellKnownSidType
0x1800318a2  mov     rcx, [rdi]; pSid
0x1800318a5  call    cs:__imp_IsWellKnownSid
0x1800318ab  test    eax, eax
0x1800318ad  jnz     loc_18003195F
0x1800318b3  lea     edx, [rax+17h]; WellKnownSidType
0x1800318b6  mov     rcx, [rdi]; pSid
0x1800318b9  call    cs:__imp_IsWellKnownSid
0x1800318bf  test    eax, eax
0x1800318c1  jnz     loc_18003195F
0x1800318c7  lea     edx, [rax+18h]; WellKnownSidType
0x1800318ca  mov     rcx, [rdi]; pSid
0x1800318cd  call    cs:__imp_IsWellKnownSid
0x1800318d3  test    eax, eax
0x1800318d5  jnz     loc_18003195F
0x1800318db  mov     rcx, [rdi]; pSid
0x1800318de  call    cs:__imp_GetLengthSid
0x1800318e4  mov     r14d, eax
0x1800318e7  mov     edx, eax; uBytes
0x1800318e9  xor     ecx, ecx; uFlags
0x1800318eb  call    cs:__imp_LocalAlloc
0x1800318f1  mov     rdx, rax
0x1800318f4  lea     rcx, [rsp+78h+pDestinationSid]
0x1800318fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180031901  mov     rsi, [rsp+78h+pDestinationSid]
0x180031909  test    rsi, rsi
0x18003190c  jnz     short loc_18003193B
0x18003190e  lea     rcx, [rsp+78h+TokenInformation]
0x180031913  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180031918  nop
0x180031919  lea     rcx, [rsp+78h+pDestinationSid]
0x180031921  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180031926  nop
0x180031927  lea     rcx, [rsp+78h+TokenHandle]
0x18003192f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031934  mov     eax, 8007000Eh
0x180031939  jmp     short loc_1800319AC
0x18003193b  mov     r8, [rdi]; pSourceSid
0x18003193e  mov     rdx, rsi; pDestinationSid
0x180031941  mov     ecx, r14d; nDestinationSidLength
0x180031944  call    cs:__imp_CopySid
0x18003194a  test    eax, eax
0x18003194c  jz      short loc_180031966
0x18003194e  mov     [rsp+78h+pDestinationSid], 0
0x18003195a  mov     [r15], rsi
0x18003195d  jmp     short loc_18003197B
0x18003195f  mov     ebx, 8001012Dh
0x180031964  jmp     short loc_18003197B
0x180031966  call    cs:__imp_GetLastError
0x18003196c  test    eax, eax
0x18003196e  mov     ebx, eax
0x180031970  jle     short loc_18003197B
0x180031972  movzx   ebx, ax
0x180031975  or      ebx, 80070000h
0x18003197b  lea     rcx, [rsp+78h+TokenInformation]
0x180031980  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180031985  nop
0x180031986  lea     rcx, [rsp+78h+pDestinationSid]
0x18003198e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180031993  nop
0x180031994  lea     rcx, [rsp+78h+TokenHandle]
0x18003199c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800319a1  mov     eax, ebx
0x1800319a3  jmp     short loc_1800319AC
0x1800319a5  mov     eax, [rsp+78h+TokenInformationLength]
0x1800319ac  add     rsp, 50h
0x1800319b0  pop     r15
0x1800319b2  pop     r14
0x1800319b4  pop     rdi
0x1800319b5  pop     rsi
0x1800319b6  pop     rbx
0x1800319b7  retn
```
