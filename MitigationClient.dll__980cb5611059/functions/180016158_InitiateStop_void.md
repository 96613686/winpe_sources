# InitiateStop(void)

- ea: `0x180016158`
- end: `0x1800161e3`
- name: `?InitiateStop@@YAXXZ`
- size: `139`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800163d0`

## callees

- `0x180016158`
- `0x180016210`
- `0x180016bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800161af`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800161af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800161d7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800161d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161b9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180016189`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180016189`

## pseudocode

```c
void __fastcall InitiateStop(__int64 a1)
{
  void *v1; // rdx
  int LastError; // eax
  int v3; // [rsp+20h] [rbp-18h] BYREF
  HANDLE hMutex; // [rsp+28h] [rbp-10h]

  g_serviceStatus.dwCurrentState = 3;
  *(_QWORD *)&g_serviceStatus.dwCheckPoint = 0;
  Microsoft::WRL::Wrappers::Mutex::Lock(a1, &v3);
  SetServiceStatus(g_serviceStatusHandle, &g_serviceStatus);
  wil::details::SetEvent(qword_180080BD8, v1);
  if ( hMutex && (v3 & 0xFFFFFF7F) == 0 && !ReleaseMutex(hMutex) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180016158  sub     rsp, 38h
0x18001615c  lea     rdx, [rsp+38h+var_18]
0x180016161  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_serviceStatus ...
0x18001616b  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_serviceStatus ...
0x180016176  call    ?Lock@Mutex@Wrappers@WRL@Microsoft@@QEAA?AV?$SyncLockWithStatusT@UMutexTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Details@234@K@Z; Microsoft::WRL::Wrappers::Mutex::Lock(ulong)
0x18001617b  mov     rcx, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180016182  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180016189  call    cs:__imp_SetServiceStatus
0x18001618f  mov     rcx, cs:qword_180080BD8; this
0x180016196  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18001619b  mov     rcx, [rsp+38h+hMutex]; hMutex
0x1800161a0  test    rcx, rcx
0x1800161a3  jz      short loc_1800161DE
0x1800161a5  test    [rsp+38h+var_18], 0FFFFFF7Fh
0x1800161ad  jnz     short loc_1800161DE
0x1800161af  call    cs:__imp_ReleaseMutex
0x1800161b5  test    eax, eax
0x1800161b7  jnz     short loc_1800161DE
0x1800161b9  call    cs:__imp_GetLastError
0x1800161bf  test    eax, eax
0x1800161c1  jle     short loc_1800161CB
0x1800161c3  movzx   eax, ax
0x1800161c6  or      eax, 80070000h
0x1800161cb  xor     r9d, r9d; lpArguments
0x1800161ce  xor     r8d, r8d; nNumberOfArguments
0x1800161d1  mov     ecx, eax; dwExceptionCode
0x1800161d3  lea     edx, [r9+1]; dwExceptionFlags
0x1800161d7  call    cs:__imp_RaiseException
0x1800161dd  int     3; Trap to Debugger
0x1800161de  add     rsp, 38h
0x1800161e2  retn
```
