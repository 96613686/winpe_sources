# PolicyTaskHelpers::TryGetLoggedOnUserToken(void * *)

- ea: `0x18002cbd4`
- end: `0x18002cf4b`
- name: `?TryGetLoggedOnUserToken@PolicyTaskHelpers@@YAJPEAPEAX@Z`
- size: `887`
- prototype: `__int64 __fastcall(PolicyTaskHelpers *__hidden this, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x18002c454`

## callees

- `0x180002590`
- `0x180002f98`
- `0x18002cbd4`
- `0x18002dccc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002cdd3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002cdd3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ce7a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ce7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cc3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cd35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cc3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cd35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cc37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cd2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ceb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cebc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cee5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cef3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cefc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cc37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cd2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ceb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cebc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cee5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cef3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cefc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf21`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002ce09`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002ce09`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18002ccb6`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18002ccb6`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18002cdbf`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18002cdbf`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18002cde5`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18002cde5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18002cc10`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18002cc10`
- `WTSAPI32!WTSQueryUserToken` at `0x18002cc55`
- `WTSAPI32!WTSQueryUserToken` at `0x18002cd4b`
- `WTSAPI32!WTSQueryUserToken` at `0x18002cc55`
- `WTSAPI32!WTSQueryUserToken` at `0x18002cd4b`
- `WTSAPI32!WTSFreeMemory` at `0x18002cd7c`
- `WTSAPI32!WTSFreeMemory` at `0x18002cecc`
- `WTSAPI32!WTSFreeMemory` at `0x18002cf0c`
- `WTSAPI32!WTSFreeMemory` at `0x18002cd7c`
- `WTSAPI32!WTSFreeMemory` at `0x18002cecc`
- `WTSAPI32!WTSFreeMemory` at `0x18002cf0c`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18002cc96`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18002cc96`

## pseudocode

```c
__int64 __fastcall PolicyTaskHelpers::TryGetLoggedOnUserToken(PolicyTaskHelpers *this, void **a2)
{
  DWORD active; // esi
  DWORD LastError; // ebx
  unsigned int v6; // r8d
  const char *v7; // r9
  char *Toolhelp32Snapshot; // rbx
  unsigned int v9; // r8d
  const char *v10; // r9
  PWTS_SESSION_INFOW v11; // rdi
  struct _WTS_SESSION_INFOW *v12; // r15
  HANDLE v13; // rsi
  DWORD v14; // ebx
  HANDLE v15; // rax
  char *v16; // rdx
  PWTS_SESSION_INFOW v17; // rcx
  HANDLE v18; // rcx
  BOOL i; // eax
  char *v20; // rdi
  unsigned int v21; // r8d
  const char *v22; // r9
  HANDLE v23; // r15
  DWORD v24; // esi
  unsigned int v25; // r8d
  const char *v26; // r9
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pCount; // [rsp+38h] [rbp-C8h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+40h] [rbp-C0h] BYREF
  PROCESSENTRY32W pe; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  *(_QWORD *)this = 0;
  hObject = 0;
  active = WTSGetActiveConsoleSessionId();
  if ( active != -1 )
  {
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(hObject);
      SetLastError(LastError);
    }
    hObject = 0;
    if ( WTSQueryUserToken(active, &hObject) )
    {
      *(_QWORD *)this = hObject;
      return 0;
    }
  }
  pCount = 0;
  ppSessionInfo = 0;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    v11 = ppSessionInfo;
    v12 = &ppSessionInfo[pCount];
    while ( 1 )
    {
      if ( v11 == v12 )
        goto LABEL_9;
      v13 = hObject;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v14 = GetLastError();
        CloseHandle(v13);
        SetLastError(v14);
      }
      hObject = 0;
      if ( WTSQueryUserToken(v11->SessionId, &hObject) )
        break;
      ++v11;
    }
    v15 = hObject;
    v16 = 0;
    v17 = ppSessionInfo;
    hObject = 0;
    *(_QWORD *)this = v15;
    if ( v17 )
    {
      WTSFreeMemory(v17);
      v16 = (char *)hObject;
    }
    if ( (unsigned __int64)(v16 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return 0;
    v18 = v16;
LABEL_39:
    CloseHandle(v18);
    return 0;
  }
  wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x32D, v6, v7);
