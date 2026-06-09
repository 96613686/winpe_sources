# AiCheckForAdminUser(void *,int,int *)

- ea: `0x180016a40`
- end: `0x180016d9e`
- name: `?AiCheckForAdminUser@@YAJPEAXHPEAH@Z`
- size: `862`
- prototype: `__int64 __fastcall(HANDLE Handle, int, int *)`
- caller_count: `7`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016da4`
- `0x180016fa0`
- `0x180025940`
- `0x18002a1d8`
- `0x18003a8b0`
- `0x18003db90`
- `0x18003e094`

## callees

- `0x180007c78`
- `0x180016a40`
- `0x180018400`
- `0x18001b494`
- `0x18001bc74`
- `0x180043690`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016b0c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016b84`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016b0c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016b84`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016d0a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b20`
- `ntdll!NtClose` at `0x180016d4a`
- `ntdll!NtClose` at `0x180016d77`
- `ntdll!NtClose` at `0x180016d4a`
- `ntdll!NtClose` at `0x180016d77`
- `ntdll!NtQueryInformationToken` at `0x180016c76`
- `ntdll!NtQueryInformationToken` at `0x180016c76`
- `ntdll!RtlEqualSid` at `0x180016bee`
- `ntdll!RtlEqualSid` at `0x180016bee`
- `ntdll!RtlGetLastNtStatus` at `0x180016c30`
- `ntdll!RtlGetLastNtStatus` at `0x180016c30`
- `ntdll!RtlQueryElevationFlags` at `0x180016ac3`
- `ntdll!RtlQueryElevationFlags` at `0x180016ac3`
- `ntdll!NtDuplicateToken` at `0x180016ce6`
- `ntdll!NtDuplicateToken` at `0x180016ce6`

## string_xrefs

- `0x180016b50`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180016b98`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180016c17`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall AiCheckForAdminUser(HANDLE Handle, int a2, int *a3)
{
  int LastStatusValue; // esi
  HANDLE v6; // r14
  __int64 v7; // r15
  _QWORD *v8; // rbx
  const char *v9; // r9
  void *v10; // rdi
  const char *v11; // r9
  int LastError; // r15d
  unsigned int v13; // edi
  __int64 v14; // rcx
  NTSTATUS v15; // eax
  int ReturnLength; // [rsp+28h] [rbp-59h]
  DWORD TokenInformationLength; // [rsp+38h] [rbp-49h] BYREF
  void *NewTokenHandle; // [rsp+40h] [rbp-41h] BYREF
  ULONG v20; // [rsp+48h] [rbp-39h] BYREF
  void *TokenInformation; // [rsp+50h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-29h] BYREF
  __int64 v23; // [rsp+88h] [rbp+7h] BYREF
  int v24; // [rsp+90h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  NewTokenHandle = 0;
  LastStatusValue = 0;
  TokenInformation = 0;
  v6 = Handle;
  v20 = 0;
  v23 = 0;
  v24 = 0;
  *a3 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a2 )
  {
LABEL_29:
    v23 = 0x20000000CLL;
    ObjectAttributes.SecurityQualityOfService = &v23;
    LOWORD(v24) = 1;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    ObjectAttributes.SecurityDescriptor = 0;
    LastStatusValue = NtDuplicateToken(v6, 0, &ObjectAttributes, 0, TokenImpersonation, &NewTokenHandle);
    if ( LastStatusValue >= 0 && !CheckTokenMembership(NewTokenHandle, *((PSID *)g_pSvchostSharedGlobals + 10), a3) )
      LastStatusValue = NtCurrentTeb()->LastStatusValue;
    goto LABEL_32;
  }
  TokenInformationLength = 0;
  if ( !(unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline()
    || (int)RtlQueryElevationFlags(&TokenInformationLength) < 0
    || (TokenInformationLength & 0x18) != 0x10 )
  {
    v15 = NtQueryInformationToken(Handle, TokenLinkedToken, &TokenInformation, 8u, &v20);
    if ( v15 < 0 )
    {
      if ( v15 != -1073741729 )
        LastStatusValue = v15;
      goto LABEL_32;
    }
    v6 = TokenInformation;
    goto LABEL_29;
  }
  TokenInformationLength = 0;
  v7 = -6;
  if ( v6 )
    v7 = (__int64)v6;
  v8 = 0;
  if ( GetTokenInformation((HANDLE)v7, TokenGroupsAndPrivileges, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v9);
LABEL_20:
    if ( LastError < 0 )
      goto LABEL_21;
    goto LABEL_14;
  }
  v10 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
LABEL_21:
    LastStatusValue = RtlGetLastNtStatus();
    goto LABEL_32;
  }
  if ( !GetTokenInformation((HANDLE)v7, TokenGroupsAndPrivileges, v10, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v11);
    operator delete(v10);
    goto LABEL_20;
  }
  v8 = v10;
