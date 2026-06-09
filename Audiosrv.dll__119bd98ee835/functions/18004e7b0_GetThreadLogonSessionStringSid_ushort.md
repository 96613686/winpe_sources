# GetThreadLogonSessionStringSid(ushort * *)

- ea: `0x18004e7b0`
- end: `0x18004e941`
- name: `?GetThreadLogonSessionStringSid@@YAJPEAPEAG@Z`
- size: `401`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800821a0`

## callees

- `0x180012a0c`
- `0x18004e7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e8d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004e7d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004e7d3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004e7e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004e7e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e8f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e8f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e915`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e915`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e80a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e853`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e80a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e853`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e88c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e88c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004e8c3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004e8c3`

## string_xrefs

- `0x18004e92b`: `GetThreadLogonSessionStringSid`

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
0x18004e7b0  mov     [rsp-18h+arg_0], rbx
0x18004e7b5  push    rbp
0x18004e7b6  push    rsi
0x18004e7b7  push    rdi
0x18004e7b8  mov     rbp, rsp
0x18004e7bb  sub     rsp, 30h
0x18004e7bf  xor     edi, edi
0x18004e7c1  mov     [rbp+TokenHandle], 0
0x18004e7c9  mov     [rbp+TokenInformationLength], edi
0x18004e7cc  mov     rsi, rcx
0x18004e7cf  mov     [rbp+StringSid], rdi
0x18004e7d3  call    cs:__imp_GetCurrentThread
0x18004e7d9  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004e7dd  xor     r8d, r8d; OpenAsSelf
0x18004e7e0  mov     rcx, rax; ThreadHandle
0x18004e7e3  lea     edx, [rdi+8]; DesiredAccess
0x18004e7e6  call    cs:__imp_OpenThreadToken
0x18004e7ec  test    eax, eax
0x18004e7ee  jz      loc_18004E8D8
0x18004e7f4  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004e7f8  lea     rax, [rbp+TokenInformationLength]
0x18004e7fc  xor     r9d, r9d; TokenInformationLength
0x18004e7ff  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18004e804  xor     r8d, r8d; TokenInformation
0x18004e807  lea     edx, [rdi+2]; TokenInformationClass
0x18004e80a  call    cs:__imp_GetTokenInformation
0x18004e810  test    eax, eax
0x18004e812  jnz     short loc_18004E83A
0x18004e814  call    cs:__imp_GetLastError
0x18004e81a  mov     ebx, eax
0x18004e81c  cmp     eax, 7Ah ; 'z'
0x18004e81f  jnz     loc_18004E8E0
0x18004e825  mov     ecx, [rbp+TokenInformationLength]; cb
0x18004e828  call    cs:__imp_CoTaskMemAlloc
0x18004e82e  mov     rdi, rax
0x18004e831  test    rax, rax
0x18004e834  jz      loc_18004E903
0x18004e83a  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18004e83e  lea     rax, [rbp+TokenInformationLength]
0x18004e842  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004e846  mov     r8, rdi; TokenInformation
0x18004e849  mov     edx, 2; TokenInformationClass
0x18004e84e  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18004e853  call    cs:__imp_GetTokenInformation
0x18004e859  test    eax, eax
0x18004e85b  jz      short loc_18004E8D8
0x18004e85d  xor     ecx, ecx
0x18004e85f  cmp     ecx, [rdi]
0x18004e861  jnb     short loc_18004E87F
0x18004e863  mov     edx, 0C0000000h
0x18004e868  mov     eax, ecx
0x18004e86a  inc     rax
0x18004e86d  add     rax, rax
0x18004e870  mov     eax, [rdi+rax*8]
0x18004e873  and     eax, edx
0x18004e875  cmp     eax, edx
0x18004e877  jz      short loc_18004E8B7
0x18004e879  inc     ecx
0x18004e87b  cmp     ecx, [rdi]
0x18004e87d  jb      short loc_18004E868
0x18004e87f  mov     ebx, 555h
0x18004e884  test    rdi, rdi
0x18004e887  jz      short loc_18004E892
0x18004e889  mov     rcx, rdi; pv
0x18004e88c  call    cs:__imp_CoTaskMemFree
0x18004e892  mov     rcx, [rbp+TokenHandle]; hObject
0x18004e896  lea     rax, [rcx-1]
0x18004e89a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e89e  jbe     short loc_18004E8F3
0x18004e8a0  test    ebx, ebx
0x18004e8a2  js      loc_18004E928
0x18004e8a8  mov     eax, ebx
0x18004e8aa  mov     rbx, [rsp+30h+arg_0]
0x18004e8af  add     rsp, 30h
0x18004e8b3  pop     rdi
0x18004e8b4  pop     rsi
0x18004e8b5  pop     rbp
0x18004e8b6  retn
0x18004e8b7  add     rcx, rcx
0x18004e8ba  lea     rdx, [rbp+StringSid]; StringSid
0x18004e8be  mov     rcx, [rdi+rcx*8+8]; Sid
0x18004e8c3  call    cs:__imp_ConvertSidToStringSidW
0x18004e8c9  test    eax, eax
0x18004e8cb  jz      short loc_18004E8D8
0x18004e8cd  mov     rax, [rbp+StringSid]
0x18004e8d1  xor     ebx, ebx
0x18004e8d3  mov     [rsi], rax
0x18004e8d6  jmp     short loc_18004E884
0x18004e8d8  call    cs:__imp_GetLastError
0x18004e8de  mov     ebx, eax
0x18004e8e0  test    eax, eax
0x18004e8e2  jle     short loc_18004E8ED
0x18004e8e4  movzx   ebx, ax
0x18004e8e7  or      ebx, 80070000h
0x18004e8ed  test    ebx, ebx
0x18004e8ef  jns     short loc_18004E884
0x18004e8f1  jmp     short loc_18004E908
0x18004e8f3  call    cs:__imp_CloseHandle
0x18004e8f9  mov     [rbp+TokenHandle], 0
0x18004e901  jmp     short loc_18004E8A0
0x18004e903  mov     ebx, 8007000Eh
0x18004e908  mov     rcx, [rbp+StringSid]; hMem
0x18004e90c  test    rcx, rcx
0x18004e90f  jz      loc_18004E884
0x18004e915  call    cs:__imp_LocalFree
0x18004e91b  mov     [rbp+StringSid], 0
0x18004e923  jmp     loc_18004E884
0x18004e928  mov     r8d, ebx; int
0x18004e92b  lea     rcx, aGetthreadlogon; "GetThreadLogonSessionStringSid"
0x18004e932  mov     edx, 1A0h; unsigned int
0x18004e937  call    ?AudSrvTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudSrvTraceLoggingErrorHelper(char const *,uint,long)
0x18004e93c  jmp     loc_18004E8A8
```
