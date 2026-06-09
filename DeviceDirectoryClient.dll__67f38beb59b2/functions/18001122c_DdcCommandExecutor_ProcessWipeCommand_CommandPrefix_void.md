# DdcCommandExecutor::ProcessWipeCommand(CommandPrefix *,void *)

- ea: `0x18001122c`
- end: `0x1800115a2`
- name: `?ProcessWipeCommand@DdcCommandExecutor@@SAJPEAUCommandPrefix@@PEAX@Z`
- size: `886`
- prototype: `__int64 __fastcall(struct CommandPrefix *, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005f5c`

## callees

- `0x1800024c0`
- `0x180003c2c`
- `0x1800050b8`
- `0x180005310`
- `0x180009164`
- `0x18001122c`
- `0x1800115c0`
- `0x180011bf0`
- `0x180011e74`
- `0x1800128fc`
- `0x1800132e4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800112a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011363`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011388`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001142c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800112a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011363`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011388`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001142c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800112c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800112c5`

## string_xrefs

- `0x1800113cf`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x1800114d6`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x18001151f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x18001140f`: `CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, &updateStatusContext))`
- `0x18001150b`: `CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, &updateStatusContext))`
- `0x1800112d8`: `WipeUpdateStatus`
- `0x18001139f`: `WipeUpdateStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DdcCommandExecutor::ProcessWipeCommand(struct CommandPrefix *a1, void *a2)
{
  int updated; // ebx
  int v4; // edx
  int v5; // ecx
  int v6; // edx
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  int v10; // edx
  int v11; // ecx
  LPVOID v12; // rcx
  unsigned int v14; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+B0h] [rbp-9h] BYREF
  void *v17; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+7h]
  struct _FILETIME SystemTimeAsFileTime[4]; // [rsp+C8h] [rbp+Fh] BYREF

  memset(SystemTimeAsFileTime, 0, 28);
  v14 = 0;
  v15 = 0;
  v17 = a2;
  v18 = 0;
  ppv = 0;
  if ( a1 )
  {
    GetSystemTimeAsFileTime(SystemTimeAsFileTime);
    SystemTimeAsFileTime[2].dwHighDateTime = CoCreateInstance(&CLSID_CommandHandler, 0, 1u, &IID_ICommandHandler, &ppv);
    if ( (SystemTimeAsFileTime[2].dwHighDateTime & 0x80000000) != 0 )
      goto LABEL_8;
    updated = 0;
    if ( DdcPdcActivationWrapper::ActivateClient((DdcPdcActivationWrapper *)&v17, L"WipeUpdateStatus") >= 0 )
      UpdateStatusWrapper(
        &v14,
        *(unsigned int *)a1,
        6,
        *((unsigned int *)a1 + 2),
        0,
        0,
        *(_QWORD *)((char *)a1 + 12),
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0);
    GetSystemTimeAsFileTime(SystemTimeAsFileTime);
    SystemTimeAsFileTime[2].dwHighDateTime = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 64LL))(ppv);
    if ( (SystemTimeAsFileTime[2].dwHighDateTime & 0x80000000) != 0 )
    {
LABEL_8:
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
      SystemTimeAsFileTime[2].dwLowDateTime = 7;
      if ( v18 || DdcPdcActivationWrapper::ActivateClient((DdcPdcActivationWrapper *)&v17, L"WipeUpdateStatus") >= 0 )
      {
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
        updated = UpdateStatusWrapper(
                    &v14,
                    *(unsigned int *)a1,
                    SystemTimeAsFileTime[2].dwLowDateTime,
                    *((unsigned int *)a1 + 2),
                    0,
                    SystemTimeAsFileTime[2].dwHighDateTime,
                    *(_QWORD *)((char *)a1 + 12),
                    SystemTimeAsFileTime,
                    &SystemTimeAsFileTime[1],
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0);
        if ( (unsigned int)ShouldRetry(updated, v14) )
        {
          updated = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v15);
          if ( updated >= 0 )
          {
            updated = DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(
                        (DdcTaskSchedulerWrapper *)&v15,
                        a1,
                        (struct UpdateStatusContext *)SystemTimeAsFileTime);
            if ( updated < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v11,
                v10,
                updated,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
                184,
                "CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, &updateStatusContext))");
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v9,
              v8,
              updated,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
              183,
              "CHR(taskSchedulerWrapper.Initialize())");
          }
        }
      }
      else
      {
        updated = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v15);
        if ( updated >= 0 )
        {
          updated = DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(
                      (DdcTaskSchedulerWrapper *)&v15,
                      a1,
                      (struct UpdateStatusContext *)SystemTimeAsFileTime);
          if ( updated < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v7,
              v6,
              updated,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
              191,
              "CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, &updateStatusContext))");
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v5,
            v4,
            updated,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
            190,
            "CHR(taskSchedulerWrapper.Initialize())");
        }
      }
    }
  }
  else
  {
    updated = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        130,
        "CPR(pPrefix)");
  }
  DdcTraceHelper::TraceCommandResult(
    v18 != 0,
    *(_DWORD *)a1,
    4u,
    *((_DWORD *)a1 + 2),
    SystemTimeAsFileTime[2].dwHighDateTime,
    v14,
    updated);
  v12 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  DdcPdcActivationWrapper::DeactivateClient((DdcPdcActivationWrapper *)&v17);
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(&v15);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18001122c  push    rbp
0x18001122e  push    rbx
0x18001122f  push    rsi
0x180011230  push    rdi
0x180011231  lea     rbp, [rsp-3Fh]
0x180011236  sub     rsp, 0F8h
0x18001123d  mov     rax, cs:__security_cookie
0x180011244  xor     rax, rsp
0x180011247  mov     [rbp+57h+var_28], rax
0x18001124b  mov     rdi, rcx
0x18001124e  xorps   xmm0, xmm0
0x180011251  movups  xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x180011255  movups  xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwHighDateTime+8], xmm0
0x180011259  xor     esi, esi
0x18001125b  mov     [rbp+57h+var_70], esi
0x18001125e  mov     [rbp+57h+var_68], rsi
0x180011262  mov     [rbp+57h+var_58], rdx
0x180011266  mov     [rbp+57h+var_50], rsi
0x18001126a  mov     [rbp+57h+var_60], rsi
0x18001126e  test    rcx, rcx
0x180011271  jnz     short loc_18001129E
0x180011273  mov     ebx, 80070057h
0x180011278  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001127f  jz      loc_18001152E
0x180011285  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x18001128c  mov     qword ptr [rsp+110h+var_E8], rax
0x180011291  mov     dword ptr [rsp+110h+ppv], 282h
0x180011299  jmp     loc_18001151F
0x18001129e  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800112a2  call    cs:__imp_GetSystemTimeAsFileTime
0x1800112a8  lea     rax, [rbp+57h+var_60]
0x1800112ac  mov     [rsp+110h+ppv], rax; ppv
0x1800112b1  lea     r9, IID_ICommandHandler; riid
0x1800112b8  xor     edx, edx; pUnkOuter
0x1800112ba  lea     r8d, [rdx+1]; dwClsContext
0x1800112be  lea     rcx, CLSID_CommandHandler; rclsid
0x1800112c5  call    cs:__imp_CoCreateInstance
0x1800112cb  mov     [rbp+57h+var_34], eax
0x1800112ce  test    eax, eax
0x1800112d0  js      loc_180011384
0x1800112d6  mov     ebx, esi
0x1800112d8  lea     rdx, aWipeupdatestat; "WipeUpdateStatus"
0x1800112df  lea     rcx, [rbp+57h+var_58]; this
0x1800112e3  call    ?ActivateClient@DdcPdcActivationWrapper@@QEAAJPEBG@Z; DdcPdcActivationWrapper::ActivateClient(ushort const *)
0x1800112e8  test    eax, eax
0x1800112ea  js      short loc_18001135F
0x1800112ec  mov     [rsp+110h+var_78], rsi
0x1800112f4  mov     [rsp+110h+var_80], rsi
0x1800112fc  mov     [rsp+110h+var_88], rsi
0x180011304  mov     [rsp+110h+var_90], rsi
0x18001130c  mov     [rsp+110h+var_98], rsi
0x180011311  mov     [rsp+110h+var_A0], rsi
0x180011316  mov     [rsp+110h+var_A8], rsi
0x18001131b  mov     [rsp+110h+var_B0], rsi
0x180011320  mov     [rsp+110h+var_B8], rsi
0x180011325  mov     [rsp+110h+var_C0], rsi
0x18001132a  mov     [rsp+110h+var_C8], rsi
0x18001132f  mov     [rsp+110h+var_D0], rsi
0x180011334  mov     [rsp+110h+var_D8], rsi
0x180011339  mov     rax, [rdi+0Ch]
0x18001133d  mov     qword ptr [rsp+110h+var_E0], rax
0x180011342  mov     [rsp+110h+var_E8], esi
0x180011346  mov     dword ptr [rsp+110h+ppv], esi
0x18001134a  mov     r9d, [rdi+8]
0x18001134e  mov     r8d, 6
0x180011354  mov     edx, [rdi]
0x180011356  lea     rcx, [rbp+57h+var_70]
0x18001135a  call    ?UpdateStatusWrapper@@YAJPEAKKW4MdmCommandStatus@@W4MdmCommandChannelType@@KKU_FILETIME@@PEAU3@4PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@6666PEAH777PEAPEAG@Z; UpdateStatusWrapper(ulong *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,ulong,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)
0x18001135f  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180011363  call    cs:__imp_GetSystemTimeAsFileTime
0x180011369  mov     rcx, [rbp+57h+var_60]
0x18001136d  mov     rax, [rcx]
0x180011370  mov     rax, [rax+40h]
0x180011374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011379  mov     [rbp+57h+var_34], eax
0x18001137c  test    eax, eax
0x18001137e  jns     loc_18001152E
0x180011384  lea     rcx, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x180011388  call    cs:__imp_GetSystemTimeAsFileTime
0x18001138e  mov     [rbp+57h+var_38], 7
0x180011395  cmp     [rbp+57h+var_50], rsi
0x180011399  jnz     loc_180011428
0x18001139f  lea     rdx, aWipeupdatestat; "WipeUpdateStatus"
0x1800113a6  lea     rcx, [rbp+57h+var_58]; this
0x1800113aa  call    ?ActivateClient@DdcPdcActivationWrapper@@QEAAJPEBG@Z; DdcPdcActivationWrapper::ActivateClient(ushort const *)
0x1800113af  test    eax, eax
0x1800113b1  jns     short loc_180011428
0x1800113b3  lea     rcx, [rbp+57h+var_68]; this
0x1800113b7  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x1800113bc  mov     ebx, eax
0x1800113be  test    eax, eax
0x1800113c0  jns     short loc_1800113E8
0x1800113c2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800113c9  jz      loc_18001152E
0x1800113cf  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x1800113d6  mov     qword ptr [rsp+110h+var_E8], rax
0x1800113db  mov     dword ptr [rsp+110h+ppv], 2BEh
0x1800113e3  jmp     loc_18001151F
0x1800113e8  lea     r8, [rbp+57h+SystemTimeAsFileTime]; struct UpdateStatusContext *
0x1800113ec  mov     rdx, rdi; struct CommandPrefix *
0x1800113ef  lea     rcx, [rbp+57h+var_68]; this
0x1800113f3  call    ?ScheduleUpdateStatusRetry@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@@Z; DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(CommandPrefix *,UpdateStatusContext *)
0x1800113f8  mov     ebx, eax
0x1800113fa  test    eax, eax
0x1800113fc  jns     loc_18001152E
0x180011402  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011409  jz      loc_18001152E
0x18001140f  lea     rax, aChrTaskschedul_8; "CHR(taskSchedulerWrapper.ScheduleUpdate"...
0x180011416  mov     qword ptr [rsp+110h+var_E8], rax
0x18001141b  mov     dword ptr [rsp+110h+ppv], 2BFh
0x180011423  jmp     loc_18001151F
0x180011428  lea     rcx, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x18001142c  call    cs:__imp_GetSystemTimeAsFileTime
0x180011432  mov     [rsp+110h+var_78], rsi
0x18001143a  mov     [rsp+110h+var_80], rsi
0x180011442  mov     [rsp+110h+var_88], rsi
0x18001144a  mov     [rsp+110h+var_90], rsi
0x180011452  mov     [rsp+110h+var_98], rsi
0x180011457  mov     [rsp+110h+var_A0], rsi
0x18001145c  mov     [rsp+110h+var_A8], rsi
0x180011461  mov     [rsp+110h+var_B0], rsi
0x180011466  mov     [rsp+110h+var_B8], rsi
0x18001146b  mov     [rsp+110h+var_C0], rsi
0x180011470  mov     [rsp+110h+var_C8], rsi
0x180011475  lea     rax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8]
0x180011479  mov     [rsp+110h+var_D0], rax
0x18001147e  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x180011482  mov     [rsp+110h+var_D8], rax
0x180011487  mov     rax, [rdi+0Ch]
0x18001148b  mov     qword ptr [rsp+110h+var_E0], rax
0x180011490  mov     eax, [rbp+57h+var_34]
0x180011493  mov     [rsp+110h+var_E8], eax
0x180011497  mov     dword ptr [rsp+110h+ppv], esi
0x18001149b  mov     r9d, [rdi+8]
0x18001149f  mov     r8d, [rbp+57h+var_38]
0x1800114a3  mov     edx, [rdi]
0x1800114a5  lea     rcx, [rbp+57h+var_70]
0x1800114a9  call    ?UpdateStatusWrapper@@YAJPEAKKW4MdmCommandStatus@@W4MdmCommandChannelType@@KKU_FILETIME@@PEAU3@4PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@6666PEAH777PEAPEAG@Z; UpdateStatusWrapper(ulong *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,ulong,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)
0x1800114ae  mov     ebx, eax
0x1800114b0  mov     edx, [rbp+57h+var_70]; unsigned int
0x1800114b3  mov     ecx, eax; int
0x1800114b5  call    ?ShouldRetry@@YAHJK@Z; ShouldRetry(long,ulong)
0x1800114ba  test    eax, eax
0x1800114bc  jz      short loc_18001152E
0x1800114be  lea     rcx, [rbp+57h+var_68]; this
0x1800114c2  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x1800114c7  mov     ebx, eax
0x1800114c9  test    eax, eax
0x1800114cb  jns     short loc_1800114EC
0x1800114cd  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800114d4  jz      short loc_18001152E
0x1800114d6  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x1800114dd  mov     qword ptr [rsp+110h+var_E8], rax
0x1800114e2  mov     dword ptr [rsp+110h+ppv], 2B7h
0x1800114ea  jmp     short loc_18001151F
0x1800114ec  lea     r8, [rbp+57h+SystemTimeAsFileTime]; struct UpdateStatusContext *
0x1800114f0  mov     rdx, rdi; struct CommandPrefix *
0x1800114f3  lea     rcx, [rbp+57h+var_68]; this
0x1800114f7  call    ?ScheduleUpdateStatusRetry@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@@Z; DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(CommandPrefix *,UpdateStatusContext *)
0x1800114fc  mov     ebx, eax
0x1800114fe  test    eax, eax
0x180011500  jns     short loc_18001152E
0x180011502  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011509  jz      short loc_18001152E
0x18001150b  lea     rax, aChrTaskschedul_8; "CHR(taskSchedulerWrapper.ScheduleUpdate"...
0x180011512  mov     qword ptr [rsp+110h+var_E8], rax
0x180011517  mov     dword ptr [rsp+110h+ppv], 2B8h
0x18001151f  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180011526  mov     r8d, ebx
0x180011529  call    McTemplateU0dsqs_EventWriteTransfer
0x18001152e  mov     eax, [rbp+57h+var_70]
0x180011531  mov     ecx, esi
0x180011533  cmp     [rbp+57h+var_50], rsi
0x180011537  setnz   cl; int
0x18001153a  mov     [rsp+110h+var_E0], ebx; int
0x18001153e  mov     [rsp+110h+var_E8], eax; unsigned int
0x180011542  mov     eax, [rbp+57h+var_34]
0x180011545  mov     dword ptr [rsp+110h+ppv], eax; int
0x180011549  mov     r9d, [rdi+8]; unsigned int
0x18001154d  mov     r8d, 4; unsigned int
0x180011553  mov     edx, [rdi]; unsigned int
0x180011555  call    ?TraceCommandResult@DdcTraceHelper@@SAXHKKKJKJ@Z; DdcTraceHelper::TraceCommandResult(int,ulong,ulong,ulong,long,ulong,long)
0x18001155a  nop
0x18001155b  mov     rcx, [rbp+57h+var_60]
0x18001155f  test    rcx, rcx
0x180011562  jz      short loc_180011575
0x180011564  mov     [rbp+57h+var_60], rsi
0x180011568  mov     rax, [rcx]
0x18001156b  mov     rax, [rax+10h]
0x18001156f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011574  nop
0x180011575  lea     rcx, [rbp+57h+var_58]; this
0x180011579  call    ?DeactivateClient@DdcPdcActivationWrapper@@QEAAXXZ; DdcPdcActivationWrapper::DeactivateClient(void)
0x18001157e  nop
0x18001157f  lea     rcx, [rbp+57h+var_68]
0x180011583  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x180011588  mov     eax, ebx
0x18001158a  mov     rcx, [rbp+57h+var_28]
0x18001158e  xor     rcx, rsp; StackCookie
0x180011591  call    __security_check_cookie
0x180011596  add     rsp, 0F8h
0x18001159d  pop     rdi
0x18001159e  pop     rsi
0x18001159f  pop     rbx
0x1800115a0  pop     rbp
0x1800115a1  retn
```
