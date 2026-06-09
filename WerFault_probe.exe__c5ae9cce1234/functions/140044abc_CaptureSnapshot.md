# CaptureSnapshot

- ea: `0x140044abc`
- end: `0x140044eb7`
- name: `CaptureSnapshot`
- size: `1019`
- prototype: `__int64 __fastcall(HANDLE hFileMappingObject)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400452c8`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14000a9a4`
- `0x14000a9c4`
- `0x14001589c`
- `0x140015b40`
- `0x140044abc`
- `0x140044ec0`
- `0x140044f1c`
- `0x140044fd4`
- `0x1400450ac`
- `0x140045588`
- `0x1400455ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x140044c7a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x140044c7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140044dc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140044dc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044cb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044d07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044d1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044e3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044e4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044e6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044e81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044cb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044d07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044d1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044e3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044e4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044e6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140044e81`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140044b13`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140044b13`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044b76`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044bfd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044c18`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044c65`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044cbe`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044d25`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044e58`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044e8b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044b76`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044bfd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044c18`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044c65`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044cbe`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044d25`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044e58`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140044e8b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140044c35`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140044c35`
- `ntdll!PssNtCaptureSnapshot` at `0x140044d4e`
- `ntdll!PssNtCaptureSnapshot` at `0x140044d4e`
- `api-ms-win-core-processsnapshot-l1-1-0!PssDuplicateSnapshot` at `0x140044ddc`
- `api-ms-win-core-processsnapshot-l1-1-0!PssDuplicateSnapshot` at `0x140044ddc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CaptureSnapshot(HANDLE hFileMappingObject, __int64 a2, DWORD a3)
{
  const void *v6; // rax
  const char *v7; // r9
  const void *v8; // rsi
  int v10; // eax
  unsigned int LastError; // ebx
  bool v12; // al
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  HANDLE v17; // rdi
  const char *v18; // r9
  HANDLE v19; // rax
  const char *v20; // r9
  void *v21; // r15
  unsigned int v22; // ebx
  int AccessToProcessSid; // eax
  unsigned int v24; // r8d
  struct HPSS__ *v25; // rbx
  HANDLE CurrentProcess; // rax
  unsigned int v27; // eax
  void *v28; // rdx
  unsigned int v29; // r8d
  int v30; // eax
  unsigned __int64 v31; // r12
  int dwNumberOfBytesToMap; // [rsp+20h] [rbp-E0h]
  int dwNumberOfBytesToMapa; // [rsp+20h] [rbp-E0h]
  int dwNumberOfBytesToMapb; // [rsp+20h] [rbp-E0h]
  char *v35; // [rsp+28h] [rbp-D8h]
  char *v36; // [rsp+30h] [rbp-D0h]
  struct HPSS__ *v37; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v38[5]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v39[4]; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+74h] [rbp-8Ch]
  DWORD dwThreadId; // [rsp+78h] [rbp-88h]
  __int64 v42; // [rsp+150h] [rbp+50h]
  char *v43; // [rsp+158h] [rbp+58h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  memset_0(v39, 0, 0xF8u);
  v6 = MapViewOfFile(hFileMappingObject, 6u, 0, 0, 0);
  v8 = v6;
  v38[1] = v6;
  if ( !v6 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xCB,
             (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
             v7);
  v10 = SafeCopyMemory(v39, v6);
  LastError = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
      (const char *)(unsigned int)v10,
      dwNumberOfBytesToMap);
    UnmapViewOfFile(v8);
    return LastError;
  }
  v12 = (unsigned int)((_DWORD)v43 + 0x3FFFFFFF) > 1 && (_DWORD)v43 != -1073741637;
  LODWORD(v36) = (_DWORD)v43;
  LOBYTE(dwNumberOfBytesToMap) = v12;
  wil::details::in1diag3::Log_HrIfMsg(
    retaddr,
    (void *)0xDE,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
    (const char *)0x8000FFFFLL,
    dwNumberOfBytesToMap,
    (bool)"Unexpected snapshot status present in the shared data %x",
    v36);
  if ( v42 )
  {
    LastError = -2147024713;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
      (const char *)0x800700B7LL,
      dwNumberOfBytesToMapa);
    UnmapViewOfFile(v8);
    return LastError;
  }
  if ( v40 != a3 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v14, v13, v15, v16);
    UnmapViewOfFile(v8);
    return 2147942487LL;
  }
  v17 = OpenProcess(0x1FFFFFu, 0, a3);
  v38[2] = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xF4,
                  (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
                  v18);
    UnmapViewOfFile(v8);
    return LastError;
  }
  v19 = OpenThread(0x1FFFFFu, 0, dwThreadId);
  v21 = v19;
  v38[3] = v19;
  if ( !v19 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xFA,
                  (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
                  v20);
    if ( (unsigned __int64)v17 + 1 > 1 )
      CloseHandle(v17);
LABEL_19:
    UnmapViewOfFile(v8);
    return LastError;
  }
  if ( (unsigned int)ShouldCaptureSnapshot(v17, v19) )
  {
    LastError = -2147020579;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
      (const char *)0x800710DDLL,
      dwNumberOfBytesToMapa);
    if ( (unsigned __int64)v21 + 1 > 1 )
      CloseHandle(v21);
    if ( (unsigned __int64)v17 + 1 > 1 )
      CloseHandle(v17);
    goto LABEL_19;
  }
  v37 = 0;
  v22 = PssNtCaptureSnapshot(&v37, v17, 3489676287LL, 1048671);
  LODWORD(v43) = v22;
  LODWORD(v35) = v22;
  wil::details::in1diag3::Log_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x12A,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
    (const char *)v22,
    (int)"PssNtCaptureSnapshot failed, Status=0x%x",
    v35);
  if ( !v22 && v37 )
  {
    v38[0] = 0;
    AccessToProcessSid = GrantTokenQueryAccessToProcessSid(v37, v17);
    if ( AccessToProcessSid < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x137,
        v24,
        (const char *)(unsigned int)AccessToProcessSid,
        dwNumberOfBytesToMapb);
    v25 = v37;
    CurrentProcess = GetCurrentProcess();
    dwNumberOfBytesToMapb = 1;
    v27 = PssDuplicateSnapshot(CurrentProcess, v25, a2, v38);
    if ( v27 )
      wil::details::in1diag3::_Log_Win32(retaddr, v28, v29, (const char *)v27, 1u);
    v42 = v38[0];
  }
  v30 = SafeCopyMemory(v8, v39);
  LastError = v30;
  v31 = (unsigned __int64)v21 + 1;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
      (const char *)(unsigned int)v30,
      dwNumberOfBytesToMapb);
    if ( v31 > 1 )
      CloseHandle(v21);
    if ( (unsigned __int64)v17 + 1 > 1 )
      CloseHandle(v17);
    UnmapViewOfFile(v8);
    return LastError;
  }
  if ( v31 > 1 )
    CloseHandle(v21);
  if ( (unsigned __int64)v17 + 1 > 1 )
    CloseHandle(v17);
  UnmapViewOfFile(v8);
  return 0;
}

