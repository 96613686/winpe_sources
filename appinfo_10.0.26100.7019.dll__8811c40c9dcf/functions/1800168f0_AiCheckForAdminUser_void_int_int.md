# AiCheckForAdminUser(void *,int,int *)

- ea: `0x1800168f0`
- end: `0x180016c4e`
- name: `?AiCheckForAdminUser@@YAJPEAXHPEAH@Z`
- size: `862`
- prototype: `__int64 __fastcall(HANDLE Handle, int, int *)`
- caller_count: `7`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001362c`
- `0x180016c54`
- `0x180026f80`
- `0x18002b828`
- `0x180039cb0`
- `0x18003bfe0`
- `0x18003c4c4`

## callees

- `0x180007c78`
- `0x1800168f0`
- `0x180018150`
- `0x18001b0c4`
- `0x18001b8a4`
- `0x180041ac8`
- `0x180042950`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016bba`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016bba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800169bc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016a34`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800169bc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016a34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169d0`
- `ntdll!NtClose` at `0x180016bfa`
- `ntdll!NtClose` at `0x180016c27`
- `ntdll!NtClose` at `0x180016bfa`
- `ntdll!NtClose` at `0x180016c27`
- `ntdll!NtQueryInformationToken` at `0x180016b26`
- `ntdll!NtQueryInformationToken` at `0x180016b26`
- `ntdll!RtlEqualSid` at `0x180016a9e`
- `ntdll!RtlEqualSid` at `0x180016a9e`
- `ntdll!RtlGetLastNtStatus` at `0x180016ae0`
- `ntdll!RtlGetLastNtStatus` at `0x180016ae0`
- `ntdll!RtlQueryElevationFlags` at `0x180016973`
- `ntdll!RtlQueryElevationFlags` at `0x180016973`
- `ntdll!NtDuplicateToken` at `0x180016b96`
- `ntdll!NtDuplicateToken` at `0x180016b96`

## string_xrefs

