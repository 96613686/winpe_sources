# IncomingMessageRegistrationEvent::_GetCurrentSID(void * *)

- ea: `0x180009be4`
- end: `0x180009e50`
- name: `?_GetCurrentSID@IncomingMessageRegistrationEvent@@CAJPEAPEAX@Z`
- size: `620`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180009e58`

## callees

- `0x180002bd8`
- `0x180009ba4`
- `0x180009bc4`
- `0x180009be4`
- `0x18000aa50`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180009d4b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009db4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009e07`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009e18`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009d4b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009db4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009e07`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009e18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009de2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009c12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009c12`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180009c24`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180009c24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ccb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009dc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ccb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009dc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e27`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009d83`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009d83`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180009d59`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180009d59`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009c86`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009d1a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009c86`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009d1a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009dd8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009dd8`

## pseudocode

```c
__int64 __fastcall IncomingMessageRegistrationEvent::_GetCurrentSID(void **a1)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  __int64 v4; // r8
  unsigned int v5; // ebx
  BOOL TokenInformation; // ebx
  signed int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // edi
  PSID *v11; // rdi
  __int64 v12; // r8
  signed int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  signed int v16; // eax
  DWORD LengthSid; // ebx
  void *v18; // rax
  __int64 v19; // r8
  void *v20; // rsi
  signed int v21; // eax
  __int64 v22; // r8
  DWORD TokenInformationLength; // [rsp+30h] [rbp-20h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-18h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    Log_HREvent_5(v5, 0, v4, 63);
    goto LABEL_5;
  }
  TokenInformationLength = 0;
  TokenInformation = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v8 = GetLastError();
  v10 = v8;
  if ( !TokenInformation && v8 != 122 )
  {
    if ( v8 > 0 )
      v10 = (unsigned __int16)v8 | 0x80070000;
    Log_HREvent_5(v10, 0, v9, 73);
    if ( !v10 )
      Log_AssertionEvent_0();
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return v10;
  }
  v11 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v11 )
  {
    Log_HREvent_5(2147942414LL, 0, v12, 78);
LABEL_31:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return 2147942414LL;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
  {
    v13 = GetLastError();
    v5 = v13;
    if ( v13 > 0 )
      v5 = (unsigned __int16)v13 | 0x80070000;
    v15 = 81;
LABEL_23:
    Log_HREvent_5(v5, 0, v14, v15);
LABEL_24:
    operator delete[](v11);
LABEL_5:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return v5;
  }
  if ( !IsValidSid(*v11) )
  {
    v16 = GetLastError();
    v5 = v16;
    if ( v16 > 0 )
      v5 = (unsigned __int16)v16 | 0x80070000;
    v15 = 84;
    goto LABEL_23;
  }
  LengthSid = GetLengthSid(*v11);
  v18 = operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
  v20 = v18;
  if ( !v18 )
  {
    Log_HREvent_5(2147942414LL, 0, v19, 90);
    operator delete[](v11);
    goto LABEL_31;
  }
  if ( !CopySid(LengthSid, v18, *v11) )
  {
    v21 = GetLastError();
    v5 = v21;
    if ( v21 > 0 )
      v5 = (unsigned __int16)v21 | 0x80070000;
    Log_HREvent_5(v5, 0, v22, 92);
    operator delete[](v20);
    goto LABEL_24;
  }
  *a1 = v20;
  operator delete[](v11);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180009be4  mov     [rsp-18h+arg_8], rbx
0x180009be9  mov     [rsp-18h+arg_10], rsi
0x180009bee  push    rbp
0x180009bef  push    rdi
0x180009bf0  push    r14
0x180009bf2  mov     rbp, rsp
0x180009bf5  sub     rsp, 50h
0x180009bf9  mov     rax, cs:__security_cookie
0x180009c00  xor     rax, rsp
0x180009c03  mov     [rbp+var_10], rax
0x180009c07  mov     r14, rcx
0x180009c0a  mov     [rbp+TokenHandle], 0
0x180009c12  call    cs:__imp_GetCurrentProcess
0x180009c18  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180009c1c  mov     edx, 8; DesiredAccess
0x180009c21  mov     rcx, rax; ProcessHandle
0x180009c24  call    cs:__imp_OpenProcessToken
0x180009c2a  test    eax, eax
0x180009c2c  jnz     short loc_180009C66
0x180009c2e  call    cs:__imp_GetLastError
0x180009c34  mov     ebx, eax
0x180009c36  test    eax, eax
0x180009c38  jle     short loc_180009C43
0x180009c3a  movzx   ebx, ax
0x180009c3d  or      ebx, 80070000h
0x180009c43  xor     edx, edx
0x180009c45  mov     ecx, ebx
0x180009c47  lea     r9d, [rdx+3Fh]
0x180009c4b  call    Log_HREvent_5
0x180009c50  mov     rcx, [rbp+TokenHandle]; hObject
0x180009c54  test    rcx, rcx
0x180009c57  jz      short loc_180009C5F
0x180009c59  call    cs:__imp_CloseHandle
0x180009c5f  mov     eax, ebx
0x180009c61  jmp     loc_180009E2F
0x180009c66  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180009c6a  lea     rax, [rbp+TokenInformationLength]
0x180009c6e  xor     r9d, r9d; TokenInformationLength
0x180009c71  mov     [rbp+TokenInformationLength], 0
0x180009c78  xor     r8d, r8d; TokenInformation
0x180009c7b  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180009c80  lea     esi, [r9+1]
0x180009c84  mov     edx, esi; TokenInformationClass
0x180009c86  call    cs:__imp_GetTokenInformation
0x180009c8c  mov     ebx, eax
0x180009c8e  call    cs:__imp_GetLastError
0x180009c94  mov     edi, eax
0x180009c96  test    ebx, ebx
0x180009c98  jnz     short loc_180009CD8
0x180009c9a  cmp     eax, 7Ah ; 'z'
0x180009c9d  jz      short loc_180009CD8
0x180009c9f  test    eax, eax
0x180009ca1  jle     short loc_180009CAC
0x180009ca3  movzx   edi, ax
0x180009ca6  or      edi, 80070000h
0x180009cac  xor     edx, edx
0x180009cae  mov     ecx, edi
0x180009cb0  lea     r9d, [rdx+49h]
0x180009cb4  call    Log_HREvent_5
0x180009cb9  test    edi, edi
0x180009cbb  jnz     short loc_180009CC2
0x180009cbd  call    Log_AssertionEvent_0
0x180009cc2  mov     rcx, [rbp+TokenHandle]; hObject
0x180009cc6  test    rcx, rcx
0x180009cc9  jz      short loc_180009CD1
0x180009ccb  call    cs:__imp_CloseHandle
0x180009cd1  mov     eax, edi
0x180009cd3  jmp     loc_180009E2F
0x180009cd8  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x180009cdb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009ce2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009ce7  mov     rdi, rax
0x180009cea  test    rax, rax
0x180009ced  jnz     short loc_180009D04
0x180009cef  xor     edx, edx
0x180009cf1  lea     r9d, [rax+4Eh]
0x180009cf5  mov     ecx, 8007000Eh
0x180009cfa  call    Log_HREvent_5
0x180009cff  jmp     loc_180009DBA
0x180009d04  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180009d08  lea     rax, [rbp+TokenInformationLength]
0x180009d0c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180009d10  mov     r8, rdi; TokenInformation
0x180009d13  mov     edx, esi; TokenInformationClass
0x180009d15  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180009d1a  call    cs:__imp_GetTokenInformation
0x180009d20  test    eax, eax
0x180009d22  jnz     short loc_180009D56
0x180009d24  call    cs:__imp_GetLastError
0x180009d2a  mov     ebx, eax
0x180009d2c  test    eax, eax
0x180009d2e  jle     short loc_180009D39
0x180009d30  movzx   ebx, ax
0x180009d33  or      ebx, 80070000h
0x180009d39  mov     r9d, 51h ; 'Q'
0x180009d3f  xor     edx, edx
0x180009d41  mov     ecx, ebx
0x180009d43  call    Log_HREvent_5
0x180009d48  mov     rcx, rdi
0x180009d4b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009d51  jmp     loc_180009C50
0x180009d56  mov     rcx, [rdi]; pSid
0x180009d59  call    cs:__imp_IsValidSid
0x180009d5f  test    eax, eax
0x180009d61  jnz     short loc_180009D80
0x180009d63  call    cs:__imp_GetLastError
0x180009d69  mov     ebx, eax
0x180009d6b  test    eax, eax
0x180009d6d  jle     short loc_180009D78
0x180009d6f  movzx   ebx, ax
0x180009d72  or      ebx, 80070000h
0x180009d78  mov     r9d, 54h ; 'T'
0x180009d7e  jmp     short loc_180009D3F
0x180009d80  mov     rcx, [rdi]; pSid
0x180009d83  call    cs:__imp_GetLengthSid
0x180009d89  mov     ecx, eax; unsigned __int64
0x180009d8b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009d92  mov     ebx, eax
0x180009d94  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009d99  mov     rsi, rax
0x180009d9c  test    rax, rax
0x180009d9f  jnz     short loc_180009DD0
0x180009da1  xor     edx, edx
0x180009da3  lea     r9d, [rax+5Ah]
0x180009da7  mov     ecx, 8007000Eh
0x180009dac  call    Log_HREvent_5
0x180009db1  mov     rcx, rdi
0x180009db4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009dba  mov     rcx, [rbp+TokenHandle]; hObject
0x180009dbe  test    rcx, rcx
0x180009dc1  jz      short loc_180009DC9
0x180009dc3  call    cs:__imp_CloseHandle
0x180009dc9  mov     eax, 8007000Eh
0x180009dce  jmp     short loc_180009E2F
0x180009dd0  mov     r8, [rdi]; pSourceSid
0x180009dd3  mov     rdx, rsi; pDestinationSid
0x180009dd6  mov     ecx, ebx; nDestinationSidLength
0x180009dd8  call    cs:__imp_CopySid
0x180009dde  test    eax, eax
0x180009de0  jnz     short loc_180009E12
0x180009de2  call    cs:__imp_GetLastError
0x180009de8  mov     ebx, eax
0x180009dea  test    eax, eax
0x180009dec  jle     short loc_180009DF7
0x180009dee  movzx   ebx, ax
0x180009df1  or      ebx, 80070000h
0x180009df7  xor     edx, edx
0x180009df9  mov     ecx, ebx
0x180009dfb  lea     r9d, [rdx+5Ch]
0x180009dff  call    Log_HREvent_5
0x180009e04  mov     rcx, rsi
0x180009e07  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009e0d  jmp     loc_180009D48
0x180009e12  mov     rcx, rdi
0x180009e15  mov     [r14], rsi
0x180009e18  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009e1e  mov     rcx, [rbp+TokenHandle]; hObject
0x180009e22  test    rcx, rcx
0x180009e25  jz      short loc_180009E2D
0x180009e27  call    cs:__imp_CloseHandle
0x180009e2d  xor     eax, eax
0x180009e2f  mov     rcx, [rbp+var_10]
0x180009e33  xor     rcx, rsp; StackCookie
0x180009e36  call    __security_check_cookie
0x180009e3b  lea     r11, [rsp+50h+var_s0]
0x180009e40  mov     rbx, [r11+28h]
0x180009e44  mov     rsi, [r11+30h]
0x180009e48  mov     rsp, r11
0x180009e4b  pop     r14
0x180009e4d  pop     rdi
0x180009e4e  pop     rbp
0x180009e4f  retn
```
