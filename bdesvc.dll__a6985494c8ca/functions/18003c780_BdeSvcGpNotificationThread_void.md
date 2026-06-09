# BdeSvcGpNotificationThread(void *)

- ea: `0x18003c780`
- end: `0x18003cd0b`
- name: `?BdeSvcGpNotificationThread@@YAIPEAX@Z`
- size: `1419`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180005374`
- `0x1800053a0`
- `0x1800065b8`
- `0x180007d10`
- `0x180009c30`
- `0x180009f30`
- `0x180009f60`
- `0x18001b8c0`
- `0x18001bdb0`
- `0x18002c84c`
- `0x18002dd88`
- `0x180034070`
- `0x18003c780`
- `0x180044534`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c9d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cc1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c9d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cc1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ca47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cbdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cc4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ca47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cbdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cc4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003ca1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003ca1e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18003ca6d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18003ca6d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003ca04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003ca04`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003c81d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003c81d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c88a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ca7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c88a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ca7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cbc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cc07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cc35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cbc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cc07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cc35`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c7eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c973`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c9b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c7eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c973`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c9b6`
- `api-ms-win-security-grouppolicy-l1-1-0!UnregisterGPNotificationInternal` at `0x18003cbea`
- `api-ms-win-security-grouppolicy-l1-1-0!UnregisterGPNotificationInternal` at `0x18003cbea`
- `api-ms-win-security-grouppolicy-l1-1-0!RegisterGPNotificationInternal` at `0x18003c87a`
- `api-ms-win-security-grouppolicy-l1-1-0!RegisterGPNotificationInternal` at `0x18003c87a`

## pseudocode

```c
__int64 __fastcall BdeSvcGpNotificationThread(void *a1)
{
  int v1; // r12d
  char v2; // r13
  ULONGLONG TickCount64; // rbx
  DWORD v4; // esi
  void *v5; // rdi
  HANDLE EventW; // rax
  void *v7; // r15
  DWORD LastError; // eax
  DWORD v9; // eax
  char v10; // bp
  ULONGLONG v11; // r14
  int v12; // eax
  int v13; // eax
  HANDLE v14; // rbx
  DWORD v15; // ebx
  DWORD v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  BdeSvcWorkTracking *v19; // rcx
  void *v21; // [rsp+30h] [rbp-78h] BYREF
  HANDLE Handles[2]; // [rsp+38h] [rbp-70h] BYREF
  void *v23; // [rsp+48h] [rbp-60h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  v1 = 0;
  *(_OWORD *)Handles = 0;
  v23 = 0;
  v21 = 0;
  v2 = 0;
  TickCount64 = GetTickCount64();
  v4 = AllocVolumeMap(&v21);
  v5 = v21;
  if ( v4 )
    goto LABEL_56;
  EventW = CreateEventW(0, 0, 0, 0);
  v7 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, LastError);
    goto LABEL_56;
  }
  if ( (unsigned int)RegisterGPNotificationInternal(EventW, 1) )
  {
    v10 = 1;
    v11 = TickCount64 + 3600000;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !v10 )
        {
LABEL_54:
          UnregisterGPNotificationInternal(v7);
          goto LABEL_55;
        }
        std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::clear(v5);
        EnumVolumes((__int64)v5, 0, 0, 1, 1);
        ++v1;
        v12 = BdeSvcApplyRecoveryPolicy();
        if ( v12 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
            (unsigned int)v12);
        BdeSvcApplyGroupPolicy(v5);
        v13 = CBdeSvcDE::NotifyGPUpdate();
        if ( v13 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
            (unsigned int)v13);
        if ( GetTickCount64() >= v11 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
          BdeSvcSqmDataPush(v5);
          v2 = 1;
          v11 = GetTickCount64() + 43200000;
        }
        v21 = &g_lockGpNotificationThreadMgmt;
        EnterCriticalSection(&g_lockGpNotificationThreadMgmt);
        if ( !(unsigned int)BdeSvcManageGpNotificationThread(v5) && !g_bPcrMon )
        {
          if ( g_hGpNotificationThreadStopEvent )
          {
            CloseHandle(g_hGpNotificationThreadStopEvent);
            g_hGpNotificationThreadStopEvent = 0;
          }
          LeaveCriticalSection(&g_lockGpNotificationThreadMgmt);
          goto LABEL_54;
        }
        AcquireSRWLockShared(&g_srwlStopEvent);
        v14 = g_hStopEvent;
        ReleaseSRWLockShared(&g_srwlStopEvent);
        Handles[0] = v14;
        Handles[1] = g_hGpNotificationThreadStopEvent;
        v23 = v7;
        LeaveCriticalSection(&g_lockGpNotificationThreadMgmt);
        v15 = WaitForMultipleObjectsEx(3u, Handles, 0, 0x36EE80u, 0);
        v16 = GetLastError();
        v4 = v16;
        if ( !v15 )
          break;
        switch ( v15 )
        {
          case 1u:
            v10 = 0;
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v18 = 56;
              goto LABEL_50;
            }
            break;
          case 2u:
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v18 = 57;
              goto LABEL_50;
            }
            break;
          case 0x102u:
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v18 = 58;
              goto LABEL_50;
            }
            break;
          case 0xFFFFFFFF:
            v10 = 0;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v16);
            break;
        }
      }
      v10 = 0;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v18 = 55;
LABEL_50:
        WPP_SF_(v17[2], v18, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
      }
    }
  }
  v9 = GetLastError();
  v4 = v9;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v9);
LABEL_55:
  CloseHandle(v7);
LABEL_56:
  EnterCriticalSection(&g_lockGpNotificationThreadMgmt);
  if ( g_hGpNotificationThreadStopEvent )
  {
    CloseHandle(g_hGpNotificationThreadStopEvent);
    g_hGpNotificationThreadStopEvent = 0;
  }
  LeaveCriticalSection(&g_lockGpNotificationThreadMgmt);
  if ( v5 )
  {
    if ( !v1 )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::clear(v5);
      EnumVolumes((__int64)v5, 0, 0, 1, 1);
      BdeSvcApplyGroupPolicy(v5);
    }
    if ( !v2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
      BdeSvcSqmDataPush(v5);
    }
    FreeVolumeMap(v5);
  }
  BdeSvcWorkTracking::FinishWorkImpl(v19);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  return v4;
}

```

