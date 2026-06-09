# ServiceMain(ulong,ushort * * const)

- ea: `0x180002ec0`
- end: `0x180003145`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `645`
- prototype: `void __fastcall(__int64, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800024ac`
- `0x1800027a8`
- `0x1800029ac`
- `0x180002a68`
- `0x180002c20`
- `0x180002e18`
- `0x180002ec0`
- `0x180003ea4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000301f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000301f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000310d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000310d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800030fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800030fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fa7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180002f95`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180002f95`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180002f60`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180002f60`

## string_xrefs

- `0x180002f0b`: `DevQueryBroker`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **const a2)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  struct SERVICE_STATUS_HANDLE__ *v4; // rcx
  signed int v5; // eax
  _QWORD *v6; // rcx
  struct SERVICE_STATUS_HANDLE__ *v7; // rcx
  struct CBrokerInstance **v8; // rcx
  int v9; // eax
  struct SERVICE_STATUS_HANDLE__ *v10; // rcx
  __int64 v11; // rdx
  struct SERVICE_STATUS_HANDLE__ *v12; // rcx
  struct SERVICE_STATUS_HANDLE__ *v13; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_dfb895cd27423fa336520d05ee2dcb21_Traceguids);
  _InterlockedExchange64((volatile __int64 *)&g_dqbSeviceControlFlags, 0);
  g_pDqbInstance = 0;
  g_hDqbStatus = 0;
  g_bDqbRpcIdle = 1;
  g_dqbCurrentState = 2;
  g_dqbServiceState = 0;
  g_bDqbStopping = 0;
  g_dqbIdleStopTimer = 0;
  g_hDqbStatus = RegisterServiceCtrlHandlerExW(L"DevQueryBroker", DqbControlHandlerEx, 0);
  if ( !g_hDqbStatus )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_13;
  }
  g_dqbIdleStopTimer = CreateThreadpoolTimer(DqbIdleStopTimerCallback, 0, 0);
  if ( !g_dqbIdleStopTimer )
  {
    v5 = GetLastError();
    v3 = v5;
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_14:
      if ( (v3 & 0x80000000) == 0 )
        goto LABEL_32;
      goto LABEL_25;
    }
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_dfb895cd27423fa336520d05ee2dcb21_Traceguids, v3);
LABEL_13:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  DqbStatusUpdate(v4, 2u, 0, 0);
  qword_180011870 = (__int64)&g_activeQueriesList;
  g_activeQueriesList.Flink = &g_activeQueriesList;
  InitializeCriticalSection(&g_csActiveQueriesList);
  g_dqbServiceState |= 1u;
  DqbStatusUpdate(v7, 2u, 1u, 0);
  v9 = CBrokerInstance::Create(v8);
  v3 = v9;
  if ( v9 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 14;
LABEL_24:
        WPP_SF_D(v6[2], v11, WPP_dfb895cd27423fa336520d05ee2dcb21_Traceguids, (unsigned int)v9);
        v6 = WPP_GLOBAL_Control;
        goto LABEL_25;
      }
      goto LABEL_25;
    }
    goto LABEL_28;
  }
  DqbStatusUpdate(v10, 2u, 2u, 0);
  v9 = InitializeRpc();
  v3 = v9;
  if ( v9 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 15;
        goto LABEL_24;
      }
LABEL_25:
      if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_D(v6[2], 16, WPP_dfb895cd27423fa336520d05ee2dcb21_Traceguids, v3);
    }
LABEL_28:
    if ( !_InterlockedExchange(&g_bDqbStopping, 1) )
      DqbServiceStop();
    goto LABEL_31;
  }
  g_dqbServiceState |= 2u;
  DqbStatusUpdate(v12, 2u, 3u, 0);
  DqbStatusUpdate(v13, 4u, 4u, 0);
  EnterCriticalSection(&g_csDqbIdleStop);
  CheckIdleStop();
  LeaveCriticalSection(&g_csDqbIdleStop);
LABEL_31:
  v6 = WPP_GLOBAL_Control;
LABEL_32:
  if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_D(v6[2], 17, WPP_dfb895cd27423fa336520d05ee2dcb21_Traceguids, v3);
}

```

## disassembly

