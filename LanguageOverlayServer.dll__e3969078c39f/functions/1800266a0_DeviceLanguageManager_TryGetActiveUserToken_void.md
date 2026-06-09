# DeviceLanguageManager::_TryGetActiveUserToken(void)

- ea: `0x1800266a0`
- end: `0x18002688c`
- name: `?_TryGetActiveUserToken@DeviceLanguageManager@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `492`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180026894`

## callees

- `0x180003a00`
- `0x180004b24`
- `0x180004c3c`
- `0x180011318`
- `0x1800266a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026818`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002682b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002682b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026823`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026823`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180026712`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180026712`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18002677e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180026795`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800267bf`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800267ce`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18002677e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180026795`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800267bf`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800267ce`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180026758`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180026758`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800267ef`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800267ef`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180026858`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180026858`

## string_xrefs

- `0x180026868`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\devicelanguagemanager.cpp`
- `0x18002687a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\devicelanguagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall DeviceLanguageManager::_TryGetActiveUserToken(__int64 a1, void **a2)
{
  int v3; // ebx
  DWORD SessionId; // esi
  __int64 v5; // rax
  const char *v7; // r9
  void *v8; // r15
  void *v9; // r14
  DWORD LastError; // ebx
  const char *v11; // r9
  void **v12; // [rsp+30h] [rbp-29h]
  void *phToken; // [rsp+38h] [rbp-21h] BYREF
  char v14; // [rsp+40h] [rbp-19h]
  int v15; // [rsp+48h] [rbp-11h]
  void **v16; // [rsp+50h] [rbp-9h]
  DWORD pCount; // [rsp+58h] [rbp-1h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+60h] [rbp+7h] BYREF
  DWORD pBytesReturned; // [rsp+68h] [rbp+Fh] BYREF
  LPWSTR ppBuffer; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v16 = a2;
  *a2 = 0;
  v15 = 1;
  if ( !(unsigned __int8)IsWTSEnumerateSessionsWPresent() || !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
    return a2;
  pCount = 0;
  ppSessionInfo = 0;
  if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) || (v3 = 0, !pCount) )
  {
LABEL_13:
    if ( ppSessionInfo )
      WTSFreeMemory(ppSessionInfo);
    return a2;
  }
  while ( ppSessionInfo[v3].State )
  {
LABEL_12:
    if ( ++v3 >= pCount )
      goto LABEL_13;
  }
  SessionId = ppSessionInfo[v3].SessionId;
  pBytesReturned = 0;
  ppBuffer = 0;
  if ( !WTSQuerySessionInformationW(0, SessionId, WTSUserName, &ppBuffer, &pBytesReturned) )
    goto LABEL_10;
  v5 = -1;
  do
    ++v5;
  while ( ppBuffer[v5] );
  if ( !v5 )
  {
LABEL_10:
    if ( ppBuffer )
      WTSFreeMemory(ppBuffer);
    goto LABEL_12;
  }
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    v12 = a2;
    phToken = 0;
    v14 = 1;
    if ( !WTSQueryUserToken(SessionId, &phToken) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\devicelanguagemanager.cpp",
        v7);
    goto LABEL_22;
  }
  if ( (unsigned __int8)IsQueryUserTokenPresent() )
  {
    v12 = a2;
    phToken = 0;
    v14 = 1;
    if ( !(unsigned int)QueryUserToken(SessionId, &phToken) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x140,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\devicelanguagemanager.cpp",
        v11);
LABEL_22:
    if ( v14 )
    {
      v8 = phToken;
      v9 = *v12;
      if ( (char *)*v12 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v9);
        SetLastError(LastError);
      }
      *v12 = v8;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800266a0  push    rbp
0x1800266a2  push    rbx
0x1800266a3  push    rsi
0x1800266a4  push    rdi
0x1800266a5  push    r14
0x1800266a7  push    r15
0x1800266a9  lea     rbp, [rsp-2Fh]
0x1800266ae  sub     rsp, 88h
0x1800266b5  mov     rax, cs:__security_cookie
0x1800266bc  xor     rax, rsp
0x1800266bf  mov     [rbp+57h+var_38], rax
0x1800266c3  mov     rdi, rdx
0x1800266c6  mov     [rbp+57h+var_60], rdx
0x1800266ca  xor     r14d, r14d
0x1800266cd  mov     [rbp+57h+var_68], r14d
0x1800266d1  mov     [rdx], r14
0x1800266d4  lea     r15d, [r14+1]
0x1800266d8  mov     [rbp+57h+var_68], r15d
0x1800266dc  call    IsWTSEnumerateSessionsWPresent
0x1800266e1  test    al, al
0x1800266e3  jz      loc_18002679B
0x1800266e9  call    IsWTSEnumerateSessionsWPresent
0x1800266ee  test    al, al
0x1800266f0  jz      loc_18002679B
0x1800266f6  mov     [rbp+57h+var_58], r14d
0x1800266fa  mov     [rbp+57h+ppSessionInfo], r14
0x1800266fe  lea     rax, [rbp+57h+var_58]
0x180026702  mov     [rsp+0B0h+pCount], rax; pCount
0x180026707  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x18002670b  mov     r8d, r15d; Version
0x18002670e  xor     edx, edx; Reserved
0x180026710  xor     ecx, ecx; hServer
0x180026712  call    cs:__imp_WTSEnumerateSessionsW
0x180026718  test    eax, eax
0x18002671a  jz      short loc_18002678C
0x18002671c  mov     ebx, r14d
0x18002671f  cmp     [rbp+57h+var_58], r14d
0x180026723  jbe     short loc_18002678C
0x180026725  mov     eax, ebx
0x180026727  lea     rcx, [rax+rax*2]
0x18002672b  mov     rax, [rbp+57h+ppSessionInfo]
0x18002672f  cmp     [rax+rcx*8+10h], r14d
0x180026734  jnz     short loc_180026784
0x180026736  mov     esi, [rax+rcx*8]
0x180026739  mov     [rbp+57h+pBytesReturned], r14d
0x18002673d  mov     [rbp+57h+ppBuffer], r14
0x180026741  lea     rax, [rbp+57h+pBytesReturned]
0x180026745  mov     [rsp+0B0h+pCount], rax; pBytesReturned
0x18002674a  lea     r9, [rbp+57h+ppBuffer]; ppBuffer
0x18002674e  mov     r8d, 5; WTSInfoClass
0x180026754  mov     edx, esi; SessionId
0x180026756  xor     ecx, ecx; hServer
0x180026758  call    cs:__imp_WTSQuerySessionInformationW
0x18002675e  mov     rcx, [rbp+57h+ppBuffer]; pMemory
0x180026762  test    eax, eax
0x180026764  jz      short loc_180026779
0x180026766  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002676a  inc     rax
0x18002676d  cmp     [rcx+rax*2], r14w
0x180026772  jnz     short loc_18002676A
0x180026774  test    rax, rax
0x180026777  jnz     short loc_1800267BA
0x180026779  test    rcx, rcx
0x18002677c  jz      short loc_180026784
0x18002677e  call    cs:__imp_WTSFreeMemory
0x180026784  add     ebx, r15d
0x180026787  cmp     ebx, [rbp+57h+var_58]
0x18002678a  jb      short loc_180026725
0x18002678c  mov     rcx, [rbp+57h+ppSessionInfo]; pMemory
0x180026790  test    rcx, rcx
0x180026793  jz      short loc_18002679B
0x180026795  call    cs:__imp_WTSFreeMemory
0x18002679b  mov     rax, rdi
0x18002679e  mov     rcx, [rbp+57h+var_38]
0x1800267a2  xor     rcx, rsp; StackCookie
0x1800267a5  call    __security_check_cookie
0x1800267aa  add     rsp, 88h
0x1800267b1  pop     r15
0x1800267b3  pop     r14
0x1800267b5  pop     rdi
0x1800267b6  pop     rsi
0x1800267b7  pop     rbx
0x1800267b8  pop     rbp
0x1800267b9  retn
0x1800267ba  test    rcx, rcx
0x1800267bd  jz      short loc_1800267C5
0x1800267bf  call    cs:__imp_WTSFreeMemory
0x1800267c5  mov     rcx, [rbp+57h+ppSessionInfo]; pMemory
0x1800267c9  test    rcx, rcx
0x1800267cc  jz      short loc_1800267D4
0x1800267ce  call    cs:__imp_WTSFreeMemory
0x1800267d4  call    IsWTSEnumerateSessionsWPresent
0x1800267d9  test    al, al
0x1800267db  jz      short loc_180026839
0x1800267dd  mov     [rbp+57h+var_80], rdi
0x1800267e1  mov     [rbp+57h+phToken], r14
0x1800267e5  mov     [rbp+57h+var_70], r15b
0x1800267e9  lea     rdx, [rbp+57h+phToken]; phToken
0x1800267ed  mov     ecx, esi; SessionId
0x1800267ef  call    cs:__imp_WTSQueryUserToken
0x1800267f5  mov     rcx, [rbp+5Fh]; this
0x1800267f9  test    eax, eax
0x1800267fb  jz      short loc_18002687A
0x1800267fd  cmp     [rbp+57h+var_70], r14b
0x180026801  jz      short loc_18002679B
0x180026803  mov     r15, [rbp+57h+phToken]
0x180026807  mov     rsi, [rbp+57h+var_80]
0x18002680b  mov     r14, [rsi]
0x18002680e  lea     rax, [r14-1]
0x180026812  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026816  ja      short loc_180026831
0x180026818  call    cs:__imp_GetLastError
0x18002681e  mov     ebx, eax
0x180026820  mov     rcx, r14; hObject
0x180026823  call    cs:__imp_CloseHandle
0x180026829  mov     ecx, ebx; dwErrCode
0x18002682b  call    cs:__imp_SetLastError
0x180026831  mov     [rsi], r15
0x180026834  jmp     loc_18002679B
0x180026839  call    IsQueryUserTokenPresent
0x18002683e  test    al, al
0x180026840  jz      loc_18002679B
0x180026846  mov     [rbp+57h+var_80], rdi
0x18002684a  mov     [rbp+57h+phToken], r14
0x18002684e  mov     [rbp+57h+var_70], r15b
0x180026852  lea     rdx, [rbp+57h+phToken]
0x180026856  mov     ecx, esi
0x180026858  call    cs:__imp_QueryUserToken
0x18002685e  mov     rcx, [rbp+5Fh]; this
0x180026862  test    eax, eax
0x180026864  jz      short loc_180026868
0x180026866  jmp     short loc_1800267FD
0x180026868  lea     r8, aOnecoreBaseLan_20; "onecore\\base\\languageoverlay\\service"...
0x18002686f  mov     edx, 140h; void *
0x180026874  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002687a  lea     r8, aOnecoreBaseLan_20; "onecore\\base\\languageoverlay\\service"...
0x180026881  mov     edx, 13Ch; void *
0x180026886  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
