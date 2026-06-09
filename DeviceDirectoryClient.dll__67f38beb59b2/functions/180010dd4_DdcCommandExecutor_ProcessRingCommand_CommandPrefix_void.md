# DdcCommandExecutor::ProcessRingCommand(CommandPrefix *,void *)

- ea: `0x180010dd4`
- end: `0x180011150`
- name: `?ProcessRingCommand@DdcCommandExecutor@@SAJPEAUCommandPrefix@@PEAX@Z`
- size: `892`
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
- `0x180010dd4`
- `0x1800115c0`
- `0x180011bf0`
- `0x180011e74`
- `0x1800128fc`
- `0x1800132e4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010e4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010f0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010f30`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010e4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010f0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010f30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010e70`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010e70`

## string_xrefs

- `0x180010f84`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x180011082`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x1800110cb`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x180010e81`: `RingUpdateStatus`
- `0x180010f54`: `RingUpdateStatus`
- `0x180010fc4`: `CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, &updateStatusContext))`
- `0x1800110b7`: `CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, &updateStatusContext))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DdcCommandExecutor::ProcessRingCommand(struct CommandPrefix *a1, void *a2)
{
  int updated; // ebx
  DWORD dwHighDateTime; // ecx
  __int64 dwLowDateTime; // r8
  int v6; // edx
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  int v10; // edx
  int v11; // ecx
  int v12; // edx
  int v13; // ecx
  LPVOID v14; // rcx
  unsigned int v16; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v17; // [rsp+A8h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+B0h] [rbp-9h] BYREF
  void *v19; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v20; // [rsp+C0h] [rbp+7h]
  struct _FILETIME SystemTimeAsFileTime[4]; // [rsp+C8h] [rbp+Fh] BYREF

  memset(SystemTimeAsFileTime, 0, 28);
  v16 = 0;
  v17 = 0;
  v19 = a2;
  v20 = 0;
  ppv = 0;
  if ( !a1 )
  {
    updated = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        25,
        "CPR(pPrefix)");
    goto LABEL_24;
  }
  GetSystemTimeAsFileTime(SystemTimeAsFileTime);
  SystemTimeAsFileTime[2].dwHighDateTime = CoCreateInstance(&CLSID_CommandHandler, 0, 1u, &IID_ICommandHandler, &ppv);
  if ( (SystemTimeAsFileTime[2].dwHighDateTime & 0x80000000) == 0 )
  {
    if ( DdcPdcActivationWrapper::ActivateClient((DdcPdcActivationWrapper *)&v19, L"RingUpdateStatus") >= 0 )
      UpdateStatusWrapper(
        &v16,
        *(unsigned int *)a1,
        4,
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
    SystemTimeAsFileTime[2].dwHighDateTime = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(
                                               ppv,
                                               1);
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
  dwHighDateTime = SystemTimeAsFileTime[2].dwHighDateTime;
  dwLowDateTime = (unsigned int)((SystemTimeAsFileTime[2].dwHighDateTime & 0x80000000) != 0) + 6;
  SystemTimeAsFileTime[2].dwLowDateTime = ((SystemTimeAsFileTime[2].dwHighDateTime & 0x80000000) != 0) + 6;
  if ( !v20 )
  {
    if ( DdcPdcActivationWrapper::ActivateClient((DdcPdcActivationWrapper *)&v19, L"RingUpdateStatus") < 0 )
    {
      updated = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v17);
      if ( updated >= 0 )
      {
        updated = DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(
                    (DdcTaskSchedulerWrapper *)&v17,
                    a1,
                    (struct UpdateStatusContext *)SystemTimeAsFileTime);
        if ( updated < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v9,
            v8,
            updated,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
            80,
            "CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, &updateStatusContext))");
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          updated,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          79,
          "CHR(taskSchedulerWrapper.Initialize())");
      }
      goto LABEL_24;
    }
    dwHighDateTime = SystemTimeAsFileTime[2].dwHighDateTime;
    dwLowDateTime = SystemTimeAsFileTime[2].dwLowDateTime;
  }
  updated = UpdateStatusWrapper(
              &v16,
              *(unsigned int *)a1,
              dwLowDateTime,
              *((unsigned int *)a1 + 2),
              0,
              dwHighDateTime,
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
  if ( (unsigned int)ShouldRetry(updated, v16) )
  {
    updated = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v17);
    if ( updated >= 0 )
    {
      updated = DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(
                  (DdcTaskSchedulerWrapper *)&v17,
                  a1,
                  (struct UpdateStatusContext *)SystemTimeAsFileTime);
      if ( updated < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v13,
          v12,
          updated,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          73,
          "CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, &updateStatusContext))");
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        v10,
        updated,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        72,
        "CHR(taskSchedulerWrapper.Initialize())");
    }
  }
