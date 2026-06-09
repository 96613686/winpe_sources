# GetThreadLogonSessionStringSid(ushort * *)

- ea: `0x18004ec40`
- end: `0x18004edd1`
- name: `?GetThreadLogonSessionStringSid@@YAJPEAPEAG@Z`
- size: `401`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800826a0`

## callees

- `0x1800128bc`
- `0x18004ec40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ed68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ed68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ec63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ec63`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ec76`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ec76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ed83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ed83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004eda5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004eda5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004ec9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004ece3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004ec9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004ece3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ecb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ecb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ed1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ed1c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004ed53`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004ed53`

## string_xrefs

- `0x18004edbb`: `GetThreadLogonSessionStringSid`

## pseudocode

```c
__int64 __fastcall GetThreadLogonSessionStringSid(unsigned __int16 **a1)
{
  _DWORD *v1; // rdi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v5; // ebx
  __int64 v6; // rcx
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+38h] BYREF

  v1 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  StringSid = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    if ( !GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError != 122 )
        goto LABEL_20;
      v1 = CoTaskMemAlloc(TokenInformationLength);
      if ( !v1 )
      {
        v5 = -2147024882;
LABEL_25:
        if ( StringSid )
        {
          LocalFree(StringSid);
          StringSid = 0;
        }
        goto LABEL_10;
      }
    }
    if ( GetTokenInformation(TokenHandle, TokenGroups, v1, TokenInformationLength, &TokenInformationLength) )
    {
      v6 = 0;
      if ( !*v1 )
      {
LABEL_9:
        v5 = 1365;
        goto LABEL_10;
      }
      while ( (v1[4 * (unsigned int)v6 + 4] & 0xC0000000) != 0xC0000000 )
      {
        v6 = (unsigned int)(v6 + 1);
        if ( (unsigned int)v6 >= *v1 )
          goto LABEL_9;
      }
      if ( ConvertSidToStringSidW(*(PSID *)&v1[4 * v6 + 2], &StringSid) )
      {
        v5 = 0;
        *a1 = StringSid;
        goto LABEL_10;
      }
    }
  }
  LastError = GetLastError();
  v5 = LastError;
LABEL_20:
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_25;
LABEL_10:
  if ( v1 )
    CoTaskMemFree(v1);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v5 < 0 )
    AudSrvTraceLoggingErrorHelper("GetThreadLogonSessionStringSid", 0x1A0u, v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004ec40  mov     [rsp-18h+arg_0], rbx
0x18004ec45  push    rbp
0x18004ec46  push    rsi
0x18004ec47  push    rdi
0x18004ec48  mov     rbp, rsp
0x18004ec4b  sub     rsp, 30h
0x18004ec4f  xor     edi, edi
0x18004ec51  mov     [rbp+TokenHandle], 0
0x18004ec59  mov     [rbp+TokenInformationLength], edi
0x18004ec5c  mov     rsi, rcx
0x18004ec5f  mov     [rbp+StringSid], rdi
0x18004ec63  call    cs:__imp_GetCurrentThread
0x18004ec69  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004ec6d  xor     r8d, r8d; OpenAsSelf
0x18004ec70  mov     rcx, rax; ThreadHandle
0x18004ec73  lea     edx, [rdi+8]; DesiredAccess
0x18004ec76  call    cs:__imp_OpenThreadToken
0x18004ec7c  test    eax, eax
0x18004ec7e  jz      loc_18004ED68
0x18004ec84  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004ec88  lea     rax, [rbp+TokenInformationLength]
0x18004ec8c  xor     r9d, r9d; TokenInformationLength
0x18004ec8f  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18004ec94  xor     r8d, r8d; TokenInformation
0x18004ec97  lea     edx, [rdi+2]; TokenInformationClass
0x18004ec9a  call    cs:__imp_GetTokenInformation
0x18004eca0  test    eax, eax
0x18004eca2  jnz     short loc_18004ECCA
0x18004eca4  call    cs:__imp_GetLastError
0x18004ecaa  mov     ebx, eax
0x18004ecac  cmp     eax, 7Ah ; 'z'
0x18004ecaf  jnz     loc_18004ED70
0x18004ecb5  mov     ecx, [rbp+TokenInformationLength]; cb
0x18004ecb8  call    cs:__imp_CoTaskMemAlloc
0x18004ecbe  mov     rdi, rax
0x18004ecc1  test    rax, rax
0x18004ecc4  jz      loc_18004ED93
0x18004ecca  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18004ecce  lea     rax, [rbp+TokenInformationLength]
0x18004ecd2  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004ecd6  mov     r8, rdi; TokenInformation
0x18004ecd9  mov     edx, 2; TokenInformationClass
0x18004ecde  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18004ece3  call    cs:__imp_GetTokenInformation
0x18004ece9  test    eax, eax
0x18004eceb  jz      short loc_18004ED68
0x18004eced  xor     ecx, ecx
0x18004ecef  cmp     ecx, [rdi]
0x18004ecf1  jnb     short loc_18004ED0F
0x18004ecf3  mov     edx, 0C0000000h
0x18004ecf8  mov     eax, ecx
0x18004ecfa  inc     rax
0x18004ecfd  add     rax, rax
0x18004ed00  mov     eax, [rdi+rax*8]
0x18004ed03  and     eax, edx
0x18004ed05  cmp     eax, edx
0x18004ed07  jz      short loc_18004ED47
0x18004ed09  inc     ecx
0x18004ed0b  cmp     ecx, [rdi]
0x18004ed0d  jb      short loc_18004ECF8
0x18004ed0f  mov     ebx, 555h
0x18004ed14  test    rdi, rdi
0x18004ed17  jz      short loc_18004ED22
0x18004ed19  mov     rcx, rdi; pv
0x18004ed1c  call    cs:__imp_CoTaskMemFree
0x18004ed22  mov     rcx, [rbp+TokenHandle]; hObject
0x18004ed26  lea     rax, [rcx-1]
0x18004ed2a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004ed2e  jbe     short loc_18004ED83
0x18004ed30  test    ebx, ebx
0x18004ed32  js      loc_18004EDB8
0x18004ed38  mov     eax, ebx
0x18004ed3a  mov     rbx, [rsp+30h+arg_0]
0x18004ed3f  add     rsp, 30h
0x18004ed43  pop     rdi
0x18004ed44  pop     rsi
0x18004ed45  pop     rbp
0x18004ed46  retn
0x18004ed47  add     rcx, rcx
0x18004ed4a  lea     rdx, [rbp+StringSid]; StringSid
0x18004ed4e  mov     rcx, [rdi+rcx*8+8]; Sid
0x18004ed53  call    cs:__imp_ConvertSidToStringSidW
0x18004ed59  test    eax, eax
0x18004ed5b  jz      short loc_18004ED68
0x18004ed5d  mov     rax, [rbp+StringSid]
0x18004ed61  xor     ebx, ebx
0x18004ed63  mov     [rsi], rax
0x18004ed66  jmp     short loc_18004ED14
0x18004ed68  call    cs:__imp_GetLastError
0x18004ed6e  mov     ebx, eax
0x18004ed70  test    eax, eax
0x18004ed72  jle     short loc_18004ED7D
0x18004ed74  movzx   ebx, ax
0x18004ed77  or      ebx, 80070000h
0x18004ed7d  test    ebx, ebx
0x18004ed7f  jns     short loc_18004ED14
0x18004ed81  jmp     short loc_18004ED98
0x18004ed83  call    cs:__imp_CloseHandle
0x18004ed89  mov     [rbp+TokenHandle], 0
0x18004ed91  jmp     short loc_18004ED30
0x18004ed93  mov     ebx, 8007000Eh
0x18004ed98  mov     rcx, [rbp+StringSid]; hMem
0x18004ed9c  test    rcx, rcx
0x18004ed9f  jz      loc_18004ED14
0x18004eda5  call    cs:__imp_LocalFree
0x18004edab  mov     [rbp+StringSid], 0
0x18004edb3  jmp     loc_18004ED14
0x18004edb8  mov     r8d, ebx; int
0x18004edbb  lea     rcx, aGetthreadlogon; "GetThreadLogonSessionStringSid"
0x18004edc2  mov     edx, 1A0h; unsigned int
0x18004edc7  call    ?AudSrvTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudSrvTraceLoggingErrorHelper(char const *,uint,long)
0x18004edcc  jmp     loc_18004ED38
```
