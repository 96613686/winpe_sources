# SuInitialize(void)

- ea: `0x18019c8ac`
- end: `0x18019cb6e`
- name: `?SuInitialize@@YAHXZ`
- size: `706`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180198204`

## callees

- `0x18019c8ac`
- `0x18019cc88`
- `0x18019ccc8`
- `0x18019cd60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18019c9b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18019c9b1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18019c979`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18019cb48`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18019c979`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18019cb48`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18019c940`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18019c940`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18019cadc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18019cadc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18019c9bf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18019c9bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18019ca03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18019ca03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18019c9eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18019c9eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019caf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019caf8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c987`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18019c8c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18019c8c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019caab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019caab`

## string_xrefs

- `0x18019cac4`: `CreateFile`
- `0x18019c9d7`: `CreateThreadpool`
- `0x18019ca1c`: `SetThreadpoolThreadMinimum`

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
      (unsigned int)&InitializeApiFailed,
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
0x18019c8ac  mov     rax, rsp
0x18019c8af  mov     [rax+18h], rbx
0x18019c8b3  mov     [rax+20h], rbp
0x18019c8b7  push    rsi
0x18019c8b8  push    r14
0x18019c8ba  push    r15
0x18019c8bc  sub     rsp, 60h
0x18019c8c0  mov     qword ptr [rax+8], 0
0x18019c8c8  call    cs:__imp_GetCurrentThreadId
0x18019c8cf  nop     dword ptr [rax+rax+00h]
0x18019c8d4  mov     ecx, eax
0x18019c8d6  jmp     short loc_18019C8E6
0x18019c8d8  pause
0x18019c8da  mov     rax, cs:?Lock@@3PEAXEA; void * Lock
0x18019c8e1  test    rax, rax
0x18019c8e4  jnz     short loc_18019C8D8
0x18019c8e6  xor     eax, eax
0x18019c8e8  lock cmpxchg cs:?Lock@@3PEAXEA, rcx; void * Lock
0x18019c8f1  jnz     short loc_18019C8D8
0x18019c8f3  mov     eax, cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x18019c8f9  test    eax, eax
0x18019c8fb  jz      short loc_18019C90F
0x18019c8fd  mov     ebx, 1
0x18019c902  inc     eax
0x18019c904  mov     cs:?ReferenceCount@@3KA, eax; ulong ReferenceCount
0x18019c90a  jmp     loc_18019CB32
0x18019c90f  call    McGenEventRegister_EventRegister
0x18019c914  lea     rax, [rsp+78h+hModule]
0x18019c91c  mov     [rsp+78h+var_38], rax
0x18019c921  mov     [rsp+78h+phModule], 0
0x18019c92a  mov     [rsp+78h+var_28], 1
0x18019c92f  lea     r8, [rsp+78h+phModule]; phModule
0x18019c934  lea     rdx, ?Spaceport@@3PEAXEA; lpModuleName
0x18019c93b  mov     ecx, 4; dwFlags
0x18019c940  call    cs:__imp_GetModuleHandleExW
0x18019c947  nop     dword ptr [rax+rax+00h]
0x18019c94c  mov     r15d, eax
0x18019c94f  cmp     [rsp+78h+var_28], 0
0x18019c954  jz      short loc_18019C997
0x18019c956  mov     r14, [rsp+78h+phModule]
0x18019c95b  mov     rsi, [rsp+78h+var_38]
0x18019c960  mov     rbp, [rsi]
0x18019c963  test    rbp, rbp
0x18019c966  jz      short loc_18019C994
0x18019c968  call    cs:__imp_GetLastError
0x18019c96f  nop     dword ptr [rax+rax+00h]
0x18019c974  mov     ebx, eax
0x18019c976  mov     rcx, rbp; hLibModule
0x18019c979  call    cs:__imp_FreeLibrary
0x18019c980  nop     dword ptr [rax+rax+00h]
0x18019c985  mov     ecx, ebx; dwErrCode
0x18019c987  call    cs:__imp_SetLastError
0x18019c98e  nop     dword ptr [rax+rax+00h]
0x18019c993  nop
0x18019c994  mov     [rsi], r14
0x18019c997  test    r15d, r15d
0x18019c99a  jz      short loc_18019C9BD
0x18019c99c  mov     r8d, 104h; nSize
0x18019c9a2  lea     rdx, ?ModuleName@@3PAGA; lpFilename
0x18019c9a9  mov     rcx, [rsp+78h+hModule]; hModule
0x18019c9b1  call    cs:__imp_GetModuleFileNameW
0x18019c9b8  nop     dword ptr [rax+rax+00h]
0x18019c9bd  xor     ecx, ecx; reserved
0x18019c9bf  call    cs:__imp_CreateThreadpool
0x18019c9c6  nop     dword ptr [rax+rax+00h]
0x18019c9cb  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * Threadpool
0x18019c9d2  test    rax, rax
0x18019c9d5  jnz     short loc_18019C9E3
0x18019c9d7  lea     rsi, aCreatethreadpo; "CreateThreadpool"
0x18019c9de  jmp     loc_18019CAD2
0x18019c9e3  mov     edx, 80h; cthrdMost
0x18019c9e8  mov     rcx, rax; ptpp
0x18019c9eb  call    cs:__imp_SetThreadpoolThreadMaximum
0x18019c9f2  nop     dword ptr [rax+rax+00h]
0x18019c9f7  mov     edx, 1; cthrdMic
0x18019c9fc  mov     rcx, cs:?Threadpool@@3PEAU_TP_POOL@@EA; ptpp
0x18019ca03  call    cs:__imp_SetThreadpoolThreadMinimum
0x18019ca0a  nop     dword ptr [rax+rax+00h]
0x18019ca0f  mov     ebx, eax
0x18019ca11  test    eax, eax
0x18019ca13  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x18019ca1a  jnz     short loc_18019CA28
0x18019ca1c  lea     rsi, aSetthreadpoolt; "SetThreadpoolThreadMinimum"
0x18019ca23  jmp     loc_18019CAD2
0x18019ca28  mov     r8d, 3; dwShareMode
0x18019ca2e  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, r8d; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019ca35  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019ca40  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019ca4b  xorps   xmm0, xmm0
0x18019ca4e  movdqa  xmmword ptr cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019ca56  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019ca61  mov     dword ptr cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019ca6b  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019ca75  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019ca7f  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x18019ca86  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18019ca8f  mov     [rsp+78h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18019ca97  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18019ca9c  xor     r9d, r9d; lpSecurityAttributes
0x18019ca9f  mov     edx, 0C0000000h; dwDesiredAccess
0x18019caa4  lea     rcx, FileName; "\\\\.\\Spaceport"
0x18019caab  call    cs:__imp_CreateFileW
0x18019cab2  nop     dword ptr [rax+rax+00h]
0x18019cab7  mov     cs:?Spaceport@@3PEAXEA, rax; void * Spaceport
0x18019cabe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18019cac2  jnz     short loc_18019CB2C
0x18019cac4  lea     rsi, aCreatefile; "CreateFile"
0x18019cacb  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x18019cad2  xor     ebx, ebx
0x18019cad4  test    rax, rax
0x18019cad7  jz      short loc_18019CAEF
0x18019cad9  mov     rcx, rax; ptpp
0x18019cadc  call    cs:__imp_CloseThreadpool
0x18019cae3  nop     dword ptr [rax+rax+00h]
0x18019cae8  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rbx; _TP_POOL * Threadpool
0x18019caef  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x18019caf6  jz      short loc_18019CB25
0x18019caf8  call    cs:__imp_GetLastError
0x18019caff  nop     dword ptr [rax+rax+00h]
0x18019cb04  mov     dword ptr [rsp+78h+hTemplateFile], eax
0x18019cb08  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rsi
0x18019cb0d  lea     rax, aSuinitialize; "SuInitialize"
0x18019cb14  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x18019cb19  lea     rdx, InitializeApiFailed
0x18019cb20  call    McTemplateK0zssq_EventWriteTransfer
0x18019cb25  call    McGenEventUnregister_EventUnregister
0x18019cb2a  jmp     short loc_18019CB32
0x18019cb2c  inc     cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x18019cb32  xor     ecx, ecx
0x18019cb34  xchg    rcx, cs:?Lock@@3PEAXEA; void * Lock
0x18019cb3b  mov     rcx, [rsp+78h+hModule]; hLibModule
0x18019cb43  test    rcx, rcx
0x18019cb46  jz      short loc_18019CB55
0x18019cb48  call    cs:__imp_FreeLibrary
0x18019cb4f  nop     dword ptr [rax+rax+00h]
0x18019cb54  nop
0x18019cb55  mov     eax, ebx
0x18019cb57  lea     r11, [rsp+78h+var_18]
0x18019cb5c  mov     rbx, [r11+30h]
0x18019cb60  mov     rbp, [r11+38h]
0x18019cb64  mov     rsp, r11
0x18019cb67  pop     r15
0x18019cb69  pop     r14
0x18019cb6b  pop     rsi
0x18019cb6c  retn
```