- `0x180016a00`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180016a48`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180016ac7`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x1800168f0  mov     r11, rsp
0x1800168f3  push    rbp
0x1800168f4  push    rsi
0x1800168f5  push    r14
0x1800168f7  lea     rbp, [r11-5Fh]
0x1800168fb  sub     rsp, 0C0h
0x180016902  mov     rax, cs:__security_cookie
0x180016909  xor     rax, rsp
0x18001690c  mov     [rbp+57h+var_40], rax
0x180016910  mov     [r11+10h], rbx
0x180016914  xor     eax, eax
0x180016916  mov     [r11-20h], rdi
0x18001691a  xorps   xmm0, xmm0
0x18001691d  xor     edi, edi
0x18001691f  mov     [r11-28h], r12
0x180016923  mov     [r11-30h], r13
0x180016927  mov     r13, r8
0x18001692a  mov     [r11-38h], r15
0x18001692e  mov     r12, rcx
0x180016931  mov     [rbp+57h+NewTokenHandle], rdi
0x180016935  mov     esi, edi
0x180016937  mov     [rbp+57h+TokenInformation], rdi
0x18001693b  mov     r14, rcx
0x18001693e  mov     [rbp+57h+var_90], edi
0x180016941  mov     [rbp+57h+var_50], rax
0x180016945  mov     [rbp+57h+var_48], eax
0x180016948  mov     [r8], edi
0x18001694b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001694f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180016953  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180016957  test    edx, edx
0x180016959  jnz     loc_180016B47
0x18001695f  mov     [rbp+57h+TokenInformationLength], edi
0x180016962  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x180016967  test    eax, eax
0x180016969  jz      loc_180016B0C
0x18001696f  lea     rcx, [rbp+57h+TokenInformationLength]
0x180016973  call    cs:__imp_RtlQueryElevationFlags
0x18001697a  nop     dword ptr [rax+rax+00h]
0x18001697f  test    eax, eax
0x180016981  js      loc_180016B0C
0x180016987  mov     eax, [rbp+57h+TokenInformationLength]
0x18001698a  and     al, 18h
0x18001698c  cmp     al, 10h
0x18001698e  jnz     loc_180016B0C
0x180016994  lea     rax, [rbp+57h+TokenInformationLength]
0x180016998  mov     [rbp+57h+TokenInformationLength], edi
0x18001699b  test    r14, r14
0x18001699e  mov     qword ptr [rsp+0D0h+ReturnLength], rax; int
0x1800169a3  mov     r15, 0FFFFFFFFFFFFFFFAh
0x1800169aa  lea     edx, [rdi+0Dh]; TokenInformationClass
0x1800169ad  cmovnz  r15, r14
0x1800169b1  mov     ebx, edi
0x1800169b3  mov     rcx, r15; TokenHandle
0x1800169b6  xor     r9d, r9d; TokenInformationLength
0x1800169b9  xor     r8d, r8d; TokenInformation
0x1800169bc  call    cs:__imp_GetTokenInformation
0x1800169c3  nop     dword ptr [rax+rax+00h]
0x1800169c8  test    eax, eax
0x1800169ca  jnz     loc_180016AC3
0x1800169d0  call    cs:__imp_GetLastError
0x1800169d7  nop     dword ptr [rax+rax+00h]
0x1800169dc  cmp     eax, 7Ah ; 'z'
0x1800169df  jnz     loc_180016AC3
0x1800169e5  mov     ecx, [rbp+57h+TokenInformationLength]; unsigned __int64
0x1800169e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800169ef  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800169f4  mov     rdi, rax
0x1800169f7  test    rax, rax
0x1800169fa  jnz     short loc_180016A1C
0x1800169fc  mov     rcx, [rbp+5Fh]; this
0x180016a00  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016a07  mov     r9d, 8007000Eh; char *
0x180016a0d  mov     edx, 119h; void *
0x180016a12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a17  jmp     loc_180016AE0
0x180016a1c  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180016a20  lea     rax, [rbp+57h+TokenInformationLength]
0x180016a24  mov     r8, rdi; TokenInformation
0x180016a27  mov     qword ptr [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180016a2c  mov     edx, 0Dh; TokenInformationClass
0x180016a31  mov     rcx, r15; TokenHandle
0x180016a34  call    cs:__imp_GetTokenInformation
0x180016a3b  nop     dword ptr [rax+rax+00h]
0x180016a40  test    eax, eax
0x180016a42  jnz     short loc_180016A66
0x180016a44  mov     rcx, [rbp+5Fh]; this
0x180016a48  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016a4f  mov     edx, 11Ah; void *
0x180016a54  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016a59  mov     rcx, rdi; Block
0x180016a5c  mov     r15d, eax
0x180016a5f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016a64  jmp     short loc_180016ADB
0x180016a66  mov     rbx, rdi
0x180016a69  xor     edi, edi
0x180016a6b  cmp     [rbx], esi
0x180016a6d  jbe     loc_180016AFD
0x180016a73  nop     dword ptr [rax+00h]
0x180016a77  nop     word ptr [rax+rax+00000000h]
0x180016a80  mov     ecx, edi
0x180016a82  shl     rcx, 4
0x180016a86  add     rcx, [rbx+8]
0x180016a8a  test    byte ptr [rcx+8], 10h
0x180016a8e  jz      short loc_180016AAE
0x180016a90  mov     rdx, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x180016a97  mov     rcx, [rcx]; Sid1
0x180016a9a  mov     rdx, [rdx+50h]; Sid2
0x180016a9e  call    cs:__imp_RtlEqualSid
0x180016aa5  nop     dword ptr [rax+rax+00h]
0x180016aaa  test    al, al
0x180016aac  jnz     short loc_180016AF5
0x180016aae  inc     edi
0x180016ab0  cmp     edi, [rbx]
0x180016ab2  jb      short loc_180016A80
0x180016ab4  mov     rcx, rbx; Block
0x180016ab7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016abc  xor     edi, edi
0x180016abe  jmp     loc_180016BD9
0x180016ac3  mov     rcx, [rbp+5Fh]; this
0x180016ac7  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016ace  mov     edx, 117h; void *
0x180016ad3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016ad8  mov     r15d, eax
0x180016adb  test    r15d, r15d
0x180016ade  jns     short loc_180016A69
0x180016ae0  call    cs:__imp_RtlGetLastNtStatus
0x180016ae7  nop     dword ptr [rax+rax+00h]
0x180016aec  mov     esi, eax
0x180016aee  xor     edi, edi
0x180016af0  jmp     loc_180016BD9
0x180016af5  mov     dword ptr [r13+0], 1
0x180016afd  mov     rcx, rbx; Block
0x180016b00  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016b05  xor     edi, edi
0x180016b07  jmp     loc_180016BD9
0x180016b0c  mov     r9d, 8; TokenInformationLength
0x180016b12  lea     rax, [rbp+57h+var_90]
0x180016b16  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180016b1a  mov     qword ptr [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180016b1f  mov     rcx, r12; TokenHandle
0x180016b22  lea     edx, [r9+0Bh]; TokenInformationClass
0x180016b26  call    cs:__imp_NtQueryInformationToken
0x180016b2d  nop     dword ptr [rax+rax+00h]
0x180016b32  test    eax, eax
0x180016b34  jns     short loc_180016B43
0x180016b36  cmp     eax, 0C000005Fh
0x180016b3b  cmovnz  esi, eax
0x180016b3e  jmp     loc_180016BD9
0x180016b43  mov     r14, [rbp+57h+TokenInformation]
0x180016b47  lea     rax, [rbp+57h+var_50]
0x180016b4b  mov     dword ptr [rbp+57h+var_50], 0Ch
0x180016b52  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x180016b56  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180016b5a  lea     rax, [rbp+57h+NewTokenHandle]
0x180016b5e  mov     dword ptr [rbp+57h+var_50+4], 2
0x180016b65  mov     qword ptr [rsp+0D0h+ReturnLength+8], rax; NewTokenHandle
0x180016b6a  xor     r9d, r9d; EffectiveOnly
0x180016b6d  xor     edx, edx; DesiredAccess
0x180016b6f  mov     [rsp+0D0h+ReturnLength], 2; TokenType
0x180016b77  mov     rcx, r14; ExistingTokenHandle
0x180016b7a  mov     word ptr [rbp+57h+var_48], 1
0x180016b80  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180016b87  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180016b8b  mov     [rbp+57h+ObjectAttributes.Attributes], edi
0x180016b8e  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x180016b92  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rdi
0x180016b96  call    cs:__imp_NtDuplicateToken
0x180016b9d  nop     dword ptr [rax+rax+00h]
0x180016ba2  mov     esi, eax
0x180016ba4  test    eax, eax
0x180016ba6  js      short loc_180016BD9
0x180016ba8  mov     rdx, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x180016baf  mov     r8, r13; IsMember
0x180016bb2  mov     rcx, [rbp+57h+NewTokenHandle]; TokenHandle
0x180016bb6  mov     rdx, [rdx+50h]; SidToCheck
0x180016bba  call    cs:__imp_CheckTokenMembership
0x180016bc1  nop     dword ptr [rax+rax+00h]
0x180016bc6  test    eax, eax
0x180016bc8  jnz     short loc_180016BD9
0x180016bca  mov     rax, gs:30h
0x180016bd3  mov     esi, [rax+1250h]
0x180016bd9  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x180016bdd  mov     r15, [rsp+0D0h+var_30]
0x180016be5  mov     r13, [rsp+0D0h+var_28]
0x180016bed  mov     rbx, [rsp+0D0h+arg_8]
0x180016bf5  test    rcx, rcx
0x180016bf8  jz      short loc_180016C0A
0x180016bfa  call    cs:__imp_NtClose
0x180016c01  nop     dword ptr [rax+rax+00h]
0x180016c06  mov     [rbp+57h+NewTokenHandle], rdi
0x180016c0a  mov     rdi, [rsp+0B8h]
0x180016c12  cmp     r14, r12
0x180016c15  mov     r12, [rsp+0D0h+var_20]
0x180016c1d  jz      short loc_180016C33
0x180016c1f  test    r14, r14
0x180016c22  jz      short loc_180016C33
0x180016c24  mov     rcx, r14; Handle
0x180016c27  call    cs:__imp_NtClose
0x180016c2e  nop     dword ptr [rax+rax+00h]
0x180016c33  mov     eax, esi
0x180016c35  mov     rcx, [rbp+57h+var_40]
0x180016c39  xor     rcx, rsp; StackCookie
0x180016c3c  call    __security_check_cookie
0x180016c41  add     rsp, 0C0h
0x180016c48  pop     r14
0x180016c4a  pop     rsi
0x180016c4b  pop     rbp
0x180016c4c  retn
```
