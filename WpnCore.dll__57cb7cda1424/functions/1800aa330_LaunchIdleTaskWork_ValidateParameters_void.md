# LaunchIdleTaskWork::ValidateParameters(void)

- ea: `0x1800aa330`
- end: `0x1800aa6d4`
- name: `?ValidateParameters@LaunchIdleTaskWork@@UEAAJXZ`
- size: `932`
- prototype: `__int64 __fastcall(LaunchIdleTaskWork *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18002ee38`
- `0x18003a184`
- `0x1800aa330`
- `0x1800af0a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa47d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa47d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aa46e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aa69b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aa46e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aa69b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa6a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa6a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa36e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa500`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa56d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa36e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa500`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa56d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800aa34f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800aa34f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800aa364`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800aa364`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa6b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa6b9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800aa3f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800aa4f6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800aa3f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800aa4f6`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800aa5e2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800aa5e2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800aa563`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800aa563`

## string_xrefs

- `0x1800aa38c`: `onecoreuap\base\diagnosis\platform\notifications\platform\infra\launchidletaskwork.cpp`
- `0x1800aa42b`: `onecoreuap\base\diagnosis\platform\notifications\platform\infra\launchidletaskwork.cpp`
- `0x1800aa490`: `onecoreuap\base\diagnosis\platform\notifications\platform\infra\launchidletaskwork.cpp`
- `0x1800aa51a`: `onecoreuap\base\diagnosis\platform\notifications\platform\infra\launchidletaskwork.cpp`
- `0x1800aa587`: `onecoreuap\base\diagnosis\platform\notifications\platform\infra\launchidletaskwork.cpp`
- `0x1800aa5f6`: `onecoreuap\base\diagnosis\platform\notifications\platform\infra\launchidletaskwork.cpp`
- `0x1800aa656`: `onecoreuap\base\diagnosis\platform\notifications\platform\infra\launchidletaskwork.cpp`

## pseudocode

