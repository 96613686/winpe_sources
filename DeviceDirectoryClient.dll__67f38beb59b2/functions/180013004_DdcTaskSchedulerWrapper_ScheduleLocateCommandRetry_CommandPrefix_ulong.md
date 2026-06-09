# DdcTaskSchedulerWrapper::ScheduleLocateCommandRetry(CommandPrefix *,ulong)

- ea: `0x180013004`
- end: `0x1800132db`
- name: `?ScheduleLocateCommandRetry@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@K@Z`
- size: `727`
- prototype: `__int64 __fastcall(DdcTaskSchedulerWrapper *this, struct CommandPrefix *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800101f0`

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
- `0x180013004`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800130f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800130f4`

## string_xrefs

- `0x180013179`: `-LocateCommandRetry`
- `0x1800131f0`: `LocateCommandRetry%lu`
- `0x1800131ac`: `<Task version="1.4" xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task"><RegistrationInfo><SecurityDescriptor>D:P(A;;FA;;;SY)(A;;FRFX;;;BA)</SecurityDescriptor></RegistrationInfo><Principals><Principal id="System"><UserId>S-1-5-18</UserId><RunLevel>LeastPrivilege</RunLevel></Principal></Principals><Triggers><TimeTrigger><Repetition><Interval>PT%luM</Interval></Repetition><StartBoundary>%.4u-%.2u-%.2uT%.2u:%.2u:%.2u</StartBoundary></TimeTrigger>%s</Triggers><Settings><MultipleInstancesP`
- `0x180013292`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x1800130d7`: `CHR(b64coder.Encode((BYTE *)pPrefix, sizeof(CommandPrefix), wstrEncodedPrefix))`
- `0x1800131d4`: `CHR(StringCchPrintfW( pwszTaskXml, 1800, pwszLocateCommandRetryXmlFormat, COMMAND_RETRY_PERIOD_DEFAULT, now.wYear, now.wMonth, now.wDay, now.wHour, now.wMinute, now.wSecond, fConnected ? L"" : pwszConnectivityBackUpTrigger, DEVICE_DIRECTORY_CLIENT_LOCATE_COMMAND_RETRY_SWITCH, dwRetries + 1, wstrEncodedPrefix.c_str()))`
- `0x180013218`: `CHR(StringCchPrintfW( pwszTaskName, 32, TASK_SCHEDULER_LOCATE_COMMAND_RETRY_FORMAT, pPrefix->dwRequestId))`
- `0x180013249`: `CHR(DeleteTaskIfExists( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName ))`
- `0x18001327e`: `CHR(CreateTask( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName, pwszTaskXml ))`

## pseudocode

```c
__int64 __fastcall DdcTaskSchedulerWrapper::ScheduleLocateCommandRetry(
        DdcTaskSchedulerWrapper *this,
        struct CommandPrefix *a2,
        int a3)
{
  int v6; // edx
  __int64 v7; // rcx
  int Task; // ebx
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  __int64 v13; // rax
  __int64 *v14; // rdi
  int v15; // edx
  int v16; // ecx
  const unsigned __int16 *v17; // rdx
  int v18; // ecx
  const unsigned __int16 *v19; // rdx
  int v20; // ecx
  int v21; // edx
  int v22; // ecx
  int v24; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h]
  int v26; // [rsp+80h] [rbp-80h]
  _SYSTEMTIME SystemTime; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v28[40]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v29[32]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v30[1800]; // [rsp+100h] [rbp+0h] BYREF

  v25 = 0;
  v26 = 0;
  std::wstring::wstring(v28);
  SystemTime = 0;
  memset_0(v30, 0, sizeof(v30));
  memset_0(v29, 0, sizeof(v29));
  v24 = 0;
  if ( a2 )
  {
    Task = DdcBase64Coder::Encode(v7, a2, 20, v28);
    if ( Task >= 0 )
    {
      GetLocalTime(&SystemTime);
      Task = DeviceConnected(&v24);
      if ( Task >= 0 )
      {
        v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
        v14 = &qword_180033BD8;
        if ( !v24 )
          v14 = (__int64 *)L"<WnfStateChangeTrigger><StateName>7510bca323028b41</StateName><Data>01</Data><DataOffset>0</D"
                            "ataOffset></WnfStateChangeTrigger>";
        Task = StringCchPrintfW(
                 v30,
                 0x708u,
                 L"<Task version=\"1.4\" xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\"><RegistrationInfo"
                  "><SecurityDescriptor>D:P(A;;FA;;;SY)(A;;FRFX;;;BA)</SecurityDescriptor></RegistrationInfo><Principals>"
                  "<Principal id=\"System\"><UserId>S-1-5-18</UserId><RunLevel>LeastPrivilege</RunLevel></Principal></Pri"
                  "ncipals><Triggers><TimeTrigger><Repetition><Interval>PT%luM</Interval></Repetition><StartBoundary>%.4u"
                  "-%.2u-%.2uT%.2u:%.2u:%.2u</StartBoundary></TimeTrigger>%s</Triggers><Settings><MultipleInstancesPolicy"
                  ">Parallel</MultipleInstancesPolicy><DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries><Stop"
                  "IfGoingOnBatteries>false</StopIfGoingOnBatteries><AllowHardTerminate>false</AllowHardTerminate><StartW"
                  "henAvailable>true</StartWhenAvailable><RunOnlyIfNetworkAvailable>true</RunOnlyIfNetworkAvailable><Allo"
                  "wStartOnDemand>true</AllowStartOnDemand><Enabled>true</Enabled><Hidden>true</Hidden><RunOnlyIfIdle>fal"
                  "se</RunOnlyIfIdle><DisallowStartOnRemoteAppSession>false</DisallowStartOnRemoteAppSession><UseUnifiedS"
                  "chedulingEngine>true</UseUnifiedSchedulingEngine><WakeToRun>false</WakeToRun><ExecutionTimeLimit>PT0S<"
                  "/ExecutionTimeLimit><Priority>10</Priority></Settings><Actions Context=\"System\"><ComHandler><ClassId"
                  ">{AE31B729-D5FD-401E-AF42-784074835AFE}</ClassId><Data>%s %lu %s</Data></ComHandler></Actions></Task>",
                 360,
                 SystemTime.wYear,
                 SystemTime.wMonth,
                 SystemTime.wDay,
                 SystemTime.wHour,
                 SystemTime.wMinute,
                 SystemTime.wSecond,
                 v14,
                 L"-LocateCommandRetry",
                 a3 + 1,
                 v13);
        if ( Task >= 0 )
        {
          Task = StringCchPrintfW(v29, 0x20u, L"LocateCommandRetry%lu", *(unsigned int *)a2);
          if ( Task >= 0 )
          {
            Task = DdcTaskSchedulerWrapper::DeleteTaskIfExists(this, v17, v29);
            if ( Task >= 0 )
            {
              Task = DdcTaskSchedulerWrapper::CreateTask(this, v19, v29, v30);
              if ( Task < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v22,
                  v21,
                  Task,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
                  91,
                  (__int64)"CHR(CreateTask( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName, pwszTaskXml ))");
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v20,
                (_DWORD)v19,
                Task,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
                84,
                (__int64)"CHR(DeleteTaskIfExists( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName ))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v18,
              (_DWORD)v17,
              Task,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
              78,
              (__int64)"CHR(StringCchPrintfW( pwszTaskName, 32, TASK_SCHEDULER_LOCATE_COMMAND_RETRY_FORMAT, pPrefix->dwRequestId))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v16,
            v15,
            Task,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
            71,
            (__int64)"CHR(StringCchPrintfW( pwszTaskXml, 1800, pwszLocateCommandRetryXmlFormat, COMMAND_RETRY_PERIOD_DEFA"
                     "ULT, now.wYear, now.wMonth, now.wDay, now.wHour, now.wMinute, now.wSecond, fConnected ? L\"\" : pws"
                     "zConnectivityBackUpTrigger, DEVICE_DIRECTORY_CLIENT_LOCATE_COMMAND_RETRY_SWITCH, dwRetries + 1, wst"
                     "rEncodedPrefix.c_str()))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          v11,
          Task,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
          54,
          (__int64)"CHR(DeviceConnected(&fConnected))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        v9,
        Task,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        48,
        (__int64)"CHR(b64coder.Encode((BYTE *)pPrefix, sizeof(CommandPrefix), wstrEncodedPrefix))");
    }
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
        45,
        (__int64)"CPR(pPrefix)");
  }
  std::wstring::_Tidy_deallocate(v28);
  operator delete(0);
  return (unsigned int)Task;
}

```

## disassembly

```asm
0x180013004  mov     [rsp-8+arg_18], rbx
0x180013009  push    rbp
0x18001300a  push    rsi
0x18001300b  push    rdi
0x18001300c  push    r14
0x18001300e  push    r15
0x180013010  lea     rbp, [rsp-0E20h]
0x180013018  sub     rsp, 0F20h
0x18001301f  mov     rax, cs:__security_cookie
0x180013026  xor     rax, rsp
0x180013029  mov     [rbp+0E40h+var_30], rax
0x180013030  mov     r15d, r8d
0x180013033  mov     rsi, rdx
0x180013036  mov     r14, rcx
0x180013039  mov     [rsp+0F40h+var_EC8], 0
0x180013042  mov     [rbp+0E40h+var_EC0], 0
0x180013049  lea     rcx, [rbp+0E40h+var_EA8]
0x18001304d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180013052  nop
0x180013053  xorps   xmm1, xmm1
0x180013056  movups  xmmword ptr [rbp+0E40h+SystemTime.wYear], xmm1
0x18001305a  xor     edx, edx; Val
0x18001305c  mov     r8d, 0E10h; Size
0x180013062  lea     rcx, [rbp+0E40h+var_E40]; void *
0x180013066  call    memset_0
0x18001306b  xor     edx, edx; Val
0x18001306d  lea     r8d, [rdx+40h]; Size
0x180013071  lea     rcx, [rbp+0E40h+var_E80]; void *
0x180013075  call    memset_0
0x18001307a  mov     [rsp+0F40h+var_ED0], 0
0x180013082  test    rsi, rsi
0x180013085  jnz     short loc_1800130B2
0x180013087  mov     ebx, 80070057h
0x18001308c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180013093  jz      loc_1800132A2
0x180013099  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x1800130a0  mov     [rsp+0F40h+var_F18], rax
0x1800130a5  mov     [rsp+0F40h+var_F20], 22Dh
0x1800130ad  jmp     loc_180013292
0x1800130b2  lea     r9, [rbp+0E40h+var_EA8]
0x1800130b6  mov     r8d, 14h
0x1800130bc  mov     rdx, rsi
0x1800130bf  call    ?Encode@DdcBase64Coder@@QEAAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcBase64Coder::Encode(uchar const *,ulong,std::wstring &)
0x1800130c4  mov     ebx, eax
0x1800130c6  test    eax, eax
0x1800130c8  jns     short loc_1800130F0
0x1800130ca  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800130d1  jz      loc_1800132A2
0x1800130d7  lea     rax, aChrB64coderEnc_0; "CHR(b64coder.Encode((BYTE *)pPrefix, si"...
0x1800130de  mov     [rsp+0F40h+var_F18], rax
0x1800130e3  mov     [rsp+0F40h+var_F20], 230h
0x1800130eb  jmp     loc_180013292
0x1800130f0  lea     rcx, [rbp+0E40h+SystemTime]; lpSystemTime
0x1800130f4  call    cs:__imp_GetLocalTime
0x1800130fa  lea     rcx, [rsp+0F40h+var_ED0]; int *
0x1800130ff  call    ?DeviceConnected@@YAJPEAH@Z; DeviceConnected(int *)
0x180013104  mov     ebx, eax
0x180013106  test    eax, eax
0x180013108  jns     short loc_180013130
0x18001310a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180013111  jz      loc_1800132A2
0x180013117  lea     rax, aChrDeviceconne; "CHR(DeviceConnected(&fConnected))"
0x18001311e  mov     [rsp+0F40h+var_F18], rax
0x180013123  mov     [rsp+0F40h+var_F20], 236h
0x18001312b  jmp     loc_180013292
0x180013130  lea     rcx, [rbp+0E40h+var_EA8]
0x180013134  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013139  lea     rdi, qword_180033BD8
0x180013140  lea     rcx, aWnfstatechange; "<WnfStateChangeTrigger><StateName>7510b"...
0x180013147  cmp     [rsp+0F40h+var_ED0], 0
0x18001314c  cmovz   rdi, rcx
0x180013150  lea     ecx, [r15+1]
0x180013154  movzx   edx, [rbp+0E40h+SystemTime.wSecond]
0x180013158  movzx   r8d, [rbp+0E40h+SystemTime.wMinute]
0x18001315d  movzx   r9d, [rbp+0E40h+SystemTime.wHour]
0x180013162  movzx   r10d, [rbp+0E40h+SystemTime.wDay]
0x180013167  movzx   r11d, [rbp+0E40h+SystemTime.wMonth]
0x18001316c  movzx   ebx, [rbp+0E40h+SystemTime.wYear]
0x180013170  mov     [rsp+0F40h+var_ED8], rax
0x180013175  mov     [rsp+0F40h+var_EE0], ecx
0x180013179  lea     rax, aLocatecommandr; "-LocateCommandRetry"
0x180013180  mov     [rsp+0F40h+var_EE8], rax
0x180013185  mov     [rsp+0F40h+var_EF0], rdi
0x18001318a  mov     [rsp+0F40h+var_EF8], edx
0x18001318e  mov     [rsp+0F40h+var_F00], r8d
0x180013193  mov     [rsp+0F40h+var_F08], r9d
0x180013198  mov     [rsp+0F40h+var_F10], r10d
0x18001319d  mov     dword ptr [rsp+0F40h+var_F18], r11d
0x1800131a2  mov     [rsp+0F40h+var_F20], ebx
0x1800131a6  mov     r9d, 168h
0x1800131ac  lea     r8, aTaskVersion14X_0; "<Task version=\"1.4\" xmlns=\"http://sc"...
0x1800131b3  mov     edx, 708h; unsigned __int64
0x1800131b8  lea     rcx, [rbp+0E40h+var_E40]; unsigned __int16 *
0x1800131bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800131c1  mov     ebx, eax
0x1800131c3  test    eax, eax
0x1800131c5  jns     short loc_1800131ED
0x1800131c7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800131ce  jz      loc_1800132A2
0x1800131d4  lea     rax, aChrStringcchpr_7; "CHR(StringCchPrintfW( pwszTaskXml, 1800"...
0x1800131db  mov     [rsp+0F40h+var_F18], rax
0x1800131e0  mov     [rsp+0F40h+var_F20], 247h
0x1800131e8  jmp     loc_180013292
0x1800131ed  mov     r9d, [rsi]
0x1800131f0  lea     r8, aLocatecommandr_0; "LocateCommandRetry%lu"
0x1800131f7  mov     edx, 20h ; ' '; unsigned __int64
0x1800131fc  lea     rcx, [rbp+0E40h+var_E80]; unsigned __int16 *
0x180013200  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013205  mov     ebx, eax
0x180013207  test    eax, eax
0x180013209  jns     short loc_18001322E
0x18001320b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180013212  jz      loc_1800132A2
0x180013218  lea     rax, aChrStringcchpr_2; "CHR(StringCchPrintfW( pwszTaskName, 32,"...
0x18001321f  mov     [rsp+0F40h+var_F18], rax
0x180013224  mov     [rsp+0F40h+var_F20], 24Eh
0x18001322c  jmp     short loc_180013292
0x18001322e  lea     r8, [rbp+0E40h+var_E80]; unsigned __int16 *
0x180013232  mov     rcx, r14; this
0x180013235  call    ?DeleteTaskIfExists@DdcTaskSchedulerWrapper@@AEAAJPEBG0@Z; DdcTaskSchedulerWrapper::DeleteTaskIfExists(ushort const *,ushort const *)
0x18001323a  mov     ebx, eax
0x18001323c  test    eax, eax
0x18001323e  jns     short loc_18001325F
0x180013240  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180013247  jz      short loc_1800132A2
0x180013249  lea     rax, aChrDeletetaski_0; "CHR(DeleteTaskIfExists( TASK_SCHEDULER_"...
0x180013250  mov     [rsp+0F40h+var_F18], rax
0x180013255  mov     [rsp+0F40h+var_F20], 254h
0x18001325d  jmp     short loc_180013292
0x18001325f  lea     r9, [rbp+0E40h+var_E40]; unsigned __int16 *
0x180013263  lea     r8, [rbp+0E40h+var_E80]; unsigned __int16 *
0x180013267  mov     rcx, r14; this
0x18001326a  call    ?CreateTask@DdcTaskSchedulerWrapper@@AEAAJPEBG00@Z; DdcTaskSchedulerWrapper::CreateTask(ushort const *,ushort const *,ushort const *)
0x18001326f  mov     ebx, eax
0x180013271  test    eax, eax
0x180013273  jns     short loc_1800132A2
0x180013275  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001327c  jz      short loc_1800132A2
0x18001327e  lea     rax, aChrCreatetaskT_0; "CHR(CreateTask( TASK_SCHEDULER_DIRECTOR"...
0x180013285  mov     [rsp+0F40h+var_F18], rax
0x18001328a  mov     [rsp+0F40h+var_F20], 25Bh
0x180013292  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180013299  mov     r8d, ebx
0x18001329c  call    McTemplateU0dsqs_EventWriteTransfer
0x1800132a1  nop
0x1800132a2  lea     rcx, [rbp+0E40h+var_EA8]
0x1800132a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800132ab  nop
0x1800132ac  xor     ecx, ecx; Block
0x1800132ae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800132b3  mov     eax, ebx
0x1800132b5  mov     rcx, [rbp+0E40h+var_30]
0x1800132bc  xor     rcx, rsp; StackCookie
0x1800132bf  call    __security_check_cookie
0x1800132c4  mov     rbx, [rsp+0F40h+arg_18]
0x1800132cc  add     rsp, 0F20h
0x1800132d3  pop     r15
0x1800132d5  pop     r14
0x1800132d7  pop     rdi
0x1800132d8  pop     rsi
0x1800132d9  pop     rbp
0x1800132da  retn
```
