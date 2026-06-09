# ShieldProvider::AutoGetUserToken::Initialize(void)

- ea: `0x1800d3f28`
- end: `0x1800d40e8`
- name: `?Initialize@AutoGetUserToken@ShieldProvider@@QEAAJXZ`
- size: `448`
- prototype: `__int64 __fastcall(ShieldProvider::AutoGetUserToken *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004d728`

## callees

- `0x18000d7fc`
- `0x1800d3f28`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800d3f5c`
- `KERNEL32!GetLastError` at `0x1800d3fef`
- `KERNEL32!GetLastError` at `0x1800d408b`
- `KERNEL32!GetLastError` at `0x1800d3f5c`
- `KERNEL32!GetLastError` at `0x1800d3fef`
- `KERNEL32!GetLastError` at `0x1800d408b`
- `KERNEL32!CloseHandle` at `0x1800d3faf`
- `KERNEL32!CloseHandle` at `0x1800d406e`
- `KERNEL32!CloseHandle` at `0x1800d40d8`
- `KERNEL32!CloseHandle` at `0x1800d3faf`
- `KERNEL32!CloseHandle` at `0x1800d406e`
- `KERNEL32!CloseHandle` at `0x1800d40d8`
- `KERNEL32!GetCurrentThread` at `0x1800d3f3e`
- `KERNEL32!GetCurrentThread` at `0x1800d3f3e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d3f52`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d3f52`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d3fe5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d3fe5`
- `ole32!CoRevertToSelf` at `0x1800d4027`
- `ole32!CoRevertToSelf` at `0x1800d4027`
- `WTSAPI32!WTSQueryUserToken` at `0x1800d4081`
- `WTSAPI32!WTSQueryUserToken` at `0x1800d4081`

## pseudocode

```c
__int64 __fastcall ShieldProvider::AutoGetUserToken::Initialize(ShieldProvider::AutoGetUserToken *this)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  signed int v8; // eax
  void *v9; // rcx
  signed int v10; // eax
  ULONG TokenInformation; // [rsp+58h] [rbp+28h] BYREF
  DWORD ReturnLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xAu, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 18;
LABEL_8:
        WPP_SF_d(v5[2], v6, WPP_e9ad2fe73d953ac4323a17feb709293e_Traceguids, (unsigned int)v4);
        goto LABEL_9;
      }
      goto LABEL_9;
    }
  }
  TokenInformation = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
  {
    v8 = GetLastError();
    v4 = v8;
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    v6 = 19;
    goto LABEL_8;
  }
  v4 = CoRevertToSelf();
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 20;
      goto LABEL_8;
    }
