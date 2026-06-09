# Windows::Compat::Ids::IdsEngine::InitializeLocks(void)

- ea: `0x1800bc3c4`
- end: `0x1800bc4bc`
- name: `?InitializeLocks@IdsEngine@Ids@Compat@Windows@@SAKXZ`
- size: `248`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b99f8`

## callees

- `0x180012920`
- `0x1800bc3c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800bc3da`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800bc3da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bc402`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bc443`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bc48d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bc402`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bc443`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bc48d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc451`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc47b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc47b`

## string_xrefs

- `0x1800bc423`: `Windows::Compat::Ids::IdsEngine::InitializeLocks`
- `0x1800bc464`: `Windows::Compat::Ids::IdsEngine::InitializeLocks`

## pseudocode

```c
__int64 Windows::Compat::Ids::IdsEngine::InitializeLocks(void)
{
  HANDLE EventW; // rdi
  DWORD LastError; // ebx
  HANDLE v2; // rbx
  HANDLE v3; // rax

  InitializeCriticalSection(&g_IdsEngineLock);
  g_IdsEngineLockCount = 0;
  g_IdsEngineState = 2;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    v2 = CreateEventW(0, 1, 0, 0);
    if ( v2 )
    {
      v3 = CreateEventW(0, 1, 0, 0);
      Windows::Compat::Ids::IdsEngine::sStopEvent = v2;
      LastError = 0;
      Windows::Compat::Ids::IdsEngine::sCallbackGuardEvent = v3;
      Windows::Compat::Ids::IdsEngine::sWorkQueued = EventW;
    }
    else
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"Windows::Compat::Ids::IdsEngine::InitializeLocks",
        675,
        (unsigned int)"Failed to initialize IdsEngine sStopEvent event [%d]\n",
        LastError);
      CloseHandle(EventW);
    }
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Ids::IdsEngine::InitializeLocks",
      666,
      (unsigned int)"Failed to initialize IdsEngine sWorkQueued event [%d]\n",
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800bc3c4  mov     [rsp+arg_0], rbx
0x1800bc3c9  mov     [rsp+arg_8], rsi
0x1800bc3ce  push    rdi
0x1800bc3cf  sub     rsp, 30h
0x1800bc3d3  lea     rcx, ?g_IdsEngineLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800bc3da  call    cs:__imp_InitializeCriticalSection
0x1800bc3e0  xor     r9d, r9d; lpName
0x1800bc3e3  mov     cs:?g_IdsEngineLockCount@@3JA, 0; long g_IdsEngineLockCount
0x1800bc3ed  xor     r8d, r8d; bInitialState
0x1800bc3f0  mov     cs:?g_IdsEngineState@@3JA, 2; long g_IdsEngineState
0x1800bc3fa  xor     ecx, ecx; lpEventAttributes
0x1800bc3fc  lea     esi, [r9+1]
0x1800bc400  mov     edx, esi; bManualReset
0x1800bc402  call    cs:__imp_CreateEventW
0x1800bc408  mov     rdi, rax
0x1800bc40b  test    rax, rax
0x1800bc40e  jnz     short loc_1800BC439
0x1800bc410  call    cs:__imp_GetLastError
0x1800bc416  lea     r9, aFailedToInitia_20; "Failed to initialize IdsEngine sWorkQue"...
0x1800bc41d  mov     r8d, 29Ah
0x1800bc423  lea     rdx, aWindowsCompatI_65; "Windows::Compat::Ids::IdsEngine::Initia"...
0x1800bc42a  mov     [rsp+38h+var_18], eax
0x1800bc42e  mov     ecx, esi
0x1800bc430  mov     ebx, eax
0x1800bc432  call    AslLogCallPrintf
0x1800bc437  jmp     short loc_1800BC4AA
0x1800bc439  xor     r9d, r9d; lpName
0x1800bc43c  xor     r8d, r8d; bInitialState
0x1800bc43f  mov     edx, esi; bManualReset
0x1800bc441  xor     ecx, ecx; lpEventAttributes
0x1800bc443  call    cs:__imp_CreateEventW
0x1800bc449  mov     rbx, rax
0x1800bc44c  test    rax, rax
0x1800bc44f  jnz     short loc_1800BC483
0x1800bc451  call    cs:__imp_GetLastError
0x1800bc457  lea     r9, aFailedToInitia_21; "Failed to initialize IdsEngine sStopEve"...
0x1800bc45e  mov     r8d, 2A3h
0x1800bc464  lea     rdx, aWindowsCompatI_65; "Windows::Compat::Ids::IdsEngine::Initia"...
0x1800bc46b  mov     [rsp+38h+var_18], eax
0x1800bc46f  mov     ecx, esi
0x1800bc471  mov     ebx, eax
0x1800bc473  call    AslLogCallPrintf
0x1800bc478  mov     rcx, rdi; hObject
0x1800bc47b  call    cs:__imp_CloseHandle
0x1800bc481  jmp     short loc_1800BC4AA
0x1800bc483  xor     r9d, r9d; lpName
0x1800bc486  xor     r8d, r8d; bInitialState
0x1800bc489  mov     edx, esi; bManualReset
0x1800bc48b  xor     ecx, ecx; lpEventAttributes
0x1800bc48d  call    cs:__imp_CreateEventW
0x1800bc493  mov     cs:?sStopEvent@IdsEngine@Ids@Compat@Windows@@2PEAXEA, rbx; void * Windows::Compat::Ids::IdsEngine::sStopEvent
0x1800bc49a  xor     ebx, ebx
0x1800bc49c  mov     cs:?sCallbackGuardEvent@IdsEngine@Ids@Compat@Windows@@2PEAXEA, rax; void * Windows::Compat::Ids::IdsEngine::sCallbackGuardEvent
0x1800bc4a3  mov     cs:?sWorkQueued@IdsEngine@Ids@Compat@Windows@@2PEAXEA, rdi; void * Windows::Compat::Ids::IdsEngine::sWorkQueued
0x1800bc4aa  mov     rsi, [rsp+38h+arg_8]
0x1800bc4af  mov     eax, ebx
0x1800bc4b1  mov     rbx, [rsp+38h+arg_0]
0x1800bc4b6  add     rsp, 30h
0x1800bc4ba  pop     rdi
0x1800bc4bb  retn
```
