# BdeSvcOnWorkComplete(_TP_CALLBACK_INSTANCE *)

- ea: `0x180004cb0`
- end: `0x1800050bc`
- name: `?BdeSvcOnWorkComplete@@YAXPEAU_TP_CALLBACK_INSTANCE@@@Z`
- size: `1036`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE pci)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800042f0`
- `0x180004974`
- `0x180004cb0`
- `0x180006260`
- `0x180009f30`
- `0x180009f60`
- `0x18002a718`
- `0x18002a774`
- `0x18002a7b8`
- `0x18002cac4`
- `0x180030508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005043`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005043`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005027`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005027`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004dea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004dea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004cee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004cee`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x180005077`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x180005077`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005057`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180004e90`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180004fb3`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180004e90`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180004fb3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004d56`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004d56`

## pseudocode

```c
void __fastcall BdeSvcOnWorkComplete(PTP_CALLBACK_INSTANCE pci)
{
  HANDLE ProcessHeap; // rbx
  void ***v3; // rdx
  unsigned int *v4; // r9
  _QWORD **v5; // r8
  _QWORD *v6; // rcx
  _QWORD **v7; // rcx
  __int64 v8; // r9
  _QWORD *v9; // r9
  int v10; // eax
  _QWORD *v11; // r9
  _QWORD *v12; // r9
  void *v13; // rbx
  struct HCMNOTIFICATION__ *v14; // rax
  unsigned int v15; // eax
  void *v16; // rbx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
  ProcessHeap = GetProcessHeap();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
  if ( g_hStatus )
  {
    EnterCriticalSection(&g_serviceStatusLock);
    *(_QWORD *)&g_serviceStatus.dwCurrentState = 3;
    SetServiceStatus(g_hStatus, &g_serviceStatus);
    LeaveCriticalSection(&g_serviceStatusLock);
  }
  BdeSvcRpcUnregisterServer();
  EnterCriticalSection(&g_svcCtlInfo);
  while ( 1 )
  {
    v3 = (void ***)qword_18009B9F8;
    if ( !*(_QWORD *)(qword_18009B9F8 + 8) )
      break;
    v4 = *(unsigned int **)(**(_QWORD **)qword_18009B9F8 + 16LL);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, *v4);
        v3 = (void ***)qword_18009B9F8;
      }
      HeapFree(ProcessHeap, 0, *((LPVOID *)**v3 + 2));
      v3 = (void ***)qword_18009B9F8;
    }
    v5 = (_QWORD **)**v3;
    v6 = *v5;
    v3[1] = (void **)((char *)v3[1] - 1);
    *v5[1] = v6;
    v6[1] = v5[1];
    std::_Deallocate<16>(v5, (struct std::nothrow_t *)0x18);
  }
  while ( 1 )
  {
    v7 = (_QWORD **)qword_18009B9F0;
    if ( !*(_QWORD *)(qword_18009B9F0 + 8) )
      break;
    v8 = **(_QWORD **)qword_18009B9F0;
    if ( *(_QWORD *)(v8 + 64) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v9 = (_QWORD *)(v8 + 32);
        if ( v9[3] > 7u )
          v9 = (_QWORD *)*v9;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, v9);
        v7 = (_QWORD **)qword_18009B9F0;
      }
      v10 = CM_Unregister_Notification(*(_QWORD *)(**v7 + 64LL));
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v11 = (_QWORD *)(**(_QWORD **)qword_18009B9F0 + 32LL);
          if ( *(_QWORD *)(**(_QWORD **)qword_18009B9F0 + 56LL) > 7u )
            v11 = (_QWORD *)*v11;
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            142,
            (unsigned int)WPP_ee35f73b350036074f815e40b51ef636_Traceguids,
            (_DWORD)v11,
            v10);
        }
      }
      else
      {
        _InterlockedDecrement(&dword_18009B9E8);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v12 = (_QWORD *)(**(_QWORD **)qword_18009B9F0 + 32LL);
          if ( *(_QWORD *)(**(_QWORD **)qword_18009B9F0 + 56LL) > 7u )
            v12 = (_QWORD *)*v12;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, v12);
        }
      }
      v7 = (_QWORD **)qword_18009B9F0;
    }
    v13 = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CSessionState>>>>::_Extract(
                    v7,
                    **v7);
    std::wstring::~wstring((__int64)v13 + 32);
    std::_Deallocate<16>(v13, (struct std::nothrow_t *)0x48);
  }
  LeaveCriticalSection(&g_svcCtlInfo);
  v14 = hDevNotify;
  if ( hDevNotify )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
      v14 = hDevNotify;
    }
    v15 = CM_Unregister_Notification(v14);
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, v15);
    }
    else
    {
      _InterlockedDecrement(&dword_18009B9E8);
      hDevNotify = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
    }
  }
  AcquireSRWLockExclusive(&g_srwlStopEvent);
  v16 = (void *)_InterlockedExchange64((volatile __int64 *)&g_hStopEvent, 0);
  ReleaseSRWLockExclusive(&g_srwlStopEvent);
  if ( v16 )
    CloseHandle(v16);
  CBdeSvcSharedState::Cleanup();
  if ( pci )
    SetEventWhenCallbackReturns(pci, g_hSvchostStopEvent);
  else
    BdeSvcStop(0, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
}

