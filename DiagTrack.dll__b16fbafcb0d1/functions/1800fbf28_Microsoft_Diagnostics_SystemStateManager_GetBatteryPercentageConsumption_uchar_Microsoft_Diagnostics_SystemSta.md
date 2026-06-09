# Microsoft::Diagnostics::SystemStateManager::GetBatteryPercentageConsumption(uchar &,Microsoft::Diagnostics::SystemStateManager::BatteryInfo const &)

- ea: `0x1800fbf28`
- end: `0x1800fc2a5`
- name: `?GetBatteryPercentageConsumption@SystemStateManager@Diagnostics@Microsoft@@CA_NAEAEAEBUBatteryInfo@123@@Z`
- size: `893`
- prototype: `bool __fastcall(unsigned __int8 *, const struct Microsoft::Diagnostics::SystemStateManager::BatteryInfo *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1801f5288`
- `0x18025e4dc`

## callees

- `0x18002b318`
- `0x1800e65d4`
- `0x1800fbf28`
- `0x1800fc2ac`
- `0x1801b2084`
- `0x1801d1b14`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800fc14a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800fc14a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800fbf8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800fbfaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800fbf8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800fbfaa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800fc0e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800fc1b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800fc0e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800fc1b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fbffe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fbffe`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800fc17d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800fc17d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800fc285`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800fc285`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800fbff4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800fbff4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800fbfd7`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800fbfd7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800fbf6a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800fbf6a`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1800fc01b`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1800fc01b`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800fc05d`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800fc05d`

## string_xrefs

- `0x1800fc165`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`
- `0x1800fc1d6`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`
- `0x1800fc209`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`
- `0x1800fc23b`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`
- `0x1800fc24d`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`
- `0x1800fbf63`: `srumapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall Microsoft::Diagnostics::SystemStateManager::GetBatteryPercentageConsumption(
        unsigned __int8 *a1,
        const struct Microsoft::Diagnostics::SystemStateManager::BatteryInfo *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rsi
  const char *v6; // r9
  void (*v7)(void); // rdi
  const char *v8; // r9
  const char *v9; // r9
  unsigned int v10; // esi
  unsigned int v12[2]; // [rsp+40h] [rbp-49h] BYREF
  DWORD Parameter; // [rsp+48h] [rbp-41h] BYREF
  char v14; // [rsp+4Ch] [rbp-3Dh]
  HRESULT v15; // [rsp+50h] [rbp-39h]
  HANDLE Timer; // [rsp+58h] [rbp-31h] BYREF
  FILETIME FileTime; // [rsp+68h] [rbp-21h] BYREF
  const struct Microsoft::Diagnostics::SystemStateManager::BatteryInfo *v18; // [rsp+70h] [rbp-19h]
  unsigned __int8 *v19; // [rsp+78h] [rbp-11h]
  HMODULE v20; // [rsp+80h] [rbp-9h] BYREF
  struct _SYSTEMTIME v21; // [rsp+88h] [rbp-1h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v18 = a2;
  v19 = a1;
  *a1 = 0;
  LibraryW = LoadLibraryW(L"srumapi.dll");
  v4 = LibraryW;
  v20 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "SruQueryStats");
    if ( !ProcAddress )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x577,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\systemstatemanager.cpp",
        v6);
    v7 = (void (*)(void))GetProcAddress(v4, "SruFreeRecordSet");
    if ( !v7 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x579,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\systemstatemanager.cpp",
        v8);
    FileTime = (FILETIME)*((_QWORD *)a2 + 1);
    SystemTime = 0;
    if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x57D,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\systemstatemanager.cpp",
        v9);
    v21 = 0;
    GetSystemTime(&v21);
    *(_QWORD *)v12 = 0;
    Parameter = GetCurrentThreadId();
    v14 = 0;
    Timer = 0;
    v15 = CoEnableCallCancellation(0);
    if ( v15 >= 0 )
      CreateTimerQueueTimer(&Timer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x1388u, 0x3E8u, 0);
    v10 = ((__int64 (__fastcall *)(__int64, struct _SYSTEMTIME *, struct _SYSTEMTIME *))ProcAddress)(
            7,
            &SystemTime,
            &v21);
    if ( v15 >= 0 )
    {
      v15 = -2147467259;
      CoDisableCallCancellation(0);
      if ( Timer )
        DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    }
    if ( v10 )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x59E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\systemstatemanager.cpp",
        (const char *)v10,
        (unsigned int)v12);
      if ( *(_QWORD *)v12 )
        v7();
      FreeLibrary(v4);
    }
    else
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x5A4,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\systemstatemanager.cpp",
        (const char *)0xE8,
        (unsigned int)v12);
      if ( *(_QWORD *)v12 )
        v7();
      Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&v20);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800fbf28  mov     [rsp-8+arg_10], rbx
0x1800fbf2d  push    rbp
0x1800fbf2e  push    rsi
0x1800fbf2f  push    rdi
0x1800fbf30  push    r12
0x1800fbf32  push    r13
0x1800fbf34  push    r14
0x1800fbf36  push    r15
0x1800fbf38  lea     rbp, [rsp-27h]
0x1800fbf3d  sub     rsp, 0B0h
0x1800fbf44  mov     rax, cs:__security_cookie
0x1800fbf4b  xor     rax, rsp
0x1800fbf4e  mov     [rbp+57h+var_38], rax
0x1800fbf52  mov     r14, rdx
0x1800fbf55  mov     [rbp+57h+var_70], rdx
0x1800fbf59  mov     [rbp+57h+var_68], rcx
0x1800fbf5d  xor     r15d, r15d
0x1800fbf60  mov     [rcx], r15b
0x1800fbf63  lea     rcx, aSrumapiDll; "srumapi.dll"
0x1800fbf6a  call    cs:__imp_LoadLibraryW
0x1800fbf70  mov     rbx, rax
0x1800fbf73  mov     [rbp+57h+var_60], rax
0x1800fbf77  test    rax, rax
0x1800fbf7a  jz      loc_1800FC163
0x1800fbf80  lea     rdx, aSruquerystats; "SruQueryStats"
0x1800fbf87  mov     rcx, rax; hModule
0x1800fbf8a  call    cs:__imp_GetProcAddress
0x1800fbf90  mov     rsi, rax
0x1800fbf93  mov     rcx, [rbp+5Fh]; this
0x1800fbf97  test    rax, rax
0x1800fbf9a  jz      loc_1800FC23B
0x1800fbfa0  lea     rdx, aSrufreerecords; "SruFreeRecordSet"
0x1800fbfa7  mov     rcx, rbx; hModule
0x1800fbfaa  call    cs:__imp_GetProcAddress
0x1800fbfb0  mov     rdi, rax
0x1800fbfb3  mov     rcx, [rbp+5Fh]; this
0x1800fbfb7  test    rax, rax
0x1800fbfba  jz      loc_1800FC24D
0x1800fbfc0  mov     rax, [r14+8]
0x1800fbfc4  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rax
0x1800fbfc8  xorps   xmm0, xmm0
0x1800fbfcb  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800fbfcf  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1800fbfd3  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x1800fbfd7  call    cs:__imp_FileTimeToSystemTime
0x1800fbfdd  mov     rcx, [rbp+5Fh]; this
0x1800fbfe1  test    eax, eax
0x1800fbfe3  jz      loc_1800FC165
0x1800fbfe9  xorps   xmm0, xmm0
0x1800fbfec  movups  xmmword ptr [rbp+57h+var_58.wYear], xmm0
0x1800fbff0  lea     rcx, [rbp+57h+var_58]; lpSystemTime
0x1800fbff4  call    cs:__imp_GetSystemTime
0x1800fbffa  mov     qword ptr [rbp+57h+var_A0], r15
0x1800fbffe  call    cs:__imp_GetCurrentThreadId
0x1800fc004  mov     [rbp+57h+Parameter], eax
0x1800fc007  mov     [rbp+57h+var_94], r15b
0x1800fc00b  mov     r14d, 80004005h
0x1800fc011  mov     [rbp+57h+var_90], r14d
0x1800fc015  mov     [rbp+57h+Timer], r15
0x1800fc019  xor     ecx, ecx; pReserved
0x1800fc01b  call    cs:__imp_CoEnableCallCancellation
0x1800fc021  mov     [rbp+57h+var_90], eax
0x1800fc024  test    eax, eax
0x1800fc026  jns     loc_1800FC25F
0x1800fc02c  lea     rax, [rbp+57h+var_A0]
0x1800fc030  mov     qword ptr [rsp+0E0h+DueTime], rax; unsigned int
0x1800fc035  mov     r9d, 2
0x1800fc03b  lea     r8, [rbp+57h+var_58]
0x1800fc03f  lea     rdx, [rbp+57h+SystemTime]
0x1800fc043  lea     ecx, [r9+5]
0x1800fc047  mov     rax, rsi
0x1800fc04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc04f  mov     esi, eax
0x1800fc051  cmp     [rbp+57h+var_90], r15d
0x1800fc055  jl      short loc_1800FC070
0x1800fc057  mov     [rbp+57h+var_90], r14d
0x1800fc05b  xor     ecx, ecx; pReserved
0x1800fc05d  call    cs:__imp_CoDisableCallCancellation
0x1800fc063  mov     rdx, [rbp+57h+Timer]; Timer
0x1800fc067  test    rdx, rdx
0x1800fc06a  jnz     loc_1800FC177
0x1800fc070  test    esi, esi
0x1800fc072  jnz     loc_1800FC1CF
0x1800fc078  mov     rdx, qword ptr [rbp+57h+var_A0]
0x1800fc07c  test    rdx, rdx
0x1800fc07f  jz      loc_1800FC1FF
0x1800fc085  cmp     [rdx], r15d
0x1800fc088  jz      loc_1800FC1FF
0x1800fc08e  mov     r13, r15
0x1800fc091  mov     r12d, r15d
0x1800fc094  mov     esi, r15d
0x1800fc097  jbe     short loc_1800FC0D3
0x1800fc099  mov     r15d, esi
0x1800fc09c  shl     r15, 6
0x1800fc0a0  add     r15, [rdx+8]
0x1800fc0a4  xor     eax, eax
0x1800fc0a6  cmp     [r15+10h], eax
0x1800fc0aa  jnz     short loc_1800FC0C4
0x1800fc0ac  mov     r9, [r15+18h]
0x1800fc0b0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800fc0b4  inc     r8
0x1800fc0b7  cmp     [r9+r8*2], ax
0x1800fc0bc  jnz     short loc_1800FC0B4
0x1800fc0be  cmp     r8, 9
0x1800fc0c2  jnb     short loc_1800FC116
0x1800fc0c4  inc     esi
0x1800fc0c6  cmp     esi, [rdx]
0x1800fc0c8  jb      short loc_1800FC099
0x1800fc0ca  test    r12d, r12d
0x1800fc0cd  jnz     loc_1800FC188
0x1800fc0d3  test    rdx, rdx
0x1800fc0d6  jz      short loc_1800FC0E4
0x1800fc0d8  mov     rcx, rdx
0x1800fc0db  mov     rax, rdi
0x1800fc0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc0e3  nop
0x1800fc0e4  mov     rcx, rbx; hLibModule
0x1800fc0e7  call    cs:__imp_FreeLibrary
0x1800fc0ed  xor     al, al
0x1800fc0ef  mov     rcx, [rbp+57h+var_38]
0x1800fc0f3  xor     rcx, rsp; StackCookie
0x1800fc0f6  call    __security_check_cookie
0x1800fc0fb  mov     rbx, [rsp+0E0h+arg_10]
0x1800fc103  add     rsp, 0B0h
0x1800fc10a  pop     r15
0x1800fc10c  pop     r14
0x1800fc10e  pop     r13
0x1800fc110  pop     r12
0x1800fc112  pop     rdi
0x1800fc113  pop     rsi
0x1800fc114  pop     rbp
0x1800fc115  retn
0x1800fc116  lea     rcx, aUtcsvc_0; "[utcsvc]"
0x1800fc11d  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800fc122  mov     rdx, rax
0x1800fc125  mov     [rbp+57h+var_80], rax
0x1800fc129  add     r8, 0FFFFFFFFFFFFFFF8h
0x1800fc12d  lea     rcx, [r9+r8*2]
0x1800fc131  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800fc136  mov     r14, rax
0x1800fc139  mov     r8, rax
0x1800fc13c  cmp     rdx, rax
0x1800fc13f  cmovb   r8, rdx
0x1800fc143  lea     rdx, aUtcsvc_0; "[utcsvc]"
0x1800fc14a  call    cs:__imp__o__wcsnicmp
0x1800fc150  test    eax, eax
0x1800fc152  jnz     short loc_1800FC15A
0x1800fc154  sub     r14d, dword ptr [rbp+57h+var_80]
0x1800fc158  jz      short loc_1800FC1BF
0x1800fc15a  mov     rdx, qword ptr [rbp+57h+var_A0]
0x1800fc15e  jmp     loc_1800FC0C4
0x1800fc163  jmp     short loc_1800FC0ED
0x1800fc165  lea     r8, aOnecoreBaseTel_47; "onecore\\base\\telemetry\\utc\\service"...
0x1800fc16c  mov     edx, 57Dh; void *
0x1800fc171  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800fc177  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800fc17b  xor     ecx, ecx; TimerQueue
0x1800fc17d  call    cs:__imp_DeleteTimerQueueTimer
0x1800fc183  jmp     loc_1800FC070
0x1800fc188  test    rdx, rdx
0x1800fc18b  jz      short loc_1800FC199
0x1800fc18d  mov     rcx, rdx
0x1800fc190  mov     rax, rdi
0x1800fc193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc198  nop
0x1800fc199  mov     rax, [rbp+57h+var_70]
0x1800fc19d  mov     ecx, [rax]
0x1800fc19f  imul    r8, rcx, 0E10h
0x1800fc1a6  test    r8, r8
0x1800fc1a9  jnz     loc_1800FC290
0x1800fc1af  mov     rcx, rbx; hLibModule
0x1800fc1b2  call    cs:__imp_FreeLibrary
0x1800fc1b8  mov     al, 1
0x1800fc1ba  jmp     loc_1800FC0EF
0x1800fc1bf  inc     r12d
0x1800fc1c2  mov     rcx, r15; struct _SRU_STATS_RECORD *
0x1800fc1c5  call    ?GetEnergyConsumption@SystemStateManager@Diagnostics@Microsoft@@CA_KAEBU_SRU_STATS_RECORD@@@Z; Microsoft::Diagnostics::SystemStateManager::GetEnergyConsumption(_SRU_STATS_RECORD const &)
0x1800fc1ca  add     r13, rax
0x1800fc1cd  jmp     short loc_1800FC15A
0x1800fc1cf  mov     rcx, [rbp+5Fh]; this
0x1800fc1d3  mov     r9d, esi; char *
0x1800fc1d6  lea     r8, aOnecoreBaseTel_47; "onecore\\base\\telemetry\\utc\\service"...
0x1800fc1dd  mov     edx, 59Eh; void *
0x1800fc1e2  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800fc1e7  nop
0x1800fc1e8  mov     rcx, qword ptr [rbp+57h+var_A0]
0x1800fc1ec  test    rcx, rcx
0x1800fc1ef  jz      short loc_1800FC1FA
0x1800fc1f1  mov     rax, rdi
0x1800fc1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc1f9  nop
0x1800fc1fa  jmp     loc_1800FC0E4
0x1800fc1ff  mov     rcx, [rbp+5Fh]; this
0x1800fc203  mov     r9d, 0E8h; char *
0x1800fc209  lea     r8, aOnecoreBaseTel_47; "onecore\\base\\telemetry\\utc\\service"...
0x1800fc210  mov     edx, 5A4h; void *
0x1800fc215  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800fc21a  nop
0x1800fc21b  mov     rcx, qword ptr [rbp+57h+var_A0]
0x1800fc21f  test    rcx, rcx
0x1800fc222  jz      short loc_1800FC22D
0x1800fc224  mov     rax, rdi
0x1800fc227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc22c  nop
0x1800fc22d  lea     rcx, [rbp+57h+var_60]
0x1800fc231  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x1800fc236  jmp     loc_1800FC0ED
0x1800fc23b  lea     r8, aOnecoreBaseTel_47; "onecore\\base\\telemetry\\utc\\service"...
0x1800fc242  mov     edx, 577h; void *
0x1800fc247  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800fc24d  lea     r8, aOnecoreBaseTel_47; "onecore\\base\\telemetry\\utc\\service"...
0x1800fc254  mov     edx, 579h; void *
0x1800fc259  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800fc25f  mov     [rsp+0E0h+Flags], r15d; Flags
0x1800fc264  mov     [rsp+0E0h+Period], 3E8h; Period
0x1800fc26c  mov     [rsp+0E0h+DueTime], 1388h; DueTime
0x1800fc274  lea     r9, [rbp+57h+Parameter]; Parameter
0x1800fc278  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x1800fc27f  xor     edx, edx; TimerQueue
0x1800fc281  lea     rcx, [rbp+57h+Timer]; phNewTimer
0x1800fc285  call    cs:__imp_CreateTimerQueueTimer
0x1800fc28b  jmp     loc_1800FC02C
0x1800fc290  imul    rax, r13, 64h ; 'd'
0x1800fc294  xor     edx, edx
0x1800fc296  div     r8
0x1800fc299  mov     rcx, [rbp+57h+var_68]
0x1800fc29d  mov     [rcx], al
0x1800fc29f  jmp     loc_1800FC1AF
```
