# TraceOutputSettings::~TraceOutputSettings(void)

- ea: `0x1800116e4`
- end: `0x1800118b6`
- name: `??1TraceOutputSettings@@QEAA@XZ`
- size: `466`
- prototype: `void __fastcall(TraceOutputSettings *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800145b0`

## callees

- `0x18000ad90`
- `0x1800116e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001172a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800118a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001172a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800118a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001173c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001173c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800116f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800117ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800116f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800117ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011712`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001187d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011712`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001187d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800117b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011860`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800117b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011860`
- `KERNEL32!UnregisterWaitEx` at `0x1800117d2`
- `KERNEL32!UnregisterWaitEx` at `0x1800117d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011895`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011895`

## string_xrefs

- `0x180011793`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x180011801`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x180011836`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18001174c`: `Failed receiving the RegistryChangeListenerFinished event`
- `0x180011768`: `Successfully received the RegistryChangeListenerFinished event`
- `0x180011816`: `Successfully unregistered for registry change notifications`

## pseudocode

```c
void __fastcall TraceOutputSettings::~TraceOutputSettings(TraceOutputSettings *this)
{
  __int64 v1; // r9
  __int64 v2; // rdx
  DWORD LastError; // [rsp+28h] [rbp-20h]
  const wchar_t *v4; // [rsp+30h] [rbp-18h]
  DWORD v5; // [rsp+38h] [rbp-10h]

  EnterCriticalSection(&stru_18001FA50);
  if ( TraceOutputSettings::fWatchingRegistry )
  {
    TraceOutputSettings::fWatchingRegistry = 0;
    RegCloseKey(TraceOutputSettings::hkConfiguration);
    TraceOutputSettings::hkConfiguration = 0;
    LeaveCriticalSection(&stru_18001FA50);
    if ( WaitForSingleObject(TraceOutputSettings::RegistryChangeListenerFinished, 0x3E8u) )
    {
      v4 = L"Failed receiving the RegistryChangeListenerFinished event";
      LastError = GetLastError();
      v1 = 101;
      v2 = 1;
    }
    else
    {
      v4 = L"Successfully received the RegistryChangeListenerFinished event";
      LastError = 0;
      v1 = 108;
      v2 = 3;
    }
    TraceStringInline(
      2,
      v2,
      L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
      v1,
      L"TraceOutputSettings::~TraceOutputSettings",
      LastError,
      v4);
    EnterCriticalSection(&stru_18001FA50);
    CloseHandle(TraceOutputSettings::RegistryChangeListenerFinished);
    TraceOutputSettings::RegistryChangeListenerFinished = 0;
    if ( UnregisterWaitEx(TraceOutputSettings::RegistryWaitObject, 0) )
    {
      TraceStringInline(
        2,
        3,
        L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
        127,
        L"TraceOutputSettings::~TraceOutputSettings",
        0,
        L"Successfully unregistered for registry change notifications");
    }
    else
    {
      v5 = GetLastError();
      TraceStringInline(
        2,
        1,
        L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
        121,
        L"TraceOutputSettings::~TraceOutputSettings",
        v5,
        L"UnregisterWait returned the 0x%x error code.",
        v5);
    }
    TraceOutputSettings::RegistryWaitObject = 0;
    if ( TraceOutputSettings::RegistryChangedEvent )
    {
      CloseHandle(TraceOutputSettings::RegistryChangedEvent);
      TraceOutputSettings::RegistryChangedEvent = 0;
    }
  }
  if ( TraceOutputSettings::hkConfiguration )
  {
    RegCloseKey(TraceOutputSettings::hkConfiguration);
    TraceOutputSettings::hkConfiguration = 0;
  }
  LocalFree(TraceOutputSettings::TraceFilePath);
  TraceOutputSettings::fInitialized = 0;
  LeaveCriticalSection(&stru_18001FA50);
}

