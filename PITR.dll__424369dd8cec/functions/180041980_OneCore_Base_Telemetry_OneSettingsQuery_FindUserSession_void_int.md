# OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)

- ea: `0x180041980`
- end: `0x180041a9c`
- name: `?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z`
- size: `284`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, void **, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180041594`
- `0x18004175c`
- `0x1800467b8`

## callees

- `0x180041980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041a04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041a31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041a78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041a31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041a78`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800419b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800419b1`
- `WTSAPI32!WTSFreeMemory` at `0x180041a87`
- `WTSAPI32!WTSFreeMemory` at `0x180041a87`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x1800419fa`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x1800419fa`
- `WTSAPI32!WTSQueryUserToken` at `0x1800419db`
- `WTSAPI32!WTSQueryUserToken` at `0x180041a47`
- `WTSAPI32!WTSQueryUserToken` at `0x1800419db`
- `WTSAPI32!WTSQueryUserToken` at `0x180041a47`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        void **a2,
        int *a3)
{
  ULONG active; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // rbx
  BOOL v9; // eax
  DWORD pCount; // [rsp+50h] [rbp+20h] BYREF
  int v12; // [rsp+54h] [rbp+24h]
  void *phToken; // [rsp+58h] [rbp+28h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+60h] [rbp+30h] BYREF

  v12 = HIDWORD(this);
  ppSessionInfo = 0;
  pCount = 0;
  phToken = 0;
  active = WTSGetActiveConsoleSessionId();
  ppSessionInfo = 0;
  *a2 = 0;
  *a3 = 0;
  if ( active == -1 )
    goto LABEL_13;
  if ( WTSQueryUserToken(active, &phToken) )
    goto LABEL_12;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    v8 = 0;
    v9 = 0;
    if ( !pCount )
    {
LABEL_13:
      v7 = 0;
      goto LABEL_14;
    }
    while ( !v9 )
    {
      if ( phToken )
        CloseHandle(phToken);
      v9 = WTSQueryUserToken(ppSessionInfo[v8].SessionId, &phToken);
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= pCount )
      {
        if ( !v9 )
          goto LABEL_13;
        break;
      }
    }
LABEL_12:
    *a2 = phToken;
    *a3 = 1;
    phToken = 0;
    goto LABEL_13;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_14:
  if ( phToken )
    CloseHandle(phToken);
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  return v7;
}

```

## disassembly

```asm
0x180041980  mov     [rsp-18h+arg_18], rbx
0x180041985  mov     qword ptr [rsp-18h+arg_0], rcx
0x18004198a  push    rbp
0x18004198b  push    rsi
0x18004198c  push    rdi
0x18004198d  mov     rbp, rsp
0x180041990  sub     rsp, 30h
0x180041994  mov     rdi, r8
0x180041997  mov     [rbp+ppSessionInfo], 0
0x18004199f  mov     rsi, rdx
0x1800419a2  mov     [rbp+arg_0], 0
0x1800419a9  mov     [rbp+phToken], 0
0x1800419b1  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800419b7  mov     [rbp+ppSessionInfo], 0
0x1800419bf  mov     qword ptr [rsi], 0
0x1800419c6  mov     dword ptr [rdi], 0
0x1800419cc  cmp     eax, 0FFFFFFFFh
0x1800419cf  jz      loc_180041A6D
0x1800419d5  lea     rdx, [rbp+phToken]; phToken
0x1800419d9  mov     ecx, eax; SessionId
0x1800419db  call    cs:__imp_WTSQueryUserToken
0x1800419e1  test    eax, eax
0x1800419e3  jnz     short loc_180041A58
0x1800419e5  xor     edx, edx; Reserved
0x1800419e7  lea     rax, [rbp+arg_0]
0x1800419eb  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x1800419ef  mov     [rsp+30h+pCount], rax; pCount
0x1800419f4  xor     ecx, ecx; hServer
0x1800419f6  lea     r8d, [rdx+1]; Version
0x1800419fa  call    cs:__imp_WTSEnumerateSessionsW
0x180041a00  test    eax, eax
0x180041a02  jnz     short loc_180041A1B
0x180041a04  call    cs:__imp_GetLastError
0x180041a0a  mov     ebx, eax
0x180041a0c  test    eax, eax
0x180041a0e  jle     short loc_180041A6F
0x180041a10  movzx   ebx, ax
0x180041a13  or      ebx, 80070000h
0x180041a19  jmp     short loc_180041A6F
0x180041a1b  xor     ebx, ebx
0x180041a1d  xor     eax, eax
0x180041a1f  cmp     [rbp+arg_0], eax
0x180041a22  jbe     short loc_180041A6D
0x180041a24  test    eax, eax
0x180041a26  jnz     short loc_180041A58
0x180041a28  mov     rcx, [rbp+phToken]; hObject
0x180041a2c  test    rcx, rcx
0x180041a2f  jz      short loc_180041A37
0x180041a31  call    cs:__imp_CloseHandle
0x180041a37  mov     rcx, [rbp+ppSessionInfo]
0x180041a3b  lea     r8, [rbx+rbx*2]
0x180041a3f  lea     rdx, [rbp+phToken]; phToken
0x180041a43  mov     ecx, [rcx+r8*8]; SessionId
0x180041a47  call    cs:__imp_WTSQueryUserToken
0x180041a4d  inc     ebx
0x180041a4f  cmp     ebx, [rbp+arg_0]
0x180041a52  jb      short loc_180041A24
0x180041a54  test    eax, eax
0x180041a56  jz      short loc_180041A6D
0x180041a58  mov     rax, [rbp+phToken]
0x180041a5c  mov     [rsi], rax
0x180041a5f  mov     dword ptr [rdi], 1
0x180041a65  mov     [rbp+phToken], 0
0x180041a6d  xor     ebx, ebx
0x180041a6f  mov     rcx, [rbp+phToken]; hObject
0x180041a73  test    rcx, rcx
0x180041a76  jz      short loc_180041A7E
0x180041a78  call    cs:__imp_CloseHandle
0x180041a7e  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x180041a82  test    rcx, rcx
0x180041a85  jz      short loc_180041A8D
0x180041a87  call    cs:__imp_WTSFreeMemory
0x180041a8d  mov     eax, ebx
0x180041a8f  mov     rbx, [rsp+30h+arg_18]
0x180041a94  add     rsp, 30h
0x180041a98  pop     rdi
0x180041a99  pop     rsi
0x180041a9a  pop     rbp
0x180041a9b  retn
```
