# DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(CommandPrefix *,UpdateStatusContext *)

- ea: `0x1800132e4`
- end: `0x180013643`
- name: `?ScheduleUpdateStatusRetry@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@@Z`
- size: `863`
- prototype: `__int64 __fastcall(DdcTaskSchedulerWrapper *__hidden this, struct CommandPrefix *, struct UpdateStatusContext *)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800107e0`
- `0x180010dd4`
- `0x18001122c`
- `0x1800118fc`

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
- `0x18001263c`
- `0x1800132e4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180013452`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180013452`

## string_xrefs

- `0x1800134e0`: `-UpdateStatusRetry`
- `0x180013557`: `UpdateStatusRetry%lu`
- `0x180013513`: `<Task version="1.4" xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task"><RegistrationInfo><SecurityDescriptor>D:P(A;;FA;;;SY)(A;;FRFX;;;BA)</SecurityDescriptor></RegistrationInfo><Principals><Principal id="System"><UserId>S-1-5-18</UserId><RunLevel>LeastPrivilege</RunLevel></Principal></Principals><Triggers><TimeTrigger><Repetition><Interval>PT%luM</Interval></Repetition><StartBoundary>%.4u-%.2u-%.2uT%.2u:%.2u:%.2u</StartBoundary></TimeTrigger>%s</Triggers><Settings><MultipleInstancesP`
- `0x1800135fc`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x1800133f7`: `CHR(b64coder.Encode((BYTE *)pPrefix, sizeof(CommandPrefix), wstrEncodedPrefix))`
- `0x1800135b0`: `CHR(DeleteTaskIfExists( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName ))`
- `0x1800135e5`: `CHR(CreateTask( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName, pwszTaskXml ))`
- `0x180013435`: `CHR(b64coder.Encode((BYTE *)pContext, sizeof(UpdateStatusContext), wstrEncodedContext))`
- `0x18001353b`: `CHR(StringCchPrintfW( pwszTaskXml, 1800, pwszUpdateStatusRetryXmlFormat, COMMAND_RETRY_PERIOD_DEFAULT, now.wYear, now.wMonth, now.wDay, now.wHour, now.wMinute, now.wSecond, fConnected ? L"" : pwszConnectivityBackUpTrigger, DEVICE_DIRECTORY_CLIENT_UPDATE_STATUS_RETRY_SWITCH, wstrEncodedPrefix.c_str(), wstrEncodedContext.c_str()))`
- `0x18001357f`: `CHR(StringCchPrintfW( pwszTaskName, 32, TASK_SCHEDULER_UPDATE_STATUS_RETRY_FORMAT, pPrefix->dwRequestId))`

## pseudocode

```c
__int64 __fastcall DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(
        DdcTaskSchedulerWrapper *this,
        struct CommandPrefix *a2,
        struct UpdateStatusContext *a3)
{
  int v6; // edx
  __int64 v7; // rcx
  int Task; // ebx
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 *v13; // rdi
  char v15; // [rsp+20h] [rbp-E0h]
  const char *v16; // [rsp+28h] [rbp-D8h]
  int v17; // [rsp+70h] [rbp-90h] BYREF
  __int64 v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+80h] [rbp-80h]
  struct _SYSTEMTIME SystemTime; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v21[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v22[40]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v23[32]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v24[1800]; // [rsp+120h] [rbp+20h] BYREF

  v18 = 0;
  v19 = 0;
  std::wstring::wstring(v22);
  std::wstring::wstring(v21);
  SystemTime = 0;
  memset_0(v24, 0, sizeof(v24));
  memset_0(v23, 0, sizeof(v23));
  v17 = 0;
  if ( a2 )
  {
    if ( a3 )
    {
      ++*((_DWORD *)a3 + 6);
      Task = DdcBase64Coder::Encode(v7, a2, 20, v22);
      if ( Task >= 0 )
      {
        Task = DdcBase64Coder::Encode(v10, a3, 28, v21);
        if ( Task >= 0 )
        {
          GetLocalTime(&SystemTime);
          Task = DeviceConnected(&v17);
          if ( Task >= 0 )
          {
            v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
            v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
            v13 = &qword_180033BD8;
            if ( !v17 )
              v13 = (__int64 *)L"<WnfStateChangeTrigger><StateName>7510bca323028b41</StateName><Data>01</Data><DataOffset>"
                                "0</DataOffset></WnfStateChangeTrigger>";
            Task = StringCchPrintfW(
                     v24,
                     0x708u,
                     L"<Task version=\"1.4\" xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\"><Registration"
                      "Info><SecurityDescriptor>D:P(A;;FA;;;SY)(A;;FRFX;;;BA)</SecurityDescriptor></RegistrationInfo><Pri"
                      "ncipals><Principal id=\"System\"><UserId>S-1-5-18</UserId><RunLevel>LeastPrivilege</RunLevel></Pri"
                      "ncipal></Principals><Triggers><TimeTrigger><Repetition><Interval>PT%luM</Interval></Repetition><St"
                      "artBoundary>%.4u-%.2u-%.2uT%.2u:%.2u:%.2u</StartBoundary></TimeTrigger>%s</Triggers><Settings><Mul"
                      "tipleInstancesPolicy>Parallel</MultipleInstancesPolicy><DisallowStartIfOnBatteries>false</Disallow"
                      "StartIfOnBatteries><StopIfGoingOnBatteries>false</StopIfGoingOnBatteries><AllowHardTerminate>false"
                      "</AllowHardTerminate><StartWhenAvailable>true</StartWhenAvailable><RunOnlyIfNetworkAvailable>true<"
                      "/RunOnlyIfNetworkAvailable><AllowStartOnDemand>true</AllowStartOnDemand><Enabled>true</Enabled><Hi"
                      "dden>true</Hidden><RunOnlyIfIdle>false</RunOnlyIfIdle><DisallowStartOnRemoteAppSession>false</Disa"
                      "llowStartOnRemoteAppSession><UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine><WakeToRu"
                      "n>false</WakeToRun><ExecutionTimeLimit>PT0S</ExecutionTimeLimit><Priority>10</Priority></Settings>"
                      "<Actions Context=\"System\"><ComHandler><ClassId>{AE31B729-D5FD-401E-AF42-784074835AFE}</ClassId><"
                      "Data>%s %s %s</Data></ComHandler></Actions></Task>",
                     360,
                     SystemTime.wYear,
                     SystemTime.wMonth,
                     SystemTime.wDay,
                     SystemTime.wHour,
                     SystemTime.wMinute,
                     SystemTime.wSecond,
                     v13,
                     L"-UpdateStatusRetry",
                     v12,
                     v11);
            if ( Task >= 0 )
            {
              Task = StringCchPrintfW(v23, 0x20u, L"UpdateStatusRetry%lu", *(unsigned int *)a2);
              if ( Task >= 0 )
              {
                Task = DdcTaskSchedulerWrapper::DeleteTaskIfExists(this, v9, v23);
                if ( Task >= 0 )
                {
                  Task = DdcTaskSchedulerWrapper::CreateTask(this, v9, v23, v24);
                  if ( Task >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                    goto LABEL_31;
                  v16 = "CHR(CreateTask( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName, pwszTaskXml ))";
                  v15 = -70;
                }
                else
                {
                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                    goto LABEL_31;
                  v16 = "CHR(DeleteTaskIfExists( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName ))";
                  v15 = -77;
                }
              }
              else
              {
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                  goto LABEL_31;
                v16 = "CHR(StringCchPrintfW( pwszTaskName, 32, TASK_SCHEDULER_UPDATE_STATUS_RETRY_FORMAT, pPrefix->dwRequestId))";
                v15 = -83;
              }
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_31;
              v16 = "CHR(StringCchPrintfW( pwszTaskXml, 1800, pwszUpdateStatusRetryXmlFormat, COMMAND_RETRY_PERIOD_DEFAUL"
                    "T, now.wYear, now.wMonth, now.wDay, now.wHour, now.wMinute, now.wSecond, fConnected ? L\"\" : pwszCo"
                    "nnectivityBackUpTrigger, DEVICE_DIRECTORY_CLIENT_UPDATE_STATUS_RETRY_SWITCH, wstrEncodedPrefix.c_str"
                    "(), wstrEncodedContext.c_str()))";
              v15 = -90;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_31;
            v16 = "CHR(DeviceConnected(&fConnected))";
            v15 = -107;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_31;
          v16 = "CHR(b64coder.Encode((BYTE *)pContext, sizeof(UpdateStatusContext), wstrEncodedContext))";
          v15 = -113;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_31;
        v16 = "CHR(b64coder.Encode((BYTE *)pPrefix, sizeof(CommandPrefix), wstrEncodedPrefix))";
        v15 = -114;
      }
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        (_DWORD)v9,
        Task,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        v15,
        (__int64)v16);
      goto LABEL_31;
    }
    Task = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v6,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        136,
        (__int64)"CPR(pContext)");
  }
  else
  {
    Task = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v6,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        135,
        (__int64)"CPR(pPrefix)");
  }
LABEL_31:
  std::wstring::_Tidy_deallocate(v21);
  std::wstring::_Tidy_deallocate(v22);
  operator delete(0);
  return (unsigned int)Task;
}

```

## disassembly

```asm
0x1800132e4  push    rbp
0x1800132e6  push    rbx
0x1800132e7  push    rsi
0x1800132e8  push    rdi
0x1800132e9  push    r14
0x1800132eb  lea     rbp, [rsp-0E40h]
0x1800132f3  sub     rsp, 0F40h
0x1800132fa  mov     rax, cs:__security_cookie
0x180013301  xor     rax, rsp
0x180013304  mov     [rbp+0E60h+var_30], rax
0x18001330b  mov     rdi, r8
0x18001330e  mov     rsi, rdx
0x180013311  mov     r14, rcx
0x180013314  mov     [rsp+0F60h+var_EE8], 0
0x18001331d  mov     [rbp+0E60h+var_EE0], 0
0x180013324  lea     rcx, [rbp+0E60h+var_EA8]
0x180013328  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001332d  nop
0x18001332e  lea     rcx, [rbp+0E60h+var_EC8]
0x180013332  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180013337  nop
0x180013338  xorps   xmm1, xmm1
0x18001333b  movups  xmmword ptr [rbp+0E60h+SystemTime.wYear], xmm1
0x18001333f  xor     edx, edx; Val
0x180013341  mov     r8d, 0E10h; Size
0x180013347  lea     rcx, [rbp+0E60h+var_E40]; void *
0x18001334b  call    memset_0
0x180013350  xor     edx, edx; Val
0x180013352  lea     r8d, [rdx+40h]; Size
0x180013356  lea     rcx, [rbp+0E60h+var_E80]; void *
0x18001335a  call    memset_0
0x18001335f  mov     [rsp+0F60h+var_EF0], 0
0x180013367  test    rsi, rsi
0x18001336a  jnz     short loc_18001339B
0x18001336c  mov     r8d, 80070057h
0x180013372  mov     ebx, r8d
0x180013375  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001337c  jz      loc_180013609
0x180013382  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x180013389  mov     [rsp+0F60h+var_F38], rax
0x18001338e  mov     dword ptr [rsp+0F60h+var_F40], 287h
0x180013396  jmp     loc_1800135FC
0x18001339b  test    rdi, rdi
0x18001339e  jnz     short loc_1800133CF
0x1800133a0  mov     r8d, 80070057h
0x1800133a6  mov     ebx, r8d
0x1800133a9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800133b0  jz      loc_180013609
0x1800133b6  lea     rax, aCprPcontext; "CPR(pContext)"
0x1800133bd  mov     [rsp+0F60h+var_F38], rax
0x1800133c2  mov     dword ptr [rsp+0F60h+var_F40], 288h
0x1800133ca  jmp     loc_1800135FC
0x1800133cf  inc     dword ptr [rdi+18h]
0x1800133d2  lea     r9, [rbp+0E60h+var_EA8]
0x1800133d6  mov     r8d, 14h
0x1800133dc  mov     rdx, rsi
0x1800133df  call    ?Encode@DdcBase64Coder@@QEAAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcBase64Coder::Encode(uchar const *,ulong,std::wstring &)
0x1800133e4  mov     ebx, eax
0x1800133e6  test    eax, eax
0x1800133e8  jns     short loc_180013410
0x1800133ea  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800133f1  jz      loc_180013609
0x1800133f7  lea     rax, aChrB64coderEnc_0; "CHR(b64coder.Encode((BYTE *)pPrefix, si"...
0x1800133fe  mov     [rsp+0F60h+var_F38], rax
0x180013403  mov     dword ptr [rsp+0F60h+var_F40], 28Eh
0x18001340b  jmp     loc_1800135F9
0x180013410  lea     r9, [rbp+0E60h+var_EC8]
0x180013414  mov     r8d, 1Ch
0x18001341a  mov     rdx, rdi
0x18001341d  call    ?Encode@DdcBase64Coder@@QEAAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcBase64Coder::Encode(uchar const *,ulong,std::wstring &)
0x180013422  mov     ebx, eax
0x180013424  test    eax, eax
0x180013426  jns     short loc_18001344E
0x180013428  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001342f  jz      loc_180013609
0x180013435  lea     rax, aChrB64coderEnc; "CHR(b64coder.Encode((BYTE *)pContext, s"...
0x18001343c  mov     [rsp+0F60h+var_F38], rax
0x180013441  mov     dword ptr [rsp+0F60h+var_F40], 28Fh
0x180013449  jmp     loc_1800135F9
0x18001344e  lea     rcx, [rbp+0E60h+SystemTime]; lpSystemTime
0x180013452  call    cs:__imp_GetLocalTime
0x180013458  lea     rcx, [rsp+0F60h+var_EF0]; int *
0x18001345d  call    ?DeviceConnected@@YAJPEAH@Z; DeviceConnected(int *)
0x180013462  mov     ebx, eax
0x180013464  test    eax, eax
0x180013466  jns     short loc_18001348E
0x180013468  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001346f  jz      loc_180013609
0x180013475  lea     rax, aChrDeviceconne; "CHR(DeviceConnected(&fConnected))"
0x18001347c  mov     [rsp+0F60h+var_F38], rax
0x180013481  mov     dword ptr [rsp+0F60h+var_F40], 295h
0x180013489  jmp     loc_1800135F9
0x18001348e  lea     rcx, [rbp+0E60h+var_EC8]
0x180013492  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013497  mov     rbx, rax
0x18001349a  lea     rcx, [rbp+0E60h+var_EA8]
0x18001349e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800134a3  lea     rdi, qword_180033BD8
0x1800134aa  lea     rcx, aWnfstatechange; "<WnfStateChangeTrigger><StateName>7510b"...
0x1800134b1  cmp     [rsp+0F60h+var_EF0], 0
0x1800134b6  cmovz   rdi, rcx
0x1800134ba  movzx   ecx, [rbp+0E60h+SystemTime.wSecond]
0x1800134be  movzx   edx, [rbp+0E60h+SystemTime.wMinute]
0x1800134c2  movzx   r8d, [rbp+0E60h+SystemTime.wHour]
0x1800134c7  movzx   r9d, [rbp+0E60h+SystemTime.wDay]
0x1800134cc  movzx   r10d, [rbp+0E60h+SystemTime.wMonth]
0x1800134d1  movzx   r11d, [rbp+0E60h+SystemTime.wYear]
0x1800134d6  mov     [rsp+0F60h+var_EF8], rbx
0x1800134db  mov     [rsp+0F60h+var_F00], rax
0x1800134e0  lea     rax, aUpdatestatusre_0; "-UpdateStatusRetry"
0x1800134e7  mov     [rsp+0F60h+var_F08], rax
0x1800134ec  mov     [rsp+0F60h+var_F10], rdi
0x1800134f1  mov     [rsp+0F60h+var_F18], ecx
0x1800134f5  mov     [rsp+0F60h+var_F20], edx
0x1800134f9  mov     [rsp+0F60h+var_F28], r8d
0x1800134fe  mov     [rsp+0F60h+var_F30], r9d
0x180013503  mov     dword ptr [rsp+0F60h+var_F38], r10d
0x180013508  mov     dword ptr [rsp+0F60h+var_F40], r11d
0x18001350d  mov     r9d, 168h
0x180013513  lea     r8, aTaskVersion14X; "<Task version=\"1.4\" xmlns=\"http://sc"...
0x18001351a  mov     edx, 708h; unsigned __int64
0x18001351f  lea     rcx, [rbp+0E60h+var_E40]; unsigned __int16 *
0x180013523  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013528  mov     ebx, eax
0x18001352a  test    eax, eax
0x18001352c  jns     short loc_180013554
0x18001352e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180013535  jz      loc_180013609
0x18001353b  lea     rax, aChrStringcchpr_3; "CHR(StringCchPrintfW( pwszTaskXml, 1800"...
0x180013542  mov     [rsp+0F60h+var_F38], rax
0x180013547  mov     dword ptr [rsp+0F60h+var_F40], 2A6h
0x18001354f  jmp     loc_1800135F9
0x180013554  mov     r9d, [rsi]
0x180013557  lea     r8, aUpdatestatusre; "UpdateStatusRetry%lu"
0x18001355e  mov     edx, 20h ; ' '; unsigned __int64
0x180013563  lea     rcx, [rbp+0E60h+var_E80]; unsigned __int16 *
0x180013567  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001356c  mov     ebx, eax
0x18001356e  test    eax, eax
0x180013570  jns     short loc_180013595
0x180013572  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180013579  jz      loc_180013609
0x18001357f  lea     rax, aChrStringcchpr_0; "CHR(StringCchPrintfW( pwszTaskName, 32,"...
0x180013586  mov     [rsp+0F60h+var_F38], rax
0x18001358b  mov     dword ptr [rsp+0F60h+var_F40], 2ADh
0x180013593  jmp     short loc_1800135F9
0x180013595  lea     r8, [rbp+0E60h+var_E80]; unsigned __int16 *
0x180013599  mov     rcx, r14; this
0x18001359c  call    ?DeleteTaskIfExists@DdcTaskSchedulerWrapper@@AEAAJPEBG0@Z; DdcTaskSchedulerWrapper::DeleteTaskIfExists(ushort const *,ushort const *)
0x1800135a1  mov     ebx, eax
0x1800135a3  test    eax, eax
0x1800135a5  jns     short loc_1800135C6
0x1800135a7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800135ae  jz      short loc_180013609
0x1800135b0  lea     rax, aChrDeletetaski_0; "CHR(DeleteTaskIfExists( TASK_SCHEDULER_"...
0x1800135b7  mov     [rsp+0F60h+var_F38], rax
0x1800135bc  mov     dword ptr [rsp+0F60h+var_F40], 2B3h
0x1800135c4  jmp     short loc_1800135F9
0x1800135c6  lea     r9, [rbp+0E60h+var_E40]; unsigned __int16 *
0x1800135ca  lea     r8, [rbp+0E60h+var_E80]; unsigned __int16 *
0x1800135ce  mov     rcx, r14; this
0x1800135d1  call    ?CreateTask@DdcTaskSchedulerWrapper@@AEAAJPEBG00@Z; DdcTaskSchedulerWrapper::CreateTask(ushort const *,ushort const *,ushort const *)
0x1800135d6  mov     ebx, eax
0x1800135d8  test    eax, eax
0x1800135da  jns     short loc_180013609
0x1800135dc  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800135e3  jz      short loc_180013609
0x1800135e5  lea     rax, aChrCreatetaskT_0; "CHR(CreateTask( TASK_SCHEDULER_DIRECTOR"...
0x1800135ec  mov     [rsp+0F60h+var_F38], rax
0x1800135f1  mov     dword ptr [rsp+0F60h+var_F40], 2BAh
0x1800135f9  mov     r8d, ebx
0x1800135fc  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180013603  call    McTemplateU0dsqs_EventWriteTransfer
0x180013608  nop
0x180013609  lea     rcx, [rbp+0E60h+var_EC8]
0x18001360d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013612  nop
0x180013613  lea     rcx, [rbp+0E60h+var_EA8]
0x180013617  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001361c  nop
0x18001361d  xor     ecx, ecx; Block
0x18001361f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013624  mov     eax, ebx
0x180013626  mov     rcx, [rbp+0E60h+var_30]
0x18001362d  xor     rcx, rsp; StackCookie
0x180013630  call    __security_check_cookie
0x180013635  add     rsp, 0F40h
0x18001363c  pop     r14
0x18001363e  pop     rdi
0x18001363f  pop     rsi
0x180013640  pop     rbx
0x180013641  pop     rbp
0x180013642  retn
```
