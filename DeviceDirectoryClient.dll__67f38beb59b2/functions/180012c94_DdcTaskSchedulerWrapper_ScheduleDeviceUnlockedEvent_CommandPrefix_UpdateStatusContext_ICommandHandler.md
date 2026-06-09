# DdcTaskSchedulerWrapper::ScheduleDeviceUnlockedEvent(CommandPrefix *,UpdateStatusContext *,ICommandHandler *)

- ea: `0x180012c94`
- end: `0x180012ffb`
- name: `?ScheduleDeviceUnlockedEvent@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@PEAUICommandHandler@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(DdcTaskSchedulerWrapper *__hidden this, struct CommandPrefix *, struct UpdateStatusContext *, struct ICommandHandler *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800107e0`

## callees

- `0x1800024c0`
- `0x1800028d4`
- `0x180002fc0`
- `0x1800036e8`
- `0x180004d5c`
- `0x180004db8`
- `0x1800050b8`
- `0x18000d79c`
- `0x18000f7e4`
- `0x180011e98`
- `0x180012380`
- `0x180012c94`
- `0x180028ad0`
- `0x18002a010`

## string_xrefs

- `0x180012db5`: `CPR(pCommandHandler)`
- `0x180012ec1`: `<Task version="1.4" xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task"><RegistrationInfo><SecurityDescriptor>D:P(A;;FA;;;SY)(A;;FRFX;;;BA)</SecurityDescriptor></RegistrationInfo><Principals><Principal id="System"><UserId>S-1-5-18</UserId><RunLevel>LeastPrivilege</RunLevel></Principal></Principals><Triggers>%s</Triggers><Settings><MultipleInstancesPolicy>Parallel</MultipleInstancesPolicy><DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries><StopIfGoingOnBatteries>false</StopIf`
- `0x180012fb0`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x180012df4`: `CHR(b64coder.Encode((BYTE *)pPrefix, sizeof(CommandPrefix), wstrEncodedPrefix))`
- `0x180012f61`: `CHR(DeleteTaskIfExists( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName ))`
- `0x180012f99`: `CHR(CreateTask( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName, pwszTaskXml ))`
- `0x180012e33`: `CHR(b64coder.Encode((BYTE *)pContext, sizeof(UpdateStatusContext), wstrEncodedContext))`
- `0x180012e77`: `CHR(pCommandHandler->GetDeviceUnlockedTrigger(pwszTrigger, &cchTrigger))`
- `0x180012eec`: `CHR(StringCchPrintfW( pwszTaskXml, 1800, pwszDeviceUnlockedXmlFormat, pwszTrigger, DEVICE_DIRECTORY_CLIENT_DEVICE_UNLOCKED_SWITCH, wstrEncodedPrefix.c_str(), wstrEncodedContext.c_str()))`
- `0x180012f30`: `CHR(StringCchPrintfW( pwszTaskName, 32, TASK_SCHEDULER_DEVICE_UNLOCKED_FORMAT, pPrefix->dwRequestId))`

## pseudocode

```c
__int64 __fastcall DdcTaskSchedulerWrapper::ScheduleDeviceUnlockedEvent(
        DdcTaskSchedulerWrapper *this,
        struct CommandPrefix *a2,
        struct UpdateStatusContext *a3,
        struct ICommandHandler *a4)
{
  int v8; // edx
  __int64 v9; // rcx
  int Task; // ebx
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  char v16; // [rsp+20h] [rbp-E0h]
  const char *v17; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+50h] [rbp-B0h]
  _BYTE v21[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[40]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v23[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v24[512]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v25[1800]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v19 = 0;
  v20 = 0;
  std::wstring::wstring(v22);
  std::wstring::wstring(v21);
  memset_0(v25, 0, sizeof(v25));
  memset_0(v23, 0, sizeof(v23));
  memset_0(v24, 0, sizeof(v24));
  v18 = 256;
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        Task = DdcBase64Coder::Encode(v9, a2, 20, v22);
        if ( Task >= 0 )
        {
          Task = DdcBase64Coder::Encode(v12, a3, 28, v21);
          if ( Task >= 0 )
          {
            Task = (*(__int64 (__fastcall **)(struct ICommandHandler *, _BYTE *, int *))(*(_QWORD *)a4 + 72LL))(
                     a4,
                     v24,
                     &v18);
            if ( Task >= 0 )
            {
              std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
              v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
              Task = StringCchPrintfW(
                       v25,
                       0x708u,
                       L"<Task version=\"1.4\" xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\"><Registrati"
                        "onInfo><SecurityDescriptor>D:P(A;;FA;;;SY)(A;;FRFX;;;BA)</SecurityDescriptor></RegistrationInfo>"
                        "<Principals><Principal id=\"System\"><UserId>S-1-5-18</UserId><RunLevel>LeastPrivilege</RunLevel"
                        "></Principal></Principals><Triggers>%s</Triggers><Settings><MultipleInstancesPolicy>Parallel</Mu"
                        "ltipleInstancesPolicy><DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries><StopIfGoing"
                        "OnBatteries>false</StopIfGoingOnBatteries><AllowHardTerminate>false</AllowHardTerminate><StartWh"
                        "enAvailable>true</StartWhenAvailable><RunOnlyIfNetworkAvailable>true</RunOnlyIfNetworkAvailable>"
                        "<AllowStartOnDemand>true</AllowStartOnDemand><Enabled>true</Enabled><Hidden>true</Hidden><RunOnl"
                        "yIfIdle>false</RunOnlyIfIdle><DisallowStartOnRemoteAppSession>false</DisallowStartOnRemoteAppSes"
                        "sion><UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine><WakeToRun>false</WakeToRun><E"
                        "xecutionTimeLimit>PT0S</ExecutionTimeLimit><Priority>10</Priority></Settings><Actions Context=\""
                        "System\"><ComHandler><ClassId>{AE31B729-D5FD-401E-AF42-784074835AFE}</ClassId><Data>%s %s %s</Da"
                        "ta></ComHandler></Actions></Task>",
                       v24,
                       L"-DeviceUnlocked",
                       v13,
                       v14);
              if ( Task >= 0 )
              {
                Task = StringCchPrintfW(v23, 0x20u, L"DeviceUnlocked%lu", *(unsigned int *)a2);
                if ( Task >= 0 )
                {
                  Task = DdcTaskSchedulerWrapper::DeleteTaskIfExists(this, v11, v23);
                  if ( Task >= 0 )
                  {
                    Task = DdcTaskSchedulerWrapper::CreateTask(this, v11, v23, v25);
                    if ( Task >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                      goto LABEL_32;
                    v17 = "CHR(CreateTask( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName, pwszTaskXml ))";
                    v16 = 14;
                  }
                  else
                  {
                    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                      goto LABEL_32;
                    v17 = "CHR(DeleteTaskIfExists( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName ))";
                    v16 = 7;
                  }
                }
                else
                {
                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                    goto LABEL_32;
                  v17 = "CHR(StringCchPrintfW( pwszTaskName, 32, TASK_SCHEDULER_DEVICE_UNLOCKED_FORMAT, pPrefix->dwRequestId))";
                  v16 = 1;
                }
              }
              else
              {
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                  goto LABEL_32;
                v17 = "CHR(StringCchPrintfW( pwszTaskXml, 1800, pwszDeviceUnlockedXmlFormat, pwszTrigger, DEVICE_DIRECTOR"
                      "Y_CLIENT_DEVICE_UNLOCKED_SWITCH, wstrEncodedPrefix.c_str(), wstrEncodedContext.c_str()))";
                v16 = -6;
              }
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_32;
              v17 = "CHR(pCommandHandler->GetDeviceUnlockedTrigger(pwszTrigger, &cchTrigger))";
              v16 = -16;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_32;
            v17 = "CHR(b64coder.Encode((BYTE *)pContext, sizeof(UpdateStatusContext), wstrEncodedContext))";
            v16 = -19;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_32;
          v17 = "CHR(b64coder.Encode((BYTE *)pPrefix, sizeof(CommandPrefix), wstrEncodedPrefix))";
          v16 = -20;
        }
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          (_DWORD)v11,
          Task,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
          v16,
          (__int64)v17);
        goto LABEL_32;
      }
      Task = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v8,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
          233,
          (__int64)"CPR(pCommandHandler)");
    }
    else
    {
      Task = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v8,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
          232,
          (__int64)"CPR(pContext)");
    }
  }
  else
  {
    Task = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        231,
        (__int64)"CPR(pPrefix)");
  }