```

## disassembly

```asm
0x140044abc  mov     [rsp-8+arg_18], rbx
0x140044ac1  push    rbp
0x140044ac2  push    rsi
0x140044ac3  push    rdi
0x140044ac4  push    r12
0x140044ac6  push    r15
0x140044ac8  lea     rbp, [rsp-80h]
0x140044acd  sub     rsp, 180h
0x140044ad4  mov     rax, cs:__security_cookie
0x140044adb  xor     rax, rsp
0x140044ade  mov     [rbp+0A0h+var_30], rax
0x140044ae2  mov     edi, r8d
0x140044ae5  mov     r12, rdx
0x140044ae8  mov     rbx, rcx
0x140044aeb  xor     edx, edx; Val
0x140044aed  mov     r8d, 0F8h; Size
0x140044af3  lea     rcx, [rsp+1A0h+var_130]; void *
0x140044af8  call    memset_0
0x140044afd  mov     [rsp+1A0h+dwNumberOfBytesToMap], 0; int
0x140044b06  xor     r9d, r9d; dwFileOffsetLow
0x140044b09  xor     r8d, r8d; dwFileOffsetHigh
0x140044b0c  lea     edx, [r9+6]; dwDesiredAccess
0x140044b10  mov     rcx, rbx; hFileMappingObject
0x140044b13  call    cs:__imp_MapViewOfFile
0x140044b19  mov     rsi, rax
0x140044b1c  mov     [rsp+1A0h+var_150], rax
0x140044b21  test    rax, rax
0x140044b24  jnz     short loc_140044B44
0x140044b26  mov     rcx, [rbp+0A8h]; this
0x140044b2d  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140044b34  mov     edx, 0CBh; void *
0x140044b39  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140044b3e  nop
0x140044b3f  jmp     loc_140044E94
0x140044b44  mov     rdx, rsi
0x140044b47  lea     rcx, [rsp+1A0h+var_130]
0x140044b4c  call    SafeCopyMemory
0x140044b51  mov     ebx, eax
0x140044b53  test    eax, eax
0x140044b55  jns     short loc_140044B84
0x140044b57  mov     rcx, [rbp+0A8h]; this
0x140044b5e  mov     r9d, eax; char *
0x140044b61  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140044b68  mov     edx, 0D1h; void *
0x140044b6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140044b72  nop
0x140044b73  mov     rcx, rsi; lpBaseAddress
0x140044b76  call    cs:__imp_UnmapViewOfFile
0x140044b7c  nop
0x140044b7d  mov     eax, ebx
0x140044b7f  jmp     loc_140044E94
0x140044b84  mov     edx, dword ptr [rbp+0A0h+var_48]
0x140044b87  lea     eax, [rdx+3FFFFFFFh]
0x140044b8d  cmp     eax, 1
0x140044b90  jbe     short loc_140044B9E
0x140044b92  cmp     edx, 0C00000BBh
0x140044b98  jz      short loc_140044B9E
0x140044b9a  mov     al, 1
0x140044b9c  jmp     short loc_140044BA0
0x140044b9e  xor     eax, eax
0x140044ba0  mov     rcx, [rbp+0A8h]; this
0x140044ba7  mov     dword ptr [rsp+1A0h+var_170], edx; char *
0x140044bab  lea     rdx, aUnexpectedSnap; "Unexpected snapshot status present in t"...
0x140044bb2  mov     [rsp+1A0h+var_178], rdx; bool
0x140044bb7  mov     byte ptr [rsp+1A0h+dwNumberOfBytesToMap], al; int
0x140044bbb  mov     r9d, 8000FFFFh; char *
0x140044bc1  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140044bc8  mov     edx, 0DEh; void *
0x140044bcd  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x140044bd2  cmp     [rbp+0A0h+var_50], 0
0x140044bd7  jz      short loc_140044C09
0x140044bd9  mov     rcx, [rbp+0A8h]; this
0x140044be0  mov     ebx, 800700B7h
0x140044be5  mov     r9d, ebx; char *
0x140044be8  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140044bef  mov     edx, 0E2h; void *
0x140044bf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140044bf9  nop
0x140044bfa  mov     rcx, rsi; lpBaseAddress
0x140044bfd  call    cs:__imp_UnmapViewOfFile
0x140044c03  nop
0x140044c04  jmp     loc_140044B7D
0x140044c09  cmp     [rsp+1A0h+var_12C], edi
0x140044c0d  jz      short loc_140044C29
0x140044c0f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140044c14  nop
0x140044c15  mov     rcx, rsi; lpBaseAddress
0x140044c18  call    cs:__imp_UnmapViewOfFile
0x140044c1e  nop
0x140044c1f  mov     eax, 80070057h
0x140044c24  jmp     loc_140044E94
0x140044c29  mov     r8d, edi; dwProcessId
0x140044c2c  xor     edx, edx; bInheritHandle
0x140044c2e  mov     ebx, 1FFFFFh
0x140044c33  mov     ecx, ebx; dwDesiredAccess
0x140044c35  call    cs:__imp_OpenProcess
0x140044c3b  mov     rdi, rax
0x140044c3e  mov     [rsp+1A0h+var_148], rax
0x140044c43  test    rax, rax
0x140044c46  jnz     short loc_140044C71
0x140044c48  mov     rcx, [rbp+0A8h]; this
0x140044c4f  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140044c56  mov     edx, 0F4h; void *
0x140044c5b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140044c60  mov     ebx, eax
0x140044c62  mov     rcx, rsi; lpBaseAddress
0x140044c65  call    cs:__imp_UnmapViewOfFile
0x140044c6b  nop
0x140044c6c  jmp     loc_140044B7D
0x140044c71  mov     r8d, [rsp+1A0h+dwThreadId]; dwThreadId
0x140044c76  xor     edx, edx; bInheritHandle
0x140044c78  mov     ecx, ebx; dwDesiredAccess
0x140044c7a  call    cs:__imp_OpenThread
0x140044c80  mov     r15, rax
0x140044c83  mov     [rsp+1A0h+var_140], rax
0x140044c88  test    rax, rax
0x140044c8b  jnz     short loc_140044CCA
0x140044c8d  mov     rcx, [rbp+0A8h]; this
0x140044c94  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140044c9b  mov     edx, 0FAh; void *
0x140044ca0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140044ca5  mov     ebx, eax
0x140044ca7  lea     rcx, [rdi+1]
0x140044cab  cmp     rcx, 1
0x140044caf  jbe     short loc_140044CBB
0x140044cb1  mov     rcx, rdi; hObject
0x140044cb4  call    cs:__imp_CloseHandle
0x140044cba  nop
0x140044cbb  mov     rcx, rsi; lpBaseAddress
0x140044cbe  call    cs:__imp_UnmapViewOfFile
0x140044cc4  nop
0x140044cc5  jmp     loc_140044B7D
0x140044cca  mov     rdx, r15; ThreadHandle
0x140044ccd  mov     rcx, rdi; hProcess
0x140044cd0  call    ShouldCaptureSnapshot
0x140044cd5  test    eax, eax
0x140044cd7  jz      short loc_140044D31
0x140044cd9  mov     rcx, [rbp+0A8h]; this
0x140044ce0  mov     ebx, 800710DDh
0x140044ce5  mov     r9d, ebx; char *
0x140044ce8  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140044cef  mov     edx, 100h; void *
0x140044cf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140044cf9  nop
0x140044cfa  lea     rax, [r15+1]
0x140044cfe  cmp     rax, 1
0x140044d02  jbe     short loc_140044D0E
0x140044d04  mov     rcx, r15; hObject
0x140044d07  call    cs:__imp_CloseHandle
0x140044d0d  nop
0x140044d0e  lea     rcx, [rdi+1]
0x140044d12  cmp     rcx, 1
0x140044d16  jbe     short loc_140044D22
0x140044d18  mov     rcx, rdi; hObject
0x140044d1b  call    cs:__imp_CloseHandle
0x140044d21  nop
0x140044d22  mov     rcx, rsi; lpBaseAddress
0x140044d25  call    cs:__imp_UnmapViewOfFile
0x140044d2b  nop
0x140044d2c  jmp     loc_140044B7D
0x140044d31  mov     [rsp+1A0h+var_160], 0
0x140044d3a  mov     r9d, 10005Fh
0x140044d40  mov     r8d, 0D0003BFFh
0x140044d46  mov     rdx, rdi
0x140044d49  lea     rcx, [rsp+1A0h+var_160]
0x140044d4e  call    cs:__imp_PssNtCaptureSnapshot
0x140044d54  mov     ebx, eax
0x140044d56  mov     dword ptr [rbp+0A0h+var_48], eax
0x140044d59  mov     rcx, [rbp+0A8h]; this
0x140044d60  mov     dword ptr [rsp+1A0h+var_178], eax; char *
0x140044d64  lea     rax, aPssntcapturesn; "PssNtCaptureSnapshot failed, Status=0x%"...
0x140044d6b  mov     [rsp+1A0h+dwNumberOfBytesToMap], rax; int
0x140044d70  mov     r9d, ebx; char *
0x140044d73  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140044d7a  mov     edx, 12Ah; void *
0x140044d7f  call    ?Log_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x140044d84  test    ebx, ebx
0x140044d86  jnz     short loc_140044DFE
0x140044d88  mov     rcx, [rsp+1A0h+var_160]; struct HPSS__ *
0x140044d8d  test    rcx, rcx
0x140044d90  jz      short loc_140044DFE
0x140044d92  mov     [rsp+1A0h+var_158], 0
0x140044d9b  mov     rdx, rdi; void *
0x140044d9e  call    ?GrantTokenQueryAccessToProcessSid@@YAJPEAUHPSS__@@PEAX@Z; GrantTokenQueryAccessToProcessSid(HPSS__ *,void *)
0x140044da3  mov     rcx, [rbp+0A8h]; this
0x140044daa  test    eax, eax
0x140044dac  jns     short loc_140044DBB
0x140044dae  mov     r9d, eax; char *
0x140044db1  mov     edx, 137h; void *
0x140044db6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140044dbb  mov     rbx, [rsp+1A0h+var_160]
0x140044dc0  call    cs:__imp_GetCurrentProcess
0x140044dc6  mov     dword ptr [rsp+1A0h+dwNumberOfBytesToMap], 1; int
0x140044dce  lea     r9, [rsp+1A0h+var_158]
0x140044dd3  mov     r8, r12
0x140044dd6  mov     rdx, rbx
0x140044dd9  mov     rcx, rax
0x140044ddc  call    cs:__imp_PssDuplicateSnapshot
0x140044de2  mov     rcx, [rbp+0A8h]; this
0x140044de9  test    eax, eax
0x140044deb  jz      short loc_140044DF5
0x140044ded  mov     r9d, eax; char *
0x140044df0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x140044df5  mov     rax, [rsp+1A0h+var_158]
0x140044dfa  mov     [rbp+0A0h+var_50], rax
0x140044dfe  lea     rdx, [rsp+1A0h+var_130]
0x140044e03  mov     rcx, rsi
0x140044e06  call    SafeCopyMemory
0x140044e0b  mov     ebx, eax
0x140044e0d  lea     r12, [r15+1]
0x140044e11  test    eax, eax
0x140044e13  jns     short loc_140044E64
0x140044e15  mov     rcx, [rbp+0A8h]; this
0x140044e1c  mov     r9d, eax; char *
0x140044e1f  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140044e26  mov     edx, 147h; void *
0x140044e2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140044e30  nop
0x140044e31  cmp     r12, 1
0x140044e35  jbe     short loc_140044E41
0x140044e37  mov     rcx, r15; hObject
0x140044e3a  call    cs:__imp_CloseHandle
0x140044e40  nop
0x140044e41  lea     rax, [rdi+1]
0x140044e45  cmp     rax, 1
0x140044e49  jbe     short loc_140044E55
0x140044e4b  mov     rcx, rdi; hObject
0x140044e4e  call    cs:__imp_CloseHandle
0x140044e54  nop
0x140044e55  mov     rcx, rsi; lpBaseAddress
0x140044e58  call    cs:__imp_UnmapViewOfFile
0x140044e5e  nop
0x140044e5f  jmp     loc_140044B7D
0x140044e64  cmp     r12, 1
0x140044e68  jbe     short loc_140044E74
0x140044e6a  mov     rcx, r15; hObject
0x140044e6d  call    cs:__imp_CloseHandle
0x140044e73  nop
0x140044e74  lea     rax, [rdi+1]
0x140044e78  cmp     rax, 1
0x140044e7c  jbe     short loc_140044E88
0x140044e7e  mov     rcx, rdi; hObject
0x140044e81  call    cs:__imp_CloseHandle
0x140044e87  nop
0x140044e88  mov     rcx, rsi; lpBaseAddress
0x140044e8b  call    cs:__imp_UnmapViewOfFile
0x140044e91  nop
0x140044e92  xor     eax, eax
0x140044e94  mov     rcx, [rbp+0A0h+var_30]
0x140044e98  xor     rcx, rsp; StackCookie
0x140044e9b  call    __security_check_cookie
0x140044ea0  mov     rbx, [rsp+1A0h+arg_18]
0x140044ea8  add     rsp, 180h
0x140044eaf  pop     r15
0x140044eb1  pop     r12
0x140044eb3  pop     rdi
0x140044eb4  pop     rsi
0x140044eb5  pop     rbp
0x140044eb6  retn
```
