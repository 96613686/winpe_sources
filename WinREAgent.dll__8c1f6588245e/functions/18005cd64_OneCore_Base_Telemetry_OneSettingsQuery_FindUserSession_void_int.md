# OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)

- ea: `0x18005cd64`
- end: `0x18005ce80`
- name: `?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z`
- size: `284`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, void **, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18005c9b4`
- `0x18005cb7c`
- `0x18006189c`

## callees

- `0x18005cd64`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18005ce15`
- `KERNEL32!CloseHandle` at `0x18005ce5c`
- `KERNEL32!CloseHandle` at `0x18005ce15`
- `KERNEL32!CloseHandle` at `0x18005ce5c`
- `KERNEL32!GetLastError` at `0x18005cde8`
- `KERNEL32!GetLastError` at `0x18005cde8`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x18005cd95`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x18005cd95`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18005cdde`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18005cdde`
- `WTSAPI32!WTSFreeMemory` at `0x18005ce6b`
- `WTSAPI32!WTSFreeMemory` at `0x18005ce6b`
- `WTSAPI32!WTSQueryUserToken` at `0x18005cdbf`
- `WTSAPI32!WTSQueryUserToken` at `0x18005ce2b`
- `WTSAPI32!WTSQueryUserToken` at `0x18005cdbf`
- `WTSAPI32!WTSQueryUserToken` at `0x18005ce2b`

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
0x18005cd64  mov     [rsp-18h+arg_18], rbx
0x18005cd69  mov     qword ptr [rsp-18h+arg_0], rcx
0x18005cd6e  push    rbp
0x18005cd6f  push    rsi
0x18005cd70  push    rdi
0x18005cd71  mov     rbp, rsp
0x18005cd74  sub     rsp, 30h
0x18005cd78  mov     rdi, r8
0x18005cd7b  mov     [rbp+ppSessionInfo], 0
0x18005cd83  mov     rsi, rdx
0x18005cd86  mov     [rbp+arg_0], 0
0x18005cd8d  mov     [rbp+phToken], 0
0x18005cd95  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18005cd9b  mov     [rbp+ppSessionInfo], 0
0x18005cda3  mov     qword ptr [rsi], 0
0x18005cdaa  mov     dword ptr [rdi], 0
0x18005cdb0  cmp     eax, 0FFFFFFFFh
0x18005cdb3  jz      loc_18005CE51
0x18005cdb9  lea     rdx, [rbp+phToken]; phToken
0x18005cdbd  mov     ecx, eax; SessionId
0x18005cdbf  call    cs:__imp_WTSQueryUserToken
0x18005cdc5  test    eax, eax
0x18005cdc7  jnz     short loc_18005CE3C
0x18005cdc9  xor     edx, edx; Reserved
0x18005cdcb  lea     rax, [rbp+arg_0]
0x18005cdcf  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x18005cdd3  mov     [rsp+30h+pCount], rax; pCount
0x18005cdd8  xor     ecx, ecx; hServer
0x18005cdda  lea     r8d, [rdx+1]; Version
0x18005cdde  call    cs:__imp_WTSEnumerateSessionsW
0x18005cde4  test    eax, eax
0x18005cde6  jnz     short loc_18005CDFF
0x18005cde8  call    cs:__imp_GetLastError
0x18005cdee  mov     ebx, eax
0x18005cdf0  test    eax, eax
0x18005cdf2  jle     short loc_18005CE53
0x18005cdf4  movzx   ebx, ax
0x18005cdf7  or      ebx, 80070000h
0x18005cdfd  jmp     short loc_18005CE53
0x18005cdff  xor     ebx, ebx
0x18005ce01  xor     eax, eax
0x18005ce03  cmp     [rbp+arg_0], eax
0x18005ce06  jbe     short loc_18005CE51
0x18005ce08  test    eax, eax
0x18005ce0a  jnz     short loc_18005CE3C
0x18005ce0c  mov     rcx, [rbp+phToken]; hObject
0x18005ce10  test    rcx, rcx
0x18005ce13  jz      short loc_18005CE1B
0x18005ce15  call    cs:__imp_CloseHandle
0x18005ce1b  mov     rcx, [rbp+ppSessionInfo]
0x18005ce1f  lea     r8, [rbx+rbx*2]
0x18005ce23  lea     rdx, [rbp+phToken]; phToken
0x18005ce27  mov     ecx, [rcx+r8*8]; SessionId
0x18005ce2b  call    cs:__imp_WTSQueryUserToken
0x18005ce31  inc     ebx
0x18005ce33  cmp     ebx, [rbp+arg_0]
0x18005ce36  jb      short loc_18005CE08
0x18005ce38  test    eax, eax
0x18005ce3a  jz      short loc_18005CE51
0x18005ce3c  mov     rax, [rbp+phToken]
0x18005ce40  mov     [rsi], rax
0x18005ce43  mov     dword ptr [rdi], 1
0x18005ce49  mov     [rbp+phToken], 0
0x18005ce51  xor     ebx, ebx
0x18005ce53  mov     rcx, [rbp+phToken]; hObject
0x18005ce57  test    rcx, rcx
0x18005ce5a  jz      short loc_18005CE62
0x18005ce5c  call    cs:__imp_CloseHandle
0x18005ce62  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x18005ce66  test    rcx, rcx
0x18005ce69  jz      short loc_18005CE71
0x18005ce6b  call    cs:__imp_WTSFreeMemory
0x18005ce71  mov     eax, ebx
0x18005ce73  mov     rbx, [rsp+30h+arg_18]
0x18005ce78  add     rsp, 30h
0x18005ce7c  pop     rdi
0x18005ce7d  pop     rsi
0x18005ce7e  pop     rbp
0x18005ce7f  retn
```
