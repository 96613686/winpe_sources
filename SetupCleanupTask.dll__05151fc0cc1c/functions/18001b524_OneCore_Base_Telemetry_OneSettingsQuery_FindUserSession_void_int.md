# OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)

- ea: `0x18001b524`
- end: `0x18001b640`
- name: `?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z`
- size: `284`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, void **, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001acb4`
- `0x18001ae7c`
- `0x180022678`

## callees

- `0x18001b524`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b5a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b5a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b5d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b61c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b5d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b61c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18001b555`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18001b555`
- `WTSAPI32!WTSQueryUserToken` at `0x18001b57f`
- `WTSAPI32!WTSQueryUserToken` at `0x18001b5eb`
- `WTSAPI32!WTSQueryUserToken` at `0x18001b57f`
- `WTSAPI32!WTSQueryUserToken` at `0x18001b5eb`
- `WTSAPI32!WTSFreeMemory` at `0x18001b62b`
- `WTSAPI32!WTSFreeMemory` at `0x18001b62b`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18001b59e`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18001b59e`

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
0x18001b524  mov     [rsp-18h+arg_18], rbx
0x18001b529  mov     qword ptr [rsp-18h+arg_0], rcx
0x18001b52e  push    rbp
0x18001b52f  push    rsi
0x18001b530  push    rdi
0x18001b531  mov     rbp, rsp
0x18001b534  sub     rsp, 30h
0x18001b538  mov     rdi, r8
0x18001b53b  mov     [rbp+ppSessionInfo], 0
0x18001b543  mov     rsi, rdx
0x18001b546  mov     [rbp+arg_0], 0
0x18001b54d  mov     [rbp+phToken], 0
0x18001b555  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18001b55b  mov     [rbp+ppSessionInfo], 0
0x18001b563  mov     qword ptr [rsi], 0
0x18001b56a  mov     dword ptr [rdi], 0
0x18001b570  cmp     eax, 0FFFFFFFFh
0x18001b573  jz      loc_18001B611
0x18001b579  lea     rdx, [rbp+phToken]; phToken
0x18001b57d  mov     ecx, eax; SessionId
0x18001b57f  call    cs:__imp_WTSQueryUserToken
0x18001b585  test    eax, eax
0x18001b587  jnz     short loc_18001B5FC
0x18001b589  xor     edx, edx; Reserved
0x18001b58b  lea     rax, [rbp+arg_0]
0x18001b58f  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x18001b593  mov     [rsp+30h+pCount], rax; pCount
0x18001b598  xor     ecx, ecx; hServer
0x18001b59a  lea     r8d, [rdx+1]; Version
0x18001b59e  call    cs:__imp_WTSEnumerateSessionsW
0x18001b5a4  test    eax, eax
0x18001b5a6  jnz     short loc_18001B5BF
0x18001b5a8  call    cs:__imp_GetLastError
0x18001b5ae  mov     ebx, eax
0x18001b5b0  test    eax, eax
0x18001b5b2  jle     short loc_18001B613
0x18001b5b4  movzx   ebx, ax
0x18001b5b7  or      ebx, 80070000h
0x18001b5bd  jmp     short loc_18001B613
0x18001b5bf  xor     ebx, ebx
0x18001b5c1  xor     eax, eax
0x18001b5c3  cmp     [rbp+arg_0], eax
0x18001b5c6  jbe     short loc_18001B611
0x18001b5c8  test    eax, eax
0x18001b5ca  jnz     short loc_18001B5FC
0x18001b5cc  mov     rcx, [rbp+phToken]; hObject
0x18001b5d0  test    rcx, rcx
0x18001b5d3  jz      short loc_18001B5DB
0x18001b5d5  call    cs:__imp_CloseHandle
0x18001b5db  mov     rcx, [rbp+ppSessionInfo]
0x18001b5df  lea     r8, [rbx+rbx*2]
0x18001b5e3  lea     rdx, [rbp+phToken]; phToken
0x18001b5e7  mov     ecx, [rcx+r8*8]; SessionId
0x18001b5eb  call    cs:__imp_WTSQueryUserToken
0x18001b5f1  inc     ebx
0x18001b5f3  cmp     ebx, [rbp+arg_0]
0x18001b5f6  jb      short loc_18001B5C8
0x18001b5f8  test    eax, eax
0x18001b5fa  jz      short loc_18001B611
0x18001b5fc  mov     rax, [rbp+phToken]
0x18001b600  mov     [rsi], rax
0x18001b603  mov     dword ptr [rdi], 1
0x18001b609  mov     [rbp+phToken], 0
0x18001b611  xor     ebx, ebx
0x18001b613  mov     rcx, [rbp+phToken]; hObject
0x18001b617  test    rcx, rcx
0x18001b61a  jz      short loc_18001B622
0x18001b61c  call    cs:__imp_CloseHandle
0x18001b622  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x18001b626  test    rcx, rcx
0x18001b629  jz      short loc_18001B631
0x18001b62b  call    cs:__imp_WTSFreeMemory
0x18001b631  mov     eax, ebx
0x18001b633  mov     rbx, [rsp+30h+arg_18]
0x18001b638  add     rsp, 30h
0x18001b63c  pop     rdi
0x18001b63d  pop     rsi
0x18001b63e  pop     rbp
0x18001b63f  retn
```
