# DdcTaskStateHandlerDesktop::ProcessStateChange(void)

- ea: `0x180003680`
- end: `0x180003e9e`
- name: `?ProcessStateChange@DdcTaskStateHandlerDesktop@@UEAAJXZ`
- size: `2078`
- prototype: `__int64 __fastcall(DdcTaskStateHandlerDesktop *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800026ac`
- `0x180003680`
- `0x1800047f8`
- `0x180004b18`
- `0x18000b1e4`
- `0x18000c010`

## import_xrefs

- `MdmCommon!MdmIsFindMyDeviceEnabled` at `0x180003721`
- `MdmCommon!MdmIsFindMyDeviceEnabled` at `0x180003721`
- `OLEAUT32!__imp_VariantInit` at `0x1800037ca`
- `OLEAUT32!__imp_VariantInit` at `0x1800037ca`
- `OLEAUT32!__imp_VariantClear` at `0x180003918`
- `OLEAUT32!__imp_VariantClear` at `0x180003918`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003813`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003813`

## string_xrefs

- `0x180003780`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddctaskstatehandlerdesktop.cpp`
- `0x180003e4f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddctaskstatehandlerdesktop.cpp`
- `0x180003952`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x180003992`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_PERIODIC_1_TASK, 0))`
- `0x1800039d2`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_PERIODIC_6_TASK, 0))`
- `0x180003a12`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_CONNECTED_TO_NETWORK_TASK, 0))`
- `0x180003a52`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_SCREEN_ON_OFF_TASK, 0))`
- `0x180003a9a`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_INTEGRITY_CHECK_TASK, 0))`
- `0x180003e3b`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_INTEGRITY_CHECK_TASK, 0))`
- `0x180003ada`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_PERIODIC_24_TASK, 0))`
- `0x180003cc5`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_PERIODIC_24_TASK, 0))`
- `0x180003b1a`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_LOCATION_RIGHTS_CHANGE, 0))`
- `0x180003d09`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_LOCATION_RIGHTS_CHANGE, 0))`
- `0x180003b5a`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_ACCOUNT_CHANGE_TASK, 0))`
- `0x180003b9e`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_REGISTER_USER_DEVICE_TASK, 0))`
- `0x180003c05`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_INTEGRITY_CHECK_TASK, 1))`
- `0x180003c45`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_ACCOUNT_CHANGE_TASK, 1))`
- `0x180003dc9`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_ACCOUNT_CHANGE_TASK, 1))`
- `0x180003c85`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_REGISTER_USER_DEVICE_TASK, 1))`
- `0x180003e02`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_REGISTER_USER_DEVICE_TASK, 1))`
- `0x180003d49`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_PERIODIC_24_TASK, 1))`
- `0x180003d89`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_LOCATION_RIGHTS_CHANGE, 1))`
- `0x180003752`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180003840`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x18000382c`: `CHR(CoCreateInstance(CLSID_TaskScheduler, 0, CLSCTX_INPROC_SERVER, IID_ITaskService, (PVOID*)&pTaskService))`
- `0x1800038e5`: `CHR(pTaskService->Connect(vtEmpty, vtEmpty, vtEmpty, vtEmpty))`

## pseudocode

```c
__int64 __fastcall DdcTaskStateHandlerDesktop::ProcessStateChange(DdcTaskStateHandlerDesktop *this)
{
  LPVOID v1; // rbx
  int v2; // edx
  int v3; // ecx
  HRESULT MyDeviceEnabled; // edi
  int v5; // esi
  int v6; // edx
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  LPVOID v10; // rcx
  int v11; // edx
  int v12; // ecx
  int v13; // edx
  int v14; // ecx
  const unsigned __int16 *v15; // rdx
  LPVOID v16; // rcx
  const unsigned __int16 *v17; // rdx
  int v18; // ecx
  const unsigned __int16 *v19; // rdx
  int v20; // ecx
  const unsigned __int16 *v21; // rdx
  int v22; // ecx
  const unsigned __int16 *v23; // rdx
  int v24; // ecx
  const unsigned __int16 *v25; // rdx
  int v26; // ecx
  const unsigned __int16 *v27; // rdx
  int v28; // ecx
  const unsigned __int16 *v29; // rdx
  int v30; // ecx
  const unsigned __int16 *v31; // rdx
  int v32; // ecx
  int v33; // edx
  int v34; // ecx
  const unsigned __int16 *v35; // rdx
  int v36; // ecx
  const unsigned __int16 *v37; // rdx
  int v38; // ecx
  const unsigned __int16 *v39; // rdx
  int v40; // ecx
  const unsigned __int16 *v41; // rdx
  int v42; // ecx
  int v43; // edx
  int v44; // ecx
  const unsigned __int16 *v45; // rdx
  int v46; // ecx
  const unsigned __int16 *v47; // rdx
  int v48; // ecx
  const unsigned __int16 *v49; // rdx
  int v50; // ecx
  const unsigned __int16 *v51; // rdx
  int v52; // ecx
  int v53; // edx
  int v54; // ecx
  LPVOID v56; // [rsp+40h] [rbp-D8h] BYREF
  int v57; // [rsp+48h] [rbp-D0h] BYREF
  unsigned int v58; // [rsp+4Ch] [rbp-CCh] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-C8h] BYREF
  VARIANTARG v60; // [rsp+70h] [rbp-A8h] BYREF
  VARIANTARG v61; // [rsp+90h] [rbp-88h] BYREF
  VARIANTARG v62; // [rsp+B0h] [rbp-68h] BYREF
  VARIANTARG v63; // [rsp+D0h] [rbp-48h] BYREF
  unsigned int v64; // [rsp+128h] [rbp+10h] BYREF
  unsigned int v65; // [rsp+130h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+138h] [rbp+20h] BYREF

  v1 = 0;
  v56 = 0;
  v65 = 0;
  v58 = 0;
  v64 = 0;
  MyDeviceEnabled = DdcAccountHelper::EnumerateUsers(0, 0, 0, 0, &v65, &v58, &v64);
  if ( MyDeviceEnabled >= 0 )
  {
    v57 = 0;
    LODWORD(ppv) = 0;
    MyDeviceEnabled = MdmIsFindMyDeviceEnabled((int *)&ppv, &v57);
    if ( MyDeviceEnabled >= 0 )
    {
      if ( (_DWORD)ppv || (v5 = 1, !v57) )
        v5 = 0;
      ppv = 0;
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v10 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
      }
      MyDeviceEnabled = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
      if ( MyDeviceEnabled >= 0 )
      {
        v60 = pvarg;
        v61 = pvarg;
        v62 = pvarg;
        v63 = pvarg;
        MyDeviceEnabled = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)ppv + 80LL))(
                            ppv,
                            &v63,
                            &v62,
                            &v61,
                            &v60);
        if ( MyDeviceEnabled >= 0 )
        {
          v1 = ppv;
          ppv = 0;
          v56 = v1;
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v14,
            v13,
            MyDeviceEnabled,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
            56,
            (__int64)"CHR(pTaskService->Connect(vtEmpty, vtEmpty, vtEmpty, vtEmpty))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          v11,
          MyDeviceEnabled,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
          55,
          (__int64)"CHR(CoCreateInstance(CLSID_TaskScheduler, 0, CLSCTX_INPROC_SERVER, IID_ITaskService, (PVOID*)&pTaskService))");
      }
      VariantClear(&pvarg);
      v16 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
      }
      if ( MyDeviceEnabled >= 0 )
      {
        MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                            (DdcTaskSchedulerWrapper *)&v56,
                            v15,
                            L"RegisterDevicePeriodic1",
                            0);
        if ( MyDeviceEnabled >= 0 )
        {
          MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                              (DdcTaskSchedulerWrapper *)&v56,
                              v17,
                              L"RegisterDevicePeriodic6",
                              0);
          if ( MyDeviceEnabled >= 0 )
          {
            MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                (DdcTaskSchedulerWrapper *)&v56,
                                v19,
                                L"RegisterDeviceConnectedToNetwork",
                                0);
            if ( MyDeviceEnabled >= 0 )
            {
              MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                  (DdcTaskSchedulerWrapper *)&v56,
                                  v21,
                                  L"RegisterDeviceScreenOnOff",
                                  0);
              if ( MyDeviceEnabled >= 0 )
              {
                if ( v5 )
                {
                  MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                      (DdcTaskSchedulerWrapper *)&v56,
                                      v23,
                                      L"IntegrityCheck",
                                      0);
                  if ( MyDeviceEnabled >= 0 )
                  {
                    MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                        (DdcTaskSchedulerWrapper *)&v56,
                                        v25,
                                        L"RegisterDevicePeriodic24",
                                        0);
                    if ( MyDeviceEnabled >= 0 )
                    {
                      MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                          (DdcTaskSchedulerWrapper *)&v56,
                                          v27,
                                          L"RegisterDeviceLocationRightsChange",
                                          0);
                      if ( MyDeviceEnabled >= 0 )
                      {
                        MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                            (DdcTaskSchedulerWrapper *)&v56,
                                            v29,
                                            L"RegisterDeviceAccountChange",
                                            0);
                        if ( MyDeviceEnabled >= 0 )
                        {
                          MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                              (DdcTaskSchedulerWrapper *)&v56,
                                              v31,
                                              L"RegisterUserDevice",
                                              0);
                          if ( MyDeviceEnabled < 0
                            && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                          {
                            McTemplateU0dsqs_EventWriteTransfer(
                              v34,
                              v33,
                              MyDeviceEnabled,
                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementat"
                                            "ionsdesktop\\ddctaskstatehandlerdesktop.cpp",
                              185,
                              (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_S"
                                       "CHEDULER_REGISTER_USER_DEVICE_TASK, 0))");
                          }
                        }
                        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                        {
                          McTemplateU0dsqs_EventWriteTransfer(
                            v32,
                            (_DWORD)v31,
                            MyDeviceEnabled,
                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementatio"
                                          "nsdesktop\\ddctaskstatehandlerdesktop.cpp",
                            184,
                            (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCH"
                                     "EDULER_ACCOUNT_CHANGE_TASK, 0))");
                        }
                      }
                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                      {
                        McTemplateU0dsqs_EventWriteTransfer(
                          v30,
                          (_DWORD)v29,
                          MyDeviceEnabled,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementations"
                                        "desktop\\ddctaskstatehandlerdesktop.cpp",
                          183,
                          (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHED"
                                   "ULER_LOCATION_RIGHTS_CHANGE, 0))");
                      }
                    }
                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    {
                      McTemplateU0dsqs_EventWriteTransfer(
                        v28,
                        (_DWORD)v27,
                        MyDeviceEnabled,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsde"
                                      "sktop\\ddctaskstatehandlerdesktop.cpp",
                        182,
                        (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDUL"
                                 "ER_PERIODIC_24_TASK, 0))");
                    }
                  }
                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  {
                    McTemplateU0dsqs_EventWriteTransfer(
                      v26,
                      (_DWORD)v25,
                      MyDeviceEnabled,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesk"
                                    "top\\ddctaskstatehandlerdesktop.cpp",
                      181,
                      (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER"
                               "_INTEGRITY_CHECK_TASK, 0))");
                  }
                }
                else if ( v65 || v58 || v64 )
                {
                  MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                      (DdcTaskSchedulerWrapper *)&v56,
                                      v23,
                                      L"RegisterDevicePeriodic24",
                                      1);
                  if ( MyDeviceEnabled >= 0 )
                  {
                    MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                        (DdcTaskSchedulerWrapper *)&v56,
                                        v45,
                                        L"RegisterDeviceLocationRightsChange",
                                        1);
                    if ( MyDeviceEnabled >= 0 )
                    {
                      MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                          (DdcTaskSchedulerWrapper *)&v56,
                                          v47,
                                          L"RegisterDeviceAccountChange",
                                          1);
                      if ( MyDeviceEnabled >= 0 )
                      {
                        MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                            (DdcTaskSchedulerWrapper *)&v56,
                                            v49,
                                            L"RegisterUserDevice",
                                            1);
                        if ( MyDeviceEnabled >= 0 )
                        {
                          MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                              (DdcTaskSchedulerWrapper *)&v56,
                                              v51,
                                              L"IntegrityCheck",
                                              0);
                          if ( MyDeviceEnabled < 0
                            && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                          {
                            McTemplateU0dsqs_EventWriteTransfer(
                              v54,
                              v53,
                              MyDeviceEnabled,
                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementat"
                                            "ionsdesktop\\ddctaskstatehandlerdesktop.cpp",
                              207,
                              (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_S"
                                       "CHEDULER_INTEGRITY_CHECK_TASK, 0))");
                          }
                        }
                        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                        {
                          McTemplateU0dsqs_EventWriteTransfer(
                            v52,
                            (_DWORD)v51,
                            MyDeviceEnabled,
                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementatio"
                                          "nsdesktop\\ddctaskstatehandlerdesktop.cpp",
                            205,
                            (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCH"
                                     "EDULER_REGISTER_USER_DEVICE_TASK, 1))");
                        }
                      }
                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                      {
                        McTemplateU0dsqs_EventWriteTransfer(
                          v50,
                          (_DWORD)v49,
                          MyDeviceEnabled,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementations"
                                        "desktop\\ddctaskstatehandlerdesktop.cpp",
                          204,
                          (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHED"
                                   "ULER_ACCOUNT_CHANGE_TASK, 1))");
                      }
                    }
                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    {
                      McTemplateU0dsqs_EventWriteTransfer(
                        v48,
                        (_DWORD)v47,
                        MyDeviceEnabled,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsde"
                                      "sktop\\ddctaskstatehandlerdesktop.cpp",
                        203,
                        (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDUL"
                                 "ER_LOCATION_RIGHTS_CHANGE, 1))");
                    }
                  }
                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  {
                    McTemplateU0dsqs_EventWriteTransfer(
                      v46,
                      (_DWORD)v45,
                      MyDeviceEnabled,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesk"
                                    "top\\ddctaskstatehandlerdesktop.cpp",
                      202,
                      (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER"
                               "_PERIODIC_24_TASK, 1))");
                  }
                }
                else
                {
                  MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                      (DdcTaskSchedulerWrapper *)&v56,
                                      v23,
                                      L"IntegrityCheck",
                                      1);
                  if ( MyDeviceEnabled >= 0 )
                  {
                    MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                        (DdcTaskSchedulerWrapper *)&v56,
                                        v35,
                                        L"RegisterDeviceAccountChange",
                                        1);
                    if ( MyDeviceEnabled >= 0 )
                    {
                      MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                          (DdcTaskSchedulerWrapper *)&v56,
                                          v37,
                                          L"RegisterUserDevice",
                                          1);
                      if ( MyDeviceEnabled >= 0 )
                      {
                        MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                            (DdcTaskSchedulerWrapper *)&v56,
                                            v39,
                                            L"RegisterDevicePeriodic24",
                                            0);
                        if ( MyDeviceEnabled >= 0 )
                        {
                          MyDeviceEnabled = DdcTaskSchedulerWrapper::EnableTaskIfExists(
                                              (DdcTaskSchedulerWrapper *)&v56,
                                              v41,
                                              L"RegisterDeviceLocationRightsChange",
                                              0);
                          if ( MyDeviceEnabled < 0
                            && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                          {
                            McTemplateU0dsqs_EventWriteTransfer(
                              v44,
                              v43,
                              MyDeviceEnabled,
                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementat"
                                            "ionsdesktop\\ddctaskstatehandlerdesktop.cpp",
                              196,
                              (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_S"
                                       "CHEDULER_LOCATION_RIGHTS_CHANGE, 0))");
                          }
                        }
                        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                        {
                          McTemplateU0dsqs_EventWriteTransfer(
                            v42,
                            (_DWORD)v41,
                            MyDeviceEnabled,
                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementatio"
                                          "nsdesktop\\ddctaskstatehandlerdesktop.cpp",
                            195,
                            (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCH"
                                     "EDULER_PERIODIC_24_TASK, 0))");
                        }
                      }
                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                      {
                        McTemplateU0dsqs_EventWriteTransfer(
                          v40,
                          (_DWORD)v39,
                          MyDeviceEnabled,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementations"
                                        "desktop\\ddctaskstatehandlerdesktop.cpp",
                          193,
                          (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHED"
                                   "ULER_REGISTER_USER_DEVICE_TASK, 1))");
                      }
                    }
                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    {
                      McTemplateU0dsqs_EventWriteTransfer(
                        v38,
                        (_DWORD)v37,
                        MyDeviceEnabled,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsde"
                                      "sktop\\ddctaskstatehandlerdesktop.cpp",
                        192,
                        (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDUL"
                                 "ER_ACCOUNT_CHANGE_TASK, 1))");
                    }
                  }
                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  {
                    McTemplateU0dsqs_EventWriteTransfer(
                      v36,
                      (_DWORD)v35,
                      MyDeviceEnabled,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesk"
                                    "top\\ddctaskstatehandlerdesktop.cpp",
                      191,
                      (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER"
                               "_INTEGRITY_CHECK_TASK, 1))");
                  }
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  v24,
                  (_DWORD)v23,
                  MyDeviceEnabled,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\"
                                "ddctaskstatehandlerdesktop.cpp",
                  175,
                  (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_SCR"
                           "EEN_ON_OFF_TASK, 0))");
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v22,
                (_DWORD)v21,
                MyDeviceEnabled,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\d"
                              "dctaskstatehandlerdesktop.cpp",
                174,
                (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_CONNE"
                         "CTED_TO_NETWORK_TASK, 0))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v20,
              (_DWORD)v19,
              MyDeviceEnabled,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddc"
                            "taskstatehandlerdesktop.cpp",
              173,
              (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_PERIODIC_6_TASK, 0))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v18,
            (_DWORD)v17,
            MyDeviceEnabled,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddcta"
                          "skstatehandlerdesktop.cpp",
            172,
            (__int64)"CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_PERIODIC_1_TASK, 0))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)v16,
          (_DWORD)v15,
          MyDeviceEnabled,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddctask"
                        "statehandlerdesktop.cpp",
          137,
          (__int64)"CHR(taskSchedulerWrapper.Initialize())");
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          MyDeviceEnabled,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          129,
          (__int64)"CHR(hr)");
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v9,
            v8,
            MyDeviceEnabled,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddcta"
                          "skstatehandlerdesktop.cpp",
            135,
            (__int64)"CHR(DdcDeviceInfoHelper::FmdDisabledByPolicy(&fFmdDisabledByPolicy))");
      }
      v5 = 0;
    }
  }
  else
  {
    v5 = 0;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v3,
        v2,
        MyDeviceEnabled,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddctaskst"
                      "atehandlerdesktop.cpp",
        134,
        (__int64)"CHR(DdcAccountHelper::EnumerateUsers(0, nullptr, nullptr, nullptr, &cAdmins, &cDeviceOwners, &cStandardUsers))");
  }
  DdcTraceHelper::TraceIntegrityCheckResult(v65, v64, v5, MyDeviceEnabled);
  if ( v1 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v1 + 16LL))(v1);
  return (unsigned int)MyDeviceEnabled;
}