```

## disassembly

```asm
0x1800116e4  push    rdi
0x1800116e6  sub     rsp, 40h
0x1800116ea  lea     rcx, stru_18001FA50; lpCriticalSection
0x1800116f1  call    cs:__imp_EnterCriticalSection
0x1800116f7  cmp     cs:?fWatchingRegistry@TraceOutputSettings@@0_NA, 0; bool TraceOutputSettings::fWatchingRegistry
0x1800116fe  jz      loc_180011871
0x180011704  mov     cs:?fWatchingRegistry@TraceOutputSettings@@0_NA, 0; bool TraceOutputSettings::fWatchingRegistry
0x18001170b  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x180011712  call    cs:__imp_RegCloseKey
0x180011718  mov     cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA, 0; HKEY__ * TraceOutputSettings::hkConfiguration
0x180011723  lea     rcx, stru_18001FA50; lpCriticalSection
0x18001172a  call    cs:__imp_LeaveCriticalSection
0x180011730  mov     edx, 3E8h; dwMilliseconds
0x180011735  mov     rcx, cs:?RegistryChangeListenerFinished@TraceOutputSettings@@0PEAXEA; hHandle
0x18001173c  call    cs:__imp_WaitForSingleObject
0x180011742  test    eax, eax
0x180011744  jz      short loc_180011768
0x180011746  call    cs:__imp_GetLastError
0x18001174c  lea     rcx, aFailedReceivin; "Failed receiving the RegistryChangeList"...
0x180011753  mov     [rsp+48h+var_18], rcx
0x180011758  mov     dword ptr [rsp+48h+var_20], eax
0x18001175c  mov     r9d, 65h ; 'e'
0x180011762  lea     edx, [r9-64h]
0x180011766  jmp     short loc_180011787
0x180011768  lea     rax, aSuccessfullyRe; "Successfully received the RegistryChang"...
0x18001176f  mov     [rsp+48h+var_18], rax
0x180011774  mov     [rsp+48h+var_20], 0
0x18001177d  mov     r9d, 6Ch ; 'l'
0x180011783  lea     edx, [r9-69h]
0x180011787  lea     rdi, aTraceoutputset_0; "TraceOutputSettings::~TraceOutputSettin"...
0x18001178e  mov     [rsp+48h+var_28], rdi
0x180011793  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18001179a  mov     ecx, 2
0x18001179f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800117a4  lea     rcx, stru_18001FA50; lpCriticalSection
0x1800117ab  call    cs:__imp_EnterCriticalSection
0x1800117b1  mov     rcx, cs:?RegistryChangeListenerFinished@TraceOutputSettings@@0PEAXEA; hObject
0x1800117b8  call    cs:__imp_CloseHandle
0x1800117be  mov     cs:?RegistryChangeListenerFinished@TraceOutputSettings@@0PEAXEA, 0; void * TraceOutputSettings::RegistryChangeListenerFinished
0x1800117c9  xor     edx, edx; CompletionEvent
0x1800117cb  mov     rcx, cs:?RegistryWaitObject@TraceOutputSettings@@0PEAXEA; WaitHandle
0x1800117d2  call    cs:__imp_UnregisterWaitEx
0x1800117d8  test    eax, eax
0x1800117da  jnz     short loc_180011816
0x1800117dc  call    cs:__imp_GetLastError
0x1800117e2  mov     [rsp+48h+var_10], eax
0x1800117e6  lea     rcx, aUnregisterwait; "UnregisterWait returned the 0x%x error "...
0x1800117ed  mov     [rsp+48h+var_18], rcx
0x1800117f2  mov     dword ptr [rsp+48h+var_20], eax
0x1800117f6  mov     [rsp+48h+var_28], rdi
0x1800117fb  mov     r9d, 79h ; 'y'
0x180011801  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x180011808  lea     edx, [r9-78h]
0x18001180c  lea     ecx, [rdx+1]
0x18001180f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011814  jmp     short loc_180011849
0x180011816  lea     rax, aSuccessfullyUn; "Successfully unregistered for registry "...
0x18001181d  mov     [rsp+48h+var_18], rax
0x180011822  mov     [rsp+48h+var_20], 0
0x18001182b  mov     [rsp+48h+var_28], rdi
0x180011830  mov     r9d, 7Fh
0x180011836  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18001183d  lea     edx, [r9-7Ch]
0x180011841  lea     ecx, [rdx-1]
0x180011844  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011849  mov     cs:?RegistryWaitObject@TraceOutputSettings@@0PEAXEA, 0; void * TraceOutputSettings::RegistryWaitObject
0x180011854  mov     rcx, cs:?RegistryChangedEvent@TraceOutputSettings@@0PEAXEA; hObject
0x18001185b  test    rcx, rcx
0x18001185e  jz      short loc_180011871
0x180011860  call    cs:__imp_CloseHandle
0x180011866  mov     cs:?RegistryChangedEvent@TraceOutputSettings@@0PEAXEA, 0; void * TraceOutputSettings::RegistryChangedEvent
0x180011871  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x180011878  test    rcx, rcx
0x18001187b  jz      short loc_18001188E
0x18001187d  call    cs:__imp_RegCloseKey
0x180011883  mov     cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA, 0; HKEY__ * TraceOutputSettings::hkConfiguration
0x18001188e  mov     rcx, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; hMem
0x180011895  call    cs:__imp_LocalFree
0x18001189b  mov     cs:?fInitialized@TraceOutputSettings@@0_NA, 0; bool TraceOutputSettings::fInitialized
0x1800118a2  lea     rcx, stru_18001FA50; lpCriticalSection
0x1800118a9  call    cs:__imp_LeaveCriticalSection
0x1800118af  nop
0x1800118b0  add     rsp, 40h
0x1800118b4  pop     rdi
0x1800118b5  retn
```