LABEL_32:
  std::wstring::_Tidy_deallocate(v21);
  std::wstring::_Tidy_deallocate(v22);
  operator delete(0);
  return (unsigned int)Task;
}

```

## disassembly

```asm
0x180012c94  push    rbp
0x180012c96  push    rbx
0x180012c97  push    rsi
0x180012c98  push    rdi
0x180012c99  push    r14
0x180012c9b  push    r15
0x180012c9d  lea     rbp, [rsp-1008h]
0x180012ca5  mov     eax, 1108h
0x180012caa  call    _alloca_probe
0x180012caf  sub     rsp, rax
0x180012cb2  mov     rax, cs:__security_cookie
0x180012cb9  xor     rax, rsp
0x180012cbc  mov     [rbp+1030h+var_40], rax
0x180012cc3  mov     rdi, r9
0x180012cc6  mov     rsi, r8
0x180012cc9  mov     r15, rdx
0x180012ccc  mov     r14, rcx
0x180012ccf  mov     [rsp+1130h+var_10E8], 0
0x180012cd8  mov     [rsp+1130h+var_10E0], 0
0x180012ce0  lea     rcx, [rsp+1130h+var_10B8]
0x180012ce5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180012cea  nop
0x180012ceb  lea     rcx, [rsp+1130h+var_10D8]
0x180012cf0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180012cf5  nop
0x180012cf6  xor     edx, edx; Val
0x180012cf8  mov     r8d, 0E10h; Size
0x180012cfe  lea     rcx, [rbp+1030h+var_E50]; void *
0x180012d05  call    memset_0
0x180012d0a  xor     edx, edx; Val
0x180012d0c  lea     r8d, [rdx+40h]; Size
0x180012d10  lea     rcx, [rbp+1030h+var_1090]; void *
0x180012d14  call    memset_0
0x180012d19  xor     edx, edx; Val
0x180012d1b  mov     r8d, 200h; Size
0x180012d21  lea     rcx, [rbp+1030h+var_1050]; void *
0x180012d25  call    memset_0
0x180012d2a  mov     [rsp+1130h+var_10F0], 100h
0x180012d32  test    r15, r15
0x180012d35  jnz     short loc_180012D66
0x180012d37  mov     r8d, 80070057h
0x180012d3d  mov     ebx, r8d
0x180012d40  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012d47  jz      loc_180012FBD
0x180012d4d  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x180012d54  mov     [rsp+1130h+var_1108], rax
0x180012d59  mov     dword ptr [rsp+1130h+var_1110], 2E7h
0x180012d61  jmp     loc_180012FB0
0x180012d66  test    rsi, rsi
0x180012d69  jnz     short loc_180012D9A
0x180012d6b  mov     r8d, 80070057h
0x180012d71  mov     ebx, r8d
0x180012d74  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012d7b  jz      loc_180012FBD
0x180012d81  lea     rax, aCprPcontext; "CPR(pContext)"
0x180012d88  mov     [rsp+1130h+var_1108], rax
0x180012d8d  mov     dword ptr [rsp+1130h+var_1110], 2E8h
0x180012d95  jmp     loc_180012FB0
0x180012d9a  test    rdi, rdi
0x180012d9d  jnz     short loc_180012DCE
0x180012d9f  mov     r8d, 80070057h
0x180012da5  mov     ebx, r8d
0x180012da8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012daf  jz      loc_180012FBD
0x180012db5  lea     rax, aCprPcommandhan; "CPR(pCommandHandler)"
0x180012dbc  mov     [rsp+1130h+var_1108], rax
0x180012dc1  mov     dword ptr [rsp+1130h+var_1110], 2E9h
0x180012dc9  jmp     loc_180012FB0
0x180012dce  lea     r9, [rsp+1130h+var_10B8]
0x180012dd3  mov     r8d, 14h
0x180012dd9  mov     rdx, r15
0x180012ddc  call    ?Encode@DdcBase64Coder@@QEAAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcBase64Coder::Encode(uchar const *,ulong,std::wstring &)
0x180012de1  mov     ebx, eax
0x180012de3  test    eax, eax
0x180012de5  jns     short loc_180012E0D
0x180012de7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012dee  jz      loc_180012FBD
0x180012df4  lea     rax, aChrB64coderEnc_0; "CHR(b64coder.Encode((BYTE *)pPrefix, si"...
0x180012dfb  mov     [rsp+1130h+var_1108], rax
0x180012e00  mov     dword ptr [rsp+1130h+var_1110], 2ECh
0x180012e08  jmp     loc_180012FAD
0x180012e0d  lea     r9, [rsp+1130h+var_10D8]
0x180012e12  mov     r8d, 1Ch
0x180012e18  mov     rdx, rsi
0x180012e1b  call    ?Encode@DdcBase64Coder@@QEAAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcBase64Coder::Encode(uchar const *,ulong,std::wstring &)
0x180012e20  mov     ebx, eax
0x180012e22  test    eax, eax
0x180012e24  jns     short loc_180012E4C
0x180012e26  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012e2d  jz      loc_180012FBD
0x180012e33  lea     rax, aChrB64coderEnc; "CHR(b64coder.Encode((BYTE *)pContext, s"...
0x180012e3a  mov     [rsp+1130h+var_1108], rax
0x180012e3f  mov     dword ptr [rsp+1130h+var_1110], 2EDh
0x180012e47  jmp     loc_180012FAD
0x180012e4c  mov     rax, [rdi]
0x180012e4f  lea     r8, [rsp+1130h+var_10F0]
0x180012e54  lea     rdx, [rbp+1030h+var_1050]
0x180012e58  mov     rcx, rdi
0x180012e5b  mov     rax, [rax+48h]
0x180012e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e64  mov     ebx, eax
0x180012e66  test    eax, eax
0x180012e68  jns     short loc_180012E90
0x180012e6a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012e71  jz      loc_180012FBD
0x180012e77  lea     rax, aChrPcommandhan; "CHR(pCommandHandler->GetDeviceUnlockedT"...
0x180012e7e  mov     [rsp+1130h+var_1108], rax
0x180012e83  mov     dword ptr [rsp+1130h+var_1110], 2F0h
0x180012e8b  jmp     loc_180012FAD
0x180012e90  lea     rcx, [rsp+1130h+var_10D8]
0x180012e95  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012e9a  mov     rdx, rax
0x180012e9d  lea     rcx, [rsp+1130h+var_10B8]
0x180012ea2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012ea7  mov     [rsp+1130h+var_1100], rdx
0x180012eac  mov     [rsp+1130h+var_1108], rax
0x180012eb1  lea     rax, aDeviceunlocked_0; "-DeviceUnlocked"
0x180012eb8  mov     [rsp+1130h+var_1110], rax
0x180012ebd  lea     r9, [rbp+1030h+var_1050]
0x180012ec1  lea     r8, aTaskVersion14X_1; "<Task version=\"1.4\" xmlns=\"http://sc"...
0x180012ec8  mov     edx, 708h; unsigned __int64
0x180012ecd  lea     rcx, [rbp+1030h+var_E50]; unsigned __int16 *
0x180012ed4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012ed9  mov     ebx, eax
0x180012edb  test    eax, eax
0x180012edd  jns     short loc_180012F05
0x180012edf  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012ee6  jz      loc_180012FBD
0x180012eec  lea     rax, aChrStringcchpr_4; "CHR(StringCchPrintfW( pwszTaskXml, 1800"...
0x180012ef3  mov     [rsp+1130h+var_1108], rax
0x180012ef8  mov     dword ptr [rsp+1130h+var_1110], 2FAh
0x180012f00  jmp     loc_180012FAD
0x180012f05  mov     r9d, [r15]
0x180012f08  lea     r8, aDeviceunlocked; "DeviceUnlocked%lu"
0x180012f0f  mov     edx, 20h ; ' '; unsigned __int64
0x180012f14  lea     rcx, [rbp+1030h+var_1090]; unsigned __int16 *
0x180012f18  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012f1d  mov     ebx, eax
0x180012f1f  test    eax, eax
0x180012f21  jns     short loc_180012F46
0x180012f23  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012f2a  jz      loc_180012FBD
0x180012f30  lea     rax, aChrStringcchpr_6; "CHR(StringCchPrintfW( pwszTaskName, 32,"...
0x180012f37  mov     [rsp+1130h+var_1108], rax
0x180012f3c  mov     dword ptr [rsp+1130h+var_1110], 301h
0x180012f44  jmp     short loc_180012FAD
0x180012f46  lea     r8, [rbp+1030h+var_1090]; unsigned __int16 *
0x180012f4a  mov     rcx, r14; this
0x180012f4d  call    ?DeleteTaskIfExists@DdcTaskSchedulerWrapper@@AEAAJPEBG0@Z; DdcTaskSchedulerWrapper::DeleteTaskIfExists(ushort const *,ushort const *)
0x180012f52  mov     ebx, eax
0x180012f54  test    eax, eax
0x180012f56  jns     short loc_180012F77
0x180012f58  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012f5f  jz      short loc_180012FBD
0x180012f61  lea     rax, aChrDeletetaski_0; "CHR(DeleteTaskIfExists( TASK_SCHEDULER_"...
0x180012f68  mov     [rsp+1130h+var_1108], rax
0x180012f6d  mov     dword ptr [rsp+1130h+var_1110], 307h
0x180012f75  jmp     short loc_180012FAD
0x180012f77  lea     r9, [rbp+1030h+var_E50]; unsigned __int16 *
0x180012f7e  lea     r8, [rbp+1030h+var_1090]; unsigned __int16 *
0x180012f82  mov     rcx, r14; this
0x180012f85  call    ?CreateTask@DdcTaskSchedulerWrapper@@AEAAJPEBG00@Z; DdcTaskSchedulerWrapper::CreateTask(ushort const *,ushort const *,ushort const *)
0x180012f8a  mov     ebx, eax
0x180012f8c  test    eax, eax
0x180012f8e  jns     short loc_180012FBD
0x180012f90  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012f97  jz      short loc_180012FBD
0x180012f99  lea     rax, aChrCreatetaskT_0; "CHR(CreateTask( TASK_SCHEDULER_DIRECTOR"...
0x180012fa0  mov     [rsp+1130h+var_1108], rax
0x180012fa5  mov     dword ptr [rsp+1130h+var_1110], 30Eh
0x180012fad  mov     r8d, ebx
0x180012fb0  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180012fb7  call    McTemplateU0dsqs_EventWriteTransfer
0x180012fbc  nop
0x180012fbd  lea     rcx, [rsp+1130h+var_10D8]
0x180012fc2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012fc7  nop
0x180012fc8  lea     rcx, [rsp+1130h+var_10B8]
0x180012fcd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012fd2  nop
0x180012fd3  xor     ecx, ecx; Block
0x180012fd5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012fda  mov     eax, ebx
0x180012fdc  mov     rcx, [rbp+1030h+var_40]
0x180012fe3  xor     rcx, rsp; StackCookie
0x180012fe6  call    __security_check_cookie
0x180012feb  add     rsp, 1108h
0x180012ff2  pop     r15
0x180012ff4  pop     r14
0x180012ff6  pop     rdi
0x180012ff7  pop     rsi
0x180012ff8  pop     rbx
0x180012ff9  pop     rbp
0x180012ffa  retn
```