LABEL_9:
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(2u, 0);
  if ( ((unsigned __int64)(Toolhelp32Snapshot + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
    || (wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x33B, v9, v10),
        (unsigned __int64)(Toolhelp32Snapshot - 1) <= 0xFFFFFFFFFFFFFFFDuLL) )
  {
    memset_0(&pe.cntUsage, 0, 0x234u);
    pe.dwSize = 568;
    for ( i = Process32FirstW(Toolhelp32Snapshot, &pe); ; i = Process32NextW(Toolhelp32Snapshot, &pe) )
    {
      if ( !i )
        goto LABEL_41;
      if ( !(unsigned int)_o__wcsicmp(pe.szExeFile, L"explorer.exe") )
        break;
    }
    if ( pe.th32ProcessID )
    {
      v20 = (char *)OpenProcess(0x1000u, 0, pe.th32ProcessID);
      if ( ((unsigned __int64)(v20 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
        || (wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x34F, v21, v22),
            (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL) )
      {
        v23 = hObject;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          v24 = GetLastError();
          CloseHandle(v23);
          SetLastError(v24);
        }
        hObject = 0;
        if ( !OpenProcessToken(v20, 8u, &hObject) )
          wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x352, v25, v26);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          *(_QWORD *)this = hObject;
          hObject = 0;
          CloseHandle(v20);
          CloseHandle(Toolhelp32Snapshot);
          if ( ppSessionInfo )
            WTSFreeMemory(ppSessionInfo);
          v18 = hObject;
          if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
            return 0;
          goto LABEL_39;
        }
        CloseHandle(v20);
      }
    }
LABEL_41:
    CloseHandle(Toolhelp32Snapshot);
  }
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 2147943568LL;
}

