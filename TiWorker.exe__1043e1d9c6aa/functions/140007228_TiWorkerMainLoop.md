# TiWorkerMainLoop

- ea: `0x140007228`
- end: `0x140007583`
- name: `TiWorkerMainLoop`
- size: `859`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140007004`

## callees

- `0x140002310`
- `0x1400064e8`
- `0x140006514`
- `0x140006644`
- `0x140006d44`
- `0x140007228`
- `0x14000e328`
- `0x14000ed6c`
- `0x14000f390`
- `0x140010fe0`
- `0x140011550`
- `0x140014c94`
- `0x1400150ac`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14000739c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14000739c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400072a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400072a5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140007427`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140007427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400073aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400073aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007319`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007319`

## string_xrefs

- `0x1400072e6`: `TiWorker failed to launch clean up thread.`
- `0x1400072c0`: `TiWorker failed to create cleanup cancel event.`
- `0x140007325`: `Failed to create context switcher.`
- `0x14000736d`: `Failed to initialize all COM objects.`
- `0x14000740c`: `Unable to mark CbsTemp content for deletion.`
- `0x140007447`: `DirectoryToDelete`
- `0x140007453`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide`

## pseudocode

```c
__int64 TiWorkerMainLoop()
{
  HANDLE v0; // rbx
  HANDLE EventW; // rax
  HANDLE v2; // rdi
  void *started; // rax
  HRESULT Instance; // eax
  unsigned int v5; // esi
  int v6; // eax
  DWORD v7; // eax
  signed int LastError; // eax
  bool v9; // sf
  int v10; // eax
  HKEY v11; // rcx
  unsigned int v12; // r8d
  const wchar_t *v13; // rdx
  HKEY v14; // rcx
  __int64 v15; // r8
  const wchar_t *v16; // r9
  int v17; // eax
  HANDLE hHandle; // [rsp+40h] [rbp-19h] BYREF
  HANDLE hEvent; // [rsp+48h] [rbp-11h] BYREF
  wchar_t *v21; // [rsp+50h] [rbp-9h] BYREF
  __int128 v22; // [rsp+58h] [rbp-1h] BYREF
  HANDLE Handles; // [rsp+68h] [rbp+Fh] BYREF

  CBSWdsLog(0x4000000, 0, 0, "Starting the TiWorker main loop.");
  v21 = 0;
  v0 = 0;
  hEvent = 0;
  hHandle = 0;
  v22 = 0;
  CBSWdsLog(0x4000000, 0, 0, "TiWorker starts successfully.");
  EventW = CreateEventW(0, 1, 0, 0);
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    &hEvent,
    EventW);
  v2 = hEvent;
  if ( hEvent )
  {
    started = StartCbsTempCleanup(hEvent);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      &hHandle,
      started);
    v0 = hHandle;
    if ( !hHandle )
      CBSWdsLog(0x4000000, 0, 0, "TiWorker failed to launch clean up thread.");
  }
  else
  {
    CBSWdsLog(0x4000000, 0, 0, "TiWorker failed to create cleanup cancel event.");
  }
  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, &ppv);
  v5 = Instance;
  if ( Instance >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(), __int128 *, GUID *, int, _QWORD))(*(_QWORD *)ppv + 24LL))(
           ppv,
           ConnectCallback,
           &v22,
           &GUID_000001da_0000_0000_c000_000000000046,
           5,
           0);
    v5 = v6;
    if ( v6 >= 0 )
    {
      do
      {
        Handles = vhShutdownEvent;
        v7 = WaitForMultipleObjectsEx(1u, &Handles, 0, 0xFFFFFFFF, 0);
        if ( !v7 )
        {
          CBSWdsLog(0x4000000, 0, 0, "TiWorker signaled for shutdown, going to exit.");
          goto LABEL_16;
        }
      }
      while ( v7 != -1 );
      LastError = GetLastError();
      v9 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v9 = LastError < 0;
      }
      if ( v9 )
        CBSWdsLog(0x4000000, (unsigned int)LastError, 1, "Unable to wait for shutdown event... shutting down.");
