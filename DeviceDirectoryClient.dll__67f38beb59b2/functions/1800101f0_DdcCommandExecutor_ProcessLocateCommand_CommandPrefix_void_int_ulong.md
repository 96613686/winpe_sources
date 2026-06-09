# DdcCommandExecutor::ProcessLocateCommand(CommandPrefix *,void *,int,ulong)

- ea: `0x1800101f0`
- end: `0x1800107d9`
- name: `?ProcessLocateCommand@DdcCommandExecutor@@SAJPEAUCommandPrefix@@PEAXHK@Z`
- size: `1513`
- prototype: `__int64 __fastcall(struct CommandPrefix *, void *, int, unsigned int)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005f5c`
- `0x1800063f4`

## callees

- `0x1800024c0`
- `0x180003c2c`
- `0x180004060`
- `0x1800050b8`
- `0x18000560c`
- `0x180009164`
- `0x1800101f0`
- `0x1800115c0`
- `0x180011bf0`
- `0x180011e74`
- `0x18001227c`
- `0x1800128fc`
- `0x180013004`
- `0x18001a7fc`
- `0x18001a8e4`
- `0x18001ae84`
- `0x18001c978`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800103f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010419`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800104bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010504`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800103f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010419`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800104bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010504`
- `MdmCommon!MdmGetLocation` at `0x180010404`
- `MdmCommon!MdmGetLocation` at `0x1800104ef`
- `MdmCommon!MdmGetLocation` at `0x180010404`
- `MdmCommon!MdmGetLocation` at `0x1800104ef`
- `MdmCommon!MdmSetFindMyDevice` at `0x18001037d`
- `MdmCommon!MdmSetFindMyDevice` at `0x18001037d`

## string_xrefs

