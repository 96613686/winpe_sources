# CaptureSnapshot

- ea: `0x140047b58`
- end: `0x140047fd6`
- name: `CaptureSnapshot`
- size: `1150`
- prototype: `__int64 __fastcall(HANDLE hFileMappingObject)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140048410`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x14000aab4`
- `0x14000aad4`
- `0x140016434`
- `0x1400166ec`
- `0x140047b58`
- `0x140047fdc`
- `0x140048038`
- `0x1400480f4`
- `0x1400481cc`
- `0x140048720`
- `0x140048748`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x140047d3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x140047d3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140047eae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140047eae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047d7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047dd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047df3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047f34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047f4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047f79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047f93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047d7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047dd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047df3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047f34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047f4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047f79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047f93`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140047baf`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140047baf`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047c18`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047ca5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047cc6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047d1f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047d8a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047e03`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047f5e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047fa3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047c18`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047ca5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047cc6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047d1f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047d8a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047e03`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047f5e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140047fa3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140047ce9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140047ce9`
- `ntdll!PssNtCaptureSnapshot` at `0x140047e32`
- `ntdll!PssNtCaptureSnapshot` at `0x140047e32`
- `api-ms-win-core-processsnapshot-l1-1-0!PssDuplicateSnapshot` at `0x140047ed0`
- `api-ms-win-core-processsnapshot-l1-1-0!PssDuplicateSnapshot` at `0x140047ed0`

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
0x140047b58  mov     [rsp-8+arg_18], rbx
0x140047b5d  push    rbp
0x140047b5e  push    rsi
0x140047b5f  push    rdi
0x140047b60  push    r12
0x140047b62  push    r15
0x140047b64  lea     rbp, [rsp-80h]
0x140047b69  sub     rsp, 180h
0x140047b70  mov     rax, cs:__security_cookie
0x140047b77  xor     rax, rsp
0x140047b7a  mov     [rbp+0A0h+var_30], rax
0x140047b7e  mov     edi, r8d
0x140047b81  mov     r12, rdx
0x140047b84  mov     rbx, rcx
0x140047b87  xor     edx, edx; Val
0x140047b89  mov     r8d, 0F8h; Size
0x140047b8f  lea     rcx, [rsp+1A0h+var_130]; void *
0x140047b94  call    memset_0
0x140047b99  mov     [rsp+1A0h+dwNumberOfBytesToMap], 0; int
0x140047ba2  xor     r9d, r9d; dwFileOffsetLow
0x140047ba5  xor     r8d, r8d; dwFileOffsetHigh
0x140047ba8  lea     edx, [r9+6]; dwDesiredAccess
0x140047bac  mov     rcx, rbx; hFileMappingObject
0x140047baf  call    cs:__imp_MapViewOfFile
0x140047bb6  nop     dword ptr [rax+rax+00h]
0x140047bbb  mov     rsi, rax
0x140047bbe  mov     [rsp+1A0h+var_150], rax
0x140047bc3  test    rax, rax
0x140047bc6  jnz     short loc_140047BE6
0x140047bc8  mov     rcx, [rbp+0A8h]; this
0x140047bcf  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140047bd6  mov     edx, 0CBh; void *
0x140047bdb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140047be0  nop
0x140047be1  jmp     loc_140047FB2
0x140047be6  mov     rdx, rsi
0x140047be9  lea     rcx, [rsp+1A0h+var_130]
0x140047bee  call    SafeCopyMemory
0x140047bf3  mov     ebx, eax
0x140047bf5  test    eax, eax
0x140047bf7  jns     short loc_140047C2C
0x140047bf9  mov     rcx, [rbp+0A8h]; this
0x140047c00  mov     r9d, eax; char *
0x140047c03  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140047c0a  mov     edx, 0D1h; void *
0x140047c0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047c14  nop
0x140047c15  mov     rcx, rsi; lpBaseAddress
0x140047c18  call    cs:__imp_UnmapViewOfFile
0x140047c1f  nop     dword ptr [rax+rax+00h]
0x140047c24  nop
0x140047c25  mov     eax, ebx
0x140047c27  jmp     loc_140047FB2
0x140047c2c  mov     edx, dword ptr [rbp+0A0h+var_48]
0x140047c2f  lea     eax, [rdx+3FFFFFFFh]
0x140047c35  cmp     eax, 1
0x140047c38  jbe     short loc_140047C46
0x140047c3a  cmp     edx, 0C00000BBh
0x140047c40  jz      short loc_140047C46
0x140047c42  mov     al, 1
0x140047c44  jmp     short loc_140047C48
0x140047c46  xor     eax, eax
0x140047c48  mov     rcx, [rbp+0A8h]; this
0x140047c4f  mov     dword ptr [rsp+1A0h+var_170], edx; char *
0x140047c53  lea     rdx, aUnexpectedSnap; "Unexpected snapshot status present in t"...
0x140047c5a  mov     [rsp+1A0h+var_178], rdx; bool
0x140047c5f  mov     byte ptr [rsp+1A0h+dwNumberOfBytesToMap], al; int
0x140047c63  mov     r9d, 8000FFFFh; char *
0x140047c69  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140047c70  mov     edx, 0DEh; void *
0x140047c75  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x140047c7a  cmp     [rbp+0A0h+var_50], 0
0x140047c7f  jz      short loc_140047CB7
0x140047c81  mov     rcx, [rbp+0A8h]; this
0x140047c88  mov     ebx, 800700B7h
0x140047c8d  mov     r9d, ebx; char *
0x140047c90  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140047c97  mov     edx, 0E2h; void *
0x140047c9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047ca1  nop
0x140047ca2  mov     rcx, rsi; lpBaseAddress
0x140047ca5  call    cs:__imp_UnmapViewOfFile
0x140047cac  nop     dword ptr [rax+rax+00h]
0x140047cb1  nop
0x140047cb2  jmp     loc_140047C25
0x140047cb7  cmp     [rsp+1A0h+var_12C], edi
0x140047cbb  jz      short loc_140047CDD
0x140047cbd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140047cc2  nop
0x140047cc3  mov     rcx, rsi; lpBaseAddress
0x140047cc6  call    cs:__imp_UnmapViewOfFile
0x140047ccd  nop     dword ptr [rax+rax+00h]
0x140047cd2  nop
0x140047cd3  mov     eax, 80070057h
0x140047cd8  jmp     loc_140047FB2
0x140047cdd  mov     r8d, edi; dwProcessId
0x140047ce0  xor     edx, edx; bInheritHandle
0x140047ce2  mov     ebx, 1FFFFFh
0x140047ce7  mov     ecx, ebx; dwDesiredAccess
0x140047ce9  call    cs:__imp_OpenProcess
0x140047cf0  nop     dword ptr [rax+rax+00h]
0x140047cf5  mov     rdi, rax
0x140047cf8  mov     [rsp+1A0h+var_148], rax
0x140047cfd  test    rax, rax
0x140047d00  jnz     short loc_140047D31
0x140047d02  mov     rcx, [rbp+0A8h]; this
0x140047d09  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140047d10  mov     edx, 0F4h; void *
0x140047d15  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140047d1a  mov     ebx, eax
0x140047d1c  mov     rcx, rsi; lpBaseAddress
0x140047d1f  call    cs:__imp_UnmapViewOfFile
0x140047d26  nop     dword ptr [rax+rax+00h]
0x140047d2b  nop
0x140047d2c  jmp     loc_140047C25
0x140047d31  mov     r8d, [rsp+1A0h+dwThreadId]; dwThreadId
0x140047d36  xor     edx, edx; bInheritHandle
0x140047d38  mov     ecx, ebx; dwDesiredAccess
0x140047d3a  call    cs:__imp_OpenThread
0x140047d41  nop     dword ptr [rax+rax+00h]
0x140047d46  mov     r15, rax
0x140047d49  mov     [rsp+1A0h+var_140], rax
0x140047d4e  test    rax, rax
0x140047d51  jnz     short loc_140047D9C
0x140047d53  mov     rcx, [rbp+0A8h]; this
0x140047d5a  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140047d61  mov     edx, 0FAh; void *
0x140047d66  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140047d6b  mov     ebx, eax
0x140047d6d  lea     rcx, [rdi+1]
0x140047d71  cmp     rcx, 1
0x140047d75  jbe     short loc_140047D87
0x140047d77  mov     rcx, rdi; hObject
0x140047d7a  call    cs:__imp_CloseHandle
0x140047d81  nop     dword ptr [rax+rax+00h]
0x140047d86  nop
0x140047d87  mov     rcx, rsi; lpBaseAddress
0x140047d8a  call    cs:__imp_UnmapViewOfFile
0x140047d91  nop     dword ptr [rax+rax+00h]
0x140047d96  nop
0x140047d97  jmp     loc_140047C25
0x140047d9c  mov     rdx, r15; ThreadHandle
0x140047d9f  mov     rcx, rdi; hProcess
0x140047da2  call    ShouldCaptureSnapshot
0x140047da7  test    eax, eax
0x140047da9  jz      short loc_140047E15
0x140047dab  mov     rcx, [rbp+0A8h]; this
0x140047db2  mov     ebx, 800710DDh
0x140047db7  mov     r9d, ebx; char *
0x140047dba  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140047dc1  mov     edx, 100h; void *
0x140047dc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047dcb  nop
0x140047dcc  lea     rax, [r15+1]
0x140047dd0  cmp     rax, 1
0x140047dd4  jbe     short loc_140047DE6
0x140047dd6  mov     rcx, r15; hObject
0x140047dd9  call    cs:__imp_CloseHandle
0x140047de0  nop     dword ptr [rax+rax+00h]
0x140047de5  nop
0x140047de6  lea     rcx, [rdi+1]
0x140047dea  cmp     rcx, 1
0x140047dee  jbe     short loc_140047E00
0x140047df0  mov     rcx, rdi; hObject
0x140047df3  call    cs:__imp_CloseHandle
0x140047dfa  nop     dword ptr [rax+rax+00h]
0x140047dff  nop
0x140047e00  mov     rcx, rsi; lpBaseAddress
0x140047e03  call    cs:__imp_UnmapViewOfFile
0x140047e0a  nop     dword ptr [rax+rax+00h]
0x140047e0f  nop
0x140047e10  jmp     loc_140047C25
0x140047e15  mov     [rsp+1A0h+var_160], 0
0x140047e1e  mov     r9d, 10005Fh
0x140047e24  mov     r8d, 0D0003BFFh
0x140047e2a  mov     rdx, rdi
0x140047e2d  lea     rcx, [rsp+1A0h+var_160]
0x140047e32  call    cs:__imp_PssNtCaptureSnapshot
0x140047e39  nop     dword ptr [rax+rax+00h]
0x140047e3e  mov     ebx, eax
0x140047e40  mov     dword ptr [rbp+0A0h+var_48], eax
0x140047e43  mov     rcx, [rbp+0A8h]; this
0x140047e4a  mov     dword ptr [rsp+1A0h+var_178], eax; char *
0x140047e4e  lea     rax, aPssntcapturesn; "PssNtCaptureSnapshot failed, Status=0x%"...
0x140047e55  mov     [rsp+1A0h+dwNumberOfBytesToMap], rax; int
0x140047e5a  mov     r9d, ebx; char *
0x140047e5d  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140047e64  mov     edx, 12Ah; void *
0x140047e69  call    ?Log_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x140047e6e  test    ebx, ebx
0x140047e70  jnz     loc_140047EF8
0x140047e76  mov     rcx, [rsp+1A0h+var_160]; struct HPSS__ *
0x140047e7b  test    rcx, rcx
0x140047e7e  jz      short loc_140047EF8
0x140047e80  mov     [rsp+1A0h+var_158], 0
0x140047e89  mov     rdx, rdi; void *
0x140047e8c  call    ?GrantTokenQueryAccessToProcessSid@@YAJPEAUHPSS__@@PEAX@Z; GrantTokenQueryAccessToProcessSid(HPSS__ *,void *)
0x140047e91  mov     rcx, [rbp+0A8h]; this
0x140047e98  test    eax, eax
0x140047e9a  jns     short loc_140047EA9
0x140047e9c  mov     r9d, eax; char *
0x140047e9f  mov     edx, 137h; void *
0x140047ea4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140047ea9  mov     rbx, [rsp+1A0h+var_160]
0x140047eae  call    cs:__imp_GetCurrentProcess
0x140047eb5  nop     dword ptr [rax+rax+00h]
0x140047eba  mov     dword ptr [rsp+1A0h+dwNumberOfBytesToMap], 1; int
0x140047ec2  lea     r9, [rsp+1A0h+var_158]
0x140047ec7  mov     r8, r12
0x140047eca  mov     rdx, rbx
0x140047ecd  mov     rcx, rax
0x140047ed0  call    cs:__imp_PssDuplicateSnapshot
0x140047ed7  nop     dword ptr [rax+rax+00h]
0x140047edc  mov     rcx, [rbp+0A8h]; this
0x140047ee3  test    eax, eax
0x140047ee5  jz      short loc_140047EEF
0x140047ee7  mov     r9d, eax; char *
0x140047eea  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x140047eef  mov     rax, [rsp+1A0h+var_158]
0x140047ef4  mov     [rbp+0A0h+var_50], rax
0x140047ef8  lea     rdx, [rsp+1A0h+var_130]
0x140047efd  mov     rcx, rsi
0x140047f00  call    SafeCopyMemory
0x140047f05  mov     ebx, eax
0x140047f07  lea     r12, [r15+1]
0x140047f0b  test    eax, eax
0x140047f0d  jns     short loc_140047F70
0x140047f0f  mov     rcx, [rbp+0A8h]; this
0x140047f16  mov     r9d, eax; char *
0x140047f19  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140047f20  mov     edx, 147h; void *
0x140047f25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047f2a  nop
0x140047f2b  cmp     r12, 1
0x140047f2f  jbe     short loc_140047F41
0x140047f31  mov     rcx, r15; hObject
0x140047f34  call    cs:__imp_CloseHandle
0x140047f3b  nop     dword ptr [rax+rax+00h]
0x140047f40  nop
0x140047f41  lea     rax, [rdi+1]
0x140047f45  cmp     rax, 1
0x140047f49  jbe     short loc_140047F5B
0x140047f4b  mov     rcx, rdi; hObject
0x140047f4e  call    cs:__imp_CloseHandle
0x140047f55  nop     dword ptr [rax+rax+00h]
0x140047f5a  nop
0x140047f5b  mov     rcx, rsi; lpBaseAddress
0x140047f5e  call    cs:__imp_UnmapViewOfFile
0x140047f65  nop     dword ptr [rax+rax+00h]
0x140047f6a  nop
0x140047f6b  jmp     loc_140047C25
0x140047f70  cmp     r12, 1
0x140047f74  jbe     short loc_140047F86
0x140047f76  mov     rcx, r15; hObject
0x140047f79  call    cs:__imp_CloseHandle
0x140047f80  nop     dword ptr [rax+rax+00h]
0x140047f85  nop
0x140047f86  lea     rax, [rdi+1]
0x140047f8a  cmp     rax, 1
0x140047f8e  jbe     short loc_140047FA0
0x140047f90  mov     rcx, rdi; hObject
0x140047f93  call    cs:__imp_CloseHandle
0x140047f9a  nop     dword ptr [rax+rax+00h]
0x140047f9f  nop
0x140047fa0  mov     rcx, rsi; lpBaseAddress
0x140047fa3  call    cs:__imp_UnmapViewOfFile
0x140047faa  nop     dword ptr [rax+rax+00h]
0x140047faf  nop
0x140047fb0  xor     eax, eax
0x140047fb2  mov     rcx, [rbp+0A0h+var_30]
0x140047fb6  xor     rcx, rsp; StackCookie
0x140047fb9  call    __security_check_cookie
0x140047fbe  mov     rbx, [rsp+1A0h+arg_18]
0x140047fc6  add     rsp, 180h
0x140047fcd  pop     r15
0x140047fcf  pop     r12
0x140047fd1  pop     rdi
0x140047fd2  pop     rsi
0x140047fd3  pop     rbp
0x140047fd4  retn
```