LABEL_16:
      if ( vpfnCbsCoreSetState )
        vpfnCbsCoreSetState(10);
      v10 = MarkCbsTempContentForDeletion();
      if ( v10 < 0 )
        CBSWdsLog(0x4000000, (unsigned int)v10, 1, "Unable to mark CbsTemp content for deletion.");
      SetEvent(vhWorkerExitEvent);
      if ( vpfnCbsCoreSetState )
        vpfnCbsCoreSetState(7);
      if ( CbsRegQueryStringValue(
             v11,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide",
             v12,
             L"DirectoryToDelete",
             &v21) >= 0 )
      {
        if ( (unsigned __int8)DoesDirectoryExist(v21) )
          RecursiveRemoveDirectoryEx(14, v21, v15, 0);
        CbsRegDeleteValue(v14, v13, v15, v16);
      }
      if ( CloseoutCleanUpThread(v0, v2) )
      {
        Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hHandle);
        Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hEvent);
        v2 = hEvent;
        v0 = hHandle;
      }
      v17 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(), __int128 *, GUID *, int, _QWORD))(*(_QWORD *)ppv + 24LL))(
              ppv,
              DisconnectCallback,
              &v22,
              &GUID_000001da_0000_0000_c000_000000000046,
              5,
              0);
      v5 = v17;
      if ( v17 < 0 )
        CBSWdsLog(0x4000000, (unsigned int)v17, 1, "Unable to disconnect all objects.");
    }
    else
    {
      CBSWdsLog(0x4000000, (unsigned int)v6, 1, "Failed to initialize all COM objects.");
    }
  }
  else
  {
    CBSWdsLog(0x4000000, (unsigned int)Instance, 1, "Failed to create context switcher.");
  }
  if ( v0 && v2 )
    CloseoutCleanUpThread(v0, v2);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  CBSWdsLog(0x4000000, 0, 0, "Ending the TiWorker main loop.");
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hHandle);
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hEvent);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v21);
  return v5;
}