```c
__int64 __fastcall LaunchIdleTaskWork::ValidateParameters(LaunchIdleTaskWork *this)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  signed int v8; // eax
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v11; // r14
  signed int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  _QWORD *v15; // rbx
  signed int v16; // eax
  __int64 v17; // rax
  unsigned __int64 v18; // rdi
  unsigned __int16 *v19; // rax
  __int64 v20; // r9
  int v21; // eax
  HANDLE v22; // rax
  int ReturnLength; // [rsp+20h] [rbp-28h]
  int ReturnLengtha; // [rsp+20h] [rbp-28h]
  int ReturnLengthb; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\launchidletaskwork.cpp",
        (const char *)(unsigned int)v4,
        ReturnLength);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v6 = 16;
LABEL_9:
      v7 = (unsigned int)v4;
LABEL_10:
      WPP_SF_d(v5[2], v6, WPP_51c9c895e5963bbc29cf904f7338ca21_Traceguids, v7);
      goto LABEL_53;
    }
    goto LABEL_53;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    goto LABEL_20;
  v8 = GetLastError();
  v4 = v8;
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x80070000;
  if ( GetLastError() == 122 )
  {
LABEL_20:
    v9 = TokenInformationLength;
    ProcessHeap = GetProcessHeap();
    v11 = (PSID *)HeapAlloc(ProcessHeap, 8u, v9);
    if ( !v11 )
    {
      v4 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\launchidletaskwork.cpp",
        (const char *)0x8007000ELL,
        ReturnLengtha);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v6 = 19;
        v7 = 2147942414LL;
        goto LABEL_10;
      }
      goto LABEL_53;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
    {
      v15 = (_QWORD *)((char *)this + 32);
      if ( ConvertSidToStringSidW(*v11, (LPWSTR *)this + 4) )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_WORD *)(*v15 + 2 * v17) );
        v18 = v17 + 40;
        *((_QWORD *)this + 5) = v17;
        v19 = SysAllocStringLen(0, (int)v17 + 40);
        *((_QWORD *)this + 3) = v19;
        if ( !v19 )
        {
          v4 = -2147024882;
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xEB,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\launchidletaskwork.cpp",
            (const char *)0x8007000ELL,
            ReturnLengthb);
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_52;
          v14 = 22;
          v20 = 2147942414LL;
LABEL_51:
          WPP_SF_d(v13[2], v14, WPP_51c9c895e5963bbc29cf904f7338ca21_Traceguids, v20);
LABEL_52:
          v22 = GetProcessHeap();
          HeapFree(v22, 0, v11);
          goto LABEL_53;
        }
        v21 = StringCchPrintfW(v19, v18, L"Optimize Push Notification Data File-%s", *v15);
        v4 = v21;
        if ( v21 >= 0 )
          goto LABEL_52;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\launchidletaskwork.cpp",
          (const char *)(unsigned int)v21,
          ReturnLengthb);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_52;
        v14 = 23;
      }
      else
      {
        v16 = GetLastError();
        v4 = v16;
        if ( v16 > 0 )
          v4 = (unsigned __int16)v16 | 0x80070000;
        if ( v4 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xE3,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\launchidletaskwork.cpp",
            (const char *)(unsigned int)v4,
            ReturnLengthb);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_52;
        v14 = 21;
      }
    }
    else
    {
      v12 = GetLastError();
      v4 = v12;
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      if ( v4 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\launchidletaskwork.cpp",
          (const char *)(unsigned int)v4,
          ReturnLengthb);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_52;
      v14 = 20;
    }
    v20 = (unsigned int)v4;
    goto LABEL_51;
  }
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\launchidletaskwork.cpp",
      (const char *)(unsigned int)v4,
      ReturnLengtha);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v6 = 18;
    goto LABEL_9;
  }
LABEL_53:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800aa330  mov     rax, rsp
0x1800aa333  mov     [rax+8], rbx
0x1800aa337  mov     [rax+20h], rbp
0x1800aa33b  push    rsi
0x1800aa33c  push    rdi
0x1800aa33d  push    r14
0x1800aa33f  sub     rsp, 30h
0x1800aa343  xor     ebp, ebp
0x1800aa345  mov     rsi, rcx
0x1800aa348  mov     [rax+10h], ebp
0x1800aa34b  mov     [rax+18h], rbp
0x1800aa34f  call    cs:__imp_GetCurrentProcess
0x1800aa355  lea     r14d, [rbp+8]
0x1800aa359  mov     rcx, rax; ProcessHandle
0x1800aa35c  mov     edx, r14d; DesiredAccess
0x1800aa35f  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x1800aa364  call    cs:__imp_OpenProcessToken
0x1800aa36a  test    eax, eax
0x1800aa36c  jnz     short loc_1800AA3DE
0x1800aa36e  call    cs:__imp_GetLastError
0x1800aa374  mov     ebx, eax
0x1800aa376  test    eax, eax
0x1800aa378  jle     short loc_1800AA383
0x1800aa37a  movzx   ebx, ax
0x1800aa37d  or      ebx, 80070000h
0x1800aa383  test    ebx, ebx
0x1800aa385  jns     short loc_1800AA3A0
0x1800aa387  mov     rcx, [rsp+48h]; this
0x1800aa38c  lea     r8, aOnecoreuapBase_146; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800aa393  mov     r9d, ebx; char *
0x1800aa396  mov     edx, 0C3h; void *
0x1800aa39b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aa3a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa3a7  lea     rax, WPP_GLOBAL_Control
0x1800aa3ae  cmp     rcx, rax
0x1800aa3b1  jz      loc_1800AA6AF
0x1800aa3b7  test    byte ptr [rcx+1Ch], 80h
0x1800aa3bb  jz      loc_1800AA6AF
0x1800aa3c1  mov     edx, 10h
0x1800aa3c6  mov     r9d, ebx
0x1800aa3c9  mov     rcx, [rcx+10h]
0x1800aa3cd  lea     r8, WPP_51c9c895e5963bbc29cf904f7338ca21_Traceguids
0x1800aa3d4  call    WPP_SF_d
0x1800aa3d9  jmp     loc_1800AA6AF
0x1800aa3de  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1800aa3e3  lea     rax, [rsp+48h+TokenInformationLength]
0x1800aa3e8  xor     r9d, r9d; TokenInformationLength
0x1800aa3eb  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x1800aa3f0  xor     r8d, r8d; TokenInformation
0x1800aa3f3  lea     edx, [r9+1]; TokenInformationClass
0x1800aa3f7  call    cs:__imp_GetTokenInformation
0x1800aa3fd  mov     edi, 80070000h
0x1800aa402  test    eax, eax
0x1800aa404  jnz     short loc_1800AA46A
0x1800aa406  call    cs:__imp_GetLastError
0x1800aa40c  mov     ebx, eax
0x1800aa40e  test    eax, eax
0x1800aa410  jle     short loc_1800AA417
0x1800aa412  movzx   ebx, ax
0x1800aa415  or      ebx, edi
0x1800aa417  call    cs:__imp_GetLastError
0x1800aa41d  cmp     eax, 7Ah ; 'z'
0x1800aa420  jz      short loc_1800AA46A
0x1800aa422  test    ebx, ebx
0x1800aa424  jns     short loc_1800AA43F
0x1800aa426  mov     rcx, [rsp+48h]; this
0x1800aa42b  lea     r8, aOnecoreuapBase_146; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800aa432  mov     r9d, ebx; char *
0x1800aa435  mov     edx, 0CDh; void *
0x1800aa43a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aa43f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa446  lea     rax, WPP_GLOBAL_Control
0x1800aa44d  cmp     rcx, rax
0x1800aa450  jz      loc_1800AA6AF
0x1800aa456  test    byte ptr [rcx+1Ch], 80h
0x1800aa45a  jz      loc_1800AA6AF
0x1800aa460  mov     edx, 12h
0x1800aa465  jmp     loc_1800AA3C6
0x1800aa46a  mov     ebx, [rsp+48h+TokenInformationLength]
0x1800aa46e  call    cs:__imp_GetProcessHeap
0x1800aa474  mov     r8d, ebx; dwBytes
0x1800aa477  mov     edx, r14d; dwFlags
0x1800aa47a  mov     rcx, rax; hHeap
0x1800aa47d  call    cs:__imp_HeapAlloc
0x1800aa483  mov     r14, rax
0x1800aa486  test    rax, rax
0x1800aa489  jnz     short loc_1800AA4DA
0x1800aa48b  mov     rcx, [rsp+48h]; this
0x1800aa490  lea     r8, aOnecoreuapBase_146; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800aa497  mov     r9d, 8007000Eh; char *
0x1800aa49d  mov     edx, 0D2h; void *
0x1800aa4a2  mov     ebx, r9d
0x1800aa4a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aa4aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa4b1  lea     rax, WPP_GLOBAL_Control
0x1800aa4b8  cmp     rcx, rax
0x1800aa4bb  jz      loc_1800AA6AF
0x1800aa4c1  test    byte ptr [rcx+1Ch], 80h
0x1800aa4c5  jz      loc_1800AA6AF
0x1800aa4cb  lea     edx, [r14+13h]
0x1800aa4cf  mov     r9d, 8007000Eh
0x1800aa4d5  jmp     loc_1800AA3C9
0x1800aa4da  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800aa4df  lea     rax, [rsp+48h+TokenInformationLength]
0x1800aa4e4  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1800aa4e9  mov     r8, r14; TokenInformation
0x1800aa4ec  mov     edx, 1; TokenInformationClass
0x1800aa4f1  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x1800aa4f6  call    cs:__imp_GetTokenInformation
0x1800aa4fc  test    eax, eax
0x1800aa4fe  jnz     short loc_1800AA559
0x1800aa500  call    cs:__imp_GetLastError
0x1800aa506  mov     ebx, eax
0x1800aa508  test    eax, eax
0x1800aa50a  jle     short loc_1800AA511
0x1800aa50c  movzx   ebx, ax
0x1800aa50f  or      ebx, edi
0x1800aa511  test    ebx, ebx
0x1800aa513  jns     short loc_1800AA52E
0x1800aa515  mov     rcx, [rsp+48h]; this
0x1800aa51a  lea     r8, aOnecoreuapBase_146; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800aa521  mov     r9d, ebx; char *
0x1800aa524  mov     edx, 0DCh; void *
0x1800aa529  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aa52e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa535  lea     rax, WPP_GLOBAL_Control
0x1800aa53c  cmp     rcx, rax
0x1800aa53f  jz      loc_1800AA69B
0x1800aa545  test    byte ptr [rcx+1Ch], 80h
0x1800aa549  jz      loc_1800AA69B
0x1800aa54f  mov     edx, 14h
0x1800aa554  jmp     loc_1800AA688
0x1800aa559  mov     rcx, [r14]; Sid
0x1800aa55c  lea     rbx, [rsi+20h]
0x1800aa560  mov     rdx, rbx; StringSid
0x1800aa563  call    cs:__imp_ConvertSidToStringSidW
0x1800aa569  test    eax, eax
0x1800aa56b  jnz     short loc_1800AA5C6
0x1800aa56d  call    cs:__imp_GetLastError
0x1800aa573  mov     ebx, eax
0x1800aa575  test    eax, eax
0x1800aa577  jle     short loc_1800AA57E
0x1800aa579  movzx   ebx, ax
0x1800aa57c  or      ebx, edi
0x1800aa57e  test    ebx, ebx
0x1800aa580  jns     short loc_1800AA59B
0x1800aa582  mov     rcx, [rsp+48h]; this
0x1800aa587  lea     r8, aOnecoreuapBase_146; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800aa58e  mov     r9d, ebx; char *
0x1800aa591  mov     edx, 0E3h; void *
0x1800aa596  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aa59b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa5a2  lea     rax, WPP_GLOBAL_Control
0x1800aa5a9  cmp     rcx, rax
0x1800aa5ac  jz      loc_1800AA69B
0x1800aa5b2  test    byte ptr [rcx+1Ch], 80h
0x1800aa5b6  jz      loc_1800AA69B
0x1800aa5bc  mov     edx, 15h
0x1800aa5c1  jmp     loc_1800AA688
0x1800aa5c6  mov     rcx, [rbx]
0x1800aa5c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800aa5cd  inc     rax
0x1800aa5d0  cmp     [rcx+rax*2], bp
0x1800aa5d4  jnz     short loc_1800AA5CD
0x1800aa5d6  lea     rdi, [rax+28h]
0x1800aa5da  mov     [rsi+28h], rax
0x1800aa5de  mov     edx, edi; ui
0x1800aa5e0  xor     ecx, ecx; strIn
0x1800aa5e2  call    cs:__imp_SysAllocStringLen
0x1800aa5e8  mov     [rsi+18h], rax
0x1800aa5ec  test    rax, rax
0x1800aa5ef  jnz     short loc_1800AA636
0x1800aa5f1  mov     rcx, [rsp+48h]; this
0x1800aa5f6  lea     r8, aOnecoreuapBase_146; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800aa5fd  mov     r9d, 8007000Eh; char *
0x1800aa603  mov     edx, 0EBh; void *
0x1800aa608  mov     ebx, r9d
0x1800aa60b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aa610  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa617  lea     rax, WPP_GLOBAL_Control
0x1800aa61e  cmp     rcx, rax
0x1800aa621  jz      short loc_1800AA69B
0x1800aa623  test    byte ptr [rcx+1Ch], 80h
0x1800aa627  jz      short loc_1800AA69B
0x1800aa629  mov     edx, 16h
0x1800aa62e  mov     r9d, 8007000Eh
0x1800aa634  jmp     short loc_1800AA68B
0x1800aa636  mov     r9, [rbx]
0x1800aa639  lea     r8, aOptimizePushNo; "Optimize Push Notification Data File-%s"
0x1800aa640  mov     rdx, rdi; unsigned __int64
0x1800aa643  mov     rcx, rax; unsigned __int16 *
0x1800aa646  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800aa64b  mov     ebx, eax
0x1800aa64d  test    eax, eax
0x1800aa64f  jns     short loc_1800AA69B
0x1800aa651  mov     rcx, [rsp+48h]; this
0x1800aa656  lea     r8, aOnecoreuapBase_146; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800aa65d  mov     r9d, eax; char *
0x1800aa660  mov     edx, 0EEh; void *
0x1800aa665  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aa66a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa671  lea     rax, WPP_GLOBAL_Control
0x1800aa678  cmp     rcx, rax
0x1800aa67b  jz      short loc_1800AA69B
0x1800aa67d  test    byte ptr [rcx+1Ch], 80h
0x1800aa681  jz      short loc_1800AA69B
0x1800aa683  mov     edx, 17h
0x1800aa688  mov     r9d, ebx
0x1800aa68b  mov     rcx, [rcx+10h]
0x1800aa68f  lea     r8, WPP_51c9c895e5963bbc29cf904f7338ca21_Traceguids
0x1800aa696  call    WPP_SF_d
0x1800aa69b  call    cs:__imp_GetProcessHeap
0x1800aa6a1  mov     r8, r14; lpMem
0x1800aa6a4  xor     edx, edx; dwFlags
0x1800aa6a6  mov     rcx, rax; hHeap
0x1800aa6a9  call    cs:__imp_HeapFree
0x1800aa6af  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800aa6b4  test    rcx, rcx
0x1800aa6b7  jz      short loc_1800AA6BF
0x1800aa6b9  call    cs:__imp_CloseHandle
0x1800aa6bf  mov     rbp, [rsp+48h+arg_18]
0x1800aa6c4  mov     eax, ebx
0x1800aa6c6  mov     rbx, [rsp+48h+arg_0]
0x1800aa6cb  add     rsp, 30h
0x1800aa6cf  pop     r14
0x1800aa6d1  pop     rdi
0x1800aa6d2  pop     rsi
0x1800aa6d3  retn
```
