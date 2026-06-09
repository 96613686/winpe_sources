# CalaisMain(ulong,ushort * *)

- ea: `0x180010f50`
- end: `0x18001140a`
- name: `?CalaisMain@@YAXKPEAPEAG@Z`
- size: `1210`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800022b0`
- `0x18000fc40`
- `0x180010f50`
- `0x180011410`
- `0x180011b78`
- `0x180011c10`
- `0x180011c5c`
- `0x1800186d0`
- `0x180019140`
- `0x18001943c`
- `0x180019bc4`
- `0x18001a0c8`
- `0x18001a1ec`
- `0x18001a21c`
- `0x18001a274`
- `0x18001a2ac`
- `0x18001c330`
- `0x18002438c`
- `0x180024710`
- `0x1800249e0`
- `0x180037010`

## import_xrefs

- `msvcrt!?set_terminate@@YAP6AXXZP6AXXZ@Z` at `0x180010f64`
- `msvcrt!?set_terminate@@YAP6AXXZP6AXXZ@Z` at `0x180010f64`
- `SCardBi!?Initialize@SmartCardBiManager@@SAJXZ` at `0x1800111d0`
- `SCardBi!?Initialize@SmartCardBiManager@@SAJXZ` at `0x1800111d0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001122d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001122d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011240`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011240`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011105`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001103d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001118d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001124a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001103d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001118d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001124a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011302`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180011373`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180011373`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001102b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001102b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800110da`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800112f4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800110da`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800112f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CalaisMain(__int64 a1, unsigned __int16 **a2)
{
  CCriticalSectionObject *v2; // rax
  unsigned int v3; // edx
  const unsigned __int8 *v4; // rcx
  const unsigned __int16 *v5; // r9
  CCriticalSectionObject *v6; // rax
  const unsigned __int8 *v7; // rcx
  const unsigned __int16 *v8; // r9
  unsigned int v9; // edx
  DWORD LastError; // eax
  const unsigned __int8 *v11; // rcx
  unsigned int v12; // eax
  const unsigned __int8 *v13; // rcx
  CCriticalSectionObject *v14; // rbx
  DWORD v15; // eax
  const unsigned __int8 *v16; // rcx
  void *v17; // rbx
  DWORD v18; // eax
  const unsigned __int8 *v19; // rcx
  unsigned int v20; // edx
  struct SERVICE_STATUS_HANDLE__ *v21; // rcx
  void *v22; // r14
  DWORD v23; // eax
  const unsigned __int8 *v24; // rcx
  struct _SERVICE_THREAD_SECURITY_INFO **v25; // rcx
  const unsigned __int8 *v26; // rcx
  __int64 (__fastcall *v27)(HANDLE *, const wchar_t *, HANDLE, void (__fastcall *)(void *, unsigned __int8)); // rax
  unsigned int v28; // eax
  unsigned int v29; // r8d
  CCriticalSectionObject *v30; // rbx
  DWORD v31; // esi
  const unsigned __int8 *v32; // rcx
  DWORD v33; // eax
  DWORD v34; // eax
  const unsigned __int8 *v35; // rcx
  const unsigned __int16 *v36; // r9
  unsigned __int16 *v37; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v38; // [rsp+20h] [rbp-58h]
  HANDLE Handles[7]; // [rsp+40h] [rbp-38h] BYREF

  set_terminate(CalaisTerminate);
  McGenEventRegister_EventRegister();
  hEventLog = 0;
  dword_18004BF50 = 1;
  SafeAllocaInitialize();
  v2 = (CCriticalSectionObject *)operator new(0x38u);
  if ( !v2 )
  {
    qword_18004BD38 = 0;
    goto LABEL_47;
  }
  v6 = CCriticalSectionObject::CCriticalSectionObject(v2, v3);
  qword_18004BD38 = v6;
  if ( !v6 )
  {
LABEL_47:
    CalaisError(v4, 0x1FBu, 0, v5, v37);
    return;
  }
  if ( (*(unsigned int (__fastcall **)(CCriticalSectionObject *))(*(_QWORD *)v6 + 16LL))(v6) )
  {
    CalaisError(v7, 0x1F6u, 0, v8, v37);
    if ( qword_18004BD38 )
      CCriticalSectionObject::`scalar deleting destructor'(qword_18004BD38, v9);
    qword_18004BD38 = 0;
    return;
  }
  ServiceStatus.dwServiceType = 32;
  *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"SCardSvr", (LPHANDLER_FUNCTION_EX)CalaisHandlerEx, 0);
  if ( !hServiceStatus )
  {
    LastError = GetLastError();
    CalaisError(v11, 0x1FAu, LastError, 0, 0, 0);
LABEL_45:
    CalaisStopService(0, 0);
    return;
  }
  dword_18004BE64 = 1;
  v12 = CalRpcInitializeTLS();
  if ( v12 )
  {
    CalaisError(v13, 0xC9u, v12, 0, 0, 0);
    goto LABEL_45;
  }
  dword_18004BE68 = 1;
  v14 = qword_18004BD38;
  (**(void (__fastcall ***)(CCriticalSectionObject *, _QWORD, _QWORD))qword_18004BD38)(qword_18004BD38, 0, 0);
  ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwWaitHint = 30000;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
    GetLastError();
  (*(void (__fastcall **)(CCriticalSectionObject *))(*(_QWORD *)v14 + 8LL))(v14);
  hEvent = CreateEventW(0, 1, 0, 0);
  if ( !hEvent )
  {
    v15 = GetLastError();
    CalaisError(v16, 0x1F8u, v15, 0, 0, 0);
    goto LABEL_45;
  }
  v17 = AccessStartedEvent();
  if ( !v17 )
  {
    v18 = GetLastError();
    CalaisError(v19, 0x26Du, v18, 0, 0, 0);
    goto LABEL_45;
  }
  v22 = AccessStoppedEvent();
  if ( !v22 )
  {
    v23 = GetLastError();
    CalaisError(v24, 0x26Eu, v23, 0, 0, 0);
    goto LABEL_45;
  }
  AppInitializeDeviceRegistration(v21, v20);
  try
  {
    SmartCardBiManager::Initialize();
  }
  catch ( ... )
  {
  }
  if ( (unsigned int)CalaisStart() )
    goto LABEL_45;
  dword_18004BE58 = 1;
  if ( (unsigned int)ServerCacheStartup() )
    goto LABEL_45;
  dword_18004BE60 = 1;
  if ( (unsigned int)CalRpcInitialize(v25) )
    goto LABEL_45;
  dword_18004BE5C = 1;
  if ( !ResetEvent(v22) )
    GetLastError();
  if ( !SetEvent(v17) )
    GetLastError();
  if ( !qword_18004BE90
    || (v27 = *(__int64 (__fastcall **)(HANDLE *, const wchar_t *, HANDLE, void (__fastcall *)(void *, unsigned __int8)))(qword_18004BE90 + 192)) == 0 )
  {
    v29 = 0;
    goto LABEL_44;
  }
  v38 = 0;
  v28 = v27(&WaitHandle, L"SCardSvr", hEvent, CalaisStopService);
  if ( v28 )
  {
    v29 = v28;
LABEL_44:
    CalaisError(v26, 0xC9u, v29, 0, 0, 0);
    goto LABEL_45;
  }
  v30 = qword_18004BD38;
  (**(void (__fastcall ***)(CCriticalSectionObject *, _QWORD, _QWORD))qword_18004BD38)(qword_18004BD38, 0, 0);
  ServiceStatus.dwControlsAccepted = 1153;
  ServiceStatus.dwCurrentState = 4;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  if ( SetServiceStatus(hServiceStatus, &ServiceStatus) )
    v31 = 0;
  else
    v31 = GetLastError();
  (*(void (__fastcall **)(CCriticalSectionObject *))(*(_QWORD *)v30 + 8LL))(v30);
  if ( v31 )
  {
    CalaisError(v32, 0xC9u, v31, 0, 0, 0);
    _SetEvent(hEvent);
  }
  while ( 1 )
  {
    Handles[0] = hEvent;
    Handles[1] = CMultiEvent::WaitHandle(g_phReaderChangeEvent);
    v33 = WaitForMultipleObjects(2u, Handles, 0, 0xEA60u);
    if ( !v33 )
      break;
    v34 = v33 - 1;
    if ( !v34 )
      break;
    if ( v34 != 257 )
    {
      _SetEvent(hEvent);
      CalaisError(v35, 0x26Au, 0, v36, v38);
      break;
    }
    if ( !_InterlockedExchange(&g_fExtendShutdownTimer, 0) )
    {
      CalaisStopServiceIfNoReaders();
      break;
    }
  }
  LogSmartCardDriverInformation();
}

```

## disassembly

```asm
0x180010f50  mov     [rsp+arg_0], rbx
0x180010f55  push    rsi
0x180010f56  push    rdi
0x180010f57  push    r14
0x180010f59  sub     rsp, 60h
0x180010f5d  lea     rcx, ?CalaisTerminate@@YAXXZ; CalaisTerminate(void)
0x180010f64  call    cs:__imp_?set_terminate@@YAP6AXXZP6AXXZ@Z; set_terminate(void (*)(void))
0x180010f6a  call    McGenEventRegister_EventRegister
0x180010f6f  xor     edi, edi
0x180010f71  mov     cs:hEventLog, rdi
0x180010f78  lea     esi, [rdi+1]
0x180010f7b  mov     cs:dword_18004BF50, esi
0x180010f81  call    SafeAllocaInitialize
0x180010f86  lea     ecx, [rdi+38h]; Size
0x180010f89  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010f8e  mov     [rsp+78h+arg_10], rax
0x180010f96  test    rax, rax
0x180010f99  jz      loc_1800113E5
0x180010f9f  mov     rcx, rax; this
0x180010fa2  call    ??0CCriticalSectionObject@@QEAA@K@Z; CCriticalSectionObject::CCriticalSectionObject(ulong)
0x180010fa7  mov     rdx, rax
0x180010faa  mov     cs:qword_18004BD38, rax
0x180010fb1  test    rax, rax
0x180010fb4  jz      loc_1800113EC
0x180010fba  mov     rcx, [rax]
0x180010fbd  mov     rax, [rcx+10h]
0x180010fc1  mov     rcx, rdx
0x180010fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fc9  test    eax, eax
0x180010fcb  jz      short loc_180010FF7
0x180010fcd  xor     r8d, r8d; unsigned __int16 *
0x180010fd0  mov     edx, 1F6h; unsigned int
0x180010fd5  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x180010fda  mov     rcx, cs:qword_18004BD38; this
0x180010fe1  test    rcx, rcx
0x180010fe4  jz      short loc_180010FEB
0x180010fe6  call    ??_GCCriticalSectionObject@@QEAAPEAXI@Z; CCriticalSectionObject::`scalar deleting destructor'(uint)
0x180010feb  mov     cs:qword_18004BD38, rdi
0x180010ff2  jmp     loc_1800113F9
0x180010ff7  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180011001  mov     qword ptr cs:ServiceStatus.dwCurrentState, 2
0x18001100c  mov     qword ptr cs:ServiceStatus.dwWin32ExitCode, rdi
0x180011013  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rdi
0x18001101a  xor     r8d, r8d; lpContext
0x18001101d  lea     rdx, CalaisHandlerEx; lpHandlerProc
0x180011024  mov     rcx, cs:lpServiceName; lpServiceName
0x18001102b  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180011031  mov     cs:hServiceStatus, rax
0x180011038  test    rax, rax
0x18001103b  jnz     short loc_180011063
0x18001103d  call    cs:__imp_GetLastError
0x180011043  mov     r8d, eax; unsigned int
0x180011046  mov     [rsp+78h+var_50], rdi; unsigned __int16 *
0x18001104b  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x180011050  xor     r9d, r9d; unsigned __int16 *
0x180011053  mov     edx, 1FAh; unsigned int
0x180011058  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001105d  nop
0x18001105e  jmp     loc_1800113DA
0x180011063  mov     cs:dword_18004BE64, esi
0x180011069  call    ?CalRpcInitializeTLS@@YAKXZ; CalRpcInitializeTLS(void)
0x18001106e  test    eax, eax
0x180011070  jz      short loc_180011092
0x180011072  mov     [rsp+78h+var_50], rdi; unsigned __int16 *
0x180011077  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x18001107c  xor     r9d, r9d; unsigned __int16 *
0x18001107f  mov     r8d, eax; unsigned int
0x180011082  mov     edx, 0C9h; unsigned int
0x180011087  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001108c  nop
0x18001108d  jmp     loc_1800113DA
0x180011092  mov     cs:dword_18004BE68, esi
0x180011098  mov     rbx, cs:qword_18004BD38
0x18001109f  mov     rax, [rbx]
0x1800110a2  xor     r8d, r8d
0x1800110a5  xor     edx, edx
0x1800110a7  mov     rcx, rbx
0x1800110aa  mov     rax, [rax]
0x1800110ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110b2  mov     cs:ServiceStatus.dwCurrentState, 2
0x1800110bc  mov     cs:ServiceStatus.dwCheckPoint, edi
0x1800110c2  mov     cs:ServiceStatus.dwWaitHint, 7530h
0x1800110cc  lea     rdx, ServiceStatus; lpServiceStatus
0x1800110d3  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800110da  call    cs:__imp_SetServiceStatus
0x1800110e0  test    eax, eax
0x1800110e2  jnz     short loc_1800110EB
0x1800110e4  call    cs:__imp_GetLastError
0x1800110ea  nop
0x1800110eb  mov     rax, [rbx]
0x1800110ee  mov     rcx, rbx
0x1800110f1  mov     rax, [rax+8]
0x1800110f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110fa  nop
0x1800110fb  xor     r9d, r9d; lpName
0x1800110fe  xor     r8d, r8d; bInitialState
0x180011101  mov     edx, esi; bManualReset
0x180011103  xor     ecx, ecx; lpEventAttributes
0x180011105  call    cs:__imp_CreateEventW
0x18001110b  mov     cs:hEvent, rax
0x180011112  test    rax, rax
0x180011115  jnz     short loc_18001113D
0x180011117  call    cs:__imp_GetLastError
0x18001111d  mov     r8d, eax; unsigned int
0x180011120  mov     [rsp+78h+var_50], rdi; unsigned __int16 *
0x180011125  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x18001112a  xor     r9d, r9d; unsigned __int16 *
0x18001112d  mov     edx, 1F8h; unsigned int
0x180011132  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x180011137  nop
0x180011138  jmp     loc_1800113DA
0x18001113d  call    ?AccessStartedEvent@@YAPEAXXZ; AccessStartedEvent(void)
0x180011142  mov     rbx, rax
0x180011145  mov     [rsp+78h+arg_18], rax
0x18001114d  test    rax, rax
0x180011150  jnz     short loc_180011178
0x180011152  call    cs:__imp_GetLastError
0x180011158  mov     r8d, eax; unsigned int
0x18001115b  mov     [rsp+78h+var_50], rdi; unsigned __int16 *
0x180011160  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x180011165  xor     r9d, r9d; unsigned __int16 *
0x180011168  mov     edx, 26Dh; unsigned int
0x18001116d  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x180011172  nop
0x180011173  jmp     loc_1800113DA
0x180011178  call    ?AccessStoppedEvent@@YAPEAXXZ; AccessStoppedEvent(void)
0x18001117d  mov     r14, rax
0x180011180  mov     [rsp+78h+arg_10], rax
0x180011188  test    rax, rax
0x18001118b  jnz     short loc_1800111B3
0x18001118d  call    cs:__imp_GetLastError
0x180011193  mov     r8d, eax; unsigned int
0x180011196  mov     [rsp+78h+var_50], rdi; unsigned __int16 *
0x18001119b  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x1800111a0  xor     r9d, r9d; unsigned __int16 *
0x1800111a3  mov     edx, 26Eh; unsigned int
0x1800111a8  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x1800111ad  nop
0x1800111ae  jmp     loc_1800113DA
0x1800111b3  call    ?AppInitializeDeviceRegistration@@YAXPEAUSERVICE_STATUS_HANDLE__@@K@Z; AppInitializeDeviceRegistration(SERVICE_STATUS_HANDLE__ *,ulong)
0x1800111b8  nop
0x1800111b9  jmp     short loc_1800111D0
0x1800111bb  xor     edi, edi
0x1800111bd  lea     esi, [rdi+1]
0x1800111c0  mov     r14, [rsp+78h+arg_10]
0x1800111c8  mov     rbx, [rsp+78h+arg_18]
0x1800111d0  call    cs:__imp_?Initialize@SmartCardBiManager@@SAJXZ; SmartCardBiManager::Initialize(void)
0x1800111d6  nop
0x1800111d7  jmp     short loc_1800111EE
0x1800111d9  xor     edi, edi
0x1800111db  lea     esi, [rdi+1]
0x1800111de  mov     r14, [rsp+78h+arg_10]
0x1800111e6  mov     rbx, [rsp+78h+arg_18]
0x1800111ee  call    ?CalaisStart@@YAKXZ; CalaisStart(void)
0x1800111f3  test    eax, eax
0x1800111f5  jz      short loc_1800111FC
0x1800111f7  jmp     loc_1800113DA
0x1800111fc  mov     cs:dword_18004BE58, esi
0x180011202  call    ?ServerCacheStartup@@YAKXZ; ServerCacheStartup(void)
0x180011207  test    eax, eax
0x180011209  jz      short loc_180011210
0x18001120b  jmp     loc_1800113DA
0x180011210  mov     cs:dword_18004BE60, esi
0x180011216  call    ?CalRpcInitialize@@YAKXZ; CalRpcInitialize(void)
0x18001121b  test    eax, eax
0x18001121d  jz      short loc_180011224
0x18001121f  jmp     loc_1800113DA
0x180011224  mov     cs:dword_18004BE5C, esi
0x18001122a  mov     rcx, r14; hEvent
0x18001122d  call    cs:__imp_ResetEvent
0x180011233  test    eax, eax
0x180011235  jnz     short loc_18001123D
0x180011237  call    cs:__imp_GetLastError
0x18001123d  mov     rcx, rbx; hEvent
0x180011240  call    cs:__imp_SetEvent
0x180011246  test    eax, eax
0x180011248  jnz     short loc_180011250
0x18001124a  call    cs:__imp_GetLastError
0x180011250  mov     rax, cs:qword_18004BE90
0x180011257  test    rax, rax
0x18001125a  jz      loc_1800113BC
0x180011260  mov     rax, [rax+0C0h]
0x180011267  test    rax, rax
0x18001126a  jz      loc_1800113BC
0x180011270  mov     dword ptr [rsp+78h+var_50], 18h
0x180011278  mov     [rsp+78h+var_58], rdi
0x18001127d  lea     r9, ?CalaisStopService@@YAXPEAXE@Z; CalaisStopService(void *,uchar)
0x180011284  mov     r8, cs:hEvent
0x18001128b  mov     rdx, cs:lpServiceName
0x180011292  lea     rcx, WaitHandle
0x180011299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001129e  test    eax, eax
0x1800112a0  jz      short loc_1800112AD
0x1800112a2  xor     r9d, r9d
0x1800112a5  mov     r8d, eax
0x1800112a8  jmp     loc_1800113C2
0x1800112ad  mov     rbx, cs:qword_18004BD38
0x1800112b4  mov     rax, [rbx]
0x1800112b7  xor     r8d, r8d
0x1800112ba  xor     edx, edx
0x1800112bc  mov     rcx, rbx
0x1800112bf  mov     rax, [rax]
0x1800112c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112c7  mov     cs:ServiceStatus.dwControlsAccepted, 481h
0x1800112d1  mov     cs:ServiceStatus.dwCurrentState, 4
0x1800112db  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x1800112e6  lea     rdx, ServiceStatus; lpServiceStatus
0x1800112ed  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800112f4  call    cs:__imp_SetServiceStatus
0x1800112fa  test    eax, eax
0x1800112fc  jz      short loc_180011302
0x1800112fe  mov     esi, edi
0x180011300  jmp     short loc_18001130A
0x180011302  call    cs:__imp_GetLastError
0x180011308  mov     esi, eax
0x18001130a  mov     rcx, [rbx]
0x18001130d  mov     rax, [rcx+8]
0x180011311  mov     rcx, rbx
0x180011314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011319  nop
0x18001131a  test    esi, esi
0x18001131c  jz      short loc_180011344
0x18001131e  mov     [rsp+78h+var_50], rdi; unsigned __int16 *
0x180011323  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x180011328  xor     r9d, r9d; unsigned __int16 *
0x18001132b  mov     r8d, esi; unsigned int
0x18001132e  mov     edx, 0C9h; unsigned int
0x180011333  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x180011338  mov     rcx, cs:hEvent; void *
0x18001133f  call    ?_SetEvent@@YAHPEAX@Z; _SetEvent(void *)
0x180011344  mov     rax, cs:hEvent
0x18001134b  mov     [rsp+78h+Handles], rax
0x180011350  mov     rcx, cs:?g_phReaderChangeEvent@@3PEAVCMultiEvent@@EA; this
0x180011357  call    ?WaitHandle@CMultiEvent@@QEAAPEAXXZ; CMultiEvent::WaitHandle(void)
0x18001135c  mov     [rsp+78h+var_30], rax
0x180011361  mov     r9d, 0EA60h; dwMilliseconds
0x180011367  xor     r8d, r8d; bWaitAll
0x18001136a  lea     rdx, [rsp+78h+Handles]; lpHandles
0x18001136f  lea     ecx, [r8+2]; nCount
0x180011373  call    cs:__imp_WaitForMultipleObjects
0x180011379  test    eax, eax
0x18001137b  jz      short loc_1800113B5
0x18001137d  sub     eax, 1
0x180011380  jz      short loc_1800113B5
0x180011382  cmp     eax, 101h
0x180011387  jnz     short loc_18001139C
0x180011389  mov     eax, edi
0x18001138b  xchg    eax, cs:?g_fExtendShutdownTimer@@3JA; long g_fExtendShutdownTimer
0x180011391  test    eax, eax
0x180011393  jnz     short loc_180011344
0x180011395  call    ?CalaisStopServiceIfNoReaders@@YAXXZ; CalaisStopServiceIfNoReaders(void)
0x18001139a  jmp     short loc_1800113B5
0x18001139c  mov     rcx, cs:hEvent; void *
0x1800113a3  call    ?_SetEvent@@YAHPEAX@Z; _SetEvent(void *)
0x1800113a8  xor     r8d, r8d; unsigned __int16 *
0x1800113ab  mov     edx, 26Ah; unsigned int
0x1800113b0  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x1800113b5  call    ?LogSmartCardDriverInformation@@YAXXZ; LogSmartCardDriverInformation(void)
0x1800113ba  jmp     short loc_1800113F9
0x1800113bc  xor     r9d, r9d; unsigned __int16 *
0x1800113bf  xor     r8d, r8d; unsigned int
0x1800113c2  mov     [rsp+78h+var_50], rdi; unsigned __int16 *
0x1800113c7  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x1800113cc  mov     edx, 0C9h; unsigned int
0x1800113d1  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x1800113d6  jmp     short loc_1800113DA
0x1800113d8  jmp     short $+2
0x1800113da  xor     edx, edx; unsigned __int8
0x1800113dc  xor     ecx, ecx; void *
0x1800113de  call    ?CalaisStopService@@YAXPEAXE@Z; CalaisStopService(void *,uchar)
0x1800113e3  jmp     short loc_1800113F9
0x1800113e5  mov     cs:qword_18004BD38, rdi
0x1800113ec  xor     r8d, r8d; unsigned __int16 *
0x1800113ef  mov     edx, 1FBh; unsigned int
0x1800113f4  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x1800113f9  mov     rbx, [rsp+78h+arg_0]
0x180011401  add     rsp, 60h
0x180011405  pop     r14
0x180011407  pop     rdi
0x180011408  pop     rsi
0x180011409  retn
```
