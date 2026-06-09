# Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(void)

- ea: `0x140268574`
- end: `0x14026888a`
- name: `?GetMostPreferredLoggedOnSessionToken@CallerToken@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `790`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x140243530`
- `0x140243d30`
- `0x140268890`
- `0x140268990`
- `0x1402a2a30`
- `0x1402a31a0`
- `0x1402a3ca0`
- `0x1402a9e20`
- `0x1402aa49c`
- `0x1402d88c4`
- `0x140329014`
- `0x14035b990`

## callees

- `0x14003c578`
- `0x140072304`
- `0x140268574`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140268675`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1402687c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140268675`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1402687c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140268662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402687b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140268662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402687b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14026866d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402687bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14026882a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14026866d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402687bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14026882a`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1402685b6`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1402686a1`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x14026870d`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1402685b6`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1402686a1`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x14026870d`
- `WTSAPI32!WTSEnumerateSessionsExW` at `0x1402685f1`
- `WTSAPI32!WTSEnumerateSessionsExW` at `0x1402685f1`
- `WTSAPI32!WTSQueryUserToken` at `0x140268689`
- `WTSAPI32!WTSQueryUserToken` at `0x1402687db`
- `WTSAPI32!WTSQueryUserToken` at `0x140268689`
- `WTSAPI32!WTSQueryUserToken` at `0x1402687db`
- `WTSAPI32!WTSFreeMemory` at `0x1402686eb`
- `WTSAPI32!WTSFreeMemory` at `0x14026875f`
- `WTSAPI32!WTSFreeMemory` at `0x1402686eb`
- `WTSAPI32!WTSFreeMemory` at `0x14026875f`
- `WTSAPI32!WTSFreeMemoryExW` at `0x140268815`
- `WTSAPI32!WTSFreeMemoryExW` at `0x140268815`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1402686c8`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x140268736`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1402686c8`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x140268736`

## string_xrefs

- `0x140268860`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\CallerToken.cpp`
- `0x140268872`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\CallerToken.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
WCHAR *__fastcall Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(WCHAR *a1)
{
  const char *v2; // r9
  int v3; // r15d
  int v4; // r12d
  DWORD v5; // r8d
  PWTS_SESSION_INFO_1W v6; // rdi
  struct _WTS_SESSION_INFO_1W *v7; // r13
  HANDLE v8; // r14
  DWORD LastError; // ebx
  DWORD SessionId; // ebx
  char v11; // bl
  DWORD v12; // ebx
  char v13; // bl
  ULONG v14; // edi
  HANDLE v15; // r14
  DWORD v16; // ebx
  const char *v17; // r9
  PWTS_SESSION_INFO_1W v18; // rdx
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+58h] [rbp-9h] BYREF
  LPWSTR v21; // [rsp+60h] [rbp-1h] BYREF
  LPWSTR ppBuffer; // [rsp+68h] [rbp+7h] BYREF
  DWORD NumberOfEntries; // [rsp+70h] [rbp+Fh] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+17h] BYREF
  DWORD pBytesReturned; // [rsp+80h] [rbp+1Fh] BYREF
  DWORD v26; // [rsp+84h] [rbp+23h] BYREF
  DWORD pLevel; // [rsp+88h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  v21 = a1;
  if ( !IsApiSetImplemented("ext-ms-win-session-wtsapi32-l1-1-0") )
  {
    *(_QWORD *)a1 = 0;
    return a1;
  }
  hObject = 0;
  NumberOfEntries = 0;
  pLevel = 1;
  ppSessionInfo = 0;
  if ( !WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &NumberOfEntries) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x43,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\CallerToken.cpp",
      v2);
  v3 = -1;
  v4 = -1;
  v5 = NumberOfEntries;
  v6 = ppSessionInfo;
  if ( !ppSessionInfo && NumberOfEntries )
    gsl::details::terminate((gsl::details *)0xFFFFFFFFLL);
  v7 = &ppSessionInfo[NumberOfEntries];
  if ( ppSessionInfo == v7 )
  {
LABEL_46:
    *(_QWORD *)a1 = 0;
    v18 = v6;
    goto LABEL_47;
  }
  while ( 1 )
  {
    if ( !v6->SessionId )
      goto LABEL_33;
    v8 = hObject;
    if ( hObject && hObject != (HANDLE)-1LL )
    {
      LastError = GetLastError();
      CloseHandle(v8);
      SetLastError(LastError);
    }
    hObject = 0;
    if ( !WTSQueryUserToken(v6->SessionId, &hObject) )
      goto LABEL_33;
    SessionId = v6->SessionId;
    if ( !IsApiSetImplemented("ext-ms-win-session-wtsapi32-l1-1-0") )
      break;
    ppBuffer = 0;
    pBytesReturned = 0;
    if ( !WTSQuerySessionInformationW(0, SessionId, WTSIsRemoteSession, &ppBuffer, &pBytesReturned) )
      break;
    if ( !pBytesReturned || (v11 = 1, *(_BYTE *)ppBuffer != 1) )
      v11 = 0;
    if ( ppBuffer )
      WTSFreeMemory(ppBuffer);
    if ( !v11 || v3 != -1 )
      break;
    v3 = v6->SessionId;
LABEL_33:
    if ( ++v6 == v7 )
      goto LABEL_36;
  }
  v12 = v6->SessionId;
  if ( !IsApiSetImplemented("ext-ms-win-session-wtsapi32-l1-1-0") )
    goto LABEL_31;
  v21 = 0;
  v26 = 0;
  if ( !WTSQuerySessionInformationW(0, v12, WTSSessionInfoEx, &v21, &v26) )
    goto LABEL_31;
  if ( !v26 || *(_DWORD *)v21 != 1 || (v13 = 1, *((_DWORD *)v21 + 4) != 1) )
    v13 = 0;
  if ( v21 )
    WTSFreeMemory(v21);
  if ( !v13 )
  {
LABEL_31:
    if ( v4 == -1 )
      v4 = v6->SessionId;
    goto LABEL_33;
  }
  v14 = v6->SessionId;
  if ( v14 != -1 )
    goto LABEL_40;