- `0x1800105db`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x180010658`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x1800106c2`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x18001070a`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x18001061a`: `CHR(taskSchedulerWrapper.ScheduleLocateCommandRetry(pPrefix, dwRetries))`
- `0x1800106f6`: `CHR(taskSchedulerWrapper.ScheduleLocateCommandRetry(pPrefix, dwRetries))`
- `0x180010694`: `CHR(taskSchedulerWrapper.DeleteLocateCommandRetrySchedule(pPrefix))`
- `0x1800103a4`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcCommandExecutor::ProcessLocateCommand(
        struct CommandPrefix *a1,
        void *a2,
        int a3,
        unsigned int a4)
{
  int Location; // r13d
  int v8; // r12d
  int CommandRetry; // edi
  int v10; // edx
  int v11; // ecx
  int v12; // edx
  int v13; // ecx
  int v14; // edx
  int v15; // ecx
  int MyDevice; // eax
  int v17; // edx
  struct Windows::Data::Json::IJsonValue *v18; // rbx
  _OWORD *v19; // rdx
  int v20; // edx
  int v21; // ecx
  int v22; // edx
  int v23; // ecx
  int v24; // edx
  int v25; // ecx
  int v26; // edx
  int v27; // ecx
  int v28; // edx
  int v29; // ecx
  int v30; // edx
  int v31; // ecx
  unsigned int v32; // edx
  unsigned int v33; // r8d
  int v35; // [rsp+A0h] [rbp-80h] BYREF
  int v36; // [rsp+A4h] [rbp-7Ch] BYREF
  int v37; // [rsp+A8h] [rbp-78h] BYREF
  int v38; // [rsp+ACh] [rbp-74h] BYREF
  unsigned int v39; // [rsp+B0h] [rbp-70h] BYREF
  __int64 v40; // [rsp+B8h] [rbp-68h] BYREF
  unsigned int v41; // [rsp+C0h] [rbp-60h] BYREF
  int v42; // [rsp+C4h] [rbp-5Ch]
  int updated; // [rsp+C8h] [rbp-58h]
  struct _FILETIME v44; // [rsp+D0h] [rbp-50h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+D8h] [rbp-48h] BYREF
  int v46; // [rsp+E0h] [rbp-40h]
  struct Windows::Data::Json::IJsonValue *v47; // [rsp+E8h] [rbp-38h] BYREF
  void *v48; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v49; // [rsp+F8h] [rbp-28h]
  _QWORD v50[3]; // [rsp+100h] [rbp-20h] BYREF
  _OWORD v51[2]; // [rsp+118h] [rbp-8h] BYREF
  __int64 v52; // [rsp+138h] [rbp+18h]

  v46 = a3;
  Location = 0;
  v8 = 0;
  updated = 0;
  v41 = 0;
  v42 = 0;
  v39 = 0;
  memset(v51, 0, sizeof(v51));
  v52 = 0;
  SystemTimeAsFileTime = 0;
  v44 = 0;
  v40 = 0;
  v47 = 0;
  v36 = 0;
  v35 = 0;
  v37 = 0;
  v38 = 0;
  v50[0] = a2;
  v50[1] = 0;
  v48 = a2;
  v49 = 0;
  v50[2] = 0;
  if ( a1 )
  {
    CommandRetry = DdcAccountHelper::UsersAuthorizedToSeeLocation(&v47);
    if ( CommandRetry >= 0 )
    {
      CommandRetry = DdcDeviceInfoHelper::MasterLocationSwitchOn(&v36, v10);
      if ( CommandRetry >= 0 )
      {
        CommandRetry = DdcDeviceInfoHelper::LocationSyncEnabled(&v35, v12);
        if ( CommandRetry >= 0 )
        {
          if ( a3 )
          {
            if ( !v36 && (int)DdcDeviceInfoHelper::SetMasterLocationSwitch(v15) >= 0 )
            {
              v36 = 1;
              v37 = 1;
            }
            if ( !v35 )
            {
              MyDevice = MdmSetFindMyDevice(1);
              if ( MyDevice >= 0 )
              {
                v35 = 1;
                v38 = 1;
              }
              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  (unsigned int)"CHR(MdmSetFindMyDevice(fEnable))",
                  v17,
                  MyDevice,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                  113,
                  "CHR(MdmSetFindMyDevice(fEnable))");
              }
            }
          }
          v18 = v47;
          if ( v36
            && v35
            && !a4
            && DdcPdcActivationWrapper::ActivateClient((DdcPdcActivationWrapper *)v50, L"QuickLocationSync") >= 0 )
          {
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            Location = MdmGetLocation(0, v51);
            if ( Location >= 0 )
            {
              GetSystemTimeAsFileTime(&v44);
              updated = UpdateStatusWrapper(
                          &v41,
                          *(unsigned int *)a1,
                          5,
                          *((unsigned int *)a1 + 2),
                          0,
                          0,
                          *(_QWORD *)((char *)a1 + 12),
                          &SystemTimeAsFileTime,
                          &v44,
                          v51,
                          v18,
                          0,
                          0,
                          0,
                          0,
                          &v36,
                          &v35,
                          &v37,
                          &v38,
                          0);
            }
            DdcPdcActivationWrapper::DeactivateClient((DdcPdcActivationWrapper *)v50);
          }
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          if ( DdcPdcActivationWrapper::ActivateClient((DdcPdcActivationWrapper *)&v48, L"AccurateLocationSync") < 0 )
          {
            CommandRetry = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v40);
            if ( CommandRetry >= 0 )
            {
              CommandRetry = DdcTaskSchedulerWrapper::ScheduleLocateCommandRetry(
                               (DdcTaskSchedulerWrapper *)&v40,
                               a1,
                               a4);
              if ( CommandRetry < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v31,
                  v30,
                  CommandRetry,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
                  247,
                  "CHR(taskSchedulerWrapper.ScheduleLocateCommandRetry(pPrefix, dwRetries))");
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v29,
                v28,
                CommandRetry,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
                246,
                "CHR(taskSchedulerWrapper.Initialize())");
            }
          }
          else
          {
            if ( v36 && v35 )
              v8 = MdmGetLocation(1, v51);
            else
              v8 = -2147024891;
            GetSystemTimeAsFileTime(&v44);
            v19 = v51;
            if ( v8 < 0 )
              v19 = 0;
            v42 = UpdateStatusWrapper(
                    &v39,
                    *(unsigned int *)a1,
                    ((v8 >> 31) & 1u) + 6,
                    *((unsigned int *)a1 + 2),
                    a4,
                    v8,
                    *(_QWORD *)((char *)a1 + 12),
                    &SystemTimeAsFileTime,
                    &v44,
                    v19,
                    v18,
                    0,
                    0,
                    0,
                    0,
                    &v36,
                    &v35,
                    &v37,
                    &v38,
                    0);
            if ( (unsigned int)ShouldRetry(v42, v39) )
            {
              CommandRetry = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v40);
              if ( CommandRetry >= 0 )
              {
                CommandRetry = DdcTaskSchedulerWrapper::ScheduleLocateCommandRetry(
                                 (DdcTaskSchedulerWrapper *)&v40,
                                 a1,
                                 a4);
                if ( CommandRetry < 0
                  && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v23,
                    v22,
                    CommandRetry,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
                    234,
                    "CHR(taskSchedulerWrapper.ScheduleLocateCommandRetry(pPrefix, dwRetries))");
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  v21,
                  v20,
                  CommandRetry,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
                  233,
                  "CHR(taskSchedulerWrapper.Initialize())");
              }
            }
            else if ( a4 )
            {
              CommandRetry = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v40);
              if ( CommandRetry >= 0 )
              {
                CommandRetry = DdcTaskSchedulerWrapper::DeleteLocateCommandRetrySchedule(
                                 (DdcTaskSchedulerWrapper *)&v40,
                                 a1);
                if ( CommandRetry < 0
                  && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v27,
                    v26,
                    CommandRetry,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
                    240,
                    "CHR(taskSchedulerWrapper.DeleteLocateCommandRetrySchedule(pPrefix))");
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  v25,
                  v24,
                  CommandRetry,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
                  239,
                  "CHR(taskSchedulerWrapper.Initialize())");
              }
            }
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v15,
            v14,
            CommandRetry,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
            132,
            "CHR(DdcDeviceInfoHelper::LocationSyncEnabled(&fLocationSyncEnabled))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v13,
          v12,
          CommandRetry,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          131,
          "CHR(DdcDeviceInfoHelper::MasterLocationSwitchOn(&fMasterLocationSwitchOn))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        v10,
        CommandRetry,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        128,
        "CHR(DdcAccountHelper::UsersAuthorizedToSeeLocation(pAuthorizedCids.GetAddressOf()))");
    }
  }
  else
  {
    CommandRetry = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        125,
        "CPR(pPrefix)");
  }
  if ( a1 )
  {
    v32 = *(_DWORD *)a1;
    v33 = *((_DWORD *)a1 + 2);
  }
  else
  {
    v32 = 0;
    v33 = 0;
  }
  DdcTraceHelper::TraceLocateCommandResult(
    v49 != 0,
    v32,
    v33,
    v36,
    v35,
    v46,
    v37,
    a4,
    Location,
    updated,
    v41,
    v8,
    v42,
    v39,
    CommandRetry);
  DdcPdcActivationWrapper::DeactivateClient((DdcPdcActivationWrapper *)&v48);
  DdcPdcActivationWrapper::DeactivateClient((DdcPdcActivationWrapper *)v50);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v47);
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(&v40);
  return (unsigned int)CommandRetry;
}

