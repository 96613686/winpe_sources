# OSIntegration::DEH::UnsignedEnforcerExtensionHandler::Verify(void)

- ea: `0x18007a3c8`
- end: `0x18007a699`
- name: `?Verify@UnsignedEnforcerExtensionHandler@DEH@OSIntegration@@AEAAJXZ`
- size: `721`
- prototype: `__int64 __fastcall(OSIntegration::DEH::UnsignedEnforcerExtensionHandler *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007a340`

## callees

- `0x18001b84c`
- `0x18007a3c8`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a219c`
- `0x1800f0260`
- `0x1800f0f0c`
- `0x1800f10e4`
- `0x1800fc0ec`
- `0x18012ba10`
- `0x1801e9484`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a4c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a4c2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007a420`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007a525`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007a420`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007a525`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18007a569`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18007a569`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18007a559`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18007a559`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageFullNameFromToken` at `0x18007a5b4`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageFullNameFromToken` at `0x18007a5b4`

## string_xrefs

- `0x18007a451`: `onecore\admin\appmodel\osim\src\deh\appx\unsignedenforcer\unsignedenforcerextensionhandler.cpp`
- `0x18007a469`: `onecore\admin\appmodel\osim\src\deh\appx\unsignedenforcer\unsignedenforcerextensionhandler.cpp`
- `0x18007a600`: `onecore\admin\appmodel\osim\src\deh\appx\unsignedenforcer\unsignedenforcerextensionhandler.cpp`
- `0x18007a683`: `onecore\admin\appmodel\osim\src\deh\appx\unsignedenforcer\unsignedenforcerextensionhandler.cpp`
- `0x18007a432`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18007a4ed`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18007a533`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OSIntegration::DEH::UnsignedEnforcerExtensionHandler::Verify(
        OSIntegration::DEH::UnsignedEnforcerExtensionHandler *this)
{
  __int64 v1; // rax
  PSID *v2; // rbx
  __int64 v4; // rdi
  const char *v5; // r9
  unsigned int LastError; // edi
  unsigned int v8; // ebx
  __int64 v9; // rdx
  PSID *v10; // rsi
  const char *v11; // r9
  PUCHAR SidSubAuthorityCount; // rax
  DWORD v13; // edi
  __int64 v14; // rcx
  LONG PackageFullNameFromToken; // eax
  const unsigned __int16 *v16; // r9
  int v17; // eax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageFullNameLength; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR *v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR packageFullName[128]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v1 = *((_QWORD *)this + 4);
  v2 = 0;
  TokenInformationLength = 0;
  v4 = -6;
  if ( *(_QWORD *)(v1 + 48) )
    v4 = *(_QWORD *)(v1 + 48);
  if ( GetTokenInformation((HANDLE)v4, TokenIntegrityLevel, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v5);
  }
  else
  {
    v10 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
    if ( !v10 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLength);
      goto LABEL_6;
    }
    if ( GetTokenInformation((HANDLE)v4, TokenIntegrityLevel, v10, TokenInformationLength, &TokenInformationLength) )
    {
      v2 = v10;
      goto LABEL_17;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v11);
    operator delete(v10);
  }
  if ( (LastError & 0x80000000) != 0 )
  {
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\unsignedenforcer\\unsignedenforcerextensionhandler.cpp",
      (const char *)LastError,
      ReturnLength);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\unsignedenforcer\\unsignedenforcerextensionhandler.cpp",
      (const char *)LastError,
      ReturnLengtha);
    return LastError;
  }
LABEL_17:
  SidSubAuthorityCount = GetSidSubAuthorityCount(*v2);
  v13 = *GetSidSubAuthority(*v2, (unsigned __int8)(*SidSubAuthorityCount - 1));
  operator delete(v2);
  if ( v13 >= 0x2000 )
    return 0;
  memset_0(packageFullName, 0, sizeof(packageFullName));
  v14 = *((_QWORD *)this + 4);
  packageFullNameLength = 128;
  PackageFullNameFromToken = GetPackageFullNameFromToken(*(HANDLE *)(v14 + 48), &packageFullNameLength, packageFullName);
  v8 = PackageFullNameFromToken;
  if ( PackageFullNameFromToken )
  {
    if ( PackageFullNameFromToken != 15700 )
    {
      if ( PackageFullNameFromToken > 0 )
        v8 = (unsigned __int16)PackageFullNameFromToken | 0x80070000;
      if ( (v8 & 0x80000000) == 0 )
        return v8;
      v9 = 123;
      goto LABEL_27;
    }
    goto LABEL_24;
  }
  v17 = PackageRequiresCustomCapability(
          packageFullName,
          *((struct PackageRepository::IRepositorySession **)this + 3),
          *(void **)(*((_QWORD *)this + 4) + 48LL),
          v16);
  v8 = v17;
  if ( v17 == -2147024436 )
  {
LABEL_24:
    v8 = -2147024891;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\unsignedenforcer\\unsignedenforcerextensionhandler.cpp",
      (const char *)0x80070005LL,
      ReturnLength);
    if ( (byte_1802E21C1 & 0x10) != 0 )
      McTemplateU0dz_EventWriteTransfer(
        &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
        &UnsignedAccessDenied,
        v13,
        packageFullName);
    TokenInformationLength = v13;
    v22 = packageFullName;
    SetAppXErrorFromLogMessage(
      -2147024891,
      &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
      &UnsignedAccessDenied,
      2u,
      &TokenInformationLength,
      &v22);
    v9 = 132;
    goto LABEL_27;
  }
  if ( v17 < 0 )
  {
    v9 = 119;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\unsignedenforcer\\unsignedenforcerextensionhandler.cpp",
      (const char *)v8,
      ReturnLength);
  }
  return v8;
}

```