LABEL_36:
  if ( v4 == -1 )
  {
    if ( v3 == -1 )
    {
      v5 = NumberOfEntries;
      v6 = ppSessionInfo;
      goto LABEL_46;
    }
    v14 = v3;
  }
  else
  {
    v14 = v4;
  }
LABEL_40:
  v15 = hObject;
  if ( hObject && hObject != (HANDLE)-1LL )
  {
    v16 = GetLastError();
    CloseHandle(v15);
    SetLastError(v16);
  }
  hObject = 0;
  if ( !WTSQueryUserToken(v14, &hObject) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x81,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\CallerToken.cpp",
      v17);
  *(_QWORD *)a1 = hObject;
  hObject = 0;
  v5 = NumberOfEntries;
  v18 = ppSessionInfo;
LABEL_47:
  WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, v18, v5);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return a1;
}

```

## disassembly

```asm
0x140268574  mov     rax, rsp
0x140268577  mov     [rax+10h], rbx
0x14026857b  mov     [rax+18h], rsi
0x14026857f  mov     [rax+20h], rdi
0x140268583  push    rbp
0x140268584  push    r12
0x140268586  push    r13
0x140268588  push    r14
0x14026858a  push    r15
0x14026858c  lea     rbp, [rax-5Fh]
0x140268590  sub     rsp, 90h
0x140268597  mov     rax, cs:__security_cookie
0x14026859e  xor     rax, rsp
0x1402685a1  mov     [rbp+57h+var_28], rax
0x1402685a5  mov     rsi, rcx
0x1402685a8  mov     [rbp+57h+var_58], rcx
0x1402685ac  xor     r14d, r14d
0x1402685af  lea     rcx, aExtMsWinSessio; "ext-ms-win-session-wtsapi32-l1-1-0"
0x1402685b6  call    cs:__imp_IsApiSetImplemented
0x1402685bc  test    eax, eax
0x1402685be  jnz     short loc_1402685C8
0x1402685c0  mov     [rsi], r14
0x1402685c3  jmp     loc_140268830
0x1402685c8  mov     [rbp+57h+hObject], r14
0x1402685cc  mov     [rbp+57h+NumberOfEntries], r14d
0x1402685d0  mov     [rbp+57h+pLevel], 1
0x1402685d7  mov     [rbp+57h+ppSessionInfo], r14
0x1402685db  lea     rax, [rbp+57h+NumberOfEntries]
0x1402685df  mov     [rsp+0B0h+pCount], rax; pCount
0x1402685e4  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x1402685e8  xor     r8d, r8d; Filter
0x1402685eb  lea     rdx, [rbp+57h+pLevel]; pLevel
0x1402685ef  xor     ecx, ecx; hServer
0x1402685f1  call    cs:__imp_WTSEnumerateSessionsExW
0x1402685f7  mov     rcx, [rbp+5Fh]; this
0x1402685fb  test    eax, eax
0x1402685fd  jz      loc_140268872
0x140268603  lea     rax, [rbp+57h+ppSessionInfo]
0x140268607  mov     [rbp+57h+var_78], rax
0x14026860b  lea     rax, [rbp+57h+NumberOfEntries]
0x14026860f  mov     [rbp+57h+var_70], rax
0x140268613  mov     [rbp+57h+var_68], 1
0x140268617  or      ecx, 0FFFFFFFFh; this
0x14026861a  mov     r15d, ecx
0x14026861d  mov     r12d, ecx
0x140268620  mov     r8d, [rbp+57h+NumberOfEntries]
0x140268624  mov     eax, r8d
0x140268627  mov     rdi, [rbp+57h+ppSessionInfo]
0x14026862b  test    rdi, rdi
0x14026862e  jnz     short loc_140268639
0x140268630  test    r8d, r8d
0x140268633  jnz     loc_140268884
0x140268639  imul    r13, rax, 38h ; '8'
0x14026863d  add     r13, rdi
0x140268640  cmp     rdi, r13
0x140268643  jz      loc_14026880A
0x140268649  cmp     [rdi+8], r14d
0x14026864d  jz      loc_14026877A
0x140268653  mov     r14, [rbp+57h+hObject]
0x140268657  test    r14, r14
0x14026865a  jz      short loc_14026867B
0x14026865c  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140268660  jz      short loc_14026867B
0x140268662  call    cs:__imp_GetLastError
0x140268668  mov     ebx, eax
0x14026866a  mov     rcx, r14; hObject
0x14026866d  call    cs:__imp_CloseHandle
0x140268673  mov     ecx, ebx; dwErrCode
0x140268675  call    cs:__imp_SetLastError
0x14026867b  xor     r14d, r14d
0x14026867e  mov     [rbp+57h+hObject], r14
0x140268682  lea     rdx, [rbp+57h+hObject]; phToken
0x140268686  mov     ecx, [rdi+8]; SessionId
0x140268689  call    cs:__imp_WTSQueryUserToken
0x14026868f  test    eax, eax
0x140268691  jz      loc_140268777
0x140268697  mov     ebx, [rdi+8]
0x14026869a  lea     rcx, aExtMsWinSessio; "ext-ms-win-session-wtsapi32-l1-1-0"
0x1402686a1  call    cs:__imp_IsApiSetImplemented
0x1402686a7  test    eax, eax
0x1402686a9  jz      short loc_140268703
0x1402686ab  mov     [rbp+57h+ppBuffer], r14
0x1402686af  mov     [rbp+57h+pBytesReturned], r14d
0x1402686b3  lea     rax, [rbp+57h+pBytesReturned]
0x1402686b7  mov     [rsp+0B0h+pCount], rax; pBytesReturned
0x1402686bc  lea     r9, [rbp+57h+ppBuffer]; ppBuffer
0x1402686c0  lea     r8d, [r14+1Dh]; WTSInfoClass
0x1402686c4  mov     edx, ebx; SessionId
0x1402686c6  xor     ecx, ecx; hServer
0x1402686c8  call    cs:__imp_WTSQuerySessionInformationW
0x1402686ce  test    eax, eax
0x1402686d0  jz      short loc_140268703
0x1402686d2  mov     rcx, [rbp+57h+ppBuffer]; pMemory
0x1402686d6  cmp     [rbp+57h+pBytesReturned], r14d
0x1402686da  jbe     short loc_1402686E3
0x1402686dc  cmp     byte ptr [rcx], 1
0x1402686df  mov     bl, 1
0x1402686e1  jz      short loc_1402686E6
0x1402686e3  mov     bl, r14b
0x1402686e6  test    rcx, rcx
0x1402686e9  jz      short loc_1402686F1
0x1402686eb  call    cs:__imp_WTSFreeMemory
0x1402686f1  test    bl, bl
0x1402686f3  jz      short loc_140268703
0x1402686f5  or      ecx, 0FFFFFFFFh
0x1402686f8  cmp     r15d, ecx
0x1402686fb  jnz     short loc_140268703
0x1402686fd  mov     r15d, [rdi+8]
0x140268701  jmp     short loc_14026877A
0x140268703  mov     ebx, [rdi+8]
0x140268706  lea     rcx, aExtMsWinSessio; "ext-ms-win-session-wtsapi32-l1-1-0"
0x14026870d  call    cs:__imp_IsApiSetImplemented
0x140268713  test    eax, eax
0x140268715  jz      short loc_140268769
0x140268717  mov     [rbp+57h+var_58], r14
0x14026871b  mov     [rbp+57h+var_34], r14d
0x14026871f  lea     rax, [rbp+57h+var_34]
0x140268723  mov     [rsp+0B0h+pCount], rax; pBytesReturned
0x140268728  lea     r9, [rbp+57h+var_58]; ppBuffer
0x14026872c  mov     r8d, 19h; WTSInfoClass
0x140268732  mov     edx, ebx; SessionId
0x140268734  xor     ecx, ecx; hServer
0x140268736  call    cs:__imp_WTSQuerySessionInformationW
0x14026873c  test    eax, eax
0x14026873e  jz      short loc_140268769
0x140268740  mov     rcx, [rbp+57h+var_58]; pMemory
0x140268744  cmp     [rbp+57h+var_34], r14d
0x140268748  jbe     short loc_140268757
0x14026874a  cmp     dword ptr [rcx], 1
0x14026874d  jnz     short loc_140268757
0x14026874f  cmp     dword ptr [rcx+10h], 1
0x140268753  mov     bl, 1
0x140268755  jz      short loc_14026875A
0x140268757  mov     bl, r14b
0x14026875a  test    rcx, rcx
0x14026875d  jz      short loc_140268765
0x14026875f  call    cs:__imp_WTSFreeMemory
0x140268765  test    bl, bl
0x140268767  jnz     short loc_140268789
0x140268769  or      ecx, 0FFFFFFFFh
0x14026876c  cmp     r12d, ecx
0x14026876f  jnz     short loc_14026877A
0x140268771  mov     r12d, [rdi+8]
0x140268775  jmp     short loc_14026877A
0x140268777  or      ecx, 0FFFFFFFFh
0x14026877a  add     rdi, 38h ; '8'
0x14026877e  cmp     rdi, r13
0x140268781  jnz     loc_140268649
0x140268787  jmp     short loc_140268793
0x140268789  mov     edi, [rdi+8]
0x14026878c  or      ecx, 0FFFFFFFFh
0x14026878f  cmp     edi, ecx
0x140268791  jnz     short loc_1402687A5
0x140268793  cmp     r12d, ecx
0x140268796  jz      short loc_14026879D
0x140268798  mov     edi, r12d
0x14026879b  jmp     short loc_1402687A5
0x14026879d  cmp     r15d, ecx
0x1402687a0  jz      short loc_140268802
0x1402687a2  mov     edi, r15d
0x1402687a5  mov     r14, [rbp+57h+hObject]
0x1402687a9  test    r14, r14
0x1402687ac  jz      short loc_1402687CD
0x1402687ae  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1402687b2  jz      short loc_1402687CD
0x1402687b4  call    cs:__imp_GetLastError
0x1402687ba  mov     ebx, eax
0x1402687bc  mov     rcx, r14; hObject
0x1402687bf  call    cs:__imp_CloseHandle
0x1402687c5  mov     ecx, ebx; dwErrCode
0x1402687c7  call    cs:__imp_SetLastError
0x1402687cd  mov     [rbp+57h+hObject], 0
0x1402687d5  lea     rdx, [rbp+57h+hObject]; phToken
0x1402687d9  mov     ecx, edi; SessionId
0x1402687db  call    cs:__imp_WTSQueryUserToken
0x1402687e1  mov     rcx, [rbp+5Fh]; this
0x1402687e5  test    eax, eax
0x1402687e7  jz      short loc_140268860
0x1402687e9  mov     rax, [rbp+57h+hObject]
0x1402687ed  mov     [rsi], rax
0x1402687f0  mov     [rbp+57h+hObject], 0
0x1402687f8  mov     r8d, [rbp+57h+NumberOfEntries]
0x1402687fc  mov     rdx, [rbp+57h+ppSessionInfo]
0x140268800  jmp     short loc_140268810
0x140268802  mov     r8d, [rbp+57h+NumberOfEntries]; NumberOfEntries
0x140268806  mov     rdi, [rbp+57h+ppSessionInfo]
0x14026880a  mov     [rsi], r14
0x14026880d  mov     rdx, rdi; pMemory
0x140268810  mov     ecx, 2; WTSTypeClass
0x140268815  call    cs:__imp_WTSFreeMemoryExW
0x14026881b  nop
0x14026881c  mov     rcx, [rbp+57h+hObject]; hObject
0x140268820  lea     rax, [rcx-1]
0x140268824  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140268828  ja      short loc_140268830
0x14026882a  call    cs:__imp_CloseHandle
0x140268830  mov     rax, rsi
0x140268833  mov     rcx, [rbp+57h+var_28]
0x140268837  xor     rcx, rsp; StackCookie
0x14026883a  call    __security_check_cookie
0x14026883f  lea     r11, [rsp+0B0h+var_20]
0x140268847  mov     rbx, [r11+38h]
0x14026884b  mov     rsi, [r11+40h]
0x14026884f  mov     rdi, [r11+48h]
0x140268853  mov     rsp, r11
0x140268856  pop     r15
0x140268858  pop     r14
0x14026885a  pop     r13
0x14026885c  pop     r12
0x14026885e  pop     rbp
0x14026885f  retn
0x140268860  lea     r8, aCW1SSrcOrchest_54; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140268867  mov     edx, 81h; void *
0x14026886c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140268872  lea     r8, aCW1SSrcOrchest_54; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140268879  mov     edx, 43h ; 'C'; void *
0x14026887e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140268884  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