LABEL_9:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return (unsigned int)v4;
  }
  *((_BYTE *)this + 16) = 1;
  v9 = (void *)*((_QWORD *)this + 3);
  if ( v9 )
  {
    CloseHandle(v9);
    *((_QWORD *)this + 3) = 0;
  }
  if ( !WTSQueryUserToken(TokenInformation, (PHANDLE)this + 3) )
  {
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 21;
        goto LABEL_8;
      }
      goto LABEL_9;
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x1800d3f28  push    rbp
0x1800d3f2a  push    rbx
0x1800d3f2b  push    rdi
0x1800d3f2c  mov     rbp, rsp
0x1800d3f2f  sub     rsp, 30h
0x1800d3f33  mov     rdi, rcx
0x1800d3f36  mov     [rbp+TokenHandle], 0
0x1800d3f3e  call    cs:__imp_GetCurrentThread
0x1800d3f44  xor     r8d, r8d; OpenAsSelf
0x1800d3f47  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d3f4b  mov     rcx, rax; ThreadHandle
0x1800d3f4e  lea     edx, [r8+0Ah]; DesiredAccess
0x1800d3f52  call    cs:__imp_OpenThreadToken
0x1800d3f58  test    eax, eax
0x1800d3f5a  jnz     short loc_1800D3FBC
0x1800d3f5c  call    cs:__imp_GetLastError
0x1800d3f62  mov     ebx, eax
0x1800d3f64  test    eax, eax
0x1800d3f66  jle     short loc_1800D3F71
0x1800d3f68  movzx   ebx, ax
0x1800d3f6b  or      ebx, 80070000h
0x1800d3f71  test    ebx, ebx
0x1800d3f73  jns     short loc_1800D3FBC
0x1800d3f75  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3f7c  lea     rax, WPP_GLOBAL_Control
0x1800d3f83  cmp     rcx, rax
0x1800d3f86  jz      short loc_1800D3FA6
0x1800d3f88  test    byte ptr [rcx+1Ch], 1
0x1800d3f8c  jz      short loc_1800D3FA6
0x1800d3f8e  mov     edx, 12h
0x1800d3f93  mov     rcx, [rcx+10h]
0x1800d3f97  lea     r8, WPP_e9ad2fe73d953ac4323a17feb709293e_Traceguids
0x1800d3f9e  mov     r9d, ebx
0x1800d3fa1  call    WPP_SF_d
0x1800d3fa6  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d3faa  test    rcx, rcx
0x1800d3fad  jz      short loc_1800D3FB5
0x1800d3faf  call    cs:__imp_CloseHandle
0x1800d3fb5  mov     eax, ebx
0x1800d3fb7  jmp     loc_1800D40E0
0x1800d3fbc  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800d3fc0  lea     rax, [rbp+arg_10]
0x1800d3fc4  mov     r9d, 4; TokenInformationLength
0x1800d3fca  mov     [rbp+TokenInformation], 0
0x1800d3fd1  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800d3fd5  mov     [rbp+arg_10], 0
0x1800d3fdc  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800d3fe1  lea     edx, [r9+8]; TokenInformationClass
0x1800d3fe5  call    cs:__imp_GetTokenInformation
0x1800d3feb  test    eax, eax
0x1800d3fed  jnz     short loc_1800D4027
0x1800d3fef  call    cs:__imp_GetLastError
0x1800d3ff5  mov     ebx, eax
0x1800d3ff7  test    eax, eax
0x1800d3ff9  jle     short loc_1800D4004
0x1800d3ffb  movzx   ebx, ax
0x1800d3ffe  or      ebx, 80070000h
0x1800d4004  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d400b  lea     rax, WPP_GLOBAL_Control
0x1800d4012  cmp     rcx, rax
0x1800d4015  jz      short loc_1800D3FA6
0x1800d4017  test    byte ptr [rcx+1Ch], 1
0x1800d401b  jz      short loc_1800D3FA6
0x1800d401d  mov     edx, 13h
0x1800d4022  jmp     loc_1800D3F93
0x1800d4027  call    cs:__imp_CoRevertToSelf
0x1800d402d  mov     ebx, eax
0x1800d402f  test    eax, eax
0x1800d4031  jns     short loc_1800D405E
0x1800d4033  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d403a  lea     rax, WPP_GLOBAL_Control
0x1800d4041  cmp     rcx, rax
0x1800d4044  jz      loc_1800D3FA6
0x1800d404a  test    byte ptr [rcx+1Ch], 1
0x1800d404e  jz      loc_1800D3FA6
0x1800d4054  mov     edx, 14h
0x1800d4059  jmp     loc_1800D3F93
0x1800d405e  lea     rbx, [rdi+18h]
0x1800d4062  mov     byte ptr [rdi+10h], 1
0x1800d4066  mov     rcx, [rbx]; hObject
0x1800d4069  test    rcx, rcx
0x1800d406c  jz      short loc_1800D407B
0x1800d406e  call    cs:__imp_CloseHandle
0x1800d4074  mov     qword ptr [rbx], 0
0x1800d407b  mov     ecx, [rbp+TokenInformation]; SessionId
0x1800d407e  mov     rdx, rbx; phToken
0x1800d4081  call    cs:__imp_WTSQueryUserToken
0x1800d4087  test    eax, eax
0x1800d4089  jnz     short loc_1800D40CF
0x1800d408b  call    cs:__imp_GetLastError
0x1800d4091  mov     ebx, eax
0x1800d4093  test    eax, eax
0x1800d4095  jle     short loc_1800D40A0
0x1800d4097  movzx   ebx, ax
0x1800d409a  or      ebx, 80070000h
0x1800d40a0  test    ebx, ebx
0x1800d40a2  jns     short loc_1800D40CF
0x1800d40a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d40ab  lea     rax, WPP_GLOBAL_Control
0x1800d40b2  cmp     rcx, rax
0x1800d40b5  jz      loc_1800D3FA6
0x1800d40bb  test    byte ptr [rcx+1Ch], 1
0x1800d40bf  jz      loc_1800D3FA6
0x1800d40c5  mov     edx, 15h
0x1800d40ca  jmp     loc_1800D3F93
0x1800d40cf  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d40d3  test    rcx, rcx
0x1800d40d6  jz      short loc_1800D40DE
0x1800d40d8  call    cs:__imp_CloseHandle
0x1800d40de  xor     eax, eax
0x1800d40e0  add     rsp, 30h
0x1800d40e4  pop     rdi
0x1800d40e5  pop     rbx
0x1800d40e6  pop     rbp
0x1800d40e7  retn
```