## disassembly

```asm
0x18007a3c8  mov     [rsp-8+arg_8], rbx
0x18007a3cd  mov     [rsp-8+arg_10], rsi
0x18007a3d2  push    rbp
0x18007a3d3  push    rdi
0x18007a3d4  push    r14
0x18007a3d6  lea     rbp, [rsp-60h]
0x18007a3db  sub     rsp, 160h
0x18007a3e2  mov     rax, cs:__security_cookie
0x18007a3e9  xor     rax, rsp
0x18007a3ec  mov     [rbp+70h+var_20], rax
0x18007a3f0  mov     rax, [rcx+20h]
0x18007a3f4  xor     ebx, ebx
0x18007a3f6  mov     r14, rcx
0x18007a3f9  mov     [rsp+170h+TokenInformationLength], ebx
0x18007a3fd  cmp     [rax+30h], rbx
0x18007a401  lea     rdi, [rbx-6]
0x18007a405  lea     edx, [rbx+19h]; TokenInformationClass
0x18007a408  cmovnz  rdi, [rax+30h]
0x18007a40d  lea     rax, [rsp+170h+TokenInformationLength]
0x18007a412  mov     rcx, rdi; TokenHandle
0x18007a415  mov     [rsp+170h+ReturnLength], rax; int
0x18007a41a  xor     r9d, r9d; TokenInformationLength
0x18007a41d  xor     r8d, r8d; TokenInformation
0x18007a420  call    cs:__imp_GetTokenInformation
0x18007a426  test    eax, eax
0x18007a428  jz      loc_18007A4C2
0x18007a42e  mov     rcx, [rbp+78h]; this
0x18007a432  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007a439  mov     edx, 117h; void *
0x18007a43e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007a443  mov     edi, eax
0x18007a445  test    edi, edi
0x18007a447  jns     loc_18007A556
0x18007a44d  mov     rcx, [rbp+78h]; this
0x18007a451  lea     r8, aOnecoreAdminAp_106; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007a458  mov     r9d, edi; char *
0x18007a45b  mov     edx, 8Ch; void *
0x18007a460  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a465  mov     rcx, [rbp+78h]; this
0x18007a469  lea     r8, aOnecoreAdminAp_106; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007a470  mov     r9d, edi; char *
0x18007a473  mov     edx, 69h ; 'i'; void *
0x18007a478  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a47d  mov     eax, edi
0x18007a47f  mov     rcx, [rbp+70h+var_20]
0x18007a483  xor     rcx, rsp; StackCookie
0x18007a486  call    __security_check_cookie
0x18007a48b  lea     r11, [rsp+170h+var_10]
0x18007a493  mov     rbx, [r11+28h]
0x18007a497  mov     rsi, [r11+30h]
0x18007a49b  mov     rsp, r11
0x18007a49e  pop     r14
0x18007a4a0  pop     rdi
0x18007a4a1  pop     rbp
0x18007a4a2  retn
0x18007a4a3  test    eax, eax
0x18007a4a5  jle     short loc_18007A4B0
0x18007a4a7  movzx   ebx, ax
0x18007a4aa  or      ebx, 80070000h
0x18007a4b0  test    ebx, ebx
0x18007a4b2  jns     loc_18007A692
0x18007a4b8  mov     edx, 7Bh ; '{'
0x18007a4bd  jmp     loc_18007A67F
0x18007a4c2  call    cs:__imp_GetLastError
0x18007a4c8  cmp     eax, 7Ah ; 'z'
0x18007a4cb  jnz     loc_18007A42E
0x18007a4d1  mov     ecx, [rsp+170h+TokenInformationLength]; unsigned __int64
0x18007a4d5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007a4dc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007a4e1  mov     rsi, rax
0x18007a4e4  test    rax, rax
0x18007a4e7  jnz     short loc_18007A50B
0x18007a4e9  mov     rcx, [rbp+78h]; this
0x18007a4ed  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007a4f4  mov     edi, 8007000Eh
0x18007a4f9  mov     edx, 119h; void *
0x18007a4fe  mov     r9d, edi; char *
0x18007a501  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a506  jmp     loc_18007A44D
0x18007a50b  mov     r9d, [rsp+170h+TokenInformationLength]; TokenInformationLength
0x18007a510  lea     rax, [rsp+170h+TokenInformationLength]
0x18007a515  mov     r8, rsi; TokenInformation
0x18007a518  mov     [rsp+170h+ReturnLength], rax; int
0x18007a51d  mov     edx, 19h; TokenInformationClass
0x18007a522  mov     rcx, rdi; TokenHandle
0x18007a525  call    cs:__imp_GetTokenInformation
0x18007a52b  test    eax, eax
0x18007a52d  jnz     short loc_18007A553
0x18007a52f  mov     rcx, [rbp+78h]; this
0x18007a533  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007a53a  mov     edx, 11Ah; void *
0x18007a53f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007a544  mov     rcx, rsi; Block
0x18007a547  mov     edi, eax
0x18007a549  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007a54e  jmp     loc_18007A445
0x18007a553  mov     rbx, rsi
0x18007a556  mov     rcx, [rbx]; pSid
0x18007a559  call    cs:__imp_GetSidSubAuthorityCount
0x18007a55f  mov     rcx, [rbx]; pSid
0x18007a562  mov     dl, [rax]
0x18007a564  dec     dl
0x18007a566  movzx   edx, dl; nSubAuthority
0x18007a569  call    cs:__imp_GetSidSubAuthority
0x18007a56f  mov     rcx, rbx; Block
0x18007a572  mov     edi, [rax]
0x18007a574  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007a579  cmp     edi, 2000h
0x18007a57f  jb      short loc_18007A588
0x18007a581  xor     eax, eax
0x18007a583  jmp     loc_18007A47F
0x18007a588  xor     edx, edx; Val
0x18007a58a  lea     rcx, [rsp+170h+packageFullName]; void *
0x18007a58f  mov     r8d, 100h; Size
0x18007a595  call    memset_0
0x18007a59a  mov     rcx, [r14+20h]
0x18007a59e  lea     r8, [rsp+170h+packageFullName]; packageFullName
0x18007a5a3  mov     [rsp+170h+packageFullNameLength], 80h
0x18007a5ab  lea     rdx, [rsp+170h+packageFullNameLength]; packageFullNameLength
0x18007a5b0  mov     rcx, [rcx+30h]; token
0x18007a5b4  call    cs:__imp_GetPackageFullNameFromToken
0x18007a5ba  mov     ebx, eax
0x18007a5bc  test    eax, eax
0x18007a5be  jnz     short loc_18007A5F1
0x18007a5c0  mov     r8, [r14+20h]
0x18007a5c4  lea     rcx, [rsp+170h+packageFullName]; unsigned __int16 *
0x18007a5c9  mov     rdx, [r14+18h]; struct PackageRepository::IRepositorySession *
0x18007a5cd  mov     r8, [r8+30h]; void *
0x18007a5d1  call    ?PackageRequiresCustomCapability@@YAJPEBGAEAVIRepositorySession@PackageRepository@@PEAX0@Z; PackageRequiresCustomCapability(ushort const *,PackageRepository::IRepositorySession &,void *,ushort const *)
0x18007a5d6  mov     ebx, eax
0x18007a5d8  cmp     eax, 800701CCh
0x18007a5dd  jz      short loc_18007A5FC
0x18007a5df  test    eax, eax
0x18007a5e1  jns     loc_18007A692
0x18007a5e7  mov     edx, 77h ; 'w'
0x18007a5ec  jmp     loc_18007A67F
0x18007a5f1  cmp     eax, 3D54h
0x18007a5f6  jnz     loc_18007A4A3
0x18007a5fc  mov     rcx, [rbp+78h]; this
0x18007a600  lea     r8, aOnecoreAdminAp_106; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007a607  mov     ebx, 80070005h
0x18007a60c  mov     edx, 83h; void *
0x18007a611  mov     r9d, ebx; char *
0x18007a614  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007a619  test    cs:byte_1802E21C1, 10h
0x18007a620  jz      short loc_18007A63D
0x18007a622  lea     r9, [rsp+170h+packageFullName]
0x18007a627  mov     r8d, edi
0x18007a62a  lea     rdx, UnsignedAccessDenied
0x18007a631  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x18007a638  call    McTemplateU0dz_EventWriteTransfer
0x18007a63d  lea     rcx, [rsp+170h+var_130]
0x18007a642  mov     [rsp+170h+TokenInformationLength], edi
0x18007a646  mov     [rsp+170h+var_148], rcx
0x18007a64b  lea     rax, [rsp+170h+packageFullName]
0x18007a650  lea     rcx, [rsp+170h+TokenInformationLength]
0x18007a655  mov     [rsp+170h+var_130], rax
0x18007a65a  mov     [rsp+170h+ReturnLength], rcx; int
0x18007a65f  lea     r8, UnsignedAccessDenied; struct _EVENT_DESCRIPTOR *
0x18007a666  mov     ecx, ebx; int
0x18007a668  lea     rdx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID; struct _GUID *
0x18007a66f  mov     r9d, 2; unsigned int
0x18007a675  call    ?SetAppXErrorFromLogMessage@@YAJJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@KZZ; SetAppXErrorFromLogMessage(long,_GUID const &,_EVENT_DESCRIPTOR const &,ulong,...)
0x18007a67a  mov     edx, 84h; void *
0x18007a67f  mov     rcx, [rbp+78h]; this
0x18007a683  lea     r8, aOnecoreAdminAp_106; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007a68a  mov     r9d, ebx; char *
0x18007a68d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a692  mov     eax, ebx
0x18007a694  jmp     loc_18007A47F
```
