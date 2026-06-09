# SuInitialize(void)

- ea: `0x18019c73c`
- end: `0x18019c9fe`
- name: `?SuInitialize@@YAHXZ`
- size: `706`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180198094`

## callees

- `0x18019c73c`
- `0x18019cb18`
- `0x18019cb58`
- `0x18019cbf0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18019c841`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18019c841`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18019c809`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18019c9d8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18019c809`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18019c9d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18019c7d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18019c7d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18019c96c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18019c96c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18019c84f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18019c84f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18019c893`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18019c893`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18019c87b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18019c87b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c7f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c7f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c988`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c817`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18019c758`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18019c758`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019c93b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019c93b`

## string_xrefs

- `0x18019c954`: `CreateFile`
- `0x18019c8ac`: `SetThreadpoolThreadMinimum`
- `0x18019c867`: `CreateThreadpool`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 SuInitialize(void)
{
  signed __int64 CurrentThreadId; // rcx
  unsigned int v1; // ebx
  BOOL ModuleHandle; // r15d
  struct _TP_POOL *Threadpool; // rax
  const char *v4; // rsi
  char LastError; // al
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  HMODULE phModule; // [rsp+48h] [rbp-30h] BYREF
  char v11; // [rsp+50h] [rbp-28h]
  HMODULE hModule; // [rsp+80h] [rbp+8h]

  hModule = 0;
  CurrentThreadId = GetCurrentThreadId();
  while ( _InterlockedCompareExchange64((volatile signed __int64 *)&Lock, CurrentThreadId, 0) )
  {
    do
      _mm_pause();
    while ( Lock );
  }
  if ( ReferenceCount )
  {
    v1 = 1;
    ++ReferenceCount;
    goto LABEL_22;
  }
  McGenEventRegister_EventRegister();
  phModule = 0;
  v11 = 1;
  ModuleHandle = GetModuleHandleExW(4u, (LPCWSTR)&Spaceport, &phModule);
  if ( v11 )
    hModule = phModule;
  if ( ModuleHandle )
    GetModuleFileNameW(hModule, &ModuleName, 0x104u);
  Threadpool = CreateThreadpool(0);
  ::Threadpool = Threadpool;
  if ( Threadpool )
  {
    SetThreadpoolThreadMaximum(Threadpool, 0x80u);
    v1 = SetThreadpoolThreadMinimum(::Threadpool, 1u);
    Threadpool = ::Threadpool;
    if ( v1 )
    {
      ThreadpoolEnv.Version = 3;
      ThreadpoolEnv.CleanupGroup = 0;
      ThreadpoolEnv.CleanupGroupCancelCallback = 0;
      *(_OWORD *)&ThreadpoolEnv.RaceDll = 0;
      ThreadpoolEnv.FinalizationCallback = 0;
      ThreadpoolEnv.u.Flags = 0;
      ThreadpoolEnv.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
      ThreadpoolEnv.Size = 72;
      ThreadpoolEnv.Pool = ::Threadpool;
      Spaceport = CreateFileW(L"\\\\.\\Spaceport", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
      if ( Spaceport != (HANDLE)-1LL )
      {
        ++ReferenceCount;
        goto LABEL_22;
      }
      v4 = "CreateFile";
      Threadpool = ::Threadpool;
    }
    else
    {
      v4 = "SetThreadpoolThreadMinimum";
    }
  }
  else
  {
    v4 = "CreateThreadpool";
  }
  v1 = 0;
  if ( Threadpool )
  {
    CloseThreadpool(Threadpool);
    ::Threadpool = 0;
  }
  if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    LastError = GetLastError();
    McTemplateK0zssq_EventWriteTransfer(
      v6,
      (unsigned int)InitializeApiFailed,
      v7,
      v8,
      (__int64)"SuInitialize",
      (__int64)v4,
      LastError);
  }
  McGenEventUnregister_EventUnregister();
LABEL_22:
  _InterlockedExchange64((volatile __int64 *)&Lock, 0);
  if ( hModule )
    FreeLibrary(hModule);
  return v1;
}

```

