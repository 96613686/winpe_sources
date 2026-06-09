# GetCurrentUserSid(_SID * *)

- ea: `0x180042964`
- end: `0x180042e23`
- name: `?GetCurrentUserSid@@YAJPEAPEAU_SID@@@Z`
- size: `1215`
- prototype: `__int64 __fastcall(struct _SID **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800435fc`

## callees

- `0x180003108`
- `0x18000b1d8`
- `0x18000ec94`
- `0x180042964`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180042df9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180042df9`
- `ADVAPI32!OpenThreadToken` at `0x1800429a2`
- `ADVAPI32!OpenThreadToken` at `0x1800429a2`
- `ADVAPI32!OpenProcessToken` at `0x180042a3a`
- `ADVAPI32!OpenProcessToken` at `0x180042a3a`
- `ADVAPI32!GetTokenInformation` at `0x180042ad1`
- `ADVAPI32!GetTokenInformation` at `0x180042c0c`
- `ADVAPI32!GetTokenInformation` at `0x180042ad1`
- `ADVAPI32!GetTokenInformation` at `0x180042c0c`
- `ADVAPI32!CopySid` at `0x180042d9a`
- `ADVAPI32!CopySid` at `0x180042d9a`
- `ADVAPI32!GetLengthSid` at `0x180042cf2`
- `ADVAPI32!GetLengthSid` at `0x180042cf2`
- `ADVAPI32!IsValidSid` at `0x180042c90`
- `ADVAPI32!IsValidSid` at `0x180042c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800429b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042dd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800429b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042dd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042a2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042a2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042e08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042e08`
- `KERNEL32!GetCurrentThread` at `0x18004298b`
- `KERNEL32!GetCurrentThread` at `0x18004298b`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(struct _SID **a1)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  unsigned int v4; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  HANDLE CurrentProcess; // rax
  signed int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  signed int v11; // eax
  unsigned int v12; // eax
  PSID *v13; // rsi
  unsigned int v14; // eax
  signed int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  __int64 v18; // rdx
  signed int v19; // eax
  unsigned int v20; // eax
  __int64 v21; // rdx
  DWORD LengthSid; // eax
  DWORD v23; // ebx
  struct _SID *v24; // rax
  unsigned int v25; // eax
  signed int v26; // eax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    goto LABEL_85;
  LastError = GetLastError();
  if ( LastError != 1008 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    else
      v4 = LastError;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 10;
LABEL_10:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_060bbe8053683a966e9955f0decff737_Traceguids,
      CurrentThreadActivityIdPrefix,
      v4);
LABEL_11:
    if ( LastError <= 0 )
      goto LABEL_80;
    LastError = (unsigned __int16)LastError;
    goto LABEL_13;
  }
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
LABEL_85:
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, TokenInformationLength, &TokenInformationLength) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_060bbe8053683a966e9955f0decff737_Traceguids,
          v12,
          -2147418113);
      }
      LastError = -2147418113;
      goto LABEL_80;
    }
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_11;
      }
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      else
        v4 = LastError;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 13;
      goto LABEL_10;
    }
    v13 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v13 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_060bbe8053683a966e9955f0decff737_Traceguids,
          v14,
          -2147024882);
      }
      LastError = -2147024882;
      goto LABEL_80;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, v13, TokenInformationLength, &TokenInformationLength) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = GetLastError();
        v16 = v15;
        if ( v15 > 0 )
          v16 = (unsigned __int16)v15 | 0x80070000;
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = 15;
LABEL_50:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_060bbe8053683a966e9955f0decff737_Traceguids, v17, v16);
        goto LABEL_51;
      }
      goto LABEL_51;
    }
    if ( IsValidSid(*v13) )
    {
      LengthSid = GetLengthSid(*v13);
      v23 = LengthSid;
      if ( LengthSid )
      {
        v24 = (struct _SID *)operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
        *a1 = v24;
        if ( !v24 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v25 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              WPP_060bbe8053683a966e9955f0decff737_Traceguids,
              v25,
              -2147024882);
          }
          LastError = -2147024882;
          goto LABEL_79;
        }
        if ( !CopySid(v23, v24, *v13) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v26 = GetLastError();
            v16 = v26;
            if ( v26 > 0 )
              v16 = (unsigned __int16)v26 | 0x80070000;
            v17 = RdpWppGetCurrentThreadActivityIdPrefix();
            v18 = 19;
            goto LABEL_50;
          }
LABEL_51:
          v19 = GetLastError();
          LastError = v19;
          if ( v19 > 0 )
            LastError = (unsigned __int16)v19 | 0x80070000;
          goto LABEL_79;
        }
        LastError = 0;
LABEL_79:
        operator delete[](v13);
        goto LABEL_80;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_59:
        LastError = -2147418113;
        goto LABEL_79;
      }
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 17;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 16;
    }
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v21,
      WPP_060bbe8053683a966e9955f0decff737_Traceguids,
      v20,
      -2147418113);
    goto LABEL_59;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_060bbe8053683a966e9955f0decff737_Traceguids, v10, v9);
  }
  v11 = GetLastError();
  LastError = v11;
  if ( v11 > 0 )
  {
    LastError = (unsigned __int16)v11;
LABEL_13:
    LastError |= 0x80070000;
  }
LABEL_80:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180042964  mov     [rsp-18h+arg_0], rbx
0x180042969  mov     [rsp-18h+arg_18], rsi
0x18004296e  push    rbp
0x18004296f  push    rdi
0x180042970  push    r14
0x180042972  mov     rbp, rsp
0x180042975  sub     rsp, 30h
0x180042979  mov     rdi, rcx
0x18004297c  mov     [rbp+TokenHandle], 0
0x180042984  mov     [rbp+TokenInformationLength], 0
0x18004298b  call    cs:__imp_GetCurrentThread
0x180042991  xor     r8d, r8d; OpenAsSelf
0x180042994  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180042998  mov     rcx, rax; ThreadHandle
0x18004299b  lea     r14d, [r8+8]
0x18004299f  mov     edx, r14d; DesiredAccess
0x1800429a2  call    cs:__imp_OpenThreadToken
0x1800429a8  test    eax, eax
0x1800429aa  jnz     loc_180042AB9
0x1800429b0  call    cs:__imp_GetLastError
0x1800429b6  mov     ebx, eax
0x1800429b8  cmp     eax, 3F0h
0x1800429bd  jz      short loc_180042A2A
0x1800429bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800429c6  lea     rax, WPP_GLOBAL_Control
0x1800429cd  mov     edi, 80070000h
0x1800429d2  cmp     rcx, rax
0x1800429d5  jz      short loc_180042A18
0x1800429d7  test    [rcx+1Ch], r14b
0x1800429db  jz      short loc_180042A18
0x1800429dd  cmp     byte ptr [rcx+19h], 2
0x1800429e1  jb      short loc_180042A18
0x1800429e3  test    ebx, ebx
0x1800429e5  jg      short loc_1800429EB
0x1800429e7  mov     esi, ebx
0x1800429e9  jmp     short loc_1800429F0
0x1800429eb  movzx   esi, bx
0x1800429ee  or      esi, edi
0x1800429f0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800429f5  mov     edx, 0Ah
0x1800429fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a01  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x180042a08  mov     r9d, eax
0x180042a0b  mov     dword ptr [rsp+30h+ReturnLength], esi
0x180042a0f  mov     rcx, [rcx+10h]
0x180042a13  call    WPP_SF_Dd
0x180042a18  test    ebx, ebx
0x180042a1a  jle     loc_180042DFF
0x180042a20  movzx   ebx, bx
0x180042a23  or      ebx, edi
0x180042a25  jmp     loc_180042DFF
0x180042a2a  call    cs:__imp_GetCurrentProcess
0x180042a30  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180042a34  mov     edx, r14d; DesiredAccess
0x180042a37  mov     rcx, rax; ProcessHandle
0x180042a3a  call    cs:__imp_OpenProcessToken
0x180042a40  test    eax, eax
0x180042a42  jnz     short loc_180042AB9
0x180042a44  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a4b  lea     rax, WPP_GLOBAL_Control
0x180042a52  mov     edi, 80070000h
0x180042a57  cmp     rcx, rax
0x180042a5a  jz      short loc_180042AA1
0x180042a5c  test    [rcx+1Ch], r14b
0x180042a60  jz      short loc_180042AA1
0x180042a62  cmp     byte ptr [rcx+19h], 2
0x180042a66  jb      short loc_180042AA1
0x180042a68  call    cs:__imp_GetLastError
0x180042a6e  mov     ebx, eax
0x180042a70  test    eax, eax
0x180042a72  jle     short loc_180042A79
0x180042a74  movzx   ebx, ax
0x180042a77  or      ebx, edi
0x180042a79  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180042a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a85  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x180042a8c  mov     edx, 0Bh
0x180042a91  mov     dword ptr [rsp+30h+ReturnLength], ebx
0x180042a95  mov     r9d, eax
0x180042a98  mov     rcx, [rcx+10h]
0x180042a9c  call    WPP_SF_Dd
0x180042aa1  call    cs:__imp_GetLastError
0x180042aa7  mov     ebx, eax
0x180042aa9  test    eax, eax
0x180042aab  jle     loc_180042DFF
0x180042ab1  movzx   ebx, ax
0x180042ab4  jmp     loc_180042A23
0x180042ab9  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180042abd  lea     rax, [rbp+TokenInformationLength]
0x180042ac1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180042ac5  xor     r8d, r8d; TokenInformation
0x180042ac8  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180042acd  lea     edx, [r8+1]; TokenInformationClass
0x180042ad1  call    cs:__imp_GetTokenInformation
0x180042ad7  test    eax, eax
0x180042ad9  jz      short loc_180042B30
0x180042adb  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ae2  lea     rax, WPP_GLOBAL_Control
0x180042ae9  cmp     rcx, rax
0x180042aec  jz      short loc_180042B26
0x180042aee  test    [rcx+1Ch], r14b
0x180042af2  jz      short loc_180042B26
0x180042af4  cmp     byte ptr [rcx+19h], 2
0x180042af8  jb      short loc_180042B26
0x180042afa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180042aff  mov     rcx, cs:WPP_GLOBAL_Control
0x180042b06  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x180042b0d  mov     edx, 0Ch
0x180042b12  mov     dword ptr [rsp+30h+ReturnLength], 8000FFFFh
0x180042b1a  mov     r9d, eax
0x180042b1d  mov     rcx, [rcx+10h]
0x180042b21  call    WPP_SF_Dd
0x180042b26  mov     ebx, 8000FFFFh
0x180042b2b  jmp     loc_180042DFF
0x180042b30  call    cs:__imp_GetLastError
0x180042b36  mov     ebx, eax
0x180042b38  cmp     eax, 7Ah ; 'z'
0x180042b3b  jz      short loc_180042B89
0x180042b3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180042b44  lea     rax, WPP_GLOBAL_Control
0x180042b4b  mov     edi, 80070000h
0x180042b50  cmp     rcx, rax
0x180042b53  jz      loc_180042A18
0x180042b59  test    [rcx+1Ch], r14b
0x180042b5d  jz      loc_180042A18
0x180042b63  cmp     byte ptr [rcx+19h], 2
0x180042b67  jb      loc_180042A18
0x180042b6d  test    ebx, ebx
0x180042b6f  jg      short loc_180042B75
0x180042b71  mov     esi, ebx
0x180042b73  jmp     short loc_180042B7A
0x180042b75  movzx   esi, bx
0x180042b78  or      esi, edi
0x180042b7a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180042b7f  mov     edx, 0Dh
0x180042b84  jmp     loc_1800429FA
0x180042b89  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x180042b8c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180042b93  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180042b98  mov     rsi, rax
0x180042b9b  test    rax, rax
0x180042b9e  jnz     short loc_180042BF3
0x180042ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ba7  lea     rax, WPP_GLOBAL_Control
0x180042bae  cmp     rcx, rax
0x180042bb1  jz      short loc_180042BE9
0x180042bb3  test    [rcx+1Ch], r14b
0x180042bb7  jz      short loc_180042BE9
0x180042bb9  cmp     byte ptr [rcx+19h], 2
0x180042bbd  jb      short loc_180042BE9
0x180042bbf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180042bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180042bcb  lea     edx, [rsi+0Eh]
0x180042bce  mov     r9d, eax
0x180042bd1  mov     dword ptr [rsp+30h+ReturnLength], 8007000Eh
0x180042bd9  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x180042be0  mov     rcx, [rcx+10h]
0x180042be4  call    WPP_SF_Dd
0x180042be9  mov     ebx, 8007000Eh
0x180042bee  jmp     loc_180042DFF
0x180042bf3  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180042bf7  lea     rax, [rbp+TokenInformationLength]
0x180042bfb  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180042bff  mov     r8, rsi; TokenInformation
0x180042c02  mov     edx, 1; TokenInformationClass
0x180042c07  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180042c0c  call    cs:__imp_GetTokenInformation
0x180042c12  test    eax, eax
0x180042c14  jnz     short loc_180042C8D
0x180042c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c1d  lea     rax, WPP_GLOBAL_Control
0x180042c24  mov     edi, 80070000h
0x180042c29  cmp     rcx, rax
0x180042c2c  jz      short loc_180042C73
0x180042c2e  test    [rcx+1Ch], r14b
0x180042c32  jz      short loc_180042C73
0x180042c34  cmp     byte ptr [rcx+19h], 2
0x180042c38  jb      short loc_180042C73
0x180042c3a  call    cs:__imp_GetLastError
0x180042c40  mov     ebx, eax
0x180042c42  test    eax, eax
0x180042c44  jle     short loc_180042C4B
0x180042c46  movzx   ebx, ax
0x180042c49  or      ebx, edi
0x180042c4b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180042c50  mov     edx, 0Fh
0x180042c55  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c5c  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x180042c63  mov     r9d, eax
0x180042c66  mov     dword ptr [rsp+30h+ReturnLength], ebx
0x180042c6a  mov     rcx, [rcx+10h]
0x180042c6e  call    WPP_SF_Dd
0x180042c73  call    cs:__imp_GetLastError
0x180042c79  mov     ebx, eax
0x180042c7b  test    eax, eax
0x180042c7d  jle     loc_180042DF6
0x180042c83  movzx   ebx, ax
0x180042c86  or      ebx, edi
0x180042c88  jmp     loc_180042DF6
0x180042c8d  mov     rcx, [rsi]; pSid
0x180042c90  call    cs:__imp_IsValidSid
0x180042c96  test    eax, eax
0x180042c98  jnz     short loc_180042CEF
0x180042c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ca1  lea     rax, WPP_GLOBAL_Control
0x180042ca8  cmp     rcx, rax
0x180042cab  jz      short loc_180042CE5
0x180042cad  test    [rcx+1Ch], r14b
0x180042cb1  jz      short loc_180042CE5
0x180042cb3  cmp     byte ptr [rcx+19h], 2
0x180042cb7  jb      short loc_180042CE5
0x180042cb9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180042cbe  mov     edx, 10h
0x180042cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180042cca  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x180042cd1  mov     r9d, eax
0x180042cd4  mov     dword ptr [rsp+30h+ReturnLength], 8000FFFFh
0x180042cdc  mov     rcx, [rcx+10h]
0x180042ce0  call    WPP_SF_Dd
0x180042ce5  mov     ebx, 8000FFFFh
0x180042cea  jmp     loc_180042DF6
0x180042cef  mov     rcx, [rsi]; pSid
0x180042cf2  call    cs:__imp_GetLengthSid
0x180042cf8  mov     ebx, eax
0x180042cfa  test    eax, eax
0x180042cfc  jnz     short loc_180042D29
0x180042cfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d05  lea     rax, WPP_GLOBAL_Control
0x180042d0c  cmp     rcx, rax
0x180042d0f  jz      short loc_180042CE5
0x180042d11  test    [rcx+1Ch], r14b
0x180042d15  jz      short loc_180042CE5
0x180042d17  cmp     byte ptr [rcx+19h], 2
0x180042d1b  jb      short loc_180042CE5
0x180042d1d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180042d22  mov     edx, 11h
0x180042d27  jmp     short loc_180042CC3
0x180042d29  mov     rcx, rbx; unsigned __int64
0x180042d2c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180042d33  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180042d38  mov     [rdi], rax
0x180042d3b  test    rax, rax
0x180042d3e  jnz     short loc_180042D92
0x180042d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d47  lea     rax, WPP_GLOBAL_Control
0x180042d4e  cmp     rcx, rax
0x180042d51  jz      short loc_180042D8B
0x180042d53  test    [rcx+1Ch], r14b
0x180042d57  jz      short loc_180042D8B
0x180042d59  cmp     byte ptr [rcx+19h], 2
0x180042d5d  jb      short loc_180042D8B
0x180042d5f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180042d64  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d6b  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x180042d72  mov     edx, 12h
0x180042d77  mov     dword ptr [rsp+30h+ReturnLength], 8007000Eh
0x180042d7f  mov     r9d, eax
0x180042d82  mov     rcx, [rcx+10h]
0x180042d86  call    WPP_SF_Dd
0x180042d8b  mov     ebx, 8007000Eh
0x180042d90  jmp     short loc_180042DF6
0x180042d92  mov     r8, [rsi]; pSourceSid
0x180042d95  mov     rdx, rax; pDestinationSid
0x180042d98  mov     ecx, ebx; nDestinationSidLength
0x180042d9a  call    cs:__imp_CopySid
0x180042da0  test    eax, eax
0x180042da2  jnz     short loc_180042DF4
0x180042da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180042dab  lea     rax, WPP_GLOBAL_Control
0x180042db2  mov     edi, 80070000h
0x180042db7  cmp     rcx, rax
0x180042dba  jz      loc_180042C73
0x180042dc0  test    [rcx+1Ch], r14b
0x180042dc4  jz      loc_180042C73
0x180042dca  cmp     byte ptr [rcx+19h], 2
0x180042dce  jb      loc_180042C73
0x180042dd4  call    cs:__imp_GetLastError
0x180042dda  mov     ebx, eax
0x180042ddc  test    eax, eax
0x180042dde  jle     short loc_180042DE5
0x180042de0  movzx   ebx, ax
0x180042de3  or      ebx, edi
0x180042de5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180042dea  mov     edx, 13h
0x180042def  jmp     loc_180042C55
0x180042df4  xor     ebx, ebx
0x180042df6  mov     rcx, rsi
0x180042df9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180042dff  mov     rcx, [rbp+TokenHandle]; hObject
0x180042e03  test    rcx, rcx
0x180042e06  jz      short loc_180042E0E
0x180042e08  call    cs:__imp_CloseHandle
0x180042e0e  mov     rsi, [rsp+30h+arg_18]
0x180042e13  mov     eax, ebx
0x180042e15  mov     rbx, [rsp+30h+arg_0]
0x180042e1a  add     rsp, 30h
0x180042e1e  pop     r14
0x180042e20  pop     rdi
0x180042e21  pop     rbp
0x180042e22  retn
  ... truncated ...
```