```

## disassembly

```asm
0x140007228  push    rbp
0x14000722a  push    rbx
0x14000722b  push    rsi
0x14000722c  push    rdi
0x14000722d  push    r12
0x14000722f  push    r15
0x140007231  lea     rbp, [rsp-2Fh]
0x140007236  sub     rsp, 88h
0x14000723d  mov     rax, cs:__security_cookie
0x140007244  xor     rax, rsp
0x140007247  mov     [rbp+57h+var_40], rax
0x14000724b  mov     r15d, 4000000h
0x140007251  lea     r9, aStartingTheTiw; "Starting the TiWorker main loop."
0x140007258  mov     ecx, r15d
0x14000725b  xor     r8d, r8d
0x14000725e  xor     edx, edx
0x140007260  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007265  xorps   xmm0, xmm0
0x140007268  mov     [rbp+57h+var_60], 0
0x140007270  xor     ebx, ebx
0x140007272  mov     [rbp+57h+hEvent], 0
0x14000727a  lea     r9, aTiworkerStarts; "TiWorker starts successfully."
0x140007281  mov     [rbp+57h+hHandle], rbx
0x140007285  xor     r8d, r8d
0x140007288  xor     edx, edx
0x14000728a  mov     ecx, r15d
0x14000728d  movups  [rbp+57h+var_58], xmm0
0x140007291  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007296  lea     r12d, [rbx+1]
0x14000729a  xor     r9d, r9d; lpName
0x14000729d  mov     edx, r12d; bManualReset
0x1400072a0  xor     r8d, r8d; bInitialState
0x1400072a3  xor     ecx, ecx; lpEventAttributes
0x1400072a5  call    cs:__imp_CreateEventW
0x1400072ab  mov     rdx, rax
0x1400072ae  lea     rcx, [rbp+57h+hEvent]
0x1400072b2  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x1400072b7  mov     rdi, [rbp+57h+hEvent]
0x1400072bb  test    rdi, rdi
0x1400072be  jnz     short loc_1400072C9
0x1400072c0  lea     r9, aTiworkerFailed; "TiWorker failed to create cleanup cance"...
0x1400072c7  jmp     short loc_1400072ED
0x1400072c9  mov     rcx, rdi; lpParameter
0x1400072cc  call    ?StartCbsTempCleanup@@YAPEAXPEAX@Z; StartCbsTempCleanup(void *)
0x1400072d1  mov     rdx, rax
0x1400072d4  lea     rcx, [rbp+57h+hHandle]
0x1400072d8  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x1400072dd  mov     rbx, [rbp+57h+hHandle]
0x1400072e1  test    rbx, rbx
0x1400072e4  jnz     short loc_1400072FA
0x1400072e6  lea     r9, aTiworkerFailed_0; "TiWorker failed to launch clean up thre"...
0x1400072ed  xor     r8d, r8d
0x1400072f0  xor     edx, edx
0x1400072f2  mov     ecx, r15d
0x1400072f5  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400072fa  lea     rax, ppv
0x140007301  mov     r8d, r12d; dwClsContext
0x140007304  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x14000730b  mov     [rsp+0B0h+ppv], rax; ppv
0x140007310  xor     edx, edx; pUnkOuter
0x140007312  lea     rcx, CLSID_ContextSwitcher; rclsid
0x140007319  call    cs:__imp_CoCreateInstance
0x14000731f  mov     esi, eax
0x140007321  test    eax, eax
0x140007323  jns     short loc_140007331
0x140007325  lea     r9, aFailedToCreate_7; "Failed to create context switcher."
0x14000732c  jmp     loc_1400074F1
0x140007331  mov     rcx, cs:ppv
0x140007338  lea     r9, _GUID_000001da_0000_0000_c000_000000000046
0x14000733f  mov     [rsp+0B0h+var_88], 0
0x140007348  lea     r8, [rbp+57h+var_58]
0x14000734c  lea     rdx, ConnectCallback
0x140007353  mov     dword ptr [rsp+0B0h+ppv], 5
0x14000735b  mov     rax, [rcx]
0x14000735e  mov     rax, [rax+18h]
0x140007362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007367  mov     esi, eax
0x140007369  test    eax, eax
0x14000736b  jns     short loc_140007379
0x14000736d  lea     r9, aFailedToInitia_4; "Failed to initialize all COM objects."
0x140007374  jmp     loc_1400074F1
0x140007379  or      esi, 0FFFFFFFFh
0x14000737c  mov     rax, cs:?vhShutdownEvent@@3PEAXEA; void * vhShutdownEvent
0x140007383  lea     rdx, [rbp+57h+Handles]; lpHandles
0x140007387  mov     r9d, esi; dwMilliseconds
0x14000738a  mov     [rbp+57h+Handles], rax
0x14000738e  xor     r8d, r8d; bWaitAll
0x140007391  mov     dword ptr [rsp+0B0h+ppv], 0; bAlertable
0x140007399  mov     ecx, r12d; nCount
0x14000739c  call    cs:__imp_WaitForMultipleObjectsEx
0x1400073a2  test    eax, eax
0x1400073a4  jz      short loc_1400073D6
0x1400073a6  cmp     eax, esi
0x1400073a8  jnz     short loc_14000737C
0x1400073aa  call    cs:__imp_GetLastError
0x1400073b0  test    eax, eax
0x1400073b2  jle     short loc_1400073BE
0x1400073b4  movzx   eax, ax
0x1400073b7  or      eax, 80070000h
0x1400073bc  test    eax, eax
0x1400073be  jns     short loc_1400073EA
0x1400073c0  lea     r9, aUnableToWaitFo; "Unable to wait for shutdown event... sh"...
0x1400073c7  mov     r8d, r12d
0x1400073ca  mov     edx, eax
0x1400073cc  mov     ecx, r15d
0x1400073cf  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400073d4  jmp     short loc_1400073EA
0x1400073d6  lea     r9, aTiworkerSignal; "TiWorker signaled for shutdown, going t"...
0x1400073dd  xor     r8d, r8d
0x1400073e0  xor     edx, edx
0x1400073e2  mov     ecx, r15d
0x1400073e5  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400073ea  mov     rax, cs:?vpfnCbsCoreSetState@@3P6AJW4CBS_CORE_STATE@@_K@ZEA; long (*vpfnCbsCoreSetState)(CBS_CORE_STATE,unsigned __int64)
0x1400073f1  test    rax, rax
0x1400073f4  jz      short loc_140007403
0x1400073f6  mov     edx, 14h
0x1400073fb  lea     ecx, [rdx-0Ah]
0x1400073fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007403  call    ?MarkCbsTempContentForDeletion@@YAJXZ; MarkCbsTempContentForDeletion(void)
0x140007408  test    eax, eax
0x14000740a  jns     short loc_140007420
0x14000740c  lea     r9, aUnableToMarkCb; "Unable to mark CbsTemp content for dele"...
0x140007413  mov     r8d, r12d
0x140007416  mov     edx, eax
0x140007418  mov     ecx, r15d
0x14000741b  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007420  mov     rcx, cs:?vhWorkerExitEvent@@3PEAXEA; hEvent
0x140007427  call    cs:__imp_SetEvent
0x14000742d  mov     rax, cs:?vpfnCbsCoreSetState@@3P6AJW4CBS_CORE_STATE@@_K@ZEA; long (*vpfnCbsCoreSetState)(CBS_CORE_STATE,unsigned __int64)
0x140007434  test    rax, rax
0x140007437  jz      short loc_140007443
0x140007439  xor     edx, edx
0x14000743b  lea     ecx, [rdx+7]
0x14000743e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007443  lea     rax, [rbp+57h+var_60]
0x140007447  lea     r9, aDirectorytodel; "DirectoryToDelete"
0x14000744e  mov     [rsp+0B0h+ppv], rax; wchar_t **
0x140007453  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14000745a  call    ?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z; CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)
0x14000745f  test    eax, eax
0x140007461  js      short loc_140007485
0x140007463  mov     rcx, [rbp+57h+var_60]
0x140007467  call    DoesDirectoryExist
0x14000746c  test    al, al
0x14000746e  jz      short loc_140007480
0x140007470  mov     rdx, [rbp+57h+var_60]; wchar_t *
0x140007474  xor     r9d, r9d
0x140007477  lea     ecx, [r9+0Eh]; unsigned int
0x14000747b  call    RecursiveRemoveDirectoryEx
0x140007480  call    ?CbsRegDeleteValue@@YAJPEAUHKEY__@@PEB_WK1@Z; CbsRegDeleteValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x140007485  mov     rdx, rdi; hEvent
0x140007488  mov     rcx, rbx; hHandle
0x14000748b  call    ?CloseoutCleanUpThread@@YA_NPEAX0@Z; CloseoutCleanUpThread(void *,void *)
0x140007490  test    al, al
0x140007492  jz      short loc_1400074AE
0x140007494  lea     rcx, [rbp+57h+hHandle]
0x140007498  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x14000749d  lea     rcx, [rbp+57h+hEvent]
0x1400074a1  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1400074a6  mov     rdi, [rbp+57h+hEvent]
0x1400074aa  mov     rbx, [rbp+57h+hHandle]
0x1400074ae  mov     rcx, cs:ppv
0x1400074b5  lea     r9, _GUID_000001da_0000_0000_c000_000000000046
0x1400074bc  mov     [rsp+0B0h+var_88], 0
0x1400074c5  lea     r8, [rbp+57h+var_58]
0x1400074c9  lea     rdx, DisconnectCallback
0x1400074d0  mov     dword ptr [rsp+0B0h+ppv], 5
0x1400074d8  mov     rax, [rcx]
0x1400074db  mov     rax, [rax+18h]
0x1400074df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074e4  mov     esi, eax
0x1400074e6  test    eax, eax
0x1400074e8  jns     short loc_1400074FE
0x1400074ea  lea     r9, aUnableToDiscon; "Unable to disconnect all objects."
0x1400074f1  mov     r8d, r12d
0x1400074f4  mov     edx, eax
0x1400074f6  mov     ecx, r15d
0x1400074f9  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400074fe  test    rbx, rbx
0x140007501  jz      short loc_140007513
0x140007503  test    rdi, rdi
0x140007506  jz      short loc_140007513
0x140007508  mov     rdx, rdi; hEvent
0x14000750b  mov     rcx, rbx; hHandle
0x14000750e  call    ?CloseoutCleanUpThread@@YA_NPEAX0@Z; CloseoutCleanUpThread(void *,void *)
0x140007513  mov     rcx, cs:ppv
0x14000751a  test    rcx, rcx
0x14000751d  jz      short loc_140007536
0x14000751f  mov     rax, [rcx]
0x140007522  mov     rax, [rax+10h]
0x140007526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000752b  mov     cs:ppv, 0
0x140007536  lea     r9, aEndingTheTiwor; "Ending the TiWorker main loop."
0x14000753d  xor     r8d, r8d
0x140007540  xor     edx, edx
0x140007542  mov     ecx, r15d
0x140007545  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000754a  lea     rcx, [rbp+57h+hHandle]
0x14000754e  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x140007553  lea     rcx, [rbp+57h+hEvent]
0x140007557  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x14000755c  lea     rcx, [rbp+57h+var_60]
0x140007560  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140007565  mov     eax, esi
0x140007567  mov     rcx, [rbp+57h+var_40]
0x14000756b  xor     rcx, rsp; StackCookie
0x14000756e  call    __security_check_cookie
0x140007573  add     rsp, 88h
0x14000757a  pop     r15
0x14000757c  pop     r12
0x14000757e  pop     rdi
0x14000757f  pop     rsi
0x140007580  pop     rbx
0x140007581  pop     rbp
0x140007582  retn
```