```

## disassembly

```asm
0x1800101f0  mov     [rsp-8+arg_8], rbx
0x1800101f5  push    rbp
0x1800101f6  push    rsi
0x1800101f7  push    rdi
0x1800101f8  push    r12
0x1800101fa  push    r13
0x1800101fc  push    r14
0x1800101fe  push    r15
0x180010200  lea     rbp, [rsp-30h]
0x180010205  sub     rsp, 150h
0x18001020c  mov     rax, cs:__security_cookie
0x180010213  xor     rax, rsp
0x180010216  mov     [rbp+60h+var_40], rax
0x18001021a  mov     r15d, r9d
0x18001021d  mov     ebx, r8d
0x180010220  mov     [rbp+60h+var_A0], ebx
0x180010223  mov     r14, rcx
0x180010226  xor     esi, esi
0x180010228  mov     r13d, esi
0x18001022b  mov     r12d, esi
0x18001022e  mov     [rbp+60h+var_B8], esi
0x180010231  mov     [rbp+60h+var_C0], esi
0x180010234  mov     [rbp+60h+var_BC], esi
0x180010237  mov     [rbp+60h+var_D0], esi
0x18001023a  xorps   xmm0, xmm0
0x18001023d  xor     eax, eax
0x18001023f  movups  [rbp+60h+var_68], xmm0
0x180010243  movups  [rbp+60h+var_58], xmm0
0x180010247  mov     [rbp+60h+var_48], rax
0x18001024b  mov     qword ptr [rbp+60h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18001024f  mov     qword ptr [rbp+60h+var_B0.dwLowDateTime], rsi
0x180010253  mov     [rbp+60h+var_C8], rsi
0x180010257  mov     [rbp+60h+var_98], rsi
0x18001025b  mov     [rbp+60h+var_DC], esi
0x18001025e  mov     [rbp+60h+var_E0], esi
0x180010261  mov     [rbp+60h+var_D8], esi
0x180010264  mov     [rbp+60h+var_D4], esi
0x180010267  mov     [rbp+60h+var_80], rdx
0x18001026b  mov     [rbp+60h+var_78], rsi
0x18001026f  mov     [rbp+60h+var_90], rdx
0x180010273  mov     [rbp+60h+var_88], rsi
0x180010277  mov     [rbp+60h+var_70], rsi
0x18001027b  test    rcx, rcx
0x18001027e  jnz     short loc_1800102AE
0x180010280  mov     edi, 80070057h
0x180010285  lea     esi, [rcx+1]
0x180010288  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x18001028f  jz      loc_180010719
0x180010295  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x18001029c  mov     qword ptr [rsp+180h+var_158], rax
0x1800102a1  mov     [rsp+180h+var_160], 7Dh ; '}'
0x1800102a9  jmp     loc_18001070A
0x1800102ae  lea     rcx, [rbp+60h+var_98]; struct Windows::Data::Json::IJsonValue **
0x1800102b2  call    ?UsersAuthorizedToSeeLocation@DdcAccountHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z; DdcAccountHelper::UsersAuthorizedToSeeLocation(Windows::Data::Json::IJsonValue * *)
0x1800102b7  mov     edi, eax
0x1800102b9  test    eax, eax
0x1800102bb  jns     short loc_1800102E8
0x1800102bd  mov     esi, 1
0x1800102c2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x1800102c9  jz      loc_180010719
0x1800102cf  lea     rax, aChrDdcaccounth_1; "CHR(DdcAccountHelper::UsersAuthorizedTo"...
0x1800102d6  mov     qword ptr [rsp+180h+var_158], rax
0x1800102db  mov     [rsp+180h+var_160], 80h
0x1800102e3  jmp     loc_18001070A
0x1800102e8  lea     rcx, [rbp+60h+var_DC]; int *
0x1800102ec  call    ?MasterLocationSwitchOn@DdcDeviceInfoHelper@@SAJPEAH@Z; DdcDeviceInfoHelper::MasterLocationSwitchOn(int *)
0x1800102f1  mov     edi, eax
0x1800102f3  test    eax, eax
0x1800102f5  jns     short loc_180010322
0x1800102f7  mov     esi, 1
0x1800102fc  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x180010303  jz      loc_180010719
0x180010309  lea     rax, aChrDdcdevicein_0; "CHR(DdcDeviceInfoHelper::MasterLocation"...
0x180010310  mov     qword ptr [rsp+180h+var_158], rax
0x180010315  mov     [rsp+180h+var_160], 83h
0x18001031d  jmp     loc_18001070A
0x180010322  lea     rcx, [rbp+60h+var_E0]; int *
0x180010326  call    ?LocationSyncEnabled@DdcDeviceInfoHelper@@SAJPEAH@Z; DdcDeviceInfoHelper::LocationSyncEnabled(int *)
0x18001032b  mov     edi, eax
0x18001032d  mov     esi, 1
0x180010332  test    eax, eax
0x180010334  jns     short loc_18001035C
0x180010336  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x18001033d  jz      loc_180010719
0x180010343  lea     rax, aChrDdcdevicein_1; "CHR(DdcDeviceInfoHelper::LocationSyncEn"...
0x18001034a  mov     qword ptr [rsp+180h+var_158], rax
0x18001034f  mov     [rsp+180h+var_160], 84h
0x180010357  jmp     loc_18001070A
0x18001035c  test    ebx, ebx
0x18001035e  jz      short loc_1800103BB
0x180010360  cmp     [rbp+60h+var_DC], 0
0x180010364  jnz     short loc_180010375
0x180010366  call    ?SetMasterLocationSwitch@DdcDeviceInfoHelper@@SAJH@Z; DdcDeviceInfoHelper::SetMasterLocationSwitch(int)
0x18001036b  test    eax, eax
0x18001036d  js      short loc_180010375
0x18001036f  mov     [rbp+60h+var_DC], esi
0x180010372  mov     [rbp+60h+var_D8], esi
0x180010375  cmp     [rbp+60h+var_E0], 0
0x180010379  jnz     short loc_1800103BB
0x18001037b  mov     ecx, esi
0x18001037d  call    cs:__imp_?MdmSetFindMyDevice@@YAJH@Z; MdmSetFindMyDevice(int)
0x180010383  test    eax, eax
0x180010385  jns     short loc_1800103B5
0x180010387  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x18001038e  jz      short loc_1800103BB
0x180010390  lea     rcx, aChrMdmsetfindm; "CHR(MdmSetFindMyDevice(fEnable))"
0x180010397  mov     qword ptr [rsp+180h+var_158], rcx
0x18001039c  mov     [rsp+180h+var_160], 371h
0x1800103a4  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800103ab  mov     r8d, eax
0x1800103ae  call    McTemplateU0dsqs_EventWriteTransfer
0x1800103b3  jmp     short loc_1800103BB
0x1800103b5  mov     [rbp+60h+var_E0], esi
0x1800103b8  mov     [rbp+60h+var_D4], esi
0x1800103bb  mov     rbx, [rbp+60h+var_98]
0x1800103bf  cmp     [rbp+60h+var_DC], 0
0x1800103c3  jz      loc_1800104BB
0x1800103c9  cmp     [rbp+60h+var_E0], 0
0x1800103cd  jz      loc_1800104BB
0x1800103d3  test    r15d, r15d
0x1800103d6  jnz     loc_1800104BB
0x1800103dc  lea     rdx, aQuicklocations; "QuickLocationSync"
0x1800103e3  lea     rcx, [rbp+60h+var_80]; this
0x1800103e7  call    ?ActivateClient@DdcPdcActivationWrapper@@QEAAJPEBG@Z; DdcPdcActivationWrapper::ActivateClient(ushort const *)
0x1800103ec  test    eax, eax
0x1800103ee  js      loc_1800104BB
0x1800103f4  lea     rcx, [rbp+60h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800103f8  call    cs:__imp_GetSystemTimeAsFileTime
0x1800103fe  lea     rdx, [rbp+60h+var_68]
0x180010402  xor     ecx, ecx
0x180010404  call    cs:__imp_?MdmGetLocation@@YAJW4PositionAccuracy@Geolocation@Devices@Windows@@PEAUMdmLocation@@@Z; MdmGetLocation(Windows::Devices::Geolocation::PositionAccuracy,MdmLocation *)
0x18001040a  mov     r13d, eax
0x18001040d  test    eax, eax
0x18001040f  js      loc_1800104B2
0x180010415  lea     rcx, [rbp+60h+var_B0]; lpSystemTimeAsFileTime
0x180010419  call    cs:__imp_GetSystemTimeAsFileTime
0x18001041f  mov     rcx, [r14+0Ch]
0x180010423  xor     edx, edx
0x180010425  mov     [rsp+180h+var_E8], rdx
0x18001042d  lea     rax, [rbp+60h+var_D4]
0x180010431  mov     [rsp+180h+var_F0], rax
0x180010439  lea     rax, [rbp+60h+var_D8]
0x18001043d  mov     [rsp+180h+var_F8], rax
0x180010445  lea     rax, [rbp+60h+var_E0]
0x180010449  mov     [rsp+180h+var_100], rax
0x180010451  lea     rax, [rbp+60h+var_DC]
0x180010455  mov     [rsp+180h+var_108], rax
0x18001045a  mov     qword ptr [rsp+180h+var_110], rdx
0x18001045f  mov     qword ptr [rsp+180h+var_118], rdx
0x180010464  mov     qword ptr [rsp+180h+var_120], rdx
0x180010469  mov     qword ptr [rsp+180h+var_128], rdx
0x18001046e  mov     qword ptr [rsp+180h+var_130], rbx
0x180010473  lea     rax, [rbp+60h+var_68]
0x180010477  mov     qword ptr [rsp+180h+var_138], rax
0x18001047c  lea     rax, [rbp+60h+var_B0]
0x180010480  mov     qword ptr [rsp+180h+var_140], rax
0x180010485  lea     rax, [rbp+60h+SystemTimeAsFileTime]
0x180010489  mov     qword ptr [rsp+180h+var_148], rax
0x18001048e  mov     qword ptr [rsp+180h+var_150], rcx
0x180010493  mov     [rsp+180h+var_158], edx
0x180010497  mov     [rsp+180h+var_160], edx
0x18001049b  mov     r9d, [r14+8]
0x18001049f  lea     r8d, [r15+5]
0x1800104a3  mov     edx, [r14]
0x1800104a6  lea     rcx, [rbp+60h+var_C0]
0x1800104aa  call    ?UpdateStatusWrapper@@YAJPEAKKW4MdmCommandStatus@@W4MdmCommandChannelType@@KKU_FILETIME@@PEAU3@4PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@6666PEAH777PEAPEAG@Z; UpdateStatusWrapper(ulong *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,ulong,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)
0x1800104af  mov     [rbp+60h+var_B8], eax
0x1800104b2  lea     rcx, [rbp+60h+var_80]; this
0x1800104b6  call    ?DeactivateClient@DdcPdcActivationWrapper@@QEAAXXZ; DdcPdcActivationWrapper::DeactivateClient(void)
0x1800104bb  lea     rcx, [rbp+60h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800104bf  call    cs:__imp_GetSystemTimeAsFileTime
0x1800104c5  lea     rdx, aAccuratelocati; "AccurateLocationSync"
0x1800104cc  lea     rcx, [rbp+60h+var_90]; this
0x1800104d0  call    ?ActivateClient@DdcPdcActivationWrapper@@QEAAJPEBG@Z; DdcPdcActivationWrapper::ActivateClient(ushort const *)
0x1800104d5  test    eax, eax
0x1800104d7  js      loc_1800106AA
0x1800104dd  cmp     [rbp+60h+var_DC], 0
0x1800104e1  jz      short loc_1800104FA
0x1800104e3  cmp     [rbp+60h+var_E0], 0
0x1800104e7  jz      short loc_1800104FA
0x1800104e9  lea     rdx, [rbp+60h+var_68]
0x1800104ed  mov     ecx, esi
0x1800104ef  call    cs:__imp_?MdmGetLocation@@YAJW4PositionAccuracy@Geolocation@Devices@Windows@@PEAUMdmLocation@@@Z; MdmGetLocation(Windows::Devices::Geolocation::PositionAccuracy,MdmLocation *)
0x1800104f5  mov     r12d, eax
0x1800104f8  jmp     short loc_180010500
0x1800104fa  mov     r12d, 80070005h
0x180010500  lea     rcx, [rbp+60h+var_B0]; lpSystemTimeAsFileTime
0x180010504  call    cs:__imp_GetSystemTimeAsFileTime
0x18001050a  mov     rax, [r14+0Ch]
0x18001050e  lea     rdx, [rbp+60h+var_68]
0x180010512  xor     r9d, r9d
0x180010515  test    r12d, r12d
0x180010518  cmovs   rdx, r9
0x18001051c  mov     r8d, r12d
0x18001051f  sar     r8d, 1Fh
0x180010523  and     r8d, esi
0x180010526  add     r8d, 6
0x18001052a  mov     [rsp+180h+var_E8], r9
0x180010532  lea     rcx, [rbp+60h+var_D4]
0x180010536  mov     [rsp+180h+var_F0], rcx
0x18001053e  lea     rcx, [rbp+60h+var_D8]
0x180010542  mov     [rsp+180h+var_F8], rcx
0x18001054a  lea     rcx, [rbp+60h+var_E0]
0x18001054e  mov     [rsp+180h+var_100], rcx
0x180010556  lea     rcx, [rbp+60h+var_DC]
0x18001055a  mov     [rsp+180h+var_108], rcx
0x18001055f  mov     qword ptr [rsp+180h+var_110], r9
0x180010564  mov     qword ptr [rsp+180h+var_118], r9
0x180010569  mov     qword ptr [rsp+180h+var_120], r9
0x18001056e  mov     qword ptr [rsp+180h+var_128], r9
0x180010573  mov     qword ptr [rsp+180h+var_130], rbx
0x180010578  mov     qword ptr [rsp+180h+var_138], rdx
0x18001057d  lea     rcx, [rbp+60h+var_B0]
0x180010581  mov     qword ptr [rsp+180h+var_140], rcx
0x180010586  lea     rcx, [rbp+60h+SystemTimeAsFileTime]
0x18001058a  mov     qword ptr [rsp+180h+var_148], rcx
0x18001058f  mov     qword ptr [rsp+180h+var_150], rax
0x180010594  mov     [rsp+180h+var_158], r12d
0x180010599  mov     [rsp+180h+var_160], r15d
0x18001059e  mov     r9d, [r14+8]
0x1800105a2  mov     edx, [r14]
0x1800105a5  lea     rcx, [rbp+60h+var_D0]
0x1800105a9  call    ?UpdateStatusWrapper@@YAJPEAKKW4MdmCommandStatus@@W4MdmCommandChannelType@@KKU_FILETIME@@PEAU3@4PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@6666PEAH777PEAPEAG@Z; UpdateStatusWrapper(ulong *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,ulong,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)
0x1800105ae  mov     ecx, eax; int
0x1800105b0  mov     [rbp+60h+var_BC], eax
0x1800105b3  mov     edx, [rbp+60h+var_D0]; unsigned int
0x1800105b6  call    ?ShouldRetry@@YAHJK@Z; ShouldRetry(long,ulong)
0x1800105bb  test    eax, eax
0x1800105bd  jz      short loc_180010633
0x1800105bf  lea     rcx, [rbp+60h+var_C8]; this
0x1800105c3  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x1800105c8  mov     edi, eax
0x1800105ca  test    eax, eax
0x1800105cc  jns     short loc_1800105F4
0x1800105ce  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x1800105d5  jz      loc_180010719
0x1800105db  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x1800105e2  mov     qword ptr [rsp+180h+var_158], rax
0x1800105e7  mov     [rsp+180h+var_160], 0E9h
0x1800105ef  jmp     loc_18001070A
0x1800105f4  mov     r8d, r15d; unsigned int
0x1800105f7  mov     rdx, r14; struct CommandPrefix *
0x1800105fa  lea     rcx, [rbp+60h+var_C8]; this
0x1800105fe  call    ?ScheduleLocateCommandRetry@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@K@Z; DdcTaskSchedulerWrapper::ScheduleLocateCommandRetry(CommandPrefix *,ulong)
0x180010603  mov     edi, eax
0x180010605  test    eax, eax
0x180010607  jns     loc_180010719
0x18001060d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x180010614  jz      loc_180010719
0x18001061a  lea     rax, aChrTaskschedul_3; "CHR(taskSchedulerWrapper.ScheduleLocate"...
0x180010621  mov     qword ptr [rsp+180h+var_158], rax
0x180010626  mov     [rsp+180h+var_160], 0EAh
0x18001062e  jmp     loc_18001070A
0x180010633  test    r15d, r15d
0x180010636  jz      loc_180010719
0x18001063c  lea     rcx, [rbp+60h+var_C8]; this
0x180010640  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x180010645  mov     edi, eax
0x180010647  test    eax, eax
0x180010649  jns     short loc_180010671
0x18001064b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x180010652  jz      loc_180010719
0x180010658  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x18001065f  mov     qword ptr [rsp+180h+var_158], rax
0x180010664  mov     [rsp+180h+var_160], 0EFh
0x18001066c  jmp     loc_18001070A
0x180010671  mov     rdx, r14; struct CommandPrefix *
0x180010674  lea     rcx, [rbp+60h+var_C8]; this
0x180010678  call    ?DeleteLocateCommandRetrySchedule@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@@Z; DdcTaskSchedulerWrapper::DeleteLocateCommandRetrySchedule(CommandPrefix *)
0x18001067d  mov     edi, eax
0x18001067f  test    eax, eax
0x180010681  jns     loc_180010719
0x180010687  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x18001068e  jz      loc_180010719
0x180010694  lea     rax, aChrTaskschedul_9; "CHR(taskSchedulerWrapper.DeleteLocateCo"...
0x18001069b  mov     qword ptr [rsp+180h+var_158], rax
0x1800106a0  mov     [rsp+180h+var_160], 0F0h
0x1800106a8  jmp     short loc_18001070A
0x1800106aa  lea     rcx, [rbp+60h+var_C8]; this
0x1800106ae  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x1800106b3  mov     edi, eax
0x1800106b5  test    eax, eax
0x1800106b7  jns     short loc_1800106D8
0x1800106b9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x1800106c0  jz      short loc_180010719
0x1800106c2  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x1800106c9  mov     qword ptr [rsp+180h+var_158], rax
0x1800106ce  mov     [rsp+180h+var_160], 0F6h
0x1800106d6  jmp     short loc_18001070A
0x1800106d8  mov     r8d, r15d; unsigned int
0x1800106db  mov     rdx, r14; struct CommandPrefix *
0x1800106de  lea     rcx, [rbp+60h+var_C8]; this
0x1800106e2  call    ?ScheduleLocateCommandRetry@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@K@Z; DdcTaskSchedulerWrapper::ScheduleLocateCommandRetry(CommandPrefix *,ulong)
0x1800106e7  mov     edi, eax
0x1800106e9  test    eax, eax
0x1800106eb  jns     short loc_180010719
0x1800106ed  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x1800106f4  jz      short loc_180010719
0x1800106f6  lea     rax, aChrTaskschedul_3; "CHR(taskSchedulerWrapper.ScheduleLocate"...
0x1800106fd  mov     qword ptr [rsp+180h+var_158], rax
  ... truncated ...
```