## disassembly

```asm
0x18019c73c  mov     rax, rsp
0x18019c73f  mov     [rax+18h], rbx
0x18019c743  mov     [rax+20h], rbp
0x18019c747  push    rsi
0x18019c748  push    r14
0x18019c74a  push    r15
0x18019c74c  sub     rsp, 60h
0x18019c750  mov     qword ptr [rax+8], 0
0x18019c758  call    cs:__imp_GetCurrentThreadId
0x18019c75f  nop     dword ptr [rax+rax+00h]
0x18019c764  mov     ecx, eax
0x18019c766  jmp     short loc_18019C776
0x18019c768  pause
0x18019c76a  mov     rax, cs:?Lock@@3PEAXEA; void * Lock
0x18019c771  test    rax, rax
0x18019c774  jnz     short loc_18019C768
0x18019c776  xor     eax, eax
0x18019c778  lock cmpxchg cs:?Lock@@3PEAXEA, rcx; void * Lock
0x18019c781  jnz     short loc_18019C768
0x18019c783  mov     eax, cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x18019c789  test    eax, eax
0x18019c78b  jz      short loc_18019C79F
0x18019c78d  mov     ebx, 1
0x18019c792  inc     eax
0x18019c794  mov     cs:?ReferenceCount@@3KA, eax; ulong ReferenceCount
0x18019c79a  jmp     loc_18019C9C2
0x18019c79f  call    McGenEventRegister_EventRegister
0x18019c7a4  lea     rax, [rsp+78h+hModule]
0x18019c7ac  mov     [rsp+78h+var_38], rax
0x18019c7b1  mov     [rsp+78h+phModule], 0
0x18019c7ba  mov     [rsp+78h+var_28], 1
0x18019c7bf  lea     r8, [rsp+78h+phModule]; phModule
0x18019c7c4  lea     rdx, ?Spaceport@@3PEAXEA; lpModuleName
0x18019c7cb  mov     ecx, 4; dwFlags
0x18019c7d0  call    cs:__imp_GetModuleHandleExW
0x18019c7d7  nop     dword ptr [rax+rax+00h]
0x18019c7dc  mov     r15d, eax
0x18019c7df  cmp     [rsp+78h+var_28], 0
0x18019c7e4  jz      short loc_18019C827
0x18019c7e6  mov     r14, [rsp+78h+phModule]
0x18019c7eb  mov     rsi, [rsp+78h+var_38]
0x18019c7f0  mov     rbp, [rsi]
0x18019c7f3  test    rbp, rbp
0x18019c7f6  jz      short loc_18019C824
0x18019c7f8  call    cs:__imp_GetLastError
0x18019c7ff  nop     dword ptr [rax+rax+00h]
0x18019c804  mov     ebx, eax
0x18019c806  mov     rcx, rbp; hLibModule
0x18019c809  call    cs:__imp_FreeLibrary
0x18019c810  nop     dword ptr [rax+rax+00h]
0x18019c815  mov     ecx, ebx; dwErrCode
0x18019c817  call    cs:__imp_SetLastError
0x18019c81e  nop     dword ptr [rax+rax+00h]
0x18019c823  nop
0x18019c824  mov     [rsi], r14
0x18019c827  test    r15d, r15d
0x18019c82a  jz      short loc_18019C84D
0x18019c82c  mov     r8d, 104h; nSize
0x18019c832  lea     rdx, ?ModuleName@@3PAGA; lpFilename
0x18019c839  mov     rcx, [rsp+78h+hModule]; hModule
0x18019c841  call    cs:__imp_GetModuleFileNameW
0x18019c848  nop     dword ptr [rax+rax+00h]
0x18019c84d  xor     ecx, ecx; reserved
0x18019c84f  call    cs:__imp_CreateThreadpool
0x18019c856  nop     dword ptr [rax+rax+00h]
0x18019c85b  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * Threadpool
0x18019c862  test    rax, rax
0x18019c865  jnz     short loc_18019C873
0x18019c867  lea     rsi, aCreatethreadpo; "CreateThreadpool"
0x18019c86e  jmp     loc_18019C962
0x18019c873  mov     edx, 80h; cthrdMost
0x18019c878  mov     rcx, rax; ptpp
0x18019c87b  call    cs:__imp_SetThreadpoolThreadMaximum
0x18019c882  nop     dword ptr [rax+rax+00h]
0x18019c887  mov     edx, 1; cthrdMic
0x18019c88c  mov     rcx, cs:?Threadpool@@3PEAU_TP_POOL@@EA; ptpp
0x18019c893  call    cs:__imp_SetThreadpoolThreadMinimum
0x18019c89a  nop     dword ptr [rax+rax+00h]
0x18019c89f  mov     ebx, eax
0x18019c8a1  test    eax, eax
0x18019c8a3  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x18019c8aa  jnz     short loc_18019C8B8
0x18019c8ac  lea     rsi, aSetthreadpoolt; "SetThreadpoolThreadMinimum"
0x18019c8b3  jmp     loc_18019C962
0x18019c8b8  mov     r8d, 3; dwShareMode
0x18019c8be  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, r8d; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019c8c5  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019c8d0  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019c8db  xorps   xmm0, xmm0
0x18019c8de  movdqa  xmmword ptr cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019c8e6  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019c8f1  mov     dword ptr cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019c8fb  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019c905  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019c90f  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019c916  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18019c91f  mov     [rsp+78h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18019c927  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18019c92c  xor     r9d, r9d; lpSecurityAttributes
0x18019c92f  mov     edx, 0C0000000h; dwDesiredAccess
0x18019c934  lea     rcx, FileName; "\\\\.\\Spaceport"
0x18019c93b  call    cs:__imp_CreateFileW
0x18019c942  nop     dword ptr [rax+rax+00h]
0x18019c947  mov     cs:?Spaceport@@3PEAXEA, rax; void * Spaceport
0x18019c94e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18019c952  jnz     short loc_18019C9BC
0x18019c954  lea     rsi, aCreatefile; "CreateFile"
0x18019c95b  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x18019c962  xor     ebx, ebx
0x18019c964  test    rax, rax
0x18019c967  jz      short loc_18019C97F
0x18019c969  mov     rcx, rax; ptpp
0x18019c96c  call    cs:__imp_CloseThreadpool
0x18019c973  nop     dword ptr [rax+rax+00h]
0x18019c978  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rbx; _TP_POOL * Threadpool
0x18019c97f  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x18019c986  jz      short loc_18019C9B5
0x18019c988  call    cs:__imp_GetLastError
0x18019c98f  nop     dword ptr [rax+rax+00h]
0x18019c994  mov     dword ptr [rsp+78h+hTemplateFile], eax
0x18019c998  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rsi
0x18019c99d  lea     rax, aSuinitialize; "SuInitialize"
0x18019c9a4  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x18019c9a9  lea     rdx, InitializeApiFailed
0x18019c9b0  call    McTemplateK0zssq_EventWriteTransfer
0x18019c9b5  call    McGenEventUnregister_EventUnregister
0x18019c9ba  jmp     short loc_18019C9C2
0x18019c9bc  inc     cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x18019c9c2  xor     ecx, ecx
0x18019c9c4  xchg    rcx, cs:?Lock@@3PEAXEA; void * Lock
0x18019c9cb  mov     rcx, [rsp+78h+hModule]; hLibModule
0x18019c9d3  test    rcx, rcx
0x18019c9d6  jz      short loc_18019C9E5
0x18019c9d8  call    cs:__imp_FreeLibrary
0x18019c9df  nop     dword ptr [rax+rax+00h]
0x18019c9e4  nop
0x18019c9e5  mov     eax, ebx
0x18019c9e7  lea     r11, [rsp+78h+var_18]
0x18019c9ec  mov     rbx, [r11+30h]
0x18019c9f0  mov     rbp, [r11+38h]
0x18019c9f4  mov     rsp, r11
0x18019c9f7  pop     r15
0x18019c9f9  pop     r14
0x18019c9fb  pop     rsi
0x18019c9fc  retn
```
