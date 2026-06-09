# DdcTaskSchedulerWrapper::ScheduleWnsChannelRegistrationFallbackSchedule(FILETIMEEX)

- ea: `0x18001364c`
- end: `0x180013866`
- name: `?ScheduleWnsChannelRegistrationFallbackSchedule@DdcTaskSchedulerWrapper@@QEAAJTFILETIMEEX@@@Z`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180024d9c`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800050b8`
- `0x18000d79c`
- `0x180011e98`
- `0x180012380`
- `0x18001364c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013715`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800136bc`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800136bc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001370b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001370b`

## string_xrefs

- `0x18001378c`: `<Task version="1.4" xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task"><RegistrationInfo><SecurityDescriptor>D:P(A;;FA;;;SY)(A;;FRFX;;;BA)</SecurityDescriptor></RegistrationInfo><Principals><Principal id="System"><UserId>S-1-5-18</UserId><RunLevel>LeastPrivilege</RunLevel></Principal></Principals><Triggers><TimeTrigger><StartBoundary>%.4u-%.2u-%.2uT%.2u:%.2u:%.2u</StartBoundary></TimeTrigger></Triggers><Settings><MultipleInstancesPolicy>Parallel</MultipleInstancesPolicy><DisallowStart`
- `0x180013831`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x1800137b0`: `CHR(StringCchPrintfW( pwszTaskXml, 1800, pwszWnsChannelRegistrationFallbackFormat, stStartTime.wYear, stStartTime.wMonth, stStartTime.wDay, stStartTime.wHour, stStartTime.wMinute, stStartTime.wSecond))`
- `0x1800137e4`: `CHR(DeleteTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_WNS_CHANNEL_REGISTRATION))`
- `0x18001381d`: `CHR(CreateTask(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_WNS_CHANNEL_REGISTRATION, pwszTaskXml))`

## pseudocode

```c
__int64 __fastcall DdcTaskSchedulerWrapper::ScheduleWnsChannelRegistrationFallbackSchedule(
        DdcTaskSchedulerWrapper *a1,
        __int64 a2)
{
  signed int v4; // eax
  int v5; // edx
  int v6; // ecx
  int Task; // ebx
  signed int LastError; // eax
  int v9; // edx
  int v10; // ecx
  const unsigned __int16 *v11; // rdx
  int v12; // ecx
  const unsigned __int16 *v13; // rdx
  int v14; // ecx
  int v15; // edx
  int v16; // ecx
  int wMonth; // [rsp+20h] [rbp-E0h]
  int wDay; // [rsp+28h] [rbp-D8h]
  int wHour; // [rsp+30h] [rbp-D0h]
  int wMinute; // [rsp+38h] [rbp-C8h]
  int wSecond; // [rsp+40h] [rbp-C0h]
  struct _FILETIME LocalFileTime; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME FileTime; // [rsp+58h] [rbp-A8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v26[1800]; // [rsp+70h] [rbp-90h] BYREF

  LocalFileTime = 0;
  SystemTime = 0;
  memset_0(v26, 0, sizeof(v26));
  FileTime = (FILETIME)(a2 - 864000000000LL);
  if ( FileTimeToLocalFileTime(&FileTime, &LocalFileTime) )
  {
    if ( FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
    {
      wSecond = SystemTime.wSecond;
      wMinute = SystemTime.wMinute;
      wHour = SystemTime.wHour;
      wDay = SystemTime.wDay;
      wMonth = SystemTime.wMonth;
      Task = StringCchPrintfW(
               v26,
               0x708u,
               L"<Task version=\"1.4\" xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\"><RegistrationInfo><"
                "SecurityDescriptor>D:P(A;;FA;;;SY)(A;;FRFX;;;BA)</SecurityDescriptor></RegistrationInfo><Principals><Pri"
                "ncipal id=\"System\"><UserId>S-1-5-18</UserId><RunLevel>LeastPrivilege</RunLevel></Principal></Principal"
                "s><Triggers><TimeTrigger><StartBoundary>%.4u-%.2u-%.2uT%.2u:%.2u:%.2u</StartBoundary></TimeTrigger></Tri"
                "ggers><Settings><MultipleInstancesPolicy>Parallel</MultipleInstancesPolicy><DisallowStartIfOnBatteries>f"
                "alse</DisallowStartIfOnBatteries><StopIfGoingOnBatteries>false</StopIfGoingOnBatteries><AllowHardTermina"
                "te>false</AllowHardTerminate><StartWhenAvailable>true</StartWhenAvailable><RunOnlyIfNetworkAvailable>tru"
                "e</RunOnlyIfNetworkAvailable><AllowStartOnDemand>true</AllowStartOnDemand><Enabled>true</Enabled><Hidden"
                ">true</Hidden><RunOnlyIfIdle>false</RunOnlyIfIdle><DisallowStartOnRemoteAppSession>false</DisallowStartO"
                "nRemoteAppSession><UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine><WakeToRun>false</WakeToR"
                "un><ExecutionTimeLimit>PT0S</ExecutionTimeLimit><Priority>10</Priority><RestartOnFailure><Interval>PT12H"
                "</Interval><Count>14</Count></RestartOnFailure></Settings><Actions Context=\"System\"><ComHandler><Class"
                "Id>{AE31B729-D5FD-401E-AF42-784074835AFE}</ClassId><Data>-RegisterDevice -Periodic</Data></ComHandler></Actions></Task>",
               SystemTime.wYear,
               wMonth,
               wDay,
               wHour,
               wMinute,
               wSecond);
      if ( Task >= 0 )
      {
        Task = DdcTaskSchedulerWrapper::DeleteTaskIfExists(a1, v11, L"RegisterDeviceWnsFallback");
        if ( Task >= 0 )
        {
          Task = DdcTaskSchedulerWrapper::CreateTask(a1, v13, L"RegisterDeviceWnsFallback", v26);
          if ( Task < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v16,
              v15,
              Task,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
              75,
              "CHR(CreateTask(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_WNS_CHANNEL_REGISTRATION, pwszTaskXml))");
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v14,
            (_DWORD)v13,
            Task,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
            72,
            "CHR(DeleteTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_WNS_CHANNEL_REGISTRATION))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          (_DWORD)v11,
          Task,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
          69,
          "CHR(StringCchPrintfW( pwszTaskXml, 1800, pwszWnsChannelRegistrationFallbackFormat, stStartTime.wYear, stStartT"
          "ime.wMonth, stStartTime.wDay, stStartTime.wHour, stStartTime.wMinute, stStartTime.wSecond))");
      }
    }
    else
    {
      LastError = GetLastError();
      Task = LastError;
      if ( LastError > 0 )
        Task = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v10,
          v9,
          Task,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
          57,
          "CBR(FileTimeToSystemTime(&ftLocalTime, &stStartTime))");
    }
  }
  else
  {
    v4 = GetLastError();
    Task = v4;
    if ( v4 > 0 )
      Task = (unsigned __int16)v4 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v6,
        v5,
        Task,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        56,
        "CBR(FileTimeToLocalFileTime(&ftExpiration.ftTime, &ftLocalTime))");
  }
  return (unsigned int)Task;
}