```asm
0x180002ec0  push    rbx
0x180002ec2  push    rbp
0x180002ec3  push    rdi
0x180002ec4  push    r14
0x180002ec6  push    r15
0x180002ec8  sub     rsp, 20h
0x180002ecc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ed3  lea     r14, WPP_GLOBAL_Control
0x180002eda  lea     r15, WPP_dfb895cd27423fa336520d05ee2dcb21_Traceguids
0x180002ee1  cmp     rcx, r14
0x180002ee4  jz      short loc_180002EFD
0x180002ee6  cmp     byte ptr [rcx+19h], 4
0x180002eea  jb      short loc_180002EFD
0x180002eec  mov     rcx, [rcx+10h]
0x180002ef0  mov     edx, 0Ch
0x180002ef5  mov     r8, r15
0x180002ef8  call    WPP_SF_
0x180002efd  mov     ebp, 2
0x180002f02  lea     rdx, ?DqbControlHandlerEx@@YAKKKPEAX0@Z; lpHandlerProc
0x180002f09  xor     eax, eax
0x180002f0b  lea     rcx, ServiceName; "DevQueryBroker"
0x180002f12  xchg    rax, cs:?g_dqbSeviceControlFlags@@3_KC; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002f19  xor     r8d, r8d; lpContext
0x180002f1c  mov     cs:?g_pDqbInstance@@3PEAVCBrokerInstance@@EA, 0; CBrokerInstance * g_pDqbInstance
0x180002f27  lea     edi, [rbp-1]
0x180002f2a  mov     cs:?g_hDqbStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA, 0; SERVICE_STATUS_HANDLE__ * g_hDqbStatus
0x180002f35  mov     cs:?g_bDqbRpcIdle@@3HA, edi; int g_bDqbRpcIdle
0x180002f3b  mov     cs:?g_dqbCurrentState@@3KA, ebp; ulong g_dqbCurrentState
0x180002f41  mov     cs:?g_dqbServiceState@@3KA, 0; ulong g_dqbServiceState
0x180002f4b  mov     cs:?g_bDqbStopping@@3JA, 0; long g_bDqbStopping
0x180002f55  mov     cs:?g_dqbIdleStopTimer@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * g_dqbIdleStopTimer
0x180002f60  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180002f66  mov     cs:?g_hDqbStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hDqbStatus
0x180002f6d  test    rax, rax
0x180002f70  jnz     short loc_180002F89
0x180002f72  call    cs:__imp_GetLastError
0x180002f78  mov     ebx, eax
0x180002f7a  test    eax, eax
0x180002f7c  jle     short loc_180002FE2
0x180002f7e  movzx   ebx, ax
0x180002f81  or      ebx, 80070000h
0x180002f87  jmp     short loc_180002FE2
0x180002f89  xor     r8d, r8d; pcbe
0x180002f8c  lea     rcx, ?DqbIdleStopTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180002f93  xor     edx, edx; pv
0x180002f95  call    cs:__imp_CreateThreadpoolTimer
0x180002f9b  mov     cs:?g_dqbIdleStopTimer@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * g_dqbIdleStopTimer
0x180002fa2  test    rax, rax
0x180002fa5  jnz     short loc_180002FF6
0x180002fa7  call    cs:__imp_GetLastError
0x180002fad  mov     ebx, eax
0x180002faf  test    eax, eax
0x180002fb1  jle     short loc_180002FBC
0x180002fb3  movzx   ebx, ax
0x180002fb6  or      ebx, 80070000h
0x180002fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fc3  cmp     rcx, r14
0x180002fc6  jz      short loc_180002FE9
0x180002fc8  cmp     [rcx+19h], bpl
0x180002fcc  jb      short loc_180002FE9
0x180002fce  mov     rcx, [rcx+10h]
0x180002fd2  mov     edx, 0Dh
0x180002fd7  mov     r9d, ebx
0x180002fda  mov     r8, r15
0x180002fdd  call    WPP_SF_D
0x180002fe2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fe9  test    ebx, ebx
0x180002feb  jns     loc_18000311A
0x180002ff1  jmp     loc_1800030A1
0x180002ff6  xor     r9d, r9d; unsigned int
0x180002ff9  xor     r8d, r8d; unsigned int
0x180002ffc  mov     edx, ebp; unsigned int
0x180002ffe  call    ?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180003003  lea     rax, ?g_activeQueriesList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_activeQueriesList
0x18000300a  lea     rcx, ?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003011  mov     cs:qword_180011870, rax
0x180003018  mov     cs:?g_activeQueriesList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_activeQueriesList
0x18000301f  call    cs:__imp_InitializeCriticalSection
0x180003025  or      cs:?g_dqbServiceState@@3KA, edi; ulong g_dqbServiceState
0x18000302b  xor     r9d, r9d; unsigned int
0x18000302e  mov     r8d, edi; unsigned int
0x180003031  mov     edx, ebp; unsigned int
0x180003033  call    ?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180003038  call    ?Create@CBrokerInstance@@SAJPEAPEAV1@@Z; CBrokerInstance::Create(CBrokerInstance * *)
0x18000303d  mov     ebx, eax
0x18000303f  test    eax, eax
0x180003041  jns     short loc_18000305C
0x180003043  mov     rcx, cs:WPP_GLOBAL_Control
0x18000304a  cmp     rcx, r14
0x18000304d  jz      short loc_1800030C0
0x18000304f  cmp     [rcx+19h], bpl
0x180003053  jb      short loc_1800030A1
0x180003055  mov     edx, 0Eh
0x18000305a  jmp     short loc_18000308B
0x18000305c  xor     r9d, r9d; unsigned int
0x18000305f  mov     r8d, ebp; unsigned int
0x180003062  mov     edx, ebp; unsigned int
0x180003064  call    ?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180003069  call    ?InitializeRpc@@YAJXZ; InitializeRpc(void)
0x18000306e  mov     ebx, eax
0x180003070  test    eax, eax
0x180003072  jns     short loc_1800030D1
0x180003074  mov     rcx, cs:WPP_GLOBAL_Control
0x18000307b  cmp     rcx, r14
0x18000307e  jz      short loc_1800030C0
0x180003080  cmp     [rcx+19h], bpl
0x180003084  jb      short loc_1800030A1
0x180003086  mov     edx, 0Fh
0x18000308b  mov     rcx, [rcx+10h]
0x18000308f  mov     r9d, eax
0x180003092  mov     r8, r15
0x180003095  call    WPP_SF_D
0x18000309a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030a1  cmp     rcx, r14
0x1800030a4  jz      short loc_1800030C0
0x1800030a6  cmp     [rcx+19h], bpl
0x1800030aa  jb      short loc_1800030C0
0x1800030ac  mov     rcx, [rcx+10h]
0x1800030b0  mov     edx, 10h
0x1800030b5  mov     r9d, ebx
0x1800030b8  mov     r8, r15
0x1800030bb  call    WPP_SF_D
0x1800030c0  xchg    edi, cs:?g_bDqbStopping@@3JA; long g_bDqbStopping
0x1800030c6  test    edi, edi
0x1800030c8  jnz     short loc_180003113
0x1800030ca  call    ?DqbServiceStop@@YAXXZ; DqbServiceStop(void)
0x1800030cf  jmp     short loc_180003113
0x1800030d1  or      cs:?g_dqbServiceState@@3KA, ebp; ulong g_dqbServiceState
0x1800030d7  xor     r9d, r9d; unsigned int
0x1800030da  mov     edx, ebp; unsigned int
0x1800030dc  lea     r8d, [r9+3]; unsigned int
0x1800030e0  call    ?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x1800030e5  xor     r9d, r9d; unsigned int
0x1800030e8  lea     edx, [r9+4]; unsigned int
0x1800030ec  mov     r8d, edx; unsigned int
0x1800030ef  call    ?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x1800030f4  lea     rcx, ?g_csDqbIdleStop@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800030fb  call    cs:__imp_EnterCriticalSection
0x180003101  call    ?CheckIdleStop@@YAXXZ; CheckIdleStop(void)
0x180003106  lea     rcx, ?g_csDqbIdleStop@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000310d  call    cs:__imp_LeaveCriticalSection
0x180003113  mov     rcx, cs:WPP_GLOBAL_Control
0x18000311a  cmp     rcx, r14
0x18000311d  jz      short loc_180003139
0x18000311f  cmp     byte ptr [rcx+19h], 4
0x180003123  jb      short loc_180003139
0x180003125  mov     rcx, [rcx+10h]
0x180003129  mov     edx, 11h
0x18000312e  mov     r9d, ebx
0x180003131  mov     r8, r15
0x180003134  call    WPP_SF_D
0x180003139  add     rsp, 20h
0x18000313d  pop     r15
0x18000313f  pop     r14
0x180003141  pop     rdi
0x180003142  pop     rbp
0x180003143  pop     rbx
0x180003144  retn
```