```

## disassembly

```asm
0x180004cb0  push    rbx
0x180004cb2  push    rbp
0x180004cb3  push    rdi
0x180004cb4  push    r14
0x180004cb6  sub     rsp, 38h
0x180004cba  mov     rdi, rcx
0x180004cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cc4  lea     rbp, WPP_GLOBAL_Control
0x180004ccb  lea     r14, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x180004cd2  cmp     rcx, rbp
0x180004cd5  jz      short loc_180004CEE
0x180004cd7  test    byte ptr [rcx+1Ch], 20h
0x180004cdb  jz      short loc_180004CEE
0x180004cdd  mov     rcx, [rcx+10h]
0x180004ce1  mov     edx, 8Ah
0x180004ce6  mov     r8, r14
0x180004ce9  call    WPP_SF_
0x180004cee  call    cs:__imp_GetProcessHeap
0x180004cf5  nop     dword ptr [rax+rax+00h]
0x180004cfa  mov     rbx, rax
0x180004cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d04  cmp     rcx, rbp
0x180004d07  jz      short loc_180004D20
0x180004d09  test    byte ptr [rcx+1Ch], 8
0x180004d0d  jz      short loc_180004D20
0x180004d0f  mov     rcx, [rcx+10h]
0x180004d13  mov     edx, 8Bh
0x180004d18  mov     r8, r14
0x180004d1b  call    WPP_SF_
0x180004d20  cmp     cs:?g_hStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA, 0; SERVICE_STATUS_HANDLE__ * g_hStatus
0x180004d28  jz      short loc_180004D75
0x180004d2a  lea     rcx, ?g_serviceStatusLock@@3VCAutoCS@@A; lpCriticalSection
0x180004d31  call    cs:__imp_EnterCriticalSection
0x180004d38  nop     dword ptr [rax+rax+00h]
0x180004d3d  mov     rcx, cs:?g_hStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180004d44  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180004d4b  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_serviceStatus ...
0x180004d56  call    cs:__imp_SetServiceStatus
0x180004d5d  nop     dword ptr [rax+rax+00h]
0x180004d62  lea     rcx, ?g_serviceStatusLock@@3VCAutoCS@@A; lpCriticalSection
0x180004d69  call    cs:__imp_LeaveCriticalSection
0x180004d70  nop     dword ptr [rax+rax+00h]
0x180004d75  call    ?BdeSvcRpcUnregisterServer@@YAXXZ; BdeSvcRpcUnregisterServer(void)
0x180004d7a  lea     rcx, ?g_svcCtlInfo@@3U_BDESVC_SVC_CTL_INFO@@A; lpCriticalSection
0x180004d81  call    cs:__imp_EnterCriticalSection
0x180004d88  nop     dword ptr [rax+rax+00h]
0x180004d8d  mov     rdx, cs:qword_18009B9F8
0x180004d94  cmp     qword ptr [rdx+8], 0
0x180004d99  jz      loc_180004E2B
0x180004d9f  mov     rax, [rdx]
0x180004da2  mov     rcx, [rax]
0x180004da5  mov     r9, [rcx+10h]
0x180004da9  test    r9, r9
0x180004dac  jz      short loc_180004DFD
0x180004dae  mov     rcx, cs:WPP_GLOBAL_Control
0x180004db5  cmp     rcx, rbp
0x180004db8  jz      short loc_180004DDB
0x180004dba  test    byte ptr [rcx+1Ch], 8
0x180004dbe  jz      short loc_180004DDB
0x180004dc0  mov     r9d, [r9]
0x180004dc3  mov     edx, 8Ch
0x180004dc8  mov     rcx, [rcx+10h]
0x180004dcc  mov     r8, r14
0x180004dcf  call    WPP_SF_d
0x180004dd4  mov     rdx, cs:qword_18009B9F8
0x180004ddb  mov     rax, [rdx]
0x180004dde  mov     rcx, rbx; hHeap
0x180004de1  xor     edx, edx; dwFlags
0x180004de3  mov     r8, [rax]
0x180004de6  mov     r8, [r8+10h]; lpMem
0x180004dea  call    cs:__imp_HeapFree
0x180004df1  nop     dword ptr [rax+rax+00h]
0x180004df6  mov     rdx, cs:qword_18009B9F8
0x180004dfd  mov     rax, [rdx]
0x180004e00  mov     r8, [rax]
0x180004e03  mov     rcx, [r8]
0x180004e06  dec     qword ptr [rdx+8]
0x180004e0a  mov     edx, 18h
0x180004e0f  mov     rax, [r8+8]
0x180004e13  mov     [rax], rcx
0x180004e16  mov     rax, [r8+8]
0x180004e1a  mov     [rcx+8], rax
0x180004e1e  mov     rcx, r8
0x180004e21  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180004e26  jmp     loc_180004D8D
0x180004e2b  mov     rcx, cs:qword_18009B9F0
0x180004e32  cmp     qword ptr [rcx+8], 0
0x180004e37  jz      loc_180004F63
0x180004e3d  mov     rax, [rcx]
0x180004e40  mov     r9, [rax]
0x180004e43  cmp     qword ptr [r9+40h], 0
0x180004e48  jz      loc_180004F3A
0x180004e4e  mov     rax, cs:WPP_GLOBAL_Control
0x180004e55  cmp     rax, rbp
0x180004e58  jz      short loc_180004E86
0x180004e5a  test    byte ptr [rax+1Ch], 8
0x180004e5e  jz      short loc_180004E86
0x180004e60  add     r9, 20h ; ' '
0x180004e64  cmp     qword ptr [r9+18h], 7
0x180004e69  jbe     short loc_180004E6E
0x180004e6b  mov     r9, [r9]
0x180004e6e  mov     rcx, [rax+10h]
0x180004e72  mov     edx, 8Dh
0x180004e77  mov     r8, r14
0x180004e7a  call    WPP_SF_S
0x180004e7f  mov     rcx, cs:qword_18009B9F0
0x180004e86  mov     rax, [rcx]
0x180004e89  mov     rcx, [rax]
0x180004e8c  mov     rcx, [rcx+40h]
0x180004e90  call    cs:__imp_CM_Unregister_Notification
0x180004e97  nop     dword ptr [rax+rax+00h]
0x180004e9c  mov     r8d, eax
0x180004e9f  test    eax, eax
0x180004ea1  jz      short loc_180004EED
0x180004ea3  mov     r10, cs:WPP_GLOBAL_Control
0x180004eaa  cmp     r10, rbp
0x180004ead  jz      loc_180004F33
0x180004eb3  test    byte ptr [r10+1Ch], 2
0x180004eb8  jz      short loc_180004F33
0x180004eba  mov     rcx, cs:qword_18009B9F0
0x180004ec1  mov     rax, [rcx]
0x180004ec4  mov     r9, [rax]
0x180004ec7  add     r9, 20h ; ' '
0x180004ecb  cmp     qword ptr [r9+18h], 7
0x180004ed0  jbe     short loc_180004ED5
0x180004ed2  mov     r9, [r9]
0x180004ed5  mov     rcx, [r10+10h]
0x180004ed9  mov     edx, 8Eh
0x180004ede  mov     [rsp+58h+var_38], r8d
0x180004ee3  mov     r8, r14
0x180004ee6  call    WPP_SF_Sd
0x180004eeb  jmp     short loc_180004F33
0x180004eed  lock dec cs:dword_18009B9E8
0x180004ef4  mov     r10, cs:WPP_GLOBAL_Control
0x180004efb  cmp     r10, rbp
0x180004efe  jz      short loc_180004F33
0x180004f00  test    byte ptr [r10+1Ch], 8
0x180004f05  jz      short loc_180004F33
0x180004f07  mov     rax, cs:qword_18009B9F0
0x180004f0e  mov     rcx, [rax]
0x180004f11  mov     r9, [rcx]
0x180004f14  add     r9, 20h ; ' '
0x180004f18  cmp     qword ptr [r9+18h], 7
0x180004f1d  jbe     short loc_180004F22
0x180004f1f  mov     r9, [r9]
0x180004f22  mov     rcx, [r10+10h]
0x180004f26  mov     edx, 8Fh
0x180004f2b  mov     r8, r14
0x180004f2e  call    WPP_SF_S
0x180004f33  mov     rcx, cs:qword_18009B9F0
0x180004f3a  mov     rdx, [rcx]
0x180004f3d  mov     rdx, [rdx]
0x180004f40  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VCSessionState@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VCSessionState@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VCSessionState@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CSessionState>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CSessionState>>>>,std::_Iterator_base0>)
0x180004f45  mov     rbx, rax
0x180004f48  lea     rcx, [rax+20h]
0x180004f4c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004f51  mov     edx, 48h ; 'H'
0x180004f56  mov     rcx, rbx
0x180004f59  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180004f5e  jmp     loc_180004E2B
0x180004f63  lea     rcx, ?g_svcCtlInfo@@3U_BDESVC_SVC_CTL_INFO@@A; lpCriticalSection
0x180004f6a  call    cs:__imp_LeaveCriticalSection
0x180004f71  nop     dword ptr [rax+rax+00h]
0x180004f76  mov     rax, cs:?hDevNotify@@3PEAUHCMNOTIFICATION__@@EA; HCMNOTIFICATION__ * hDevNotify
0x180004f7d  test    rax, rax
0x180004f80  jz      loc_180005020
0x180004f86  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f8d  cmp     rcx, rbp
0x180004f90  jz      short loc_180004FB0
0x180004f92  test    byte ptr [rcx+1Ch], 8
0x180004f96  jz      short loc_180004FB0
0x180004f98  mov     rcx, [rcx+10h]
0x180004f9c  mov     edx, 90h
0x180004fa1  mov     r8, r14
0x180004fa4  call    WPP_SF_
0x180004fa9  mov     rax, cs:?hDevNotify@@3PEAUHCMNOTIFICATION__@@EA; HCMNOTIFICATION__ * hDevNotify
0x180004fb0  mov     rcx, rax
0x180004fb3  call    cs:__imp_CM_Unregister_Notification
0x180004fba  nop     dword ptr [rax+rax+00h]
0x180004fbf  test    eax, eax
0x180004fc1  jz      short loc_180004FEB
0x180004fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fca  cmp     rcx, rbp
0x180004fcd  jz      short loc_180005020
0x180004fcf  test    byte ptr [rcx+1Ch], 2
0x180004fd3  jz      short loc_180005020
0x180004fd5  mov     rcx, [rcx+10h]
0x180004fd9  mov     edx, 91h
0x180004fde  mov     r9d, eax
0x180004fe1  mov     r8, r14
0x180004fe4  call    WPP_SF_d
0x180004fe9  jmp     short loc_180005020
0x180004feb  lock dec cs:dword_18009B9E8
0x180004ff2  mov     cs:?hDevNotify@@3PEAUHCMNOTIFICATION__@@EA, 0; HCMNOTIFICATION__ * hDevNotify
0x180004ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005004  cmp     rcx, rbp
0x180005007  jz      short loc_180005020
0x180005009  test    byte ptr [rcx+1Ch], 8
0x18000500d  jz      short loc_180005020
0x18000500f  mov     rcx, [rcx+10h]
0x180005013  mov     edx, 92h
0x180005018  mov     r8, r14
0x18000501b  call    WPP_SF_
0x180005020  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x180005027  call    cs:__imp_AcquireSRWLockExclusive
0x18000502e  nop     dword ptr [rax+rax+00h]
0x180005033  xor     ebx, ebx
0x180005035  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000503c  xchg    rbx, cs:?g_hStopEvent@@3REAXEA; void * g_hStopEvent
0x180005043  call    cs:__imp_ReleaseSRWLockExclusive
0x18000504a  nop     dword ptr [rax+rax+00h]
0x18000504f  test    rbx, rbx
0x180005052  jz      short loc_180005063
0x180005054  mov     rcx, rbx; hObject
0x180005057  call    cs:__imp_CloseHandle
0x18000505e  nop     dword ptr [rax+rax+00h]
0x180005063  call    ?Cleanup@CBdeSvcSharedState@@SAKXZ; CBdeSvcSharedState::Cleanup(void)
0x180005068  test    rdi, rdi
0x18000506b  jz      short loc_180005085
0x18000506d  mov     rdx, cs:?g_hSvchostStopEvent@@3PEAXEA; evt
0x180005074  mov     rcx, rdi; pci
0x180005077  call    cs:__imp_SetEventWhenCallbackReturns
0x18000507e  nop     dword ptr [rax+rax+00h]
0x180005083  jmp     short loc_18000508E
0x180005085  xor     edx, edx; unsigned __int8
0x180005087  xor     ecx, ecx; void *
0x180005089  call    ?BdeSvcStop@@YAXPEAXE@Z; BdeSvcStop(void *,uchar)
0x18000508e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005095  cmp     rcx, rbp
0x180005098  jz      short loc_1800050B1
0x18000509a  test    byte ptr [rcx+1Ch], 20h
0x18000509e  jz      short loc_1800050B1
0x1800050a0  mov     rcx, [rcx+10h]
0x1800050a4  mov     edx, 93h
0x1800050a9  mov     r8, r14
0x1800050ac  call    WPP_SF_
0x1800050b1  add     rsp, 38h
0x1800050b5  pop     r14
0x1800050b7  pop     rdi
0x1800050b8  pop     rbp
0x1800050b9  pop     rbx
0x1800050ba  retn
```
