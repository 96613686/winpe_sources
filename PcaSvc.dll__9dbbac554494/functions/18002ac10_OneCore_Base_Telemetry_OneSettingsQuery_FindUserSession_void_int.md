# OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)

- ea: `0x18002ac10`
- end: `0x18002ad2c`
- name: `?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z`
- size: `284`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, void **, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002aa28`
- `0x180085fdc`
- `0x180089408`

## callees

- `0x18002ac10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad08`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18002ac41`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18002ac41`
- `WTSAPI32!WTSFreeMemory` at `0x18002ad17`
- `WTSAPI32!WTSFreeMemory` at `0x18002ad17`
- `WTSAPI32!WTSQueryUserToken` at `0x18002ac6b`
- `WTSAPI32!WTSQueryUserToken` at `0x18002acd7`
- `WTSAPI32!WTSQueryUserToken` at `0x18002ac6b`
- `WTSAPI32!WTSQueryUserToken` at `0x18002acd7`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18002ac8a`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18002ac8a`

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
0x18002ac10  mov     [rsp-18h+arg_18], rbx
0x18002ac15  mov     qword ptr [rsp-18h+arg_0], rcx
0x18002ac1a  push    rbp
0x18002ac1b  push    rsi
0x18002ac1c  push    rdi
0x18002ac1d  mov     rbp, rsp
0x18002ac20  sub     rsp, 30h
0x18002ac24  mov     rdi, r8
0x18002ac27  mov     [rbp+ppSessionInfo], 0
0x18002ac2f  mov     rsi, rdx
0x18002ac32  mov     [rbp+arg_0], 0
0x18002ac39  mov     [rbp+phToken], 0
0x18002ac41  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18002ac47  mov     [rbp+ppSessionInfo], 0
0x18002ac4f  mov     qword ptr [rsi], 0
0x18002ac56  mov     dword ptr [rdi], 0
0x18002ac5c  cmp     eax, 0FFFFFFFFh
0x18002ac5f  jz      loc_18002ACFD
0x18002ac65  lea     rdx, [rbp+phToken]; phToken
0x18002ac69  mov     ecx, eax; SessionId
0x18002ac6b  call    cs:__imp_WTSQueryUserToken
0x18002ac71  test    eax, eax
0x18002ac73  jnz     short loc_18002ACE8
0x18002ac75  xor     edx, edx; Reserved
0x18002ac77  lea     rax, [rbp+arg_0]
0x18002ac7b  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x18002ac7f  mov     [rsp+30h+pCount], rax; pCount
0x18002ac84  xor     ecx, ecx; hServer
0x18002ac86  lea     r8d, [rdx+1]; Version
0x18002ac8a  call    cs:__imp_WTSEnumerateSessionsW
0x18002ac90  test    eax, eax
0x18002ac92  jnz     short loc_18002ACAB
0x18002ac94  call    cs:__imp_GetLastError
0x18002ac9a  mov     ebx, eax
0x18002ac9c  test    eax, eax
0x18002ac9e  jle     short loc_18002ACFF
0x18002aca0  movzx   ebx, ax
0x18002aca3  or      ebx, 80070000h
0x18002aca9  jmp     short loc_18002ACFF
0x18002acab  xor     ebx, ebx
0x18002acad  xor     eax, eax
0x18002acaf  cmp     [rbp+arg_0], eax
0x18002acb2  jbe     short loc_18002ACFD
0x18002acb4  test    eax, eax
0x18002acb6  jnz     short loc_18002ACE8
0x18002acb8  mov     rcx, [rbp+phToken]; hObject
0x18002acbc  test    rcx, rcx
0x18002acbf  jz      short loc_18002ACC7
0x18002acc1  call    cs:__imp_CloseHandle
0x18002acc7  mov     rcx, [rbp+ppSessionInfo]
0x18002accb  lea     r8, [rbx+rbx*2]
0x18002accf  lea     rdx, [rbp+phToken]; phToken
0x18002acd3  mov     ecx, [rcx+r8*8]; SessionId
0x18002acd7  call    cs:__imp_WTSQueryUserToken
0x18002acdd  inc     ebx
0x18002acdf  cmp     ebx, [rbp+arg_0]
0x18002ace2  jb      short loc_18002ACB4
0x18002ace4  test    eax, eax
0x18002ace6  jz      short loc_18002ACFD
0x18002ace8  mov     rax, [rbp+phToken]
0x18002acec  mov     [rsi], rax
0x18002acef  mov     dword ptr [rdi], 1
0x18002acf5  mov     [rbp+phToken], 0
0x18002acfd  xor     ebx, ebx
0x18002acff  mov     rcx, [rbp+phToken]; hObject
0x18002ad03  test    rcx, rcx
0x18002ad06  jz      short loc_18002AD0E
0x18002ad08  call    cs:__imp_CloseHandle
0x18002ad0e  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x18002ad12  test    rcx, rcx
0x18002ad15  jz      short loc_18002AD1D
0x18002ad17  call    cs:__imp_WTSFreeMemory
0x18002ad1d  mov     eax, ebx
0x18002ad1f  mov     rbx, [rsp+30h+arg_18]
0x18002ad24  add     rsp, 30h
0x18002ad28  pop     rdi
0x18002ad29  pop     rsi
0x18002ad2a  pop     rbp
0x18002ad2b  retn
```