LABEL_24:
  DdcTraceHelper::TraceCommandResult(
    v20 != 0,
    *(_DWORD *)a1,
    1u,
    *((_DWORD *)a1 + 2),
    SystemTimeAsFileTime[2].dwHighDateTime,
    v16,
    updated);
  v14 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
  }
  DdcPdcActivationWrapper::DeactivateClient((DdcPdcActivationWrapper *)&v19);
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(&v17);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180010dd4  push    rbp
0x180010dd6  push    rbx
0x180010dd7  push    rsi
0x180010dd8  push    r14
0x180010dda  lea     rbp, [rsp-3Fh]
0x180010ddf  sub     rsp, 0F8h
0x180010de6  mov     rax, cs:__security_cookie
0x180010ded  xor     rax, rsp
0x180010df0  mov     [rbp+57h+var_28], rax
0x180010df4  mov     rsi, rcx
0x180010df7  xorps   xmm0, xmm0
0x180010dfa  movups  xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x180010dfe  movups  xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwHighDateTime+8], xmm0
0x180010e02  xor     r14d, r14d
0x180010e05  mov     [rbp+57h+var_70], r14d
0x180010e09  mov     [rbp+57h+var_68], r14
0x180010e0d  mov     [rbp+57h+var_58], rdx
0x180010e11  mov     [rbp+57h+var_50], r14
0x180010e15  mov     [rbp+57h+var_60], r14
0x180010e19  test    rcx, rcx
0x180010e1c  jnz     short loc_180010E49
0x180010e1e  mov     ebx, 80070057h
0x180010e23  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180010e2a  jz      loc_1800110DA
0x180010e30  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x180010e37  mov     qword ptr [rsp+110h+var_E8], rax
0x180010e3c  mov     dword ptr [rsp+110h+ppv], 119h
0x180010e44  jmp     loc_1800110CB
0x180010e49  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010e4d  call    cs:__imp_GetSystemTimeAsFileTime
0x180010e53  lea     rax, [rbp+57h+var_60]
0x180010e57  mov     [rsp+110h+ppv], rax; ppv
0x180010e5c  lea     r9, IID_ICommandHandler; riid
0x180010e63  xor     edx, edx; pUnkOuter
0x180010e65  lea     r8d, [rdx+1]; dwClsContext
0x180010e69  lea     rcx, CLSID_CommandHandler; rclsid
0x180010e70  call    cs:__imp_CoCreateInstance
0x180010e76  mov     [rbp+57h+var_34], eax
0x180010e79  test    eax, eax
0x180010e7b  js      loc_180010F2C
0x180010e81  lea     rdx, aRingupdatestat; "RingUpdateStatus"
0x180010e88  lea     rcx, [rbp+57h+var_58]; this
0x180010e8c  call    ?ActivateClient@DdcPdcActivationWrapper@@QEAAJPEBG@Z; DdcPdcActivationWrapper::ActivateClient(ushort const *)
0x180010e91  test    eax, eax
0x180010e93  js      short loc_180010F0A
0x180010e95  mov     [rsp+110h+var_78], r14
0x180010e9d  mov     [rsp+110h+var_80], r14
0x180010ea5  mov     [rsp+110h+var_88], r14
0x180010ead  mov     [rsp+110h+var_90], r14
0x180010eb5  mov     [rsp+110h+var_98], r14
0x180010eba  mov     [rsp+110h+var_A0], r14
0x180010ebf  mov     [rsp+110h+var_A8], r14
0x180010ec4  mov     [rsp+110h+var_B0], r14
0x180010ec9  mov     [rsp+110h+var_B8], r14
0x180010ece  mov     [rsp+110h+var_C0], r14
0x180010ed3  mov     [rsp+110h+var_C8], r14
0x180010ed8  mov     [rsp+110h+var_D0], r14
0x180010edd  mov     [rsp+110h+var_D8], r14
0x180010ee2  mov     rax, [rsi+0Ch]
0x180010ee6  mov     qword ptr [rsp+110h+var_E0], rax
0x180010eeb  mov     [rsp+110h+var_E8], r14d
0x180010ef0  mov     dword ptr [rsp+110h+ppv], r14d
0x180010ef5  mov     r9d, [rsi+8]
0x180010ef9  mov     r8d, 4
0x180010eff  mov     edx, [rsi]
0x180010f01  lea     rcx, [rbp+57h+var_70]
0x180010f05  call    ?UpdateStatusWrapper@@YAJPEAKKW4MdmCommandStatus@@W4MdmCommandChannelType@@KKU_FILETIME@@PEAU3@4PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@6666PEAH777PEAPEAG@Z; UpdateStatusWrapper(ulong *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,ulong,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)
0x180010f0a  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010f0e  call    cs:__imp_GetSystemTimeAsFileTime
0x180010f14  mov     rcx, [rbp+57h+var_60]
0x180010f18  mov     rax, [rcx]
0x180010f1b  mov     edx, 1
0x180010f20  mov     rax, [rax+18h]
0x180010f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f29  mov     [rbp+57h+var_34], eax
0x180010f2c  lea     rcx, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x180010f30  call    cs:__imp_GetSystemTimeAsFileTime
0x180010f36  mov     r8d, r14d
0x180010f39  mov     ecx, [rbp+57h+var_34]
0x180010f3c  test    ecx, ecx
0x180010f3e  sets    r8b
0x180010f42  add     r8d, 6
0x180010f46  mov     [rbp+57h+var_38], r8d
0x180010f4a  cmp     [rbp+57h+var_50], r14
0x180010f4e  jnz     loc_180010FE4
0x180010f54  lea     rdx, aRingupdatestat; "RingUpdateStatus"
0x180010f5b  lea     rcx, [rbp+57h+var_58]; this
0x180010f5f  call    ?ActivateClient@DdcPdcActivationWrapper@@QEAAJPEBG@Z; DdcPdcActivationWrapper::ActivateClient(ushort const *)
0x180010f64  test    eax, eax
0x180010f66  jns     short loc_180010FDD
0x180010f68  lea     rcx, [rbp+57h+var_68]; this
0x180010f6c  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x180010f71  mov     ebx, eax
0x180010f73  test    eax, eax
0x180010f75  jns     short loc_180010F9D
0x180010f77  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180010f7e  jz      loc_1800110DA
0x180010f84  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x180010f8b  mov     qword ptr [rsp+110h+var_E8], rax
0x180010f90  mov     dword ptr [rsp+110h+ppv], 14Fh
0x180010f98  jmp     loc_1800110CB
0x180010f9d  lea     r8, [rbp+57h+SystemTimeAsFileTime]; struct UpdateStatusContext *
0x180010fa1  mov     rdx, rsi; struct CommandPrefix *
0x180010fa4  lea     rcx, [rbp+57h+var_68]; this
0x180010fa8  call    ?ScheduleUpdateStatusRetry@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@@Z; DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(CommandPrefix *,UpdateStatusContext *)
0x180010fad  mov     ebx, eax
0x180010faf  test    eax, eax
0x180010fb1  jns     loc_1800110DA
0x180010fb7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180010fbe  jz      loc_1800110DA
0x180010fc4  lea     rax, aChrTaskschedul_8; "CHR(taskSchedulerWrapper.ScheduleUpdate"...
0x180010fcb  mov     qword ptr [rsp+110h+var_E8], rax
0x180010fd0  mov     dword ptr [rsp+110h+ppv], 150h
0x180010fd8  jmp     loc_1800110CB
0x180010fdd  mov     ecx, [rbp+57h+var_34]
0x180010fe0  mov     r8d, [rbp+57h+var_38]
0x180010fe4  mov     [rsp+110h+var_78], r14
0x180010fec  mov     [rsp+110h+var_80], r14
0x180010ff4  mov     [rsp+110h+var_88], r14
0x180010ffc  mov     [rsp+110h+var_90], r14
0x180011004  mov     [rsp+110h+var_98], r14
0x180011009  mov     [rsp+110h+var_A0], r14
0x18001100e  mov     [rsp+110h+var_A8], r14
0x180011013  mov     [rsp+110h+var_B0], r14
0x180011018  mov     [rsp+110h+var_B8], r14
0x18001101d  mov     [rsp+110h+var_C0], r14
0x180011022  mov     [rsp+110h+var_C8], r14
0x180011027  lea     rax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8]
0x18001102b  mov     [rsp+110h+var_D0], rax
0x180011030  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x180011034  mov     [rsp+110h+var_D8], rax
0x180011039  mov     rax, [rsi+0Ch]
0x18001103d  mov     qword ptr [rsp+110h+var_E0], rax
0x180011042  mov     [rsp+110h+var_E8], ecx
0x180011046  mov     dword ptr [rsp+110h+ppv], r14d
0x18001104b  mov     r9d, [rsi+8]
0x18001104f  mov     edx, [rsi]
0x180011051  lea     rcx, [rbp+57h+var_70]
0x180011055  call    ?UpdateStatusWrapper@@YAJPEAKKW4MdmCommandStatus@@W4MdmCommandChannelType@@KKU_FILETIME@@PEAU3@4PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@6666PEAH777PEAPEAG@Z; UpdateStatusWrapper(ulong *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,ulong,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)
0x18001105a  mov     ebx, eax
0x18001105c  mov     edx, [rbp+57h+var_70]; unsigned int
0x18001105f  mov     ecx, eax; int
0x180011061  call    ?ShouldRetry@@YAHJK@Z; ShouldRetry(long,ulong)
0x180011066  test    eax, eax
0x180011068  jz      short loc_1800110DA
0x18001106a  lea     rcx, [rbp+57h+var_68]; this
0x18001106e  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x180011073  mov     ebx, eax
0x180011075  test    eax, eax
0x180011077  jns     short loc_180011098
0x180011079  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011080  jz      short loc_1800110DA
0x180011082  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x180011089  mov     qword ptr [rsp+110h+var_E8], rax
0x18001108e  mov     dword ptr [rsp+110h+ppv], 148h
0x180011096  jmp     short loc_1800110CB
0x180011098  lea     r8, [rbp+57h+SystemTimeAsFileTime]; struct UpdateStatusContext *
0x18001109c  mov     rdx, rsi; struct CommandPrefix *
0x18001109f  lea     rcx, [rbp+57h+var_68]; this
0x1800110a3  call    ?ScheduleUpdateStatusRetry@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@@Z; DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(CommandPrefix *,UpdateStatusContext *)
0x1800110a8  mov     ebx, eax
0x1800110aa  test    eax, eax
0x1800110ac  jns     short loc_1800110DA
0x1800110ae  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800110b5  jz      short loc_1800110DA
0x1800110b7  lea     rax, aChrTaskschedul_8; "CHR(taskSchedulerWrapper.ScheduleUpdate"...
0x1800110be  mov     qword ptr [rsp+110h+var_E8], rax
0x1800110c3  mov     dword ptr [rsp+110h+ppv], 149h
0x1800110cb  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800110d2  mov     r8d, ebx
0x1800110d5  call    McTemplateU0dsqs_EventWriteTransfer
0x1800110da  mov     eax, [rbp+57h+var_70]
0x1800110dd  mov     ecx, r14d
0x1800110e0  cmp     [rbp+57h+var_50], r14
0x1800110e4  setnz   cl; int
0x1800110e7  mov     [rsp+110h+var_E0], ebx; int
0x1800110eb  mov     [rsp+110h+var_E8], eax; unsigned int
0x1800110ef  mov     eax, [rbp+57h+var_34]
0x1800110f2  mov     dword ptr [rsp+110h+ppv], eax; int
0x1800110f6  mov     r9d, [rsi+8]; unsigned int
0x1800110fa  mov     r8d, 1; unsigned int
0x180011100  mov     edx, [rsi]; unsigned int
0x180011102  call    ?TraceCommandResult@DdcTraceHelper@@SAXHKKKJKJ@Z; DdcTraceHelper::TraceCommandResult(int,ulong,ulong,ulong,long,ulong,long)
0x180011107  nop
0x180011108  mov     rcx, [rbp+57h+var_60]
0x18001110c  test    rcx, rcx
0x18001110f  jz      short loc_180011122
0x180011111  mov     [rbp+57h+var_60], r14
0x180011115  mov     rax, [rcx]
0x180011118  mov     rax, [rax+10h]
0x18001111c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011121  nop
0x180011122  lea     rcx, [rbp+57h+var_58]; this
0x180011126  call    ?DeactivateClient@DdcPdcActivationWrapper@@QEAAXXZ; DdcPdcActivationWrapper::DeactivateClient(void)
0x18001112b  nop
0x18001112c  lea     rcx, [rbp+57h+var_68]
0x180011130  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x180011135  mov     eax, ebx
0x180011137  mov     rcx, [rbp+57h+var_28]
0x18001113b  xor     rcx, rsp; StackCookie
0x18001113e  call    __security_check_cookie
0x180011143  add     rsp, 0F8h
0x18001114a  pop     r14
0x18001114c  pop     rsi
0x18001114d  pop     rbx
0x18001114e  pop     rbp
0x18001114f  retn
```