## disassembly

```asm
0x18003c780  push    rbx
0x18003c782  push    rbp
0x18003c783  push    rsi
0x18003c784  push    rdi
0x18003c785  push    r12
0x18003c787  push    r13
0x18003c789  push    r14
0x18003c78b  push    r15
0x18003c78d  sub     rsp, 68h
0x18003c791  mov     rax, cs:__security_cookie
0x18003c798  xor     rax, rsp
0x18003c79b  mov     [rsp+0A8h+var_58], rax
0x18003c7a0  lea     rbp, WPP_GLOBAL_Control
0x18003c7a7  lea     r14, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003c7ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c7b5  cmp     rcx, rbp
0x18003c7b8  jz      short loc_18003C7D1
0x18003c7ba  test    byte ptr [rcx+1Ch], 20h
0x18003c7be  jz      short loc_18003C7D1
0x18003c7c0  mov     edx, 31h ; '1'
0x18003c7c5  mov     r8, r14
0x18003c7c8  mov     rcx, [rcx+10h]
0x18003c7cc  call    WPP_SF_
0x18003c7d1  xor     r12d, r12d
0x18003c7d4  xorps   xmm0, xmm0
0x18003c7d7  xor     eax, eax
0x18003c7d9  movups  xmmword ptr [rsp+0A8h+Handles], xmm0
0x18003c7de  mov     [rsp+0A8h+var_60], rax
0x18003c7e3  mov     [rsp+0A8h+var_78], rax
0x18003c7e8  xor     r13b, r13b
0x18003c7eb  call    cs:__imp_GetTickCount64
0x18003c7f2  nop     dword ptr [rax+rax+00h]
0x18003c7f7  mov     rbx, rax
0x18003c7fa  lea     rcx, [rsp+0A8h+var_78]
0x18003c7ff  call    ?AllocVolumeMap@@YAKPEAPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; AllocVolumeMap(std::map<std::wstring,VolumeEntry> * *)
0x18003c804  mov     esi, eax
0x18003c806  mov     rdi, [rsp+0A8h+var_78]
0x18003c80b  test    eax, eax
0x18003c80d  jnz     loc_18003CC13
0x18003c813  xor     r9d, r9d; lpName
0x18003c816  xor     r8d, r8d; bInitialState
0x18003c819  xor     edx, edx; bManualReset
0x18003c81b  xor     ecx, ecx; lpEventAttributes
0x18003c81d  call    cs:__imp_CreateEventW
0x18003c824  nop     dword ptr [rax+rax+00h]
0x18003c829  mov     r15, rax
0x18003c82c  test    rax, rax
0x18003c82f  jnz     short loc_18003C872
0x18003c831  call    cs:__imp_GetLastError
0x18003c838  nop     dword ptr [rax+rax+00h]
0x18003c83d  mov     esi, eax
0x18003c83f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c846  cmp     rcx, rbp
0x18003c849  jz      loc_18003CC13
0x18003c84f  test    byte ptr [rcx+1Ch], 2
0x18003c853  jz      loc_18003CC13
0x18003c859  lea     edx, [r12+32h]
0x18003c85e  mov     r9d, eax
0x18003c861  mov     r8, r14
0x18003c864  mov     rcx, [rcx+10h]
0x18003c868  call    WPP_SF_d
0x18003c86d  jmp     loc_18003CC13
0x18003c872  mov     edx, 1
0x18003c877  mov     rcx, r15
0x18003c87a  call    cs:__imp_RegisterGPNotificationInternal
0x18003c881  nop     dword ptr [rax+rax+00h]
0x18003c886  test    eax, eax
0x18003c888  jnz     short loc_18003C8CB
0x18003c88a  call    cs:__imp_GetLastError
0x18003c891  nop     dword ptr [rax+rax+00h]
0x18003c896  mov     esi, eax
0x18003c898  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c89f  cmp     rcx, rbp
0x18003c8a2  jz      loc_18003CC04
0x18003c8a8  test    byte ptr [rcx+1Ch], 2
0x18003c8ac  jz      loc_18003CC04
0x18003c8b2  mov     edx, 33h ; '3'
0x18003c8b7  mov     r9d, eax
0x18003c8ba  mov     r8, r14
0x18003c8bd  mov     rcx, [rcx+10h]
0x18003c8c1  call    WPP_SF_d
0x18003c8c6  jmp     loc_18003CC04
0x18003c8cb  mov     bpl, 1
0x18003c8ce  lea     r14, [rbx+36EE80h]
0x18003c8d5  lea     rbx, WPP_GLOBAL_Control
0x18003c8dc  test    bpl, bpl
0x18003c8df  jz      loc_18003CBE7
0x18003c8e5  mov     rcx, rdi
0x18003c8e8  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::clear(void)
0x18003c8ed  mov     byte ptr [rsp+0A8h+bAlertable], 1
0x18003c8f2  mov     r9b, 1
0x18003c8f5  xor     r8d, r8d
0x18003c8f8  xor     edx, edx
0x18003c8fa  mov     rcx, rdi
0x18003c8fd  call    ?EnumVolumes@@YAKPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@_NPEA_K11@Z; EnumVolumes(std::map<std::wstring,VolumeEntry> *,bool,unsigned __int64 *,bool,bool)
0x18003c902  inc     r12d
0x18003c905  call    ?BdeSvcApplyRecoveryPolicy@@YAJXZ; BdeSvcApplyRecoveryPolicy(void)
0x18003c90a  test    eax, eax
0x18003c90c  jns     short loc_18003C938
0x18003c90e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c915  cmp     rcx, rbx
0x18003c918  jz      short loc_18003C938
0x18003c91a  test    byte ptr [rcx+1Ch], 2
0x18003c91e  jz      short loc_18003C938
0x18003c920  mov     edx, 34h ; '4'
0x18003c925  mov     r9d, eax
0x18003c928  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003c92f  mov     rcx, [rcx+10h]
0x18003c933  call    WPP_SF_d
0x18003c938  mov     rcx, rdi
0x18003c93b  call    ?BdeSvcApplyGroupPolicy@@YAXPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; BdeSvcApplyGroupPolicy(std::map<std::wstring,VolumeEntry> *)
0x18003c940  call    ?NotifyGPUpdate@CBdeSvcDE@@SAJXZ; CBdeSvcDE::NotifyGPUpdate(void)
0x18003c945  test    eax, eax
0x18003c947  jns     short loc_18003C973
0x18003c949  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c950  cmp     rcx, rbx
0x18003c953  jz      short loc_18003C973
0x18003c955  test    byte ptr [rcx+1Ch], 2
0x18003c959  jz      short loc_18003C973
0x18003c95b  mov     edx, 35h ; '5'
0x18003c960  mov     r9d, eax
0x18003c963  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003c96a  mov     rcx, [rcx+10h]
0x18003c96e  call    WPP_SF_d
0x18003c973  call    cs:__imp_GetTickCount64
0x18003c97a  nop     dword ptr [rax+rax+00h]
0x18003c97f  cmp     rax, r14
0x18003c982  jb      short loc_18003C9C9
0x18003c984  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c98b  cmp     rcx, rbx
0x18003c98e  jz      short loc_18003C9AB
0x18003c990  test    byte ptr [rcx+1Ch], 8
0x18003c994  jz      short loc_18003C9AB
0x18003c996  mov     edx, 36h ; '6'
0x18003c99b  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003c9a2  mov     rcx, [rcx+10h]
0x18003c9a6  call    WPP_SF_
0x18003c9ab  mov     rcx, rdi
0x18003c9ae  call    ?BdeSvcSqmDataPush@@YAXPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; BdeSvcSqmDataPush(std::map<std::wstring,VolumeEntry> *)
0x18003c9b3  mov     r13b, 1
0x18003c9b6  call    cs:__imp_GetTickCount64
0x18003c9bd  nop     dword ptr [rax+rax+00h]
0x18003c9c2  lea     r14, [rax+2932E00h]
0x18003c9c9  lea     rbx, ?g_lockGpNotificationThreadMgmt@@3VCAutoCS@@A; CAutoCS g_lockGpNotificationThreadMgmt
0x18003c9d0  mov     [rsp+0A8h+var_78], rbx
0x18003c9d5  mov     rcx, rbx; lpCriticalSection
0x18003c9d8  call    cs:__imp_EnterCriticalSection
0x18003c9df  nop     dword ptr [rax+rax+00h]
0x18003c9e4  nop
0x18003c9e5  mov     rcx, rdi
0x18003c9e8  call    ?BdeSvcManageGpNotificationThread@@YAKPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; BdeSvcManageGpNotificationThread(std::map<std::wstring,VolumeEntry> *)
0x18003c9ed  test    eax, eax
0x18003c9ef  jnz     short loc_18003C9FD
0x18003c9f1  cmp     cs:?g_bPcrMon@@3_NA, al; bool g_bPcrMon
0x18003c9f7  jz      loc_18003CBB5
0x18003c9fd  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x18003ca04  call    cs:__imp_AcquireSRWLockShared
0x18003ca0b  nop     dword ptr [rax+rax+00h]
0x18003ca10  mov     rbx, cs:?g_hStopEvent@@3REAXEA; void * g_hStopEvent
0x18003ca17  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x18003ca1e  call    cs:__imp_ReleaseSRWLockShared
0x18003ca25  nop     dword ptr [rax+rax+00h]
0x18003ca2a  mov     [rsp+0A8h+Handles], rbx
0x18003ca2f  mov     rax, cs:?g_hGpNotificationThreadStopEvent@@3PEAXEA; void * g_hGpNotificationThreadStopEvent
0x18003ca36  mov     [rsp+0A8h+Handles+8], rax
0x18003ca3b  mov     [rsp+0A8h+var_60], r15
0x18003ca40  lea     rcx, ?g_lockGpNotificationThreadMgmt@@3VCAutoCS@@A; lpCriticalSection
0x18003ca47  call    cs:__imp_LeaveCriticalSection
0x18003ca4e  nop     dword ptr [rax+rax+00h]
0x18003ca53  mov     [rsp+0A8h+bAlertable], 0; bAlertable
0x18003ca5b  mov     r9d, 36EE80h; dwMilliseconds
0x18003ca61  xor     r8d, r8d; bWaitAll
0x18003ca64  lea     rdx, [rsp+0A8h+Handles]; lpHandles
0x18003ca69  lea     ecx, [r8+3]; nCount
0x18003ca6d  call    cs:__imp_WaitForMultipleObjectsEx
0x18003ca74  nop     dword ptr [rax+rax+00h]
0x18003ca79  mov     ebx, eax
0x18003ca7b  call    cs:__imp_GetLastError
0x18003ca82  nop     dword ptr [rax+rax+00h]
0x18003ca87  mov     esi, eax
0x18003ca89  test    ebx, ebx
0x18003ca8b  jz      loc_18003CB77
0x18003ca91  cmp     ebx, 1
0x18003ca94  jz      loc_18003CB4C
0x18003ca9a  cmp     ebx, 2
0x18003ca9d  jz      loc_18003CB24
0x18003caa3  cmp     ebx, 102h
0x18003caa9  jz      short loc_18003CAFC
0x18003caab  cmp     ebx, 0FFFFFFFFh
0x18003caae  lea     rbx, WPP_GLOBAL_Control
0x18003cab5  jnz     loc_18003C8DC
0x18003cabb  xor     bpl, bpl
0x18003cabe  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cac5  lea     rbx, WPP_GLOBAL_Control
0x18003cacc  cmp     rcx, rbx
0x18003cacf  jz      loc_18003C8DC
0x18003cad5  test    byte ptr [rcx+1Ch], 2
0x18003cad9  jz      loc_18003C8DC
0x18003cadf  mov     edx, 3Bh ; ';'
0x18003cae4  mov     r9d, eax
0x18003cae7  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003caee  mov     rcx, [rcx+10h]
0x18003caf2  call    WPP_SF_d
0x18003caf7  jmp     loc_18003C8DC
0x18003cafc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb03  lea     rbx, WPP_GLOBAL_Control
0x18003cb0a  cmp     rcx, rbx
0x18003cb0d  jz      loc_18003C8DC
0x18003cb13  test    byte ptr [rcx+1Ch], 8
0x18003cb17  jz      loc_18003C8DC
0x18003cb1d  mov     edx, 3Ah ; ':'
0x18003cb22  jmp     short loc_18003CBA0
0x18003cb24  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb2b  lea     rbx, WPP_GLOBAL_Control
0x18003cb32  cmp     rcx, rbx
0x18003cb35  jz      loc_18003C8DC
0x18003cb3b  test    byte ptr [rcx+1Ch], 8
0x18003cb3f  jz      loc_18003C8DC
0x18003cb45  mov     edx, 39h ; '9'
0x18003cb4a  jmp     short loc_18003CBA0
0x18003cb4c  xor     bpl, bpl
0x18003cb4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb56  lea     rbx, WPP_GLOBAL_Control
0x18003cb5d  cmp     rcx, rbx
0x18003cb60  jz      loc_18003C8DC
0x18003cb66  test    byte ptr [rcx+1Ch], 8
0x18003cb6a  jz      loc_18003C8DC
0x18003cb70  mov     edx, 38h ; '8'
0x18003cb75  jmp     short loc_18003CBA0
0x18003cb77  xor     bpl, bpl
0x18003cb7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb81  lea     rbx, WPP_GLOBAL_Control
0x18003cb88  cmp     rcx, rbx
0x18003cb8b  jz      loc_18003C8DC
0x18003cb91  test    byte ptr [rcx+1Ch], 8
0x18003cb95  jz      loc_18003C8DC
0x18003cb9b  mov     edx, 37h ; '7'
0x18003cba0  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003cba7  mov     rcx, [rcx+10h]
0x18003cbab  call    WPP_SF_
0x18003cbb0  jmp     loc_18003C8DC
0x18003cbb5  mov     rcx, cs:?g_hGpNotificationThreadStopEvent@@3PEAXEA; hObject
0x18003cbbc  test    rcx, rcx
0x18003cbbf  jz      short loc_18003CBD8
0x18003cbc1  call    cs:__imp_CloseHandle
0x18003cbc8  nop     dword ptr [rax+rax+00h]
0x18003cbcd  mov     cs:?g_hGpNotificationThreadStopEvent@@3PEAXEA, 0; void * g_hGpNotificationThreadStopEvent
0x18003cbd8  mov     rcx, rbx; lpCriticalSection
0x18003cbdb  call    cs:__imp_LeaveCriticalSection
0x18003cbe2  nop     dword ptr [rax+rax+00h]
0x18003cbe7  mov     rcx, r15
0x18003cbea  call    cs:__imp_UnregisterGPNotificationInternal
0x18003cbf1  nop     dword ptr [rax+rax+00h]
0x18003cbf6  lea     rbp, WPP_GLOBAL_Control
0x18003cbfd  lea     r14, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003cc04  mov     rcx, r15; hObject
0x18003cc07  call    cs:__imp_CloseHandle
0x18003cc0e  nop     dword ptr [rax+rax+00h]
0x18003cc13  lea     rbx, ?g_lockGpNotificationThreadMgmt@@3VCAutoCS@@A; CAutoCS g_lockGpNotificationThreadMgmt
0x18003cc1a  mov     rcx, rbx; lpCriticalSection
0x18003cc1d  call    cs:__imp_EnterCriticalSection
0x18003cc24  nop     dword ptr [rax+rax+00h]
0x18003cc29  mov     rcx, cs:?g_hGpNotificationThreadStopEvent@@3PEAXEA; hObject
0x18003cc30  test    rcx, rcx
0x18003cc33  jz      short loc_18003CC4C
0x18003cc35  call    cs:__imp_CloseHandle
0x18003cc3c  nop     dword ptr [rax+rax+00h]
0x18003cc41  mov     cs:?g_hGpNotificationThreadStopEvent@@3PEAXEA, 0; void * g_hGpNotificationThreadStopEvent
0x18003cc4c  mov     rcx, rbx; lpCriticalSection
0x18003cc4f  call    cs:__imp_LeaveCriticalSection
0x18003cc56  nop     dword ptr [rax+rax+00h]
0x18003cc5b  test    rdi, rdi
0x18003cc5e  jz      short loc_18003CCC2
0x18003cc60  test    r12d, r12d
0x18003cc63  jnz     short loc_18003CC8A
0x18003cc65  mov     rcx, rdi
0x18003cc68  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::clear(void)
0x18003cc6d  mov     byte ptr [rsp+0A8h+bAlertable], 1
0x18003cc72  mov     r9b, 1
0x18003cc75  xor     r8d, r8d
0x18003cc78  xor     edx, edx
0x18003cc7a  mov     rcx, rdi
0x18003cc7d  call    ?EnumVolumes@@YAKPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@_NPEA_K11@Z; EnumVolumes(std::map<std::wstring,VolumeEntry> *,bool,unsigned __int64 *,bool,bool)
0x18003cc82  mov     rcx, rdi
0x18003cc85  call    ?BdeSvcApplyGroupPolicy@@YAXPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; BdeSvcApplyGroupPolicy(std::map<std::wstring,VolumeEntry> *)
0x18003cc8a  test    r13b, r13b
0x18003cc8d  jnz     short loc_18003CCBA
0x18003cc8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cc96  cmp     rcx, rbp
0x18003cc99  jz      short loc_18003CCB2
0x18003cc9b  test    byte ptr [rcx+1Ch], 8
0x18003cc9f  jz      short loc_18003CCB2
0x18003cca1  mov     edx, 3Ch ; '<'
0x18003cca6  mov     r8, r14
0x18003cca9  mov     rcx, [rcx+10h]
0x18003ccad  call    WPP_SF_
0x18003ccb2  mov     rcx, rdi
0x18003ccb5  call    ?BdeSvcSqmDataPush@@YAXPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; BdeSvcSqmDataPush(std::map<std::wstring,VolumeEntry> *)
0x18003ccba  mov     rcx, rdi; void *
0x18003ccbd  call    ?FreeVolumeMap@@YAXPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; FreeVolumeMap(std::map<std::wstring,VolumeEntry> *)
  ... truncated ...
```