```

## disassembly

```asm
0x180003680  mov     r11, rsp
0x180003683  push    rbx
0x180003684  push    rsi
0x180003685  push    rdi
0x180003686  push    r14
0x180003688  push    r15
0x18000368a  sub     rsp, 0F0h
0x180003691  xor     r15d, r15d
0x180003694  mov     ebx, r15d
0x180003697  mov     [rsp+118h+var_D8], rbx
0x18000369c  mov     [r11+18h], r15d
0x1800036a0  mov     [rsp+118h+var_CC], r15d
0x1800036a5  mov     [r11+10h], r15d
0x1800036a9  lea     rax, [r11+10h]
0x1800036ad  mov     [rsp+118h+var_E8], rax; unsigned int *
0x1800036b2  lea     rax, [rsp+118h+var_CC]
0x1800036b7  mov     [rsp+118h+var_F0], rax; unsigned int *
0x1800036bc  lea     rax, [r11+18h]
0x1800036c0  mov     [rsp+118h+ppv], rax; unsigned int *
0x1800036c5  xor     r9d, r9d; struct Windows::Data::Json::IJsonValue **
0x1800036c8  xor     r8d, r8d; struct Windows::Data::Json::IJsonValue **
0x1800036cb  xor     edx, edx; struct Windows::Data::Json::IJsonValue **
0x1800036cd  xor     ecx, ecx; int
0x1800036cf  call    ?EnumerateUsers@DdcAccountHelper@@SAJHPEAPEAUIJsonValue@Json@Data@Windows@@00PEAK11@Z; DdcAccountHelper::EnumerateUsers(int,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,ulong *,ulong *,ulong *)
0x1800036d4  mov     edi, eax
0x1800036d6  test    eax, eax
0x1800036d8  jns     short loc_180003707
0x1800036da  mov     esi, r15d
0x1800036dd  lea     r14d, [r15+1]
0x1800036e1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x1800036e8  jz      loc_180003E5E
0x1800036ee  lea     rax, aChrDdcaccounth; "CHR(DdcAccountHelper::EnumerateUsers(0,"...
0x1800036f5  mov     [rsp+118h+var_F0], rax
0x1800036fa  mov     dword ptr [rsp+118h+ppv], 86h
0x180003702  jmp     loc_180003E4F
0x180003707  mov     [rsp+118h+var_D0], r15d
0x18000370c  mov     dword ptr [rsp+118h+arg_18], r15d
0x180003714  lea     rdx, [rsp+118h+var_D0]
0x180003719  lea     rcx, [rsp+118h+arg_18]
0x180003721  call    cs:__imp_?MdmIsFindMyDeviceEnabled@@YAJPEAH0@Z; MdmIsFindMyDeviceEnabled(int *,int *)
0x180003727  mov     edi, eax
0x180003729  mov     r14d, 1
0x18000372f  test    eax, eax
0x180003731  jns     short loc_180003797
0x180003733  mov     eax, cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
0x180003739  test    r14b, al
0x18000373c  jz      short loc_18000378F
0x18000373e  lea     rax, aChrHr; "CHR(hr)"
0x180003745  mov     [rsp+118h+var_F0], rax
0x18000374a  mov     dword ptr [rsp+118h+ppv], 381h
0x180003752  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180003759  mov     r8d, edi
0x18000375c  call    McTemplateU0dsqs_EventWriteTransfer
0x180003761  mov     eax, cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
0x180003767  test    r14b, al
0x18000376a  jz      short loc_18000378F
0x18000376c  lea     rax, aChrDdcdevicein; "CHR(DdcDeviceInfoHelper::FmdDisabledByP"...
0x180003773  mov     [rsp+118h+var_F0], rax
0x180003778  mov     dword ptr [rsp+118h+ppv], 87h
0x180003780  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180003787  mov     r8d, edi
0x18000378a  call    McTemplateU0dsqs_EventWriteTransfer
0x18000378f  mov     esi, r15d
0x180003792  jmp     loc_180003E5E
0x180003797  cmp     dword ptr [rsp+118h+arg_18], r15d
0x18000379f  jnz     short loc_1800037AB
0x1800037a1  cmp     [rsp+118h+var_D0], r15d
0x1800037a6  mov     esi, r14d
0x1800037a9  jnz     short loc_1800037AE
0x1800037ab  mov     esi, r15d
0x1800037ae  mov     [rsp+118h+arg_18], r15
0x1800037b6  xorps   xmm0, xmm0
0x1800037b9  xor     eax, eax
0x1800037bb  movups  xmmword ptr [rsp+118h+pvarg], xmm0
0x1800037c0  mov     qword ptr [rsp+118h+pvarg+10h], rax
0x1800037c5  lea     rcx, [rsp+118h+pvarg]; pvarg
0x1800037ca  call    cs:__imp_VariantInit
0x1800037d0  nop
0x1800037d1  mov     rcx, [rsp+118h+arg_18]
0x1800037d9  test    rcx, rcx
0x1800037dc  jz      short loc_1800037F3
0x1800037de  mov     [rsp+118h+arg_18], r15
0x1800037e6  mov     rax, [rcx]
0x1800037e9  mov     rax, [rax+10h]
0x1800037ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f2  nop
0x1800037f3  lea     rax, [rsp+118h+arg_18]
0x1800037fb  mov     [rsp+118h+ppv], rax; ppv
0x180003800  lea     r9, IID_ITaskService; riid
0x180003807  mov     r8d, r14d; dwClsContext
0x18000380a  xor     edx, edx; pUnkOuter
0x18000380c  lea     rcx, CLSID_TaskScheduler; rclsid
0x180003813  call    cs:__imp_CoCreateInstance
0x180003819  mov     edi, eax
0x18000381b  test    eax, eax
0x18000381d  jns     short loc_180003854
0x18000381f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x180003826  jz      loc_180003913
0x18000382c  lea     rax, aChrCocreateins; "CHR(CoCreateInstance(CLSID_TaskSchedule"...
0x180003833  mov     [rsp+118h+var_F0], rax
0x180003838  mov     dword ptr [rsp+118h+ppv], 137h
0x180003840  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180003847  mov     r8d, edi
0x18000384a  call    McTemplateU0dsqs_EventWriteTransfer
0x18000384f  jmp     loc_180003913
0x180003854  mov     rcx, [rsp+118h+arg_18]
0x18000385c  movups  xmm1, xmmword ptr [rsp+118h+pvarg]
0x180003861  movsd   xmm0, qword ptr [rsp+118h+pvarg+10h]
0x180003867  movaps  [rsp+118h+var_A8], xmm1
0x18000386c  movsd   [rsp+118h+var_98], xmm0
0x180003875  movaps  [rsp+118h+var_88], xmm1
0x18000387d  movsd   [rsp+118h+var_78], xmm0
0x180003886  movaps  [rsp+118h+var_68], xmm1
0x18000388e  movsd   [rsp+118h+var_58], xmm0
0x180003897  movaps  [rsp+118h+var_48], xmm1
0x18000389f  movsd   [rsp+118h+var_38], xmm0
0x1800038a8  mov     rax, [rcx]
0x1800038ab  lea     rdx, [rsp+118h+var_A8]
0x1800038b0  mov     [rsp+118h+ppv], rdx
0x1800038b5  lea     r9, [rsp+118h+var_88]
0x1800038bd  lea     r8, [rsp+118h+var_68]
0x1800038c5  lea     rdx, [rsp+118h+var_48]
0x1800038cd  mov     rax, [rax+50h]
0x1800038d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d6  mov     edi, eax
0x1800038d8  test    eax, eax
0x1800038da  jns     short loc_1800038FE
0x1800038dc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x1800038e3  jz      short loc_180003913
0x1800038e5  lea     rax, aChrPtaskservic; "CHR(pTaskService->Connect(vtEmpty, vtEm"...
0x1800038ec  mov     [rsp+118h+var_F0], rax
0x1800038f1  mov     dword ptr [rsp+118h+ppv], 138h
0x1800038f9  jmp     loc_180003840
0x1800038fe  mov     rbx, [rsp+118h+arg_18]
0x180003906  mov     [rsp+118h+arg_18], r15
0x18000390e  mov     [rsp+118h+var_D8], rbx
0x180003913  lea     rcx, [rsp+118h+pvarg]; pvarg
0x180003918  call    cs:__imp_VariantClear
0x18000391e  nop
0x18000391f  mov     rcx, [rsp+118h+arg_18]
0x180003927  test    rcx, rcx
0x18000392a  jz      short loc_180003941
0x18000392c  mov     [rsp+118h+arg_18], r15
0x180003934  mov     rax, [rcx]
0x180003937  mov     rax, [rax+10h]
0x18000393b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003940  nop
0x180003941  test    edi, edi
0x180003943  jns     short loc_18000396B
0x180003945  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x18000394c  jz      loc_180003E5E
0x180003952  lea     rax, aChrTaskschedul_3; "CHR(taskSchedulerWrapper.Initialize())"
0x180003959  mov     [rsp+118h+var_F0], rax
0x18000395e  mov     dword ptr [rsp+118h+ppv], 89h
0x180003966  jmp     loc_180003E4F
0x18000396b  xor     r9d, r9d; int
0x18000396e  lea     r8, aRegisterdevice_2; "RegisterDevicePeriodic1"
0x180003975  lea     rcx, [rsp+118h+var_D8]; this
0x18000397a  call    ?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z; DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)
0x18000397f  mov     edi, eax
0x180003981  test    eax, eax
0x180003983  jns     short loc_1800039AB
0x180003985  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x18000398c  jz      loc_180003E5E
0x180003992  lea     rax, aChrTaskschedul_13; "CHR(taskSchedulerWrapper.EnableTaskIfEx"...
0x180003999  mov     [rsp+118h+var_F0], rax
0x18000399e  mov     dword ptr [rsp+118h+ppv], 0ACh
0x1800039a6  jmp     loc_180003E4F
0x1800039ab  xor     r9d, r9d; int
0x1800039ae  lea     r8, aRegisterdevice_3; "RegisterDevicePeriodic6"
0x1800039b5  lea     rcx, [rsp+118h+var_D8]; this
0x1800039ba  call    ?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z; DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)
0x1800039bf  mov     edi, eax
0x1800039c1  test    eax, eax
0x1800039c3  jns     short loc_1800039EB
0x1800039c5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x1800039cc  jz      loc_180003E5E
0x1800039d2  lea     rax, aChrTaskschedul_11; "CHR(taskSchedulerWrapper.EnableTaskIfEx"...
0x1800039d9  mov     [rsp+118h+var_F0], rax
0x1800039de  mov     dword ptr [rsp+118h+ppv], 0ADh
0x1800039e6  jmp     loc_180003E4F
0x1800039eb  xor     r9d, r9d; int
0x1800039ee  lea     r8, aRegisterdevice_0; "RegisterDeviceConnectedToNetwork"
0x1800039f5  lea     rcx, [rsp+118h+var_D8]; this
0x1800039fa  call    ?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z; DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)
0x1800039ff  mov     edi, eax
0x180003a01  test    eax, eax
0x180003a03  jns     short loc_180003A2B
0x180003a05  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x180003a0c  jz      loc_180003E5E
0x180003a12  lea     rax, aChrTaskschedul_12; "CHR(taskSchedulerWrapper.EnableTaskIfEx"...
0x180003a19  mov     [rsp+118h+var_F0], rax
0x180003a1e  mov     dword ptr [rsp+118h+ppv], 0AEh
0x180003a26  jmp     loc_180003E4F
0x180003a2b  xor     r9d, r9d; int
0x180003a2e  lea     r8, aRegisterdevice_4; "RegisterDeviceScreenOnOff"
0x180003a35  lea     rcx, [rsp+118h+var_D8]; this
0x180003a3a  call    ?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z; DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)
0x180003a3f  mov     edi, eax
0x180003a41  test    eax, eax
0x180003a43  jns     short loc_180003A6B
0x180003a45  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x180003a4c  jz      loc_180003E5E
0x180003a52  lea     rax, aChrTaskschedul_7; "CHR(taskSchedulerWrapper.EnableTaskIfEx"...
0x180003a59  mov     [rsp+118h+var_F0], rax
0x180003a5e  mov     dword ptr [rsp+118h+ppv], 0AFh
0x180003a66  jmp     loc_180003E4F
0x180003a6b  test    esi, esi
0x180003a6d  jz      loc_180003BB7
0x180003a73  xor     r9d, r9d; int
0x180003a76  lea     r8, aIntegritycheck; "IntegrityCheck"
0x180003a7d  lea     rcx, [rsp+118h+var_D8]; this
0x180003a82  call    ?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z; DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)
0x180003a87  mov     edi, eax
0x180003a89  test    eax, eax
0x180003a8b  jns     short loc_180003AB3
0x180003a8d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x180003a94  jz      loc_180003E5E
0x180003a9a  lea     rax, aChrTaskschedul_5; "CHR(taskSchedulerWrapper.EnableTaskIfEx"...
0x180003aa1  mov     [rsp+118h+var_F0], rax
0x180003aa6  mov     dword ptr [rsp+118h+ppv], 0B5h
0x180003aae  jmp     loc_180003E4F
0x180003ab3  xor     r9d, r9d; int
0x180003ab6  lea     r8, aRegisterdevice; "RegisterDevicePeriodic24"
0x180003abd  lea     rcx, [rsp+118h+var_D8]; this
0x180003ac2  call    ?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z; DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)
0x180003ac7  mov     edi, eax
0x180003ac9  test    eax, eax
0x180003acb  jns     short loc_180003AF3
0x180003acd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x180003ad4  jz      loc_180003E5E
0x180003ada  lea     rax, aChrTaskschedul_2; "CHR(taskSchedulerWrapper.EnableTaskIfEx"...
0x180003ae1  mov     [rsp+118h+var_F0], rax
0x180003ae6  mov     dword ptr [rsp+118h+ppv], 0B6h
0x180003aee  jmp     loc_180003E4F
0x180003af3  xor     r9d, r9d; int
0x180003af6  lea     r8, aRegisterdevice_5; "RegisterDeviceLocationRightsChange"
0x180003afd  lea     rcx, [rsp+118h+var_D8]; this
0x180003b02  call    ?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z; DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)
0x180003b07  mov     edi, eax
0x180003b09  test    eax, eax
0x180003b0b  jns     short loc_180003B33
0x180003b0d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x180003b14  jz      loc_180003E5E
0x180003b1a  lea     rax, aChrTaskschedul_8; "CHR(taskSchedulerWrapper.EnableTaskIfEx"...
0x180003b21  mov     [rsp+118h+var_F0], rax
0x180003b26  mov     dword ptr [rsp+118h+ppv], 0B7h
0x180003b2e  jmp     loc_180003E4F
0x180003b33  xor     r9d, r9d; int
0x180003b36  lea     r8, aRegisterdevice_1; "RegisterDeviceAccountChange"
0x180003b3d  lea     rcx, [rsp+118h+var_D8]; this
0x180003b42  call    ?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z; DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)
0x180003b47  mov     edi, eax
0x180003b49  test    eax, eax
0x180003b4b  jns     short loc_180003B73
0x180003b4d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x180003b54  jz      loc_180003E5E
0x180003b5a  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.EnableTaskIfEx"...
0x180003b61  mov     [rsp+118h+var_F0], rax
0x180003b66  mov     dword ptr [rsp+118h+ppv], 0B8h
0x180003b6e  jmp     loc_180003E4F
0x180003b73  xor     r9d, r9d; int
0x180003b76  lea     r8, aRegisteruserde; "RegisterUserDevice"
0x180003b7d  lea     rcx, [rsp+118h+var_D8]; this
0x180003b82  call    ?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z; DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)
0x180003b87  mov     edi, eax
0x180003b89  test    eax, eax
0x180003b8b  jns     loc_180003E5E
0x180003b91  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x180003b98  jz      loc_180003E5E
0x180003b9e  lea     rax, aChrTaskschedul_4; "CHR(taskSchedulerWrapper.EnableTaskIfEx"...
0x180003ba5  mov     [rsp+118h+var_F0], rax
0x180003baa  mov     dword ptr [rsp+118h+ppv], 0B9h
0x180003bb2  jmp     loc_180003E4F
0x180003bb7  cmp     [rsp+118h+arg_10], r15d
0x180003bbf  jnz     loc_180003D22
0x180003bc5  cmp     [rsp+118h+var_CC], r15d
0x180003bca  jnz     loc_180003D22
0x180003bd0  cmp     [rsp+118h+arg_8], r15d
0x180003bd8  jnz     loc_180003D22
0x180003bde  mov     r9d, r14d; int
0x180003be1  lea     r8, aIntegritycheck; "IntegrityCheck"
0x180003be8  lea     rcx, [rsp+118h+var_D8]; this
0x180003bed  call    ?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z; DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)
0x180003bf2  mov     edi, eax
0x180003bf4  test    eax, eax
0x180003bf6  jns     short loc_180003C1E
0x180003bf8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x180003bff  jz      loc_180003E5E
0x180003c05  lea     rax, aChrTaskschedul_6; "CHR(taskSchedulerWrapper.EnableTaskIfEx"...
0x180003c0c  mov     [rsp+118h+var_F0], rax
0x180003c11  mov     dword ptr [rsp+118h+ppv], 0BFh
0x180003c19  jmp     loc_180003E4F
0x180003c1e  mov     r9d, r14d; int
0x180003c21  lea     r8, aRegisterdevice_1; "RegisterDeviceAccountChange"
0x180003c28  lea     rcx, [rsp+118h+var_D8]; this
0x180003c2d  call    ?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z; DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)
0x180003c32  mov     edi, eax
0x180003c34  test    eax, eax
0x180003c36  jns     short loc_180003C5E
  ... truncated ...
```
