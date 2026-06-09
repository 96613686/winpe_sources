# InitializeSession

- ea: `0x140003e54`
- end: `0x140004696`
- name: `InitializeSession`
- size: `2114`
- prototype: `__int64 __fastcall(HINSTANCE, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140003c5c`
- `0x1400046a0`

## callees

- `0x140001008`
- `0x1400025fc`
- `0x140003a18`
- `0x140003e54`
- `0x140006b48`
- `0x140007735`
- `0x140007750`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14000410a`
- `ntdll!RtlAllocateHeap` at `0x14000410a`
- `ntdll!swprintf_s` at `0x1400041bd`
- `ntdll!swprintf_s` at `0x1400041bd`
- `ntdll!wcscpy_s` at `0x140003fcb`
- `ntdll!wcscpy_s` at `0x140003fcb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140003fe9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140003fe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000429f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000441d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400045e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000429f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000441d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400045e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400040b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000426e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400043d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400045b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000466b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400040b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000426e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400043d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400045b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000466b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400045d4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400045d4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14000454a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14000454a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140004291`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140004291`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000427e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000427e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140004377`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140004377`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140004413`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140004413`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x140004486`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x140004486`

## pseudocode

```c
__int64 __fastcall InitializeSession(HINSTANCE a1, _QWORD *a2)
{
  unsigned int v3; // esi
  int ModuleFileNameOrPath; // edi
  int v5; // r9d
  int v7; // r9d
  HANDLE EventW; // rax
  signed int LastError; // ebx
  int v10; // r8d
  int v11; // r9d
  wchar_t *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rsi
  SIZE_T v16; // rax
  PVOID ProcessHeap; // rcx
  PVOID Heap; // rdi
  int v19; // r8d
  int v20; // r9d
  int v21; // r8d
  int v22; // r9d
  HANDLE CurrentProcess; // rax
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  void *v27; // rdx
  HANDLE hThread; // rcx
  HANDLE Thread; // rax
  int v30; // [rsp+60h] [rbp-A0h] BYREF
  int v31; // [rsp+64h] [rbp-9Ch] BYREF
  const char *v32; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *Source; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpApplicationName; // [rsp+80h] [rbp-80h] BYREF
  HANDLE TokenHandle; // [rsp+88h] [rbp-78h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-70h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+120h] [rbp+20h] BYREF

  *((_DWORD *)a2 + 4) = (_DWORD)a1;
  lpApplicationName = 0;
  Source = 0;
  hObject = 0;
  v3 = (unsigned int)a1;
  ModuleFileNameOrPath = GetModuleFileNameOrPath(a1, (bool)a2, (unsigned __int16 **)&lpApplicationName);
  if ( ModuleFileNameOrPath < 0 )
  {
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v30 = ModuleFileNameOrPath;
      v32 = "onecore\\xbox\\gameinput\\published\\svc\\session.cpp";
      v31 = 137;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E010,
        (unsigned int)byte_14000B16D,
        qword_14000E018,
        v5,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
LABEL_6:
    if ( lpApplicationName )
      operator delete[]((PVOID)lpApplicationName);
    if ( Source )
      operator delete[](Source);
    if ( hObject )
      CloseHandle(hObject);
    return (unsigned int)ModuleFileNameOrPath;
  }
  ModuleFileNameOrPath = CreateEventName(v3, &Source);
  if ( ModuleFileNameOrPath < 0 )
  {
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v31 = ModuleFileNameOrPath;
      v32 = "onecore\\xbox\\gameinput\\published\\svc\\session.cpp";
      v30 = 140;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E010,
        (unsigned int)&unk_14000B130,
        qword_14000E018,
        v7,
        (__int64)&v32,
        (__int64)&v30,
        (__int64)&v31);
    }
    goto LABEL_6;
  }
  wcscpy_s((wchar_t *)a2 + 10, 0x28u, Source);
  if ( !a2[13] )
  {
    EventW = CreateEventW(0, 1, 0, Source);
    a2[13] = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_14000E000 > 2
        && (qword_14000E010 & 0x800) != 0
        && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v31 = LastError;
        v32 = "onecore\\xbox\\gameinput\\published\\svc\\session.cpp";
        v30 = 146;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14000E018,
          (unsigned int)&unk_14000B0F0,
          v10,
          v11,
          (__int64)&v32,
          (__int64)&v30,
          (__int64)&v31);
      }
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2147418113;
      }
      goto LABEL_28;
    }
  }
  v13 = -1;
  do
    ++v13;
  while ( lpApplicationName[v13] );
  v14 = -1;
  do
    ++v14;
  while ( Source[v14] );
  v15 = v13 + v14 + 4;
  v16 = 2 * v15;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  if ( !is_mul_ok(v15, 2u) )
    v16 = -1;
  Heap = RtlAllocateHeap(ProcessHeap, 0, v16);
  if ( !Heap )
  {
    LastError = -2147024882;
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v31 = -2147024882;
      v32 = "onecore\\xbox\\gameinput\\published\\svc\\session.cpp";
      v30 = 152;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018,
        (unsigned int)&unk_14000B0A0,
        v19,
        v20,
        (__int64)&v32,
        (__int64)&v30,
        (__int64)&v31);
    }
LABEL_28:
    if ( lpApplicationName )
      operator delete[]((PVOID)lpApplicationName);
    v12 = Source;
    if ( !Source )
      goto LABEL_32;
    goto LABEL_31;
  }
  if ( swprintf_s((wchar_t *const)Heap, v15, L"\"%ls\" %ls", lpApplicationName, Source) < 0 )
  {
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v31 = 122;
      v32 = "onecore\\xbox\\gameinput\\published\\svc\\session.cpp";
      v30 = 157;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018,
        (unsigned int)&unk_14000B060,
        v21,
        v22,
        (__int64)&v32,
        (__int64)&v30,
        (__int64)&v31);
    }
    if ( lpApplicationName )
      operator delete[]((PVOID)lpApplicationName);
    if ( Source )
      operator delete[](Source);
    operator delete[](Heap);
    if ( hObject )
      CloseHandle(hObject);
    return 2147942522LL;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x201EBu, &hObject) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 <= 2 )
      goto LABEL_64;
    v26 = qword_14000E018;
    if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
      goto LABEL_64;
    v30 = 168;
    v27 = &unk_14000B020;
LABEL_63:
    v32 = "onecore\\xbox\\gameinput\\published\\svc\\session.cpp";
    v31 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v26,
      (_DWORD)v27,
      v24,
      v25,
      (__int64)&v32,
      (__int64)&v30,
      (__int64)&v31);
LABEL_64:
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2147418113;
    }
    if ( lpApplicationName )
      operator delete[]((PVOID)lpApplicationName);
    if ( Source )
      operator delete[](Source);
    v12 = (wchar_t *)Heap;
LABEL_31:
    operator delete[](v12);
LABEL_32:
    if ( hObject )
      CloseHandle(hObject);
    return (unsigned int)LastError;
  }
  TokenHandle = 0;
  if ( !DuplicateTokenEx(hObject, 0, 0, SecurityImpersonation, TokenPrimary, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 <= 2 )
      goto LABEL_64;
    v26 = qword_14000E018;
    if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
      goto LABEL_64;
    v30 = 172;
    v27 = &unk_14000AFE0;
    goto LABEL_63;
  }
  CloseHandle(hObject);
  hObject = TokenHandle;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 2;
  NewState.Privileges[0].Luid = (LUID)7LL;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 <= 2 )
      goto LABEL_64;
    v26 = qword_14000E018;
    if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
      goto LABEL_64;
    v30 = 186;
    v27 = &unk_14000AFA0;
    goto LABEL_63;
  }
  if ( !SetTokenInformation(hObject, TokenSessionId, a2 + 2, 4u) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 <= 2 )
      goto LABEL_64;
    v26 = qword_14000E018;
    if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
      goto LABEL_64;
    v30 = 190;
    v27 = &unk_14000AF60;
    goto LABEL_63;
  }
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.lpDesktop = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessAsUserW(
          hObject,
          lpApplicationName,
          (LPWSTR)Heap,
          0,
          0,
          0,
          0x1000000u,
          0,
          0,
          &StartupInfo,
          &ProcessInformation) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 <= 2 )
      goto LABEL_64;
    v26 = qword_14000E018;
    if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
      goto LABEL_64;
    v30 = 209;
    v27 = &unk_14000AF20;
    goto LABEL_63;
  }
  hThread = ProcessInformation.hThread;
  a2[15] = ProcessInformation.hProcess;
  CloseHandle(hThread);
  Thread = CreateThread(0, 0, ProcessWaitCallbackWatcher, a2, 0, 0);
  a2[16] = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 <= 2 )
      goto LABEL_64;
    v26 = qword_14000E018;
    if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
      goto LABEL_64;
    v30 = 219;
    v27 = &unk_14000AEE0;
    goto LABEL_63;
  }
  if ( lpApplicationName )
    operator delete[]((PVOID)lpApplicationName);
  if ( Source )
    operator delete[](Source);
  operator delete[](Heap);
  if ( hObject )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x140003e54  mov     [rsp-8+arg_10], rbx
0x140003e59  push    rbp
0x140003e5a  push    rsi
0x140003e5b  push    rdi
0x140003e5c  push    r14
0x140003e5e  push    r15
0x140003e60  lea     rbp, [rsp-40h]
0x140003e65  sub     rsp, 140h
0x140003e6c  mov     rax, cs:__security_cookie
0x140003e73  xor     rax, rsp
0x140003e76  mov     [rbp+60h+var_30], rax
0x140003e7a  xor     r15d, r15d
0x140003e7d  mov     [rdx+10h], ecx
0x140003e80  lea     r8, [rbp+60h+lpApplicationName]; unsigned __int16 **
0x140003e84  mov     [rbp+60h+lpApplicationName], r15
0x140003e88  mov     [rsp+160h+Source], r15
0x140003e8d  mov     rbx, rdx
0x140003e90  mov     [rsp+160h+hObject], r15
0x140003e95  mov     esi, ecx
0x140003e97  call    ?GetModuleFileNameOrPath@@YAJPEAUHINSTANCE__@@_NPEAPEAG@Z; GetModuleFileNameOrPath(HINSTANCE__ *,bool,ushort * *)
0x140003e9c  mov     edi, eax
0x140003e9e  test    eax, eax
0x140003ea0  jns     loc_140003F4A
0x140003ea6  mov     ecx, cs:dword_14000E000
0x140003eac  cmp     ecx, 2
0x140003eaf  jbe     short loc_140003F16
0x140003eb1  mov     r8, cs:qword_14000E018
0x140003eb8  mov     edx, 800h
0x140003ebd  mov     rcx, cs:qword_14000E010
0x140003ec4  test    rdx, rcx
0x140003ec7  jz      short loc_140003F16
0x140003ec9  mov     rax, r8
0x140003ecc  and     rax, rdx
0x140003ecf  cmp     rax, r8
0x140003ed2  jnz     short loc_140003F16
0x140003ed4  lea     rax, aOnecoreXboxGam_3; "onecore\\xbox\\gameinput\\published\\sv"...
0x140003edb  mov     [rsp+160h+var_100], edi
0x140003edf  mov     [rsp+160h+var_F8], rax
0x140003ee4  lea     rdx, byte_14000B16D
0x140003eeb  lea     rax, [rsp+160h+var_100]
0x140003ef0  mov     [rsp+160h+var_FC], 89h
0x140003ef8  mov     qword ptr [rsp+160h+dwCreationFlags], rax
0x140003efd  lea     rax, [rsp+160h+var_FC]
0x140003f02  mov     [rsp+160h+phNewToken], rax
0x140003f07  lea     rax, [rsp+160h+var_F8]
0x140003f0c  mov     qword ptr [rsp+160h+TokenType], rax
0x140003f11  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140003f16  mov     rcx, [rbp+60h+lpApplicationName]; P
0x140003f1a  test    rcx, rcx
0x140003f1d  jz      short loc_140003F24
0x140003f1f  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140003f24  mov     rcx, [rsp+160h+Source]; P
0x140003f29  test    rcx, rcx
0x140003f2c  jz      short loc_140003F33
0x140003f2e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140003f33  mov     rcx, [rsp+160h+hObject]; hObject
0x140003f38  test    rcx, rcx
0x140003f3b  jz      short loc_140003F43
0x140003f3d  call    cs:__imp_CloseHandle
0x140003f43  mov     eax, edi
0x140003f45  jmp     loc_140004673
0x140003f4a  lea     rdx, [rsp+160h+Source]
0x140003f4f  mov     ecx, esi
0x140003f51  call    CreateEventName
0x140003f56  mov     edi, eax
0x140003f58  test    eax, eax
0x140003f5a  jns     short loc_140003FBD
0x140003f5c  mov     ecx, cs:dword_14000E000
0x140003f62  cmp     ecx, 2
0x140003f65  jbe     short loc_140003F16
0x140003f67  mov     r8, cs:qword_14000E018
0x140003f6e  mov     edx, 800h
0x140003f73  mov     rcx, cs:qword_14000E010
0x140003f7a  test    rdx, rcx
0x140003f7d  jz      short loc_140003F16
0x140003f7f  mov     rax, r8
0x140003f82  and     rax, rdx
0x140003f85  cmp     rax, r8
0x140003f88  jnz     short loc_140003F16
0x140003f8a  lea     rax, aOnecoreXboxGam_3; "onecore\\xbox\\gameinput\\published\\sv"...
0x140003f91  mov     [rsp+160h+var_FC], edi
0x140003f95  mov     [rsp+160h+var_F8], rax
0x140003f9a  lea     rdx, unk_14000B130
0x140003fa1  lea     rax, [rsp+160h+var_FC]
0x140003fa6  mov     [rsp+160h+var_100], 8Ch
0x140003fae  mov     qword ptr [rsp+160h+dwCreationFlags], rax
0x140003fb3  lea     rax, [rsp+160h+var_100]
0x140003fb8  jmp     loc_140003F02
0x140003fbd  mov     r8, [rsp+160h+Source]; Source
0x140003fc2  lea     rcx, [rbx+14h]; Destination
0x140003fc6  mov     edx, 28h ; '('; SizeInWords
0x140003fcb  call    cs:__imp_wcscpy_s
0x140003fd1  cmp     [rbx+68h], r15
0x140003fd5  jnz     loc_1400040BE
0x140003fdb  mov     r9, [rsp+160h+Source]; lpName
0x140003fe0  xor     r8d, r8d; bInitialState
0x140003fe3  xor     ecx, ecx; lpEventAttributes
0x140003fe5  lea     edx, [r8+1]; bManualReset
0x140003fe9  call    cs:__imp_CreateEventW
0x140003fef  mov     [rbx+68h], rax
0x140003ff3  test    rax, rax
0x140003ff6  jnz     loc_1400040BE
0x140003ffc  call    cs:__imp_GetLastError
0x140004002  mov     ebx, eax
0x140004004  mov     eax, cs:dword_14000E000
0x14000400a  cmp     eax, 2
0x14000400d  jbe     short loc_140004074
0x14000400f  mov     rcx, cs:qword_14000E018
0x140004016  mov     edx, 800h
0x14000401b  mov     rax, cs:qword_14000E010
0x140004022  test    rdx, rax
0x140004025  jz      short loc_140004074
0x140004027  mov     rax, rcx
0x14000402a  and     rax, rdx
0x14000402d  cmp     rax, rcx
0x140004030  jnz     short loc_140004074
0x140004032  lea     rax, aOnecoreXboxGam_3; "onecore\\xbox\\gameinput\\published\\sv"...
0x140004039  mov     [rsp+160h+var_FC], ebx
0x14000403d  mov     [rsp+160h+var_F8], rax
0x140004042  lea     rdx, unk_14000B0F0
0x140004049  lea     rax, [rsp+160h+var_FC]
0x14000404e  mov     [rsp+160h+var_100], 92h
0x140004056  mov     qword ptr [rsp+160h+dwCreationFlags], rax
0x14000405b  lea     rax, [rsp+160h+var_100]
0x140004060  mov     [rsp+160h+phNewToken], rax
0x140004065  lea     rax, [rsp+160h+var_F8]
0x14000406a  mov     qword ptr [rsp+160h+TokenType], rax
0x14000406f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140004074  test    ebx, ebx
0x140004076  jnz     short loc_14000407F
0x140004078  mov     ebx, 8000FFFFh
0x14000407d  jmp     short loc_14000408A
0x14000407f  jle     short loc_14000408A
0x140004081  movzx   ebx, bx
0x140004084  or      ebx, 80070000h
0x14000408a  mov     rcx, [rbp+60h+lpApplicationName]; P
0x14000408e  test    rcx, rcx
0x140004091  jz      short loc_140004098
0x140004093  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140004098  mov     rcx, [rsp+160h+Source]; P
0x14000409d  test    rcx, rcx
0x1400040a0  jz      short loc_1400040A7
0x1400040a2  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1400040a7  mov     rcx, [rsp+160h+hObject]; hObject
0x1400040ac  test    rcx, rcx
0x1400040af  jz      short loc_1400040B7
0x1400040b1  call    cs:__imp_CloseHandle
0x1400040b7  mov     eax, ebx
0x1400040b9  jmp     loc_140004673
0x1400040be  mov     rcx, [rbp+60h+lpApplicationName]
0x1400040c2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400040c6  mov     rax, r8
0x1400040c9  inc     rax
0x1400040cc  cmp     [rcx+rax*2], r15w
0x1400040d1  jnz     short loc_1400040C9
0x1400040d3  mov     rdx, [rsp+160h+Source]
0x1400040d8  mov     rcx, r8
0x1400040db  inc     rcx
0x1400040de  cmp     [rdx+rcx*2], r15w
0x1400040e3  jnz     short loc_1400040DB
0x1400040e5  lea     rsi, [rcx+4]
0x1400040e9  mov     rcx, gs:60h
0x1400040f2  add     rsi, rax
0x1400040f5  mov     eax, 2
0x1400040fa  mul     rsi
0x1400040fd  mov     rcx, [rcx+30h]; HeapHandle
0x140004101  cmovb   rax, r8
0x140004105  xor     edx, edx; Flags
0x140004107  mov     r8, rax; Size
0x14000410a  call    cs:__imp_RtlAllocateHeap
0x140004110  mov     rdi, rax
0x140004113  test    rax, rax
0x140004116  jnz     loc_1400041A2
0x14000411c  mov     eax, cs:dword_14000E000
0x140004122  mov     ebx, 8007000Eh
0x140004127  cmp     eax, 2
0x14000412a  jbe     loc_14000408A
0x140004130  mov     rcx, cs:qword_14000E018
0x140004137  mov     edx, 800h
0x14000413c  mov     rax, cs:qword_14000E010
0x140004143  test    rdx, rax
0x140004146  jz      loc_14000408A
0x14000414c  mov     rax, rcx
0x14000414f  and     rax, rdx
0x140004152  cmp     rax, rcx
0x140004155  jnz     loc_14000408A
0x14000415b  lea     rax, aOnecoreXboxGam_3; "onecore\\xbox\\gameinput\\published\\sv"...
0x140004162  mov     [rsp+160h+var_FC], ebx
0x140004166  mov     [rsp+160h+var_F8], rax
0x14000416b  lea     rdx, unk_14000B0A0
0x140004172  lea     rax, [rsp+160h+var_FC]
0x140004177  mov     [rsp+160h+var_100], 98h
0x14000417f  mov     qword ptr [rsp+160h+dwCreationFlags], rax
0x140004184  lea     rax, [rsp+160h+var_100]
0x140004189  mov     [rsp+160h+phNewToken], rax
0x14000418e  lea     rax, [rsp+160h+var_F8]
0x140004193  mov     qword ptr [rsp+160h+TokenType], rax
0x140004198  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000419d  jmp     loc_14000408A
0x1400041a2  mov     rax, [rsp+160h+Source]
0x1400041a7  lea     r8, aLsLs; "\"%ls\" %ls"
0x1400041ae  mov     r9, [rbp+60h+lpApplicationName]
0x1400041b2  mov     rdx, rsi; BufferCount
0x1400041b5  mov     rcx, rdi; Buffer
0x1400041b8  mov     qword ptr [rsp+160h+TokenType], rax
0x1400041bd  call    cs:__imp_swprintf_s
0x1400041c3  test    eax, eax
0x1400041c5  jns     loc_14000427E
0x1400041cb  mov     eax, cs:dword_14000E000
0x1400041d1  cmp     eax, 2
0x1400041d4  jbe     short loc_14000423F
0x1400041d6  mov     rcx, cs:qword_14000E018
0x1400041dd  mov     edx, 800h
0x1400041e2  mov     rax, cs:qword_14000E010
0x1400041e9  test    rdx, rax
0x1400041ec  jz      short loc_14000423F
0x1400041ee  mov     rax, rcx
0x1400041f1  and     rax, rdx
0x1400041f4  cmp     rax, rcx
0x1400041f7  jnz     short loc_14000423F
0x1400041f9  lea     rax, aOnecoreXboxGam_3; "onecore\\xbox\\gameinput\\published\\sv"...
0x140004200  mov     [rsp+160h+var_FC], 7Ah ; 'z'
0x140004208  mov     [rsp+160h+var_F8], rax
0x14000420d  lea     rdx, unk_14000B060
0x140004214  lea     rax, [rsp+160h+var_FC]
0x140004219  mov     [rsp+160h+var_100], 9Dh
0x140004221  mov     qword ptr [rsp+160h+dwCreationFlags], rax
0x140004226  lea     rax, [rsp+160h+var_100]
0x14000422b  mov     [rsp+160h+phNewToken], rax
0x140004230  lea     rax, [rsp+160h+var_F8]
0x140004235  mov     qword ptr [rsp+160h+TokenType], rax
0x14000423a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000423f  mov     rcx, [rbp+60h+lpApplicationName]; P
0x140004243  test    rcx, rcx
0x140004246  jz      short loc_14000424D
0x140004248  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x14000424d  mov     rcx, [rsp+160h+Source]; P
0x140004252  test    rcx, rcx
0x140004255  jz      short loc_14000425C
0x140004257  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x14000425c  mov     rcx, rdi; P
0x14000425f  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140004264  mov     rcx, [rsp+160h+hObject]; hObject
0x140004269  test    rcx, rcx
0x14000426c  jz      short loc_140004274
0x14000426e  call    cs:__imp_CloseHandle
0x140004274  mov     eax, 8007007Ah
0x140004279  jmp     loc_140004673
0x14000427e  call    cs:__imp_GetCurrentProcess
0x140004284  lea     r8, [rsp+160h+hObject]; TokenHandle
0x140004289  mov     edx, 201EBh; DesiredAccess
0x14000428e  mov     rcx, rax; ProcessHandle
0x140004291  call    cs:__imp_OpenProcessToken
0x140004297  test    eax, eax
0x140004299  jnz     loc_140004352
0x14000429f  call    cs:__imp_GetLastError
0x1400042a5  mov     ebx, eax
0x1400042a7  mov     eax, cs:dword_14000E000
0x1400042ad  cmp     eax, 2
0x1400042b0  jbe     short loc_140004317
0x1400042b2  mov     rcx, cs:qword_14000E018
0x1400042b9  mov     edx, 800h
0x1400042be  mov     rax, cs:qword_14000E010
0x1400042c5  test    rdx, rax
0x1400042c8  jz      short loc_140004317
0x1400042ca  mov     rax, rcx
0x1400042cd  and     rax, rdx
0x1400042d0  cmp     rax, rcx
0x1400042d3  jnz     short loc_140004317
0x1400042d5  mov     [rsp+160h+var_100], 0A8h
0x1400042dd  lea     rdx, unk_14000B020
0x1400042e4  lea     rax, aOnecoreXboxGam_3; "onecore\\xbox\\gameinput\\published\\sv"...
0x1400042eb  mov     [rsp+160h+var_F8], rax
0x1400042f0  lea     rax, [rsp+160h+var_FC]
0x1400042f5  mov     qword ptr [rsp+160h+dwCreationFlags], rax
0x1400042fa  lea     rax, [rsp+160h+var_100]
0x1400042ff  mov     [rsp+160h+phNewToken], rax
0x140004304  lea     rax, [rsp+160h+var_F8]
0x140004309  mov     qword ptr [rsp+160h+TokenType], rax
0x14000430e  mov     [rsp+160h+var_FC], ebx
0x140004312  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140004317  test    ebx, ebx
0x140004319  jnz     short loc_140004322
0x14000431b  mov     ebx, 8000FFFFh
0x140004320  jmp     short loc_14000432D
0x140004322  jle     short loc_14000432D
0x140004324  movzx   ebx, bx
0x140004327  or      ebx, 80070000h
0x14000432d  mov     rcx, [rbp+60h+lpApplicationName]; P
0x140004331  test    rcx, rcx
0x140004334  jz      short loc_14000433B
0x140004336  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x14000433b  mov     rcx, [rsp+160h+Source]; P
0x140004340  test    rcx, rcx
0x140004343  jz      short loc_14000434A
0x140004345  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x14000434a  mov     rcx, rdi
0x14000434d  jmp     loc_1400040A2
0x140004352  mov     rcx, [rsp+160h+hObject]; hExistingToken
0x140004357  lea     rax, [rbp+60h+TokenHandle]
  ... truncated ...
```
