# DumpRunningProcessesLoadedDllDetector_ScheduleTask(void)

- ea: `0x18008b010`
- end: `0x18008b36a`
- name: `?DumpRunningProcessesLoadedDllDetector_ScheduleTask@@YAKXZ`
- size: `858`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008b4f0`

## callees

- `0x180012920`
- `0x18008b010`
- `0x1800f7010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18008b13b`
- `OLEAUT32!__imp_SysAllocString` at `0x18008b1cf`
- `OLEAUT32!__imp_SysAllocString` at `0x18008b224`
- `OLEAUT32!__imp_SysAllocString` at `0x18008b13b`
- `OLEAUT32!__imp_SysAllocString` at `0x18008b1cf`
- `OLEAUT32!__imp_SysAllocString` at `0x18008b224`
- `OLEAUT32!__imp_SysFreeString` at `0x18008b2d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18008b2da`
- `OLEAUT32!__imp_SysFreeString` at `0x18008b2e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18008b2d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18008b2da`
- `OLEAUT32!__imp_SysFreeString` at `0x18008b2e3`
- `OLEAUT32!__imp_VariantInit` at `0x18008b07a`
- `OLEAUT32!__imp_VariantInit` at `0x18008b07a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008b0a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008b0a0`

## string_xrefs

- `0x18008b149`: `Failed to allocate task folder name`
- `0x18008b1dd`: `Failed to allocate task definition content`
- `0x18008b232`: `Failed to allocate task name`
- `0x18008b048`: `PcaDumpRunningProcessesLoadedDllDetect`
- `0x18008b21d`: `PcaDumpRunningProcessesLoadedDllDetect`
- `0x18008b1c8`: `\n<Task version="1.6" xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task">\n  <RegistrationInfo>\n    <Source>Microsoft Corporation</Source>\n    <Author>Microsoft Corporation</Author>\n    <Version>1.0</Version>\n    <Description>Dump running processes loaded DLL list</Description>\n    <URI>\Microsoft\Windows\Application Experience\PCA Dump Running Processes Loaded DLL Detection Task</URI>\n    <SecurityDescriptor>D:(A;;GA;;;BA)(A;;GA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>\n  </Reg`
- `0x18008b03a`: `Scheduling %ws task...`
- `0x18008b0ac`: `Failed to create a task scheduler [%x]`
- `0x18008b029`: `DumpRunningProcessesLoadedDllDetector_ScheduleTask`
- `0x18008b20b`: `Failed to put task definition [%x]`
- `0x18008b1b6`: `Failed to create task definition [%x]`
- `0x18008b2ba`: `Failed to register task [%x]`

## pseudocode

