# CleanupService(int)

- ea: `0x18002bf18`
- end: `0x18002c07b`
- name: `?CleanupService@@YAXH@Z`
- size: `355`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800274e8`
- `0x180034080`

## callees

- `0x1800023b0`
- `0x180008938`
- `0x180009034`
- `0x180023f14`
- `0x18002bf18`
- `0x18003f0bc`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bfb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bfd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bfb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bfd2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002bfa3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002bfa3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002bff1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002bff1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002bf2e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002bf2e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002c04a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002c04a`

## string_xrefs

- `0x18002c058`: `SetServiceStatus`
- `0x18002c009`: `com\complus\src\events\tier2\service.cpp`
- `0x18002c064`: `com\complus\src\events\tier2\service.cpp`

## pseudocode

```c
void __fastcall CleanupService(int a1)
{
  HRESULT v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8

  v2 = 0;
  if ( a1 )
    v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
    goto LABEL_15;
  if ( g_pServiceContextCallBack )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)g_pServiceContextCallBack + 24LL))(
           g_pServiceContextCallBack,
           ServiceCleanup,
           0,
           &IID_IContextCallback,
           5,
           0);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pServiceContextCallBack + 16LL))(g_pServiceContextCallBack);
  }
  if ( g_hServiceWait )
    UnregisterWaitEx(g_hServiceWait, 0);
  if ( g_hServiceStopEvent )
  {
    CloseHandle(g_hServiceStopEvent);
    g_hServiceStopEvent = 0;
  }
  if ( g_hMaxCommitEvent )
  {
    CloseHandle(g_hMaxCommitEvent);
    g_hMaxCommitEvent = 0;
  }
  RemoveServiceLogger();
  StopWorkerQueues(v4, v3, v5);
  if ( a1 )
    CoUninitialize();
  if ( v2 < 0 )
LABEL_15:
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\service.cpp", 0x155u, 0x11u, v2);
  g_status.dwControlsAccepted = 1;
  g_status.dwCurrentState = 1;
  g_status.dwWin32ExitCode = 0;
  *(_QWORD *)&g_status.dwCheckPoint = 0;
  if ( !SetServiceStatus(g_statusHandle, &g_status) )
    InternalError_Win32(L"com\\complus\\src\\events\\tier2\\service.cpp", 0x172u, 0x11u, L"SetServiceStatus");
}

```

## disassembly