```

## disassembly

```asm
0x18001364c  mov     [rsp-8+arg_10], rbx
0x180013651  mov     [rsp-8+arg_18], rdi
0x180013656  push    rbp
0x180013657  lea     rbp, [rsp-0D90h]
0x18001365f  sub     rsp, 0E90h
0x180013666  mov     rax, cs:__security_cookie
0x18001366d  xor     rax, rsp
0x180013670  mov     [rbp+0D90h+var_10], rax
0x180013677  mov     rbx, rdx
0x18001367a  mov     qword ptr [rsp+0E90h+LocalFileTime.dwLowDateTime], 0
0x180013683  mov     rdi, rcx
0x180013686  xorps   xmm0, xmm0
0x180013689  xor     edx, edx; Val
0x18001368b  lea     rcx, [rsp+0E90h+var_E20]; void *
0x180013690  mov     r8d, 0E10h; Size
0x180013696  movups  xmmword ptr [rsp+0E90h+SystemTime.wYear], xmm0
0x18001369b  call    memset_0
0x1800136a0  mov     rax, 0FFFFFF36D5964000h
0x1800136aa  lea     rdx, [rsp+0E90h+LocalFileTime]; lpLocalFileTime
0x1800136af  add     rax, rbx
0x1800136b2  lea     rcx, [rsp+0E90h+FileTime]; lpFileTime
0x1800136b7  mov     qword ptr [rsp+0E90h+FileTime.dwLowDateTime], rax
0x1800136bc  call    cs:__imp_FileTimeToLocalFileTime
0x1800136c2  test    eax, eax
0x1800136c4  jnz     short loc_180013701
0x1800136c6  call    cs:__imp_GetLastError
0x1800136cc  mov     ebx, eax
0x1800136ce  test    eax, eax
0x1800136d0  jle     short loc_1800136DB
0x1800136d2  movzx   ebx, ax
0x1800136d5  or      ebx, 80070000h
0x1800136db  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800136e2  jz      loc_180013840
0x1800136e8  lea     rax, aCbrFiletimetol; "CBR(FileTimeToLocalFileTime(&ftExpirati"...
0x1800136ef  mov     [rsp+0E90h+var_E68], rax
0x1800136f4  mov     [rsp+0E90h+var_E70], 338h
0x1800136fc  jmp     loc_180013831
0x180013701  lea     rdx, [rsp+0E90h+SystemTime]; lpSystemTime
0x180013706  lea     rcx, [rsp+0E90h+LocalFileTime]; lpFileTime
0x18001370b  call    cs:__imp_FileTimeToSystemTime
0x180013711  test    eax, eax
0x180013713  jnz     short loc_180013750
0x180013715  call    cs:__imp_GetLastError
0x18001371b  mov     ebx, eax
0x18001371d  test    eax, eax
0x18001371f  jle     short loc_18001372A
0x180013721  movzx   ebx, ax
0x180013724  or      ebx, 80070000h
0x18001372a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180013731  jz      loc_180013840
0x180013737  lea     rax, aCbrFiletimetos; "CBR(FileTimeToSystemTime(&ftLocalTime, "...
0x18001373e  mov     [rsp+0E90h+var_E68], rax
0x180013743  mov     [rsp+0E90h+var_E70], 339h
0x18001374b  jmp     loc_180013831
0x180013750  movzx   ecx, [rsp+0E90h+SystemTime.wMinute]
0x180013755  movzx   edx, [rsp+0E90h+SystemTime.wHour]
0x18001375a  movzx   r8d, [rsp+0E90h+SystemTime.wDay]
0x180013760  movzx   eax, [rsp+0E90h+SystemTime.wSecond]
0x180013765  movzx   r10d, [rsp+0E90h+SystemTime.wMonth]
0x18001376b  movzx   r9d, [rsp+0E90h+SystemTime.wYear]
0x180013771  mov     [rsp+0E90h+var_E50], eax
0x180013775  mov     [rsp+0E90h+var_E58], ecx
0x180013779  lea     rcx, [rsp+0E90h+var_E20]; unsigned __int16 *
0x18001377e  mov     [rsp+0E90h+var_E60], edx
0x180013782  mov     edx, 708h; unsigned __int64
0x180013787  mov     dword ptr [rsp+0E90h+var_E68], r8d
0x18001378c  lea     r8, aTaskVersion14X_2; "<Task version=\"1.4\" xmlns=\"http://sc"...
0x180013793  mov     [rsp+0E90h+var_E70], r10d
0x180013798  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001379d  mov     ebx, eax
0x18001379f  test    eax, eax
0x1800137a1  jns     short loc_1800137C6
0x1800137a3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800137aa  jz      loc_180013840
0x1800137b0  lea     rax, aChrStringcchpr; "CHR(StringCchPrintfW( pwszTaskXml, 1800"...
0x1800137b7  mov     [rsp+0E90h+var_E68], rax
0x1800137bc  mov     [rsp+0E90h+var_E70], 345h
0x1800137c4  jmp     short loc_180013831
0x1800137c6  lea     r8, aRegisterdevice_0; "RegisterDeviceWnsFallback"
0x1800137cd  mov     rcx, rdi; this
0x1800137d0  call    ?DeleteTaskIfExists@DdcTaskSchedulerWrapper@@AEAAJPEBG0@Z; DdcTaskSchedulerWrapper::DeleteTaskIfExists(ushort const *,ushort const *)
0x1800137d5  mov     ebx, eax
0x1800137d7  test    eax, eax
0x1800137d9  jns     short loc_1800137FA
0x1800137db  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800137e2  jz      short loc_180013840
0x1800137e4  lea     rax, aChrDeletetaski; "CHR(DeleteTaskIfExists(TASK_SCHEDULER_D"...
0x1800137eb  mov     [rsp+0E90h+var_E68], rax
0x1800137f0  mov     [rsp+0E90h+var_E70], 348h
0x1800137f8  jmp     short loc_180013831
0x1800137fa  lea     r9, [rsp+0E90h+var_E20]; unsigned __int16 *
0x1800137ff  mov     rcx, rdi; this
0x180013802  lea     r8, aRegisterdevice_0; "RegisterDeviceWnsFallback"
0x180013809  call    ?CreateTask@DdcTaskSchedulerWrapper@@AEAAJPEBG00@Z; DdcTaskSchedulerWrapper::CreateTask(ushort const *,ushort const *,ushort const *)
0x18001380e  mov     ebx, eax
0x180013810  test    eax, eax
0x180013812  jns     short loc_180013840
0x180013814  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001381b  jz      short loc_180013840
0x18001381d  lea     rax, aChrCreatetaskT; "CHR(CreateTask(TASK_SCHEDULER_DIRECTORY"...
0x180013824  mov     [rsp+0E90h+var_E68], rax
0x180013829  mov     [rsp+0E90h+var_E70], 34Bh
0x180013831  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180013838  mov     r8d, ebx
0x18001383b  call    McTemplateU0dsqs_EventWriteTransfer
0x180013840  mov     eax, ebx
0x180013842  mov     rcx, [rbp+0D90h+var_10]
0x180013849  xor     rcx, rsp; StackCookie
0x18001384c  call    __security_check_cookie
0x180013851  lea     r11, [rsp+0E90h+var_s0]
0x180013859  mov     rbx, [r11+20h]
0x18001385d  mov     rdi, [r11+28h]
0x180013861  mov     rsp, r11
0x180013864  pop     rbp
0x180013865  retn
```