```

## disassembly

```asm
0x18002cbd4  push    rbp
0x18002cbd6  push    rbx
0x18002cbd7  push    rsi
0x18002cbd8  push    rdi
0x18002cbd9  push    r14
0x18002cbdb  push    r15
0x18002cbdd  lea     rbp, [rsp-1A8h]
0x18002cbe5  sub     rsp, 2A8h
0x18002cbec  mov     rax, cs:__security_cookie
0x18002cbf3  xor     rax, rsp
0x18002cbf6  mov     [rbp+1D0h+var_40], rax
0x18002cbfd  mov     r14, rcx
0x18002cc00  mov     qword ptr [rcx], 0
0x18002cc07  mov     [rsp+2D0h+hObject], 0
0x18002cc10  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18002cc16  mov     esi, eax
0x18002cc18  cmp     eax, 0FFFFFFFFh
0x18002cc1b  jz      short loc_18002CC6E
0x18002cc1d  mov     rdi, [rsp+2D0h+hObject]
0x18002cc22  lea     rdx, [rdi-1]
0x18002cc26  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002cc2a  ja      short loc_18002CC45
0x18002cc2c  call    cs:__imp_GetLastError
0x18002cc32  mov     rcx, rdi; hObject
0x18002cc35  mov     ebx, eax
0x18002cc37  call    cs:__imp_CloseHandle
0x18002cc3d  mov     ecx, ebx; dwErrCode
0x18002cc3f  call    cs:__imp_SetLastError
0x18002cc45  lea     rdx, [rsp+2D0h+hObject]; phToken
0x18002cc4a  mov     [rsp+2D0h+hObject], 0
0x18002cc53  mov     ecx, esi; SessionId
0x18002cc55  call    cs:__imp_WTSQueryUserToken
0x18002cc5b  test    eax, eax
0x18002cc5d  jz      short loc_18002CC6E
0x18002cc5f  mov     rax, [rsp+2D0h+hObject]
0x18002cc64  mov     [r14], rax
0x18002cc67  xor     eax, eax
0x18002cc69  jmp     loc_18002CF2C
0x18002cc6e  xor     edx, edx; Reserved
0x18002cc70  mov     [rsp+2D0h+var_298], 0
0x18002cc78  lea     rax, [rsp+2D0h+var_298]
0x18002cc7d  mov     [rsp+2D0h+ppSessionInfo], 0
0x18002cc86  lea     r9, [rsp+2D0h+ppSessionInfo]; ppSessionInfo
0x18002cc8b  mov     [rsp+2D0h+pCount], rax; pCount
0x18002cc90  xor     ecx, ecx; hServer
0x18002cc92  lea     r8d, [rdx+1]; Version
0x18002cc96  call    cs:__imp_WTSEnumerateSessionsW
0x18002cc9c  test    eax, eax
0x18002cc9e  jnz     short loc_18002CD00
0x18002cca0  mov     rcx, [rbp+1D8h]; this
0x18002cca7  mov     edx, 32Dh; void *
0x18002ccac  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002ccb1  xor     edx, edx; th32ProcessID
0x18002ccb3  lea     ecx, [rdx+2]; dwFlags
0x18002ccb6  call    cs:__imp_CreateToolhelp32Snapshot
0x18002ccbc  mov     rcx, [rbp+1D8h]; this
0x18002ccc3  mov     rbx, rax
0x18002ccc6  inc     rax
0x18002ccc9  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002cccf  jnz     loc_18002CD9D
0x18002ccd5  mov     edx, 33Bh; void *
0x18002ccda  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002ccdf  lea     rax, [rbx-1]
0x18002cce3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002cce7  jbe     loc_18002CD9D
0x18002cced  lea     rax, [rbx-1]
0x18002ccf1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ccf5  ja      loc_18002CF02
0x18002ccfb  jmp     loc_18002CEF9
0x18002cd00  mov     eax, [rsp+2D0h+var_298]
0x18002cd04  mov     rdi, [rsp+2D0h+ppSessionInfo]
0x18002cd09  lea     rcx, [rax+rax*2]
0x18002cd0d  lea     r15, [rdi+rcx*8]
0x18002cd11  jmp     short loc_18002CD59
0x18002cd13  mov     rsi, [rsp+2D0h+hObject]
0x18002cd18  lea     rax, [rsi-1]
0x18002cd1c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002cd20  ja      short loc_18002CD3B
0x18002cd22  call    cs:__imp_GetLastError
0x18002cd28  mov     rcx, rsi; hObject
0x18002cd2b  mov     ebx, eax
0x18002cd2d  call    cs:__imp_CloseHandle
0x18002cd33  mov     ecx, ebx; dwErrCode
0x18002cd35  call    cs:__imp_SetLastError
0x18002cd3b  mov     [rsp+2D0h+hObject], 0
0x18002cd44  lea     rdx, [rsp+2D0h+hObject]; phToken
0x18002cd49  mov     ecx, [rdi]; SessionId
0x18002cd4b  call    cs:__imp_WTSQueryUserToken
0x18002cd51  test    eax, eax
0x18002cd53  jnz     short loc_18002CD63
0x18002cd55  add     rdi, 18h
0x18002cd59  cmp     rdi, r15
0x18002cd5c  jnz     short loc_18002CD13
0x18002cd5e  jmp     loc_18002CCB1
0x18002cd63  mov     rax, [rsp+2D0h+hObject]
0x18002cd68  xor     edx, edx
0x18002cd6a  mov     rcx, [rsp+2D0h+ppSessionInfo]; pMemory
0x18002cd6f  mov     [rsp+2D0h+hObject], rdx
0x18002cd74  mov     [r14], rax
0x18002cd77  test    rcx, rcx
0x18002cd7a  jz      short loc_18002CD87
0x18002cd7c  call    cs:__imp_WTSFreeMemory
0x18002cd82  mov     rdx, [rsp+2D0h+hObject]
0x18002cd87  lea     rax, [rdx-1]
0x18002cd8b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002cd8f  ja      loc_18002CC67
0x18002cd95  mov     rcx, rdx
0x18002cd98  jmp     loc_18002CEE5
0x18002cd9d  xor     edx, edx; Val
0x18002cd9f  lea     rcx, [rsp+2D0h+pe.cntUsage]; void *
0x18002cda4  mov     r8d, 234h; Size
0x18002cdaa  call    memset_0
0x18002cdaf  lea     rdx, [rsp+2D0h+pe]; lppe
0x18002cdb4  mov     [rsp+2D0h+pe.dwSize], 238h
0x18002cdbc  mov     rcx, rbx; hSnapshot
0x18002cdbf  call    cs:__imp_Process32FirstW
0x18002cdc5  jmp     short loc_18002CDEB
0x18002cdc7  lea     rdx, aExplorerExe; "explorer.exe"
0x18002cdce  lea     rcx, [rsp+2D0h+pe.szExeFile]
0x18002cdd3  call    cs:__imp__o__wcsicmp
0x18002cdd9  test    eax, eax
0x18002cddb  jz      short loc_18002CDF4
0x18002cddd  lea     rdx, [rsp+2D0h+pe]; lppe
0x18002cde2  mov     rcx, rbx; hSnapshot
0x18002cde5  call    cs:__imp_Process32NextW
0x18002cdeb  test    eax, eax
0x18002cded  jnz     short loc_18002CDC7
0x18002cdef  jmp     loc_18002CEF9
0x18002cdf4  mov     r8d, [rsp+2D0h+pe.th32ProcessID]; dwProcessId
0x18002cdf9  test    r8d, r8d
0x18002cdfc  jz      loc_18002CEF9
0x18002ce02  xor     edx, edx; bInheritHandle
0x18002ce04  mov     ecx, 1000h; dwDesiredAccess
0x18002ce09  call    cs:__imp_OpenProcess
0x18002ce0f  mov     rcx, [rbp+1D8h]; this
0x18002ce16  mov     rdi, rax
0x18002ce19  inc     rax
0x18002ce1c  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002ce22  jnz     short loc_18002CE3C
0x18002ce24  mov     edx, 34Fh; void *
0x18002ce29  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002ce2e  lea     rax, [rdi-1]
0x18002ce32  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ce36  ja      loc_18002CEF9
0x18002ce3c  mov     r15, [rsp+2D0h+hObject]
0x18002ce41  lea     rax, [r15-1]
0x18002ce45  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ce49  ja      short loc_18002CE64
0x18002ce4b  call    cs:__imp_GetLastError
0x18002ce51  mov     rcx, r15; hObject
0x18002ce54  mov     esi, eax
0x18002ce56  call    cs:__imp_CloseHandle
0x18002ce5c  mov     ecx, esi; dwErrCode
0x18002ce5e  call    cs:__imp_SetLastError
0x18002ce64  lea     r8, [rsp+2D0h+hObject]; TokenHandle
0x18002ce69  mov     [rsp+2D0h+hObject], 0
0x18002ce72  mov     edx, 8; DesiredAccess
0x18002ce77  mov     rcx, rdi; ProcessHandle
0x18002ce7a  call    cs:__imp_OpenProcessToken
0x18002ce80  test    eax, eax
0x18002ce82  jnz     short loc_18002CE95
0x18002ce84  mov     rcx, [rbp+1D8h]; this
0x18002ce8b  mov     edx, 352h; void *
0x18002ce90  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002ce95  mov     rcx, [rsp+2D0h+hObject]
0x18002ce9a  lea     rax, [rcx-1]
0x18002ce9e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002cea2  ja      short loc_18002CEF0
0x18002cea4  mov     [r14], rcx
0x18002cea7  mov     rcx, rdi; hObject
0x18002ceaa  mov     [rsp+2D0h+hObject], 0
0x18002ceb3  call    cs:__imp_CloseHandle
0x18002ceb9  mov     rcx, rbx; hObject
0x18002cebc  call    cs:__imp_CloseHandle
0x18002cec2  mov     rcx, [rsp+2D0h+ppSessionInfo]; pMemory
0x18002cec7  test    rcx, rcx
0x18002ceca  jz      short loc_18002CED2
0x18002cecc  call    cs:__imp_WTSFreeMemory
0x18002ced2  mov     rcx, [rsp+2D0h+hObject]; hObject
0x18002ced7  lea     rax, [rcx-1]
0x18002cedb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002cedf  ja      loc_18002CC67
0x18002cee5  call    cs:__imp_CloseHandle
0x18002ceeb  jmp     loc_18002CC67
0x18002cef0  mov     rcx, rdi; hObject
0x18002cef3  call    cs:__imp_CloseHandle
0x18002cef9  mov     rcx, rbx; hObject
0x18002cefc  call    cs:__imp_CloseHandle
0x18002cf02  mov     rcx, [rsp+2D0h+ppSessionInfo]; pMemory
0x18002cf07  test    rcx, rcx
0x18002cf0a  jz      short loc_18002CF12
0x18002cf0c  call    cs:__imp_WTSFreeMemory
0x18002cf12  mov     rcx, [rsp+2D0h+hObject]; hObject
0x18002cf17  lea     rax, [rcx-1]
0x18002cf1b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002cf1f  ja      short loc_18002CF27
0x18002cf21  call    cs:__imp_CloseHandle
0x18002cf27  mov     eax, 80070490h
0x18002cf2c  mov     rcx, [rbp+1D0h+var_40]
0x18002cf33  xor     rcx, rsp; StackCookie
0x18002cf36  call    __security_check_cookie
0x18002cf3b  add     rsp, 2A8h
0x18002cf42  pop     r15
0x18002cf44  pop     r14
0x18002cf46  pop     rdi
0x18002cf47  pop     rsi
0x18002cf48  pop     rbx
0x18002cf49  pop     rbp
0x18002cf4a  retn
```