LABEL_14:
  v13 = 0;
  if ( *(_DWORD *)v8 )
  {
    while ( 1 )
    {
      v14 = v8[1] + 16LL * v13;
      if ( (*(_BYTE *)(v14 + 8) & 0x10) != 0 )
      {
        if ( RtlEqualSid(*(PSID *)v14, *((PSID *)g_pSvchostSharedGlobals + 10)) )
          break;
      }
      if ( ++v13 >= *(_DWORD *)v8 )
        goto LABEL_18;
    }
    *a3 = 1;
  }
LABEL_18:
  operator delete(v8);
LABEL_32:
  if ( NewTokenHandle )
  {
    NtClose(NewTokenHandle);
    NewTokenHandle = 0;
  }
  if ( v6 != Handle && v6 )
    NtClose(v6);
  return (unsigned int)LastStatusValue;
}

```

## disassembly

```asm
0x180016a40  mov     r11, rsp
0x180016a43  push    rbp
0x180016a44  push    rsi
0x180016a45  push    r14
0x180016a47  lea     rbp, [r11-5Fh]
0x180016a4b  sub     rsp, 0C0h
0x180016a52  mov     rax, cs:__security_cookie
0x180016a59  xor     rax, rsp
0x180016a5c  mov     [rbp+57h+var_40], rax
0x180016a60  mov     [r11+10h], rbx
0x180016a64  xor     eax, eax
0x180016a66  mov     [r11-20h], rdi
0x180016a6a  xorps   xmm0, xmm0
0x180016a6d  xor     edi, edi
0x180016a6f  mov     [r11-28h], r12
0x180016a73  mov     [r11-30h], r13
0x180016a77  mov     r13, r8
0x180016a7a  mov     [r11-38h], r15
0x180016a7e  mov     r12, rcx
0x180016a81  mov     [rbp+57h+NewTokenHandle], rdi
0x180016a85  mov     esi, edi
0x180016a87  mov     [rbp+57h+TokenInformation], rdi
0x180016a8b  mov     r14, rcx
0x180016a8e  mov     [rbp+57h+var_90], edi
0x180016a91  mov     [rbp+57h+var_50], rax
0x180016a95  mov     [rbp+57h+var_48], eax
0x180016a98  mov     [r8], edi
0x180016a9b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180016a9f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180016aa3  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180016aa7  test    edx, edx
0x180016aa9  jnz     loc_180016C97
0x180016aaf  mov     [rbp+57h+TokenInformationLength], edi
0x180016ab2  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x180016ab7  test    eax, eax
0x180016ab9  jz      loc_180016C5C
0x180016abf  lea     rcx, [rbp+57h+TokenInformationLength]
0x180016ac3  call    cs:__imp_RtlQueryElevationFlags
0x180016aca  nop     dword ptr [rax+rax+00h]
0x180016acf  test    eax, eax
0x180016ad1  js      loc_180016C5C
0x180016ad7  mov     eax, [rbp+57h+TokenInformationLength]
0x180016ada  and     al, 18h
0x180016adc  cmp     al, 10h
0x180016ade  jnz     loc_180016C5C
0x180016ae4  lea     rax, [rbp+57h+TokenInformationLength]
0x180016ae8  mov     [rbp+57h+TokenInformationLength], edi
0x180016aeb  test    r14, r14
0x180016aee  mov     qword ptr [rsp+0D0h+ReturnLength], rax; int
0x180016af3  mov     r15, 0FFFFFFFFFFFFFFFAh
0x180016afa  lea     edx, [rdi+0Dh]; TokenInformationClass
0x180016afd  cmovnz  r15, r14
0x180016b01  mov     ebx, edi
0x180016b03  mov     rcx, r15; TokenHandle
0x180016b06  xor     r9d, r9d; TokenInformationLength
0x180016b09  xor     r8d, r8d; TokenInformation
0x180016b0c  call    cs:__imp_GetTokenInformation
0x180016b13  nop     dword ptr [rax+rax+00h]
0x180016b18  test    eax, eax
0x180016b1a  jnz     loc_180016C13
0x180016b20  call    cs:__imp_GetLastError
0x180016b27  nop     dword ptr [rax+rax+00h]
0x180016b2c  cmp     eax, 7Ah ; 'z'
0x180016b2f  jnz     loc_180016C13
0x180016b35  mov     ecx, [rbp+57h+TokenInformationLength]; unsigned __int64
0x180016b38  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016b3f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016b44  mov     rdi, rax
0x180016b47  test    rax, rax
0x180016b4a  jnz     short loc_180016B6C
0x180016b4c  mov     rcx, [rbp+5Fh]; this
0x180016b50  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016b57  mov     r9d, 8007000Eh; char *
0x180016b5d  mov     edx, 119h; void *
0x180016b62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b67  jmp     loc_180016C30
0x180016b6c  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180016b70  lea     rax, [rbp+57h+TokenInformationLength]
0x180016b74  mov     r8, rdi; TokenInformation
0x180016b77  mov     qword ptr [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180016b7c  mov     edx, 0Dh; TokenInformationClass
0x180016b81  mov     rcx, r15; TokenHandle
0x180016b84  call    cs:__imp_GetTokenInformation
0x180016b8b  nop     dword ptr [rax+rax+00h]
0x180016b90  test    eax, eax
0x180016b92  jnz     short loc_180016BB6
0x180016b94  mov     rcx, [rbp+5Fh]; this
0x180016b98  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016b9f  mov     edx, 11Ah; void *
0x180016ba4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016ba9  mov     rcx, rdi; Block
0x180016bac  mov     r15d, eax
0x180016baf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016bb4  jmp     short loc_180016C2B
0x180016bb6  mov     rbx, rdi
0x180016bb9  xor     edi, edi
0x180016bbb  cmp     [rbx], esi
0x180016bbd  jbe     loc_180016C4D
0x180016bc3  nop     dword ptr [rax+00h]
0x180016bc7  nop     word ptr [rax+rax+00000000h]
0x180016bd0  mov     ecx, edi
0x180016bd2  shl     rcx, 4
0x180016bd6  add     rcx, [rbx+8]
0x180016bda  test    byte ptr [rcx+8], 10h
0x180016bde  jz      short loc_180016BFE
0x180016be0  mov     rdx, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x180016be7  mov     rcx, [rcx]; Sid1
0x180016bea  mov     rdx, [rdx+50h]; Sid2
0x180016bee  call    cs:__imp_RtlEqualSid
0x180016bf5  nop     dword ptr [rax+rax+00h]
0x180016bfa  test    al, al
0x180016bfc  jnz     short loc_180016C45
0x180016bfe  inc     edi
0x180016c00  cmp     edi, [rbx]
0x180016c02  jb      short loc_180016BD0
0x180016c04  mov     rcx, rbx; Block
0x180016c07  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016c0c  xor     edi, edi
0x180016c0e  jmp     loc_180016D29
0x180016c13  mov     rcx, [rbp+5Fh]; this
0x180016c17  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016c1e  mov     edx, 117h; void *
0x180016c23  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016c28  mov     r15d, eax
0x180016c2b  test    r15d, r15d
0x180016c2e  jns     short loc_180016BB9
0x180016c30  call    cs:__imp_RtlGetLastNtStatus
0x180016c37  nop     dword ptr [rax+rax+00h]
0x180016c3c  mov     esi, eax
0x180016c3e  xor     edi, edi
0x180016c40  jmp     loc_180016D29
0x180016c45  mov     dword ptr [r13+0], 1
0x180016c4d  mov     rcx, rbx; Block
0x180016c50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016c55  xor     edi, edi
0x180016c57  jmp     loc_180016D29
0x180016c5c  mov     r9d, 8; TokenInformationLength
0x180016c62  lea     rax, [rbp+57h+var_90]
0x180016c66  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180016c6a  mov     qword ptr [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180016c6f  mov     rcx, r12; TokenHandle
0x180016c72  lea     edx, [r9+0Bh]; TokenInformationClass
0x180016c76  call    cs:__imp_NtQueryInformationToken
0x180016c7d  nop     dword ptr [rax+rax+00h]
0x180016c82  test    eax, eax
0x180016c84  jns     short loc_180016C93
0x180016c86  cmp     eax, 0C000005Fh
0x180016c8b  cmovnz  esi, eax
0x180016c8e  jmp     loc_180016D29
0x180016c93  mov     r14, [rbp+57h+TokenInformation]
0x180016c97  lea     rax, [rbp+57h+var_50]
0x180016c9b  mov     dword ptr [rbp+57h+var_50], 0Ch
0x180016ca2  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x180016ca6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180016caa  lea     rax, [rbp+57h+NewTokenHandle]
0x180016cae  mov     dword ptr [rbp+57h+var_50+4], 2
0x180016cb5  mov     qword ptr [rsp+0D0h+ReturnLength+8], rax; NewTokenHandle
0x180016cba  xor     r9d, r9d; EffectiveOnly
0x180016cbd  xor     edx, edx; DesiredAccess
0x180016cbf  mov     [rsp+0D0h+ReturnLength], 2; TokenType
0x180016cc7  mov     rcx, r14; ExistingTokenHandle
0x180016cca  mov     word ptr [rbp+57h+var_48], 1
0x180016cd0  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180016cd7  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180016cdb  mov     [rbp+57h+ObjectAttributes.Attributes], edi
0x180016cde  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x180016ce2  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rdi
0x180016ce6  call    cs:__imp_NtDuplicateToken
0x180016ced  nop     dword ptr [rax+rax+00h]
0x180016cf2  mov     esi, eax
0x180016cf4  test    eax, eax
0x180016cf6  js      short loc_180016D29
0x180016cf8  mov     rdx, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x180016cff  mov     r8, r13; IsMember
0x180016d02  mov     rcx, [rbp+57h+NewTokenHandle]; TokenHandle
0x180016d06  mov     rdx, [rdx+50h]; SidToCheck
0x180016d0a  call    cs:__imp_CheckTokenMembership
0x180016d11  nop     dword ptr [rax+rax+00h]
0x180016d16  test    eax, eax
0x180016d18  jnz     short loc_180016D29
0x180016d1a  mov     rax, gs:30h
0x180016d23  mov     esi, [rax+1250h]
0x180016d29  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x180016d2d  mov     r15, [rsp+0D0h+var_30]
0x180016d35  mov     r13, [rsp+0D0h+var_28]
0x180016d3d  mov     rbx, [rsp+0D0h+arg_8]
0x180016d45  test    rcx, rcx
0x180016d48  jz      short loc_180016D5A
0x180016d4a  call    cs:__imp_NtClose
0x180016d51  nop     dword ptr [rax+rax+00h]
0x180016d56  mov     [rbp+57h+NewTokenHandle], rdi
0x180016d5a  mov     rdi, [rsp+0B8h]
0x180016d62  cmp     r14, r12
0x180016d65  mov     r12, [rsp+0D0h+var_20]
0x180016d6d  jz      short loc_180016D83
0x180016d6f  test    r14, r14
0x180016d72  jz      short loc_180016D83
0x180016d74  mov     rcx, r14; Handle
0x180016d77  call    cs:__imp_NtClose
0x180016d7e  nop     dword ptr [rax+rax+00h]
0x180016d83  mov     eax, esi
0x180016d85  mov     rcx, [rbp+57h+var_40]
0x180016d89  xor     rcx, rsp; StackCookie
0x180016d8c  call    __security_check_cookie
0x180016d91  add     rsp, 0C0h
0x180016d98  pop     r14
0x180016d9a  pop     rsi
0x180016d9b  pop     rbp
0x180016d9c  retn
```