```c
__int64 DumpRunningProcessesLoadedDllDetector_ScheduleTask(void)
{
  OLECHAR *v0; // rsi
  OLECHAR *v1; // r14
  OLECHAR *v2; // rdi
  HRESULT v3; // eax
  int v4; // ebx
  const char *v5; // r9
  int v6; // r8d
  __int64 v7; // rax
  __int64 (__fastcall *v8)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  BSTR v9; // rax
  const char *v10; // r9
  int v11; // r8d
  BSTR v12; // rax
  __int64 (__fastcall *v13)(__int64, OLECHAR *, __int64, __int64, VARIANTARG *, VARIANTARG *, int, VARIANTARG *, __int64 *); // rax
  LPVOID *ppv; // [rsp+20h] [rbp-A9h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-79h] BYREF
  VARIANTARG v17; // [rsp+70h] [rbp-59h] BYREF
  VARIANTARG v18; // [rsp+90h] [rbp-39h] BYREF
  VARIANTARG v19; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v20; // [rsp+D0h] [rbp+7h] BYREF
  IRecordInfo *pRecInfo; // [rsp+E0h] [rbp+17h]
  LPVOID v22; // [rsp+130h] [rbp+67h] BYREF
  __int64 v23; // [rsp+138h] [rbp+6Fh] BYREF
  __int64 v24; // [rsp+140h] [rbp+77h] BYREF
  __int64 v25; // [rsp+148h] [rbp+7Fh] BYREF

  v0 = 0;
  v22 = 0;
  v24 = 0;
  v23 = 0;
  v25 = 0;
  v1 = 0;
  v2 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  AslLogCallPrintf(
    3,
    (unsigned int)"DumpRunningProcessesLoadedDllDetector_ScheduleTask",
    1566,
    (unsigned int)"Scheduling %ws task...",
    L"PcaDumpRunningProcessesLoadedDllDetect");
  VariantInit(&pvarg);
  v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v22);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "Failed to create a task scheduler [%x]";
    v6 = 1576;
LABEL_3:
    LODWORD(ppv) = v3;
    AslLogCallPrintf(1, (unsigned int)"DumpRunningProcessesLoadedDllDetector_ScheduleTask", v6, (_DWORD)v5, ppv);
    goto LABEL_22;
  }
  v20 = *(_OWORD *)&pvarg.vt;
  v7 = *(_QWORD *)v22;
  pRecInfo = pvarg.pRecInfo;
  v17 = pvarg;
  v8 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v7 + 80);
  v18 = pvarg;
  v19 = pvarg;
  v3 = v8(v22, &v19, &v18, &v17, &v20);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "Failed to connect to scheduler [%x]";
    v6 = 1583;
    goto LABEL_3;
  }
  v9 = SysAllocString(L"Microsoft\\Windows\\Application Experience");
  v0 = v9;
  if ( !v9 )
  {
    v10 = "Failed to allocate task folder name";
    v11 = 1591;
LABEL_8:
    v4 = -2147024888;
    AslLogCallPrintf(1, (unsigned int)"DumpRunningProcessesLoadedDllDetector_ScheduleTask", v11, (_DWORD)v10);
    goto LABEL_22;
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v22 + 56LL))(v22, v9, &v24);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "Failed to get scheduler folder [%x]";
    v6 = 1598;
    goto LABEL_3;
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v22 + 72LL))(v22, 0, &v23);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "Failed to create task definition [%x]";
    v6 = 1605;
    goto LABEL_3;
  }
  v12 = SysAllocString(
          L"\n"
           "<Task version=\"1.6\" xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\">\n"
           "  <RegistrationInfo>\n"
           "    <Source>Microsoft Corporation</Source>\n"
           "    <Author>Microsoft Corporation</Author>\n"
           "    <Version>1.0</Version>\n"
           "    <Description>Dump running processes loaded DLL list</Description>\n"
           "    <URI>\\Microsoft\\Windows\\Application Experience\\PCA Dump Running Processes Loaded DLL Detection Task</"
           "URI>\n"
           "    <SecurityDescriptor>D:(A;;GA;;;BA)(A;;GA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>\n"
           "  </RegistrationInfo>\n"
           "  <Triggers>\n"
           "  <TimeTrigger>\n"
           "      <Repetition>\n"
           "        <Interval>PT3H</Interval>\n"
           "        <StopAtDurationEnd>false</StopAtDurationEnd>\n"
           "      </Repetition>\n"
           "      <StartBoundary>2025-07-01T03:00:00</StartBoundary>\n"
           "      <Enabled>true</Enabled>\n"
           "      <RandomDelay>PT30M</RandomDelay>\n"
           "    </TimeTrigger>\n"
           "  </Triggers>\n"
           "  <Settings>\n"
           "    <MultipleInstancesPolicy>IgnoreNew</MultipleInstancesPolicy>\n"
           "    <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>\n"
           "    <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>\n"
           "    <AllowHardTerminate>true</AllowHardTerminate>\n"
           "    <StartWhenAvailable>true</StartWhenAvailable>\n"
           "    <RunOnlyIfNetworkAvailable>false</RunOnlyIfNetworkAvailable>\n"
           "    <IdleSettings>\n"
           "      <StopOnIdleEnd>false</StopOnIdleEnd>\n"
           "    </IdleSettings>\n"
           "    <AllowStartOnDemand>true</AllowStartOnDemand>\n"
           "    <Enabled>true</Enabled>\n"
           "    <Hidden>false</Hidden>\n"
           "    <RunOnlyIfIdle>false</RunOnlyIfIdle>\n"
           "    <DisallowStartOnRemoteAppSession>false</DisallowStartOnRemoteAppSession>\n"
           "    <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\n"
           "    <WakeToRun>false</WakeToRun>\n"
           "    <ExecutionTimeLimit>PT30M</ExecutionTimeLimit>\n"
           "    <Priority>7</Priority>\n"
           "  </Settings>\n"
           "   <Principals>\n"
           "    <Principal id=\"LocalSystem\">\n"
           "      <UserId>S-1-5-18</UserId>\n"
           "      <RunLevel>LeastPrivilege</RunLevel>\n"
           "    </Principal>\n"
           "  </Principals>\n"
           "  <Actions Context=\"LocalSystem\">\n"
           "    <Exec>\n"
           "      <Command>%windir%\\system32\\rundll32.exe</Command>\n"
           "      <Arguments>%windir%\\system32\\PcaSvc.dll,PcaDumpRunningProcessesLoadedDllDetect</Arguments>\n"
           "    </Exec>\n"
           "  </Actions>\n"
           "</Task>\n");
  v2 = v12;
  if ( !v12 )
  {
    v10 = "Failed to allocate task definition content";
    v11 = 1613;
    goto LABEL_8;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v23 + 160LL))(v23, v12);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "Failed to put task definition [%x]";
    v6 = 1620;
    goto LABEL_3;
  }
  v1 = SysAllocString(L"PcaDumpRunningProcessesLoadedDllDetect");
  if ( !v1 )
  {
    v10 = "Failed to allocate task name";
    v11 = 1628;
    goto LABEL_8;
  }
  v13 = *(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, __int64, VARIANTARG *, VARIANTARG *, int, VARIANTARG *, __int64 *))(*(_QWORD *)v24 + 136LL);
  v19 = pvarg;
  v18 = pvarg;
  v17 = pvarg;
  v3 = v13(v24, v1, v23, 6, &v17, &v18, 3, &v19, &v25);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "Failed to register task [%x]";
    v6 = 1642;
    goto LABEL_3;
  }
  v4 = 0;
LABEL_22:
  SysFreeString(v0);
  SysFreeString(v1);
  SysFreeString(v2);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v22 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v4 < 0 )
  {
    if ( (v4 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v4;
  }
  else
  {
    return 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008b010  push    rbp
0x18008b012  push    rbx
0x18008b013  push    rsi
0x18008b014  push    rdi
0x18008b015  push    r12
0x18008b017  push    r13
0x18008b019  push    r14
0x18008b01b  lea     rbp, [rsp-27h]
0x18008b020  sub     rsp, 0F0h
0x18008b027  xor     esi, esi
0x18008b029  lea     r12, aDumprunningpro_9; "DumpRunningProcessesLoadedDllDetector_S"...
0x18008b030  xor     eax, eax
0x18008b032  mov     [rbp+57h+arg_0], rsi
0x18008b036  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18008b03a  lea     r9, aSchedulingWsTa; "Scheduling %ws task..."
0x18008b041  xorps   xmm0, xmm0
0x18008b044  mov     [rbp+57h+arg_10], rsi
0x18008b048  lea     rax, aPcadumprunning_1; "PcaDumpRunningProcessesLoadedDllDetect"
0x18008b04f  mov     [rbp+57h+arg_8], rsi
0x18008b053  lea     ecx, [rsi+3]
0x18008b056  mov     [rbp+57h+arg_18], rsi
0x18008b05a  mov     r8d, 61Eh
0x18008b060  mov     [rsp+120h+ppv], rax
0x18008b065  mov     rdx, r12
0x18008b068  xor     r14d, r14d
0x18008b06b  xor     edi, edi
0x18008b06d  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18008b071  call    AslLogCallPrintf
0x18008b076  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18008b07a  call    cs:__imp_VariantInit
0x18008b080  lea     rax, [rbp+57h+arg_0]
0x18008b084  xor     edx, edx; pUnkOuter
0x18008b086  lea     r13d, [rsi+1]
0x18008b08a  mov     [rsp+120h+ppv], rax; ppv
0x18008b08f  mov     r8d, r13d; dwClsContext
0x18008b092  lea     r9, IID_ITaskService; riid
0x18008b099  lea     rcx, CLSID_TaskScheduler; rclsid
0x18008b0a0  call    cs:__imp_CoCreateInstance
0x18008b0a6  mov     ebx, eax
0x18008b0a8  test    eax, eax
0x18008b0aa  jns     short loc_18008B0CD
0x18008b0ac  lea     r9, aFailedToCreate_6; "Failed to create a task scheduler [%x]"
0x18008b0b3  mov     r8d, 628h
0x18008b0b9  mov     rdx, r12
0x18008b0bc  mov     dword ptr [rsp+120h+ppv], eax
0x18008b0c0  mov     ecx, r13d
0x18008b0c3  call    AslLogCallPrintf
0x18008b0c8  jmp     loc_18008B2CE
0x18008b0cd  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18008b0d1  lea     rdx, [rbp+57h+var_50]
0x18008b0d5  mov     rcx, [rbp+57h+arg_0]
0x18008b0d9  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18008b0de  lea     r9, [rbp+57h+var_B0]
0x18008b0e2  mov     [rsp+120h+ppv], rdx
0x18008b0e7  lea     r8, [rbp+57h+var_90]
0x18008b0eb  lea     rdx, [rbp+57h+var_70]
0x18008b0ef  movaps  [rbp+57h+var_50], xmm1
0x18008b0f3  mov     rax, [rcx]
0x18008b0f6  movsd   [rbp+57h+var_40], xmm0
0x18008b0fb  movaps  [rbp+57h+var_B0], xmm1
0x18008b0ff  movsd   [rbp+57h+var_A0], xmm0
0x18008b104  mov     rax, [rax+50h]
0x18008b108  movaps  [rbp+57h+var_90], xmm1
0x18008b10c  movsd   [rbp+57h+var_80], xmm0
0x18008b111  movaps  [rbp+57h+var_70], xmm1
0x18008b115  movsd   [rbp+57h+var_60], xmm0
0x18008b11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b11f  mov     ebx, eax
0x18008b121  test    eax, eax
0x18008b123  jns     short loc_18008B134
0x18008b125  lea     r9, aFailedToConnec; "Failed to connect to scheduler [%x]"
0x18008b12c  mov     r8d, 62Fh
0x18008b132  jmp     short loc_18008B0B9
0x18008b134  lea     rcx, psz; "Microsoft\\Windows\\Application Experie"...
0x18008b13b  call    cs:__imp_SysAllocString
0x18008b141  mov     rsi, rax
0x18008b144  test    rax, rax
0x18008b147  jnz     short loc_18008B16B
0x18008b149  lea     r9, aFailedToAlloca_6; "Failed to allocate task folder name"
0x18008b150  mov     r8d, 637h
0x18008b156  mov     rdx, r12
0x18008b159  mov     ecx, r13d
0x18008b15c  mov     ebx, 80070008h
0x18008b161  call    AslLogCallPrintf
0x18008b166  jmp     loc_18008B2CE
0x18008b16b  mov     rcx, [rbp+57h+arg_0]
0x18008b16f  lea     r8, [rbp+57h+arg_10]
0x18008b173  mov     rdx, rsi
0x18008b176  mov     rax, [rcx]
0x18008b179  mov     rax, [rax+38h]
0x18008b17d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b182  mov     ebx, eax
0x18008b184  test    eax, eax
0x18008b186  jns     short loc_18008B19A
0x18008b188  lea     r9, aFailedToGetSch; "Failed to get scheduler folder [%x]"
0x18008b18f  mov     r8d, 63Eh
0x18008b195  jmp     loc_18008B0B9
0x18008b19a  mov     rcx, [rbp+57h+arg_0]
0x18008b19e  lea     r8, [rbp+57h+arg_8]
0x18008b1a2  xor     edx, edx
0x18008b1a4  mov     rax, [rcx]
0x18008b1a7  mov     rax, [rax+48h]
0x18008b1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b1b0  mov     ebx, eax
0x18008b1b2  test    eax, eax
0x18008b1b4  jns     short loc_18008B1C8
0x18008b1b6  lea     r9, aFailedToCreate_84; "Failed to create task definition [%x]"
0x18008b1bd  mov     r8d, 645h
0x18008b1c3  jmp     loc_18008B0B9
0x18008b1c8  lea     rcx, aTaskVersion16X_0; "\n<Task version=\"1.6\" xmlns=\"http://"...
0x18008b1cf  call    cs:__imp_SysAllocString
0x18008b1d5  mov     rdi, rax
0x18008b1d8  test    rax, rax
0x18008b1db  jnz     short loc_18008B1EF
0x18008b1dd  lea     r9, aFailedToAlloca_36; "Failed to allocate task definition cont"...
0x18008b1e4  mov     r8d, 64Dh
0x18008b1ea  jmp     loc_18008B156
0x18008b1ef  mov     rcx, [rbp+57h+arg_8]
0x18008b1f3  mov     rdx, rdi
0x18008b1f6  mov     rax, [rcx]
0x18008b1f9  mov     rax, [rax+0A0h]
0x18008b200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b205  mov     ebx, eax
0x18008b207  test    eax, eax
0x18008b209  jns     short loc_18008B21D
0x18008b20b  lea     r9, aFailedToPutTas_0; "Failed to put task definition [%x]"
0x18008b212  mov     r8d, 654h
0x18008b218  jmp     loc_18008B0B9
0x18008b21d  lea     rcx, aPcadumprunning_1; "PcaDumpRunningProcessesLoadedDllDetect"
0x18008b224  call    cs:__imp_SysAllocString
0x18008b22a  mov     r14, rax
0x18008b22d  test    rax, rax
0x18008b230  jnz     short loc_18008B244
0x18008b232  lea     r9, aFailedToAlloca_17; "Failed to allocate task name"
0x18008b239  mov     r8d, 65Ch
0x18008b23f  jmp     loc_18008B156
0x18008b244  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18008b248  lea     rdx, [rbp+57h+arg_18]
0x18008b24c  mov     rcx, [rbp+57h+arg_10]
0x18008b250  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18008b255  mov     r9d, 6
0x18008b25b  mov     r8, [rbp+57h+arg_8]
0x18008b25f  mov     [rsp+120h+var_E0], rdx
0x18008b264  lea     rdx, [rbp+57h+var_70]
0x18008b268  mov     rax, [rcx]
0x18008b26b  mov     [rsp+120h+var_E8], rdx
0x18008b270  lea     rdx, [rbp+57h+var_90]
0x18008b274  mov     [rsp+120h+var_F0], 3
0x18008b27c  mov     [rsp+120h+var_F8], rdx
0x18008b281  lea     rdx, [rbp+57h+var_B0]
0x18008b285  mov     rax, [rax+88h]
0x18008b28c  mov     [rsp+120h+ppv], rdx
0x18008b291  mov     rdx, r14
0x18008b294  movaps  [rbp+57h+var_70], xmm1
0x18008b298  movsd   [rbp+57h+var_60], xmm0
0x18008b29d  movaps  [rbp+57h+var_90], xmm1
0x18008b2a1  movsd   [rbp+57h+var_80], xmm0
0x18008b2a6  movaps  [rbp+57h+var_B0], xmm1
0x18008b2aa  movsd   [rbp+57h+var_A0], xmm0
0x18008b2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b2b4  mov     ebx, eax
0x18008b2b6  test    eax, eax
0x18008b2b8  jns     short loc_18008B2CC
0x18008b2ba  lea     r9, aFailedToRegist; "Failed to register task [%x]"
0x18008b2c1  mov     r8d, 66Ah
0x18008b2c7  jmp     loc_18008B0B9
0x18008b2cc  xor     ebx, ebx
0x18008b2ce  mov     rcx, rsi; bstrString
0x18008b2d1  call    cs:__imp_SysFreeString
0x18008b2d7  mov     rcx, r14; bstrString
0x18008b2da  call    cs:__imp_SysFreeString
0x18008b2e0  mov     rcx, rdi; bstrString
0x18008b2e3  call    cs:__imp_SysFreeString
0x18008b2e9  mov     rcx, [rbp+57h+arg_18]
0x18008b2ed  test    rcx, rcx
0x18008b2f0  jz      short loc_18008B2FE
0x18008b2f2  mov     rax, [rcx]
0x18008b2f5  mov     rax, [rax+10h]
0x18008b2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b2fe  mov     rcx, [rbp+57h+arg_8]
0x18008b302  test    rcx, rcx
0x18008b305  jz      short loc_18008B313
0x18008b307  mov     rax, [rcx]
0x18008b30a  mov     rax, [rax+10h]
0x18008b30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b313  mov     rcx, [rbp+57h+arg_10]
0x18008b317  test    rcx, rcx
0x18008b31a  jz      short loc_18008B328
0x18008b31c  mov     rax, [rcx]
0x18008b31f  mov     rax, [rax+10h]
0x18008b323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b328  mov     rcx, [rbp+57h+arg_0]
0x18008b32c  test    rcx, rcx
0x18008b32f  jz      short loc_18008B33D
0x18008b331  mov     rax, [rcx]
0x18008b334  mov     rax, [rax+10h]
0x18008b338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b33d  test    ebx, ebx
0x18008b33f  js      short loc_18008B345
0x18008b341  xor     ebx, ebx
0x18008b343  jmp     short loc_18008B356
0x18008b345  mov     eax, ebx
0x18008b347  and     eax, 1FFF0000h
0x18008b34c  cmp     eax, 70000h
0x18008b351  jnz     short loc_18008B356
0x18008b353  movzx   ebx, bx
0x18008b356  mov     eax, ebx
0x18008b358  add     rsp, 0F0h
0x18008b35f  pop     r14
0x18008b361  pop     r13
0x18008b363  pop     r12
0x18008b365  pop     rdi
0x18008b366  pop     rsi
0x18008b367  pop     rbx
0x18008b368  pop     rbp
0x18008b369  retn
```
