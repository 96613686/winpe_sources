# BdeSvcCtlHandler

- ea: `0x180025350`
- end: `0x180025830`
- name: `BdeSvcCtlHandler`
- size: `1248`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000a010`
- `0x18001f664`
- `0x180023e60`
- `0x180025350`
- `0x180027940`
- `0x180034070`
- `0x180046560`
- `0x1800563dc`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180025593`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180025593`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002577b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800257ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002577b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800257ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025799`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800257d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025799`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800257d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800253d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800253d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800253b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800253b7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025768`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025768`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800257c6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800257c6`
- `FVEAPI!FveControl` at `0x180025438`
- `FVEAPI!FveControl` at `0x18002572f`
- `FVEAPI!FveControl` at `0x180025438`
- `FVEAPI!FveControl` at `0x18002572f`

## pseudocode

```c
__int64 __fastcall BdeSvcCtlHandler(DWORD dwControl, DWORD dwEventType, unsigned int *lpEventData, LPVOID lpContext)
{
  unsigned int v7; // r14d
  HANDLE v8; // rsi
  DWORD v9; // edi
  DWORD v10; // edi
  DWORD v11; // edi
  DWORD v12; // ebx
  DWORD v13; // ebx
  DWORD v14; // ebx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  PVOID *v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // eax
  int v24; // [rsp+30h] [rbp-38h] BYREF
  int v25; // [rsp+34h] [rbp-34h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
  v7 = 0;
  AcquireSRWLockShared(&g_srwlStopEvent);
  v8 = g_hStopEvent;
  ReleaseSRWLockShared(&g_srwlStopEvent);
  v25 = 0;
  v9 = dwControl - 1;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
LABEL_77:
    if ( v8 )
      SetEvent(v8);
    EnterCriticalSection(&g_serviceStatusLock);
    *(_QWORD *)&g_serviceStatus.dwCurrentState = 3;
    LeaveCriticalSection(&g_serviceStatusLock);
    goto LABEL_80;
  }
  v10 = v9 - 12;
  if ( !v10 )
  {
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( dwEventType == 4 )
    {
      if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 8) != 0 )
        WPP_SF_(v20[2], 32, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
      FveControl(7, 0, 0, 0, &v25);
      goto LABEL_80;
    }
    if ( dwEventType != 18 || v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 8) == 0 )
      goto LABEL_80;
    v21 = 33;
LABEL_24:
    WPP_SF_(v20[2], v21, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
    goto LABEL_80;
  }
  v11 = v10 - 1;
  if ( v11 )
  {
    if ( v11 != 1 )
      goto LABEL_80;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
    FveControl(7, 0, 0, 0, &v25);
    goto LABEL_77;
  }
  v12 = dwEventType - 1;
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
    if ( BdeSvcShouldProcessVolumesOnLogon() )
      WorkerThreadLauncher((unsigned int (*)(void *))ProcessVolumesOnLogonWorker);
    goto LABEL_80;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_80;
    v21 = 21;
    goto LABEL_24;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_80;
    v21 = 22;
    goto LABEL_24;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_80;
    v21 = 23;
    goto LABEL_24;
  }
  v16 = v15 - 1;
  if ( v16 )
  {
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          if ( v19 != 1 )
            goto LABEL_80;
          v20 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_80;
          v21 = 29;
        }
        else
        {
          v20 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_80;
          v21 = 28;
        }
      }
      else
      {
        v20 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_80;
        v21 = 27;
      }
      goto LABEL_24;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
    CBdeSvcDE::ProcessLogoff(lpEventData[1]);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
    if ( BdeSvcShouldProcessVolumesOnLogon() )
      WorkerThreadLauncher((unsigned int (*)(void *))ProcessVolumesOnLogonWorker);
    if ( CBdeSvcDE::ShouldProcessLogons() )
      CBdeSvcDE::ProcessLogonAsync(lpEventData[1]);
    if ( lpEventData )
    {
      v24 = 0;
      RtlGetDeviceFamilyInfoEnum(0, &v24, 0);
      if ( v24 == 3 )
      {
        v22 = WorkerThreadLauncher((__int64)BdeSvcBackupMonitorCheckWorkerThread, lpEventData[1], 7, 0);
        v7 = v22;
        if ( v22 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, v22);
        }
      }
    }
  }
LABEL_80:
  EnterCriticalSection(&g_serviceStatusLock);
  SetServiceStatus(g_hStatus, &g_serviceStatus);
  LeaveCriticalSection(&g_serviceStatusLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x180025350  mov     [rsp+arg_0], rbx
0x180025355  mov     [rsp+arg_8], rbp
0x18002535a  push    rsi
0x18002535b  push    rdi
0x18002535c  push    r12
0x18002535e  push    r14
0x180025360  push    r15
0x180025362  sub     rsp, 40h
0x180025366  mov     rax, cs:__security_cookie
0x18002536d  xor     rax, rsp
0x180025370  mov     [rsp+68h+var_30], rax
0x180025375  mov     rbp, r8
0x180025378  mov     ebx, edx
0x18002537a  mov     edi, ecx
0x18002537c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025383  lea     r15, WPP_GLOBAL_Control
0x18002538a  lea     r12, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x180025391  cmp     rcx, r15
0x180025394  jz      short loc_1800253AD
0x180025396  test    byte ptr [rcx+1Ch], 20h
0x18002539a  jz      short loc_1800253AD
0x18002539c  mov     rcx, [rcx+10h]
0x1800253a0  mov     edx, 12h
0x1800253a5  mov     r8, r12
0x1800253a8  call    WPP_SF_
0x1800253ad  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800253b4  xor     r14d, r14d
0x1800253b7  call    cs:__imp_AcquireSRWLockShared
0x1800253be  nop     dword ptr [rax+rax+00h]
0x1800253c3  mov     rsi, cs:?g_hStopEvent@@3REAXEA; void * g_hStopEvent
0x1800253ca  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800253d1  call    cs:__imp_ReleaseSRWLockShared
0x1800253d8  nop     dword ptr [rax+rax+00h]
0x1800253dd  mov     [rsp+68h+var_34], r14d
0x1800253e2  sub     edi, 1
0x1800253e5  jz      loc_18002573D
0x1800253eb  sub     edi, 0Ch
0x1800253ee  jz      loc_1800256AB
0x1800253f4  sub     edi, 1
0x1800253f7  jz      short loc_180025449
0x1800253f9  cmp     edi, 1
0x1800253fc  jnz     loc_1800257A5
0x180025402  mov     rcx, cs:WPP_GLOBAL_Control
0x180025409  cmp     rcx, r15
0x18002540c  jz      short loc_180025423
0x18002540e  test    byte ptr [rcx+1Ch], 8
0x180025412  jz      short loc_180025423
0x180025414  mov     rcx, [rcx+10h]
0x180025418  lea     edx, [rdi+1Dh]
0x18002541b  mov     r8, r12
0x18002541e  call    WPP_SF_
0x180025423  xor     edx, edx
0x180025425  lea     rax, [rsp+68h+var_34]
0x18002542a  xor     r9d, r9d
0x18002542d  mov     [rsp+68h+var_48], rax
0x180025432  xor     r8d, r8d
0x180025435  lea     ecx, [rdx+7]
0x180025438  call    cs:__imp_FveControl
0x18002543f  nop     dword ptr [rax+rax+00h]
0x180025444  jmp     loc_180025760
0x180025449  sub     ebx, 1
0x18002544c  jz      loc_18002566A
0x180025452  sub     ebx, 1
0x180025455  jz      loc_180025646
0x18002545b  sub     ebx, 1
0x18002545e  jz      loc_180025622
0x180025464  sub     ebx, 1
0x180025467  jz      loc_1800255FE
0x18002546d  sub     ebx, 1
0x180025470  jz      loc_180025532
0x180025476  sub     ebx, 1
0x180025479  jz      loc_180025502
0x18002547f  sub     ebx, 1
0x180025482  jz      short loc_1800254E1
0x180025484  sub     ebx, 1
0x180025487  jz      short loc_1800254C0
0x180025489  cmp     ebx, 1
0x18002548c  jnz     loc_1800257A5
0x180025492  mov     rcx, cs:WPP_GLOBAL_Control
0x180025499  cmp     rcx, r15
0x18002549c  jz      loc_1800257A5
0x1800254a2  test    byte ptr [rcx+1Ch], 8
0x1800254a6  jz      loc_1800257A5
0x1800254ac  lea     edx, [rbx+1Ch]
0x1800254af  mov     rcx, [rcx+10h]
0x1800254b3  mov     r8, r12
0x1800254b6  call    WPP_SF_
0x1800254bb  jmp     loc_1800257A5
0x1800254c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254c7  cmp     rcx, r15
0x1800254ca  jz      loc_1800257A5
0x1800254d0  test    byte ptr [rcx+1Ch], 8
0x1800254d4  jz      loc_1800257A5
0x1800254da  mov     edx, 1Ch
0x1800254df  jmp     short loc_1800254AF
0x1800254e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254e8  cmp     rcx, r15
0x1800254eb  jz      loc_1800257A5
0x1800254f1  test    byte ptr [rcx+1Ch], 8
0x1800254f5  jz      loc_1800257A5
0x1800254fb  mov     edx, 1Bh
0x180025500  jmp     short loc_1800254AF
0x180025502  mov     rcx, cs:WPP_GLOBAL_Control
0x180025509  cmp     rcx, r15
0x18002550c  jz      short loc_180025525
0x18002550e  test    byte ptr [rcx+1Ch], 8
0x180025512  jz      short loc_180025525
0x180025514  mov     rcx, [rcx+10h]
0x180025518  mov     edx, 1Ah
0x18002551d  mov     r8, r12
0x180025520  call    WPP_SF_
0x180025525  mov     ecx, [rbp+4]; unsigned int
0x180025528  call    ?ProcessLogoff@CBdeSvcDE@@SAXK@Z; CBdeSvcDE::ProcessLogoff(ulong)
0x18002552d  jmp     loc_1800257A5
0x180025532  mov     rcx, cs:WPP_GLOBAL_Control
0x180025539  cmp     rcx, r15
0x18002553c  jz      short loc_180025555
0x18002553e  test    byte ptr [rcx+1Ch], 8
0x180025542  jz      short loc_180025555
0x180025544  mov     rcx, [rcx+10h]
0x180025548  mov     edx, 18h
0x18002554d  mov     r8, r12
0x180025550  call    WPP_SF_
0x180025555  call    ?BdeSvcShouldProcessVolumesOnLogon@@YA_NXZ; BdeSvcShouldProcessVolumesOnLogon(void)
0x18002555a  test    al, al
0x18002555c  jz      short loc_18002556A
0x18002555e  lea     rcx, ?ProcessVolumesOnLogonWorker@@YAIPEAX@Z; unsigned int (*)(void *)
0x180025565  call    ?WorkerThreadLauncher@@YAKP6AIPEAX@Z@Z; WorkerThreadLauncher(uint (*)(void *))
0x18002556a  call    ?ShouldProcessLogons@CBdeSvcDE@@SA_NXZ; CBdeSvcDE::ShouldProcessLogons(void)
0x18002556f  test    al, al
0x180025571  jz      short loc_18002557B
0x180025573  mov     ecx, [rbp+4]; unsigned int
0x180025576  call    ?ProcessLogonAsync@CBdeSvcDE@@SAJK@Z; CBdeSvcDE::ProcessLogonAsync(ulong)
0x18002557b  test    rbp, rbp
0x18002557e  jz      loc_1800257A5
0x180025584  xor     r8d, r8d
0x180025587  mov     [rsp+68h+var_38], r14d
0x18002558c  lea     rdx, [rsp+68h+var_38]
0x180025591  xor     ecx, ecx
0x180025593  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18002559a  nop     dword ptr [rax+rax+00h]
0x18002559f  cmp     [rsp+68h+var_38], 3
0x1800255a4  jnz     loc_1800257A5
0x1800255aa  mov     edx, [rbp+4]
0x1800255ad  lea     rcx, ?BdeSvcBackupMonitorCheckWorkerThread@@YAIPEAX@Z; BdeSvcBackupMonitorCheckWorkerThread(void *)
0x1800255b4  xor     r9d, r9d
0x1800255b7  lea     r8d, [r9+7]
0x1800255bb  call    ?WorkerThreadLauncher@@YAKP6AIPEAX@Z0W4WorkerThreadFlags@@PEAK@Z; WorkerThreadLauncher(uint (*)(void *),void *,WorkerThreadFlags,ulong *)
0x1800255c0  mov     r14d, eax
0x1800255c3  test    eax, eax
0x1800255c5  jz      loc_1800257A5
0x1800255cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255d2  cmp     rcx, r15
0x1800255d5  jz      loc_1800257A5
0x1800255db  test    byte ptr [rcx+1Ch], 2
0x1800255df  jz      loc_1800257A5
0x1800255e5  mov     rcx, [rcx+10h]
0x1800255e9  mov     edx, 19h
0x1800255ee  mov     r9d, eax
0x1800255f1  mov     r8, r12
0x1800255f4  call    WPP_SF_d
0x1800255f9  jmp     loc_1800257A5
0x1800255fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180025605  cmp     rcx, r15
0x180025608  jz      loc_1800257A5
0x18002560e  test    byte ptr [rcx+1Ch], 8
0x180025612  jz      loc_1800257A5
0x180025618  mov     edx, 17h
0x18002561d  jmp     loc_1800254AF
0x180025622  mov     rcx, cs:WPP_GLOBAL_Control
0x180025629  cmp     rcx, r15
0x18002562c  jz      loc_1800257A5
0x180025632  test    byte ptr [rcx+1Ch], 8
0x180025636  jz      loc_1800257A5
0x18002563c  mov     edx, 16h
0x180025641  jmp     loc_1800254AF
0x180025646  mov     rcx, cs:WPP_GLOBAL_Control
0x18002564d  cmp     rcx, r15
0x180025650  jz      loc_1800257A5
0x180025656  test    byte ptr [rcx+1Ch], 8
0x18002565a  jz      loc_1800257A5
0x180025660  mov     edx, 15h
0x180025665  jmp     loc_1800254AF
0x18002566a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025671  cmp     rcx, r15
0x180025674  jz      short loc_18002568D
0x180025676  test    byte ptr [rcx+1Ch], 8
0x18002567a  jz      short loc_18002568D
0x18002567c  mov     rcx, [rcx+10h]
0x180025680  mov     edx, 14h
0x180025685  mov     r8, r12
0x180025688  call    WPP_SF_
0x18002568d  call    ?BdeSvcShouldProcessVolumesOnLogon@@YA_NXZ; BdeSvcShouldProcessVolumesOnLogon(void)
0x180025692  test    al, al
0x180025694  jz      loc_1800257A5
0x18002569a  lea     rcx, ?ProcessVolumesOnLogonWorker@@YAIPEAX@Z; unsigned int (*)(void *)
0x1800256a1  call    ?WorkerThreadLauncher@@YAKP6AIPEAX@Z@Z; WorkerThreadLauncher(uint (*)(void *))
0x1800256a6  jmp     loc_1800257A5
0x1800256ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256b2  cmp     rcx, r15
0x1800256b5  jz      short loc_1800256D5
0x1800256b7  test    byte ptr [rcx+1Ch], 8
0x1800256bb  jz      short loc_1800256D5
0x1800256bd  mov     rcx, [rcx+10h]
0x1800256c1  mov     edx, 1Fh
0x1800256c6  mov     r8, r12
0x1800256c9  call    WPP_SF_
0x1800256ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256d5  cmp     ebx, 4
0x1800256d8  jz      short loc_1800256FE
0x1800256da  cmp     ebx, 12h
0x1800256dd  jnz     loc_1800257A5
0x1800256e3  cmp     rcx, r15
0x1800256e6  jz      loc_1800257A5
0x1800256ec  test    byte ptr [rcx+1Ch], 8
0x1800256f0  jz      loc_1800257A5
0x1800256f6  lea     edx, [rbx+0Fh]
0x1800256f9  jmp     loc_1800254AF
0x1800256fe  cmp     rcx, r15
0x180025701  jz      short loc_18002571A
0x180025703  test    byte ptr [rcx+1Ch], 8
0x180025707  jz      short loc_18002571A
0x180025709  mov     rcx, [rcx+10h]
0x18002570d  mov     edx, 20h ; ' '
0x180025712  mov     r8, r12
0x180025715  call    WPP_SF_
0x18002571a  xor     edx, edx
0x18002571c  lea     rax, [rsp+68h+var_34]
0x180025721  xor     r9d, r9d
0x180025724  mov     [rsp+68h+var_48], rax
0x180025729  xor     r8d, r8d
0x18002572c  lea     ecx, [rdx+7]
0x18002572f  call    cs:__imp_FveControl
0x180025736  nop     dword ptr [rax+rax+00h]
0x18002573b  jmp     short loc_1800257A5
0x18002573d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025744  cmp     rcx, r15
0x180025747  jz      short loc_180025760
0x180025749  test    byte ptr [rcx+1Ch], 8
0x18002574d  jz      short loc_180025760
0x18002574f  mov     rcx, [rcx+10h]
0x180025753  mov     edx, 13h
0x180025758  mov     r8, r12
0x18002575b  call    WPP_SF_
0x180025760  test    rsi, rsi
0x180025763  jz      short loc_180025774
0x180025765  mov     rcx, rsi; hEvent
0x180025768  call    cs:__imp_SetEvent
0x18002576f  nop     dword ptr [rax+rax+00h]
0x180025774  lea     rcx, ?g_serviceStatusLock@@3VCAutoCS@@A; lpCriticalSection
0x18002577b  call    cs:__imp_EnterCriticalSection
0x180025782  nop     dword ptr [rax+rax+00h]
0x180025787  lea     rcx, ?g_serviceStatusLock@@3VCAutoCS@@A; lpCriticalSection
0x18002578e  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_serviceStatus ...
0x180025799  call    cs:__imp_LeaveCriticalSection
0x1800257a0  nop     dword ptr [rax+rax+00h]
0x1800257a5  lea     rcx, ?g_serviceStatusLock@@3VCAutoCS@@A; lpCriticalSection
0x1800257ac  call    cs:__imp_EnterCriticalSection
0x1800257b3  nop     dword ptr [rax+rax+00h]
0x1800257b8  mov     rcx, cs:?g_hStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800257bf  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800257c6  call    cs:__imp_SetServiceStatus
0x1800257cd  nop     dword ptr [rax+rax+00h]
0x1800257d2  lea     rcx, ?g_serviceStatusLock@@3VCAutoCS@@A; lpCriticalSection
0x1800257d9  call    cs:__imp_LeaveCriticalSection
0x1800257e0  nop     dword ptr [rax+rax+00h]
0x1800257e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257ec  cmp     rcx, r15
0x1800257ef  jz      short loc_180025808
0x1800257f1  test    byte ptr [rcx+1Ch], 20h
0x1800257f5  jz      short loc_180025808
0x1800257f7  mov     rcx, [rcx+10h]
0x1800257fb  mov     edx, 22h ; '"'
0x180025800  mov     r8, r12
0x180025803  call    WPP_SF_
0x180025808  mov     eax, r14d
0x18002580b  mov     rcx, [rsp+68h+var_30]
0x180025810  xor     rcx, rsp; StackCookie
0x180025813  call    __security_check_cookie
0x180025818  mov     rbx, [rsp+68h+arg_0]
0x18002581d  mov     rbp, [rsp+68h+arg_8]
0x180025822  add     rsp, 40h
0x180025826  pop     r15
0x180025828  pop     r14
0x18002582a  pop     r12
0x18002582c  pop     rdi
0x18002582d  pop     rsi
0x18002582e  retn
```