```asm
0x18002bf18  mov     [rsp+arg_0], rbx
0x18002bf1d  push    rdi
0x18002bf1e  sub     rsp, 50h
0x18002bf22  mov     edi, ecx
0x18002bf24  xor     ebx, ebx
0x18002bf26  test    ecx, ecx
0x18002bf28  jz      short loc_18002BF3A
0x18002bf2a  xor     edx, edx; dwCoInit
0x18002bf2c  xor     ecx, ecx; pvReserved
0x18002bf2e  call    cs:__imp_CoInitializeEx
0x18002bf34  mov     ebx, eax
0x18002bf36  mov     [rsp+58h+var_18], eax
0x18002bf3a  test    ebx, ebx
0x18002bf3c  js      loc_18002BFFB
0x18002bf42  mov     rcx, cs:?g_pServiceContextCallBack@@3PEAUIContextCallback@@EA; IContextCallback * g_pServiceContextCallBack
0x18002bf49  test    rcx, rcx
0x18002bf4c  jz      short loc_18002BF95
0x18002bf4e  mov     rax, [rcx]
0x18002bf51  mov     [rsp+58h+var_30], 0
0x18002bf5a  mov     [rsp+58h+var_38], 5
0x18002bf62  lea     r9, IID_IContextCallback
0x18002bf69  xor     r8d, r8d
0x18002bf6c  lea     rdx, ?ServiceCleanup@@YAJPEAUtagComCallData@@@Z; ServiceCleanup(tagComCallData *)
0x18002bf73  mov     rax, [rax+18h]
0x18002bf77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf7c  mov     ebx, eax
0x18002bf7e  mov     [rsp+58h+var_18], eax
0x18002bf82  mov     rcx, cs:?g_pServiceContextCallBack@@3PEAUIContextCallback@@EA; IContextCallback * g_pServiceContextCallBack
0x18002bf89  mov     rax, [rcx]
0x18002bf8c  mov     rax, [rax+10h]
0x18002bf90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf95  mov     rcx, cs:?g_hServiceWait@@3PEAXEA; WaitHandle
0x18002bf9c  test    rcx, rcx
0x18002bf9f  jz      short loc_18002BFA9
0x18002bfa1  xor     edx, edx; CompletionEvent
0x18002bfa3  call    cs:__imp_UnregisterWaitEx
0x18002bfa9  mov     rcx, cs:?g_hServiceStopEvent@@3PEAXEA; hObject
0x18002bfb0  test    rcx, rcx
0x18002bfb3  jz      short loc_18002BFC6
0x18002bfb5  call    cs:__imp_CloseHandle
0x18002bfbb  mov     cs:?g_hServiceStopEvent@@3PEAXEA, 0; void * g_hServiceStopEvent
0x18002bfc6  mov     rcx, cs:?g_hMaxCommitEvent@@3PEAXEA; hObject
0x18002bfcd  test    rcx, rcx
0x18002bfd0  jz      short loc_18002BFE3
0x18002bfd2  call    cs:__imp_CloseHandle
0x18002bfd8  mov     cs:?g_hMaxCommitEvent@@3PEAXEA, 0; void * g_hMaxCommitEvent
0x18002bfe3  call    ?RemoveServiceLogger@@YAXXZ; RemoveServiceLogger(void)
0x18002bfe8  call    StopWorkerQueues
0x18002bfed  test    edi, edi
0x18002bfef  jz      short loc_18002BFF7
0x18002bff1  call    cs:__imp_CoUninitialize
0x18002bff7  test    ebx, ebx
0x18002bff9  jns     short loc_18002C016
0x18002bffb  mov     r8d, 11h; unsigned __int16
0x18002c001  mov     r9d, ebx; int
0x18002c004  mov     edx, 155h; unsigned int
0x18002c009  lea     rcx, aComComplusSrcE_8; "com\\complus\\src\\events\\tier2\\servi"...
0x18002c010  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18002c015  nop
0x18002c016  mov     eax, 1
0x18002c01b  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwControlsAccepted, eax; _SERVICE_STATUS g_status ...
0x18002c021  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwCurrentState, eax; _SERVICE_STATUS g_status ...
0x18002c027  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS g_status ...
0x18002c031  mov     qword ptr cs:?g_status@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_status ...
0x18002c03c  lea     rdx, ?g_status@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18002c043  mov     rcx, cs:?g_statusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18002c04a  call    cs:__imp_SetServiceStatus
0x18002c050  test    eax, eax
0x18002c052  jnz     short loc_18002C070
0x18002c054  lea     r8d, [rax+11h]; unsigned __int16
0x18002c058  lea     r9, aSetservicestat_0; "SetServiceStatus"
0x18002c05f  mov     edx, 172h; unsigned int
0x18002c064  lea     rcx, aComComplusSrcE_8; "com\\complus\\src\\events\\tier2\\servi"...
0x18002c06b  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x18002c070  mov     rbx, [rsp+58h+arg_0]
0x18002c075  add     rsp, 50h
0x18002c079  pop     rdi
0x18002c07a  retn
0x18004536f  push    rbp
0x180045371  sub     rsp, 40h
0x180045375  mov     rbp, rdx
0x180045378  xor     edx, edx; unsigned int
0x18004537a  lea     ecx, [rdx+1]; unsigned int
0x18004537d  call    ?ReportStatusToSCM@@YAXKK@Z; ReportStatusToSCM(ulong,ulong)
0x180045382  nop
0x180045383  add     rsp, 40h
0x180045387  pop     rbp
0x180045388  retn
```
