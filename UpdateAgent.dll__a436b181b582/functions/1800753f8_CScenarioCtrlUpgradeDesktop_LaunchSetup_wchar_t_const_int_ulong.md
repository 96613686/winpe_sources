# CScenarioCtrlUpgradeDesktop::LaunchSetup(wchar_t const *,int,ulong *)

- ea: `0x1800753f8`
- end: `0x180075bb6`
- name: `?LaunchSetup@CScenarioCtrlUpgradeDesktop@@AEAAJPEB_WHPEAK@Z`
- size: `1982`
- prototype: `int(CScenarioCtrlUpgradeDesktop *__hidden this, const wchar_t *, int, unsigned int *)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c960`
- `0x1800498e0`
- `0x180064610`
- `0x180080850`

## callees

- `0x1800059d0`
- `0x180008fbc`
- `0x180039f90`
- `0x1800408d0`
- `0x180040b48`
- `0x1800674f0`
- `0x18007528c`
- `0x1800753f8`
- `0x180077664`
- `0x180078b9c`
- `0x180079870`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180075852`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800758a3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800758d3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180075a2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180075a3f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180075852`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800758a3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800758d3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180075a2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180075a3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075b62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075b62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180075b77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180075b77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007565d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007565d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075ab8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800757c6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800757c6`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180075aa8`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180075aa8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007563e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007563e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800756c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075b3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075b50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800756c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075b3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075b50`

## string_xrefs

- `0x1800755f2`: `ProcessId`
- `0x1800759a3`: `ProcessId`
- `0x180075625`: `UpgradeDesktop: Found running instance of setup. Attempting reconnect...`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CScenarioCtrlUpgradeDesktop::LaunchSetup(__int64 this, wchar_t *a2, int a3, unsigned int *a4)
{
  __int64 v5; // rsi
  LPWSTR v6; // r13
  HANDLE v7; // rbx
  HANDLE v8; // r14
  __int64 updated; // rcx
  signed int v10; // edi
  __int64 v11; // rdx
  CProgressHandler *v12; // r13
  int v13; // ebx
  const wchar_t *v14; // rdx
  int Value; // eax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rdx
  const wchar_t *v22; // rdx
  DWORD v23; // ebx
  __int64 v24; // rcx
  HANDLE v25; // rax
  signed int LastError; // eax
  __int64 v27; // rcx
  int StringCch; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdx
  int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rdx
  DWORD ProcessId; // eax
  __int64 v37; // rcx
  int v38; // eax
  DWORD i; // eax
  DWORD v40; // r15d
  __int64 v41; // rcx
  void *v42; // rcx
  __int64 v43; // rcx
  void *v44; // rcx
  __int64 v45; // rcx
  const wchar_t *v46; // rdx
  int v47; // eax
  __int64 v48; // rcx
  const wchar_t *v49; // rdx
  __int64 v50; // rcx
  int v51; // eax
  __int64 v52; // rcx
  int v53; // eax
  signed int v54; // eax
  DWORD v55; // eax
  const char *v56; // r9
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  int v59; // [rsp+20h] [rbp-A8h]
  int v60; // [rsp+28h] [rbp-A0h]
  int v61; // [rsp+30h] [rbp-98h] BYREF
  LPWSTR lpCommandLine; // [rsp+38h] [rbp-90h]
  DWORD dwProcessId; // [rsp+40h] [rbp-88h] BYREF
  int v64; // [rsp+44h] [rbp-84h]
  unsigned int v65; // [rsp+48h] [rbp-80h] BYREF
  int v66; // [rsp+4Ch] [rbp-7Ch]
  int v67; // [rsp+50h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-70h] BYREF
  unsigned int *v69; // [rsp+60h] [rbp-68h]
  __int64 v70; // [rsp+68h] [rbp-60h]
  DWORD ExitCode; // [rsp+70h] [rbp-58h] BYREF
  HANDLE Process; // [rsp+78h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v70 = -2;
  try
  {
    v69 = a4;
    v66 = a3;
    v5 = this;
    v6 = 0;
    lpCommandLine = 0;
    v7 = 0;
    hObject = 0;
    v8 = 0;
    Process = 0;
    v61 = 0;
    dwProcessId = 0;
    v65 = 0;
    ExitCode = 0;
    if ( !a2 )
    {
      updated = 0;
      v10 = -2147024809;
      if ( *(_QWORD *)(v5 + 32) )
      {
        updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  *(_QWORD *)(v5 + 32),
                                  4,
                                  L"%s(%d): Result = 0x%X",
                                  L"CScenarioCtrlUpgradeDesktop::LaunchSetup",
                                  1090,
                                  -2147024809);
        goto LABEL_5;
      }
      goto LABEL_7;
    }
    if ( !a4 )
    {
      updated = 0;
      v10 = -2147024809;
      if ( *(_QWORD *)(v5 + 32) )
      {
        updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  *(_QWORD *)(v5 + 32),
                                  4,
                                  L"%s(%d): Result = 0x%X",
                                  L"CScenarioCtrlUpgradeDesktop::LaunchSetup",
                                  1091,
                                  -2147024809);
LABEL_5:
        if ( (int)updated < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated, v11);
      }
LABEL_7:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_121:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
      if ( v8 )
        CloseHandle(v8);
      if ( v7 )
        CloseHandle(v7);
      if ( v6 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v6 - 2);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      return (unsigned int)v10;
    }
    v12 = 0;
    v13 = 0;
    v64 = 0;
    v67 = 0;
    if ( *(_DWORD *)(this + 24) != 28 )
    {
      v12 = (CProgressHandler *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(this + 16) + 64LL))(*(_QWORD *)(this + 16));
      if ( v12 )
      {
        v14 = L"SYSTEM\\Setup\\Servicing\\Volatile";
        if ( *(_DWORD *)(v5 + 24) != 28 )
          v14 = L"SYSTEM\\Setup\\MoSetup\\Volatile";
        Value = CRegUtilT<unsigned long,CRegType,0,1>::GetValue(this, v14, L"SetupProgress", &v67);
        this = 1;
        if ( Value >= 0 )
          v13 = 1;
        v64 = v13;
      }
    }
    v16 = CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(this, (__int64)a2, &hObject, &v61);
    v10 = v16;
    if ( v16 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16, v17);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
    if ( v10 < 0 )
    {
      v19 = 0;
      if ( *(_QWORD *)(v5 + 32) )
      {
        v20 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                *(_QWORD *)(v5 + 32),
                4,
                L"%s(%d): Result = 0x%X",
                L"CScenarioCtrlUpgradeDesktop::LaunchSetup",
                1122,
                v10);
        v19 = (unsigned int)v20;
        if ( v20 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v20, v21);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
      v7 = hObject;
      goto LABEL_120;
    }
    if ( v61 && *(_DWORD *)(v5 + 164) )
    {
      v22 = L"SYSTEM\\Setup\\MoSetup\\Volatile";
      if ( *(_DWORD *)(v5 + 24) == 28 )
        v22 = L"SYSTEM\\Setup\\Servicing\\Volatile";
      if ( (int)CRegUtilT<unsigned long,CRegType,0,1>::GetValue(v18, v22, L"ProcessId", &dwProcessId) >= 0 )
      {
        v23 = dwProcessId;
        if ( *(_DWORD *)(v5 + 164) == dwProcessId )
        {
          v24 = *(_QWORD *)(v5 + 32);
          if ( v24 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v24,
              2,
              L"UpgradeDesktop: Found running instance of setup. Attempting reconnect...");
          v25 = OpenProcess(0x100400u, 0, v23);
          v8 = v25;
          if ( v25 )
          {
            Process = v25;
            v27 = *(_QWORD *)(v5 + 32);
            if ( v27 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v27, 2, L"UpgradeDesktop: Process reconnnect successful!");
          }
          else
          {
            Process = 0;
            if ( *(_QWORD *)(v5 + 32) )
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                *(_QWORD *)(v5 + 32),
                3,
                L"UpgradeDesktop: Process reconnnect failed -> [0x%X]",
                (unsigned int)LastError);
            }
          }
        }
      }
    }
    v7 = hObject;
    if ( hObject )
    {
      CloseHandle(hObject);
      v7 = 0;
      hObject = 0;
    }
    if ( !v8 )
    {
      v61 = 0;
      StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a2, &v61);
      v10 = StringCch;
      if ( StringCch < 0
        || (StringCch = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(a2),
            v10 = StringCch,
            StringCch < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch, v29);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
      if ( v10 < 0 )
      {
        v30 = 0;
        if ( *(_QWORD *)(v5 + 32) )
        {
          v30 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                *(_QWORD *)(v5 + 32),
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CScenarioCtrlUpgradeDesktop::LaunchSetup",
                                1150,
                                v10);
          goto LABEL_49;
        }
LABEL_51:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v30);
LABEL_120:
        v6 = lpCommandLine;
        goto LABEL_121;
      }
      v32 = CMoUpdateHelpersT<CEmptyType>::LaunchProcess(lpCommandLine);
      v10 = v32;
      if ( v32 < 0 )
      {
        v33 = 0;
        if ( *(_QWORD *)(v5 + 32) )
        {
          v34 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  *(_QWORD *)(v5 + 32),
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CScenarioCtrlUpgradeDesktop::LaunchSetup",
                  1151,
                  v32);
          v33 = (unsigned int)v34;
          if ( v34 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v34, v35);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v33);
        v8 = Process;
        goto LABEL_120;
      }
      v8 = Process;
      ProcessId = GetProcessId(Process);
      *(_DWORD *)(v5 + 164) = ProcessId;
      v37 = *(_QWORD *)(v5 + 32);
      if ( v37 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v37, 2, L"UpgradeDesktop: Saving process id [0x%X].", ProcessId);
      v38 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 16) + 112LL))(*(_QWORD *)(v5 + 16));
      v10 = v38;
      if ( v38 < 0 )
      {
        v30 = 0;
        if ( !*(_QWORD *)(v5 + 32) )
          goto LABEL_51;
        v60 = v38;
        v59 = 1157;
        goto LABEL_62;
      }
    }
    if ( !v12 )
    {
      WaitForSingleObject(v8, 0xFFFFFFFF);
LABEL_103:
      *(_DWORD *)(v5 + 164) = 0;
      v52 = *(_QWORD *)(v5 + 32);
      if ( v52 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v52, 2, L"UpgradeDesktop: Clearing process id.");
      v53 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 16) + 112LL))(*(_QWORD *)(v5 + 16));
      v10 = v53;
      if ( v53 >= 0 )
      {
        if ( GetExitCodeProcess(v8, &ExitCode) )
        {
          v55 = ExitCode;
          if ( v66 && ExitCode == -1047526935 )
          {
            v55 = -2147024891;
            ExitCode = -2147024891;
          }
          *v69 = v55;
          goto LABEL_120;
        }
        v54 = GetLastError();
        v10 = v54;
        if ( v54 )
        {
          if ( v54 > 0 )
            v10 = (unsigned __int16)v54 | 0x80070000;
          v30 = 0;
          if ( v10 >= 0 )
            goto LABEL_51;
        }
        else
        {
          v10 = -2147467259;
          v30 = 0;
        }
        if ( !*(_QWORD *)(v5 + 32) )
          goto LABEL_51;
        v60 = v10;
        v59 = 1253;
      }
      else
      {
        v30 = 0;
        if ( !*(_QWORD *)(v5 + 32) )
          goto LABEL_51;
        v60 = v53;
        v59 = 1249;
      }
LABEL_62:
      v30 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                            *(_QWORD *)(v5 + 32),
                            4,
                            L"%s(%d): Result = 0x%X",
                            L"CScenarioCtrlUpgradeDesktop::LaunchSetup",
                            v59,
                            v60);
LABEL_49:
      if ( (int)v30 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v30, v31);
      goto LABEL_51;
    }
    for ( i = WaitForSingleObject(v8, 0); ; i = WaitForSingleObject(v8, 0x3E8u) )
    {
      v40 = i;
      if ( i != 258 && i )
        goto LABEL_103;
      v41 = *(_QWORD *)(v5 + 16);
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 120LL))(v41);
      if ( v12 )
      {
        v42 = *(void **)(v5 + 128);
        if ( v42 && !WaitForSingleObject(v42, 0) )
        {
          v43 = *(_QWORD *)(v5 + 32);
          if ( v43 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v43,
              2,
              L"UpgradeDesktop: Cancel event signalled. Disabling progress.");
LABEL_78:
          v12 = 0;
          goto LABEL_100;
        }
        v44 = *(void **)(v5 + 144);
        if ( v44 && !WaitForSingleObject(v44, 0) )
        {
          v45 = *(_QWORD *)(v5 + 32);
          if ( v45 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v45,
              2,
              L"UpgradeDesktop: Suspend event signalled. Disabling progress.");
          goto LABEL_78;
        }
        v46 = L"SYSTEM\\Setup\\MoSetup\\Volatile";
        if ( *(_DWORD *)(v5 + 24) == 28 )
          v46 = L"SYSTEM\\Setup\\Servicing\\Volatile";
        if ( (int)CRegUtilT<unsigned long,CRegType,0,1>::GetValue(v44, v46, L"SetupProgress", &v65) >= 0 )
        {
          if ( v64 )
          {
            if ( v65 == v67 )
            {
              if ( v40 )
                goto LABEL_100;
            }
            else
            {
              v64 = 0;
            }
          }
          v47 = CProgressHandler::OnSetupProgress(v12, v65);
          v10 = v47;
          if ( v47 == -2147023174 )
          {
            v10 = -1047526938;
LABEL_89:
            v30 = 0;
            if ( !*(_QWORD *)(v5 + 32) )
              goto LABEL_51;
            v60 = v10;
            v59 = 1211;
            goto LABEL_62;
          }
          if ( v47 < 0 )
            goto LABEL_89;
          v49 = L"SYSTEM\\Setup\\MoSetup\\Volatile";
          if ( *(_DWORD *)(v5 + 24) == 28 )
            v49 = L"SYSTEM\\Setup\\Servicing\\Volatile";
          if ( (int)CRegUtilT<unsigned long,CRegType,0,1>::GetValue(v48, v49, L"ProcessId", &dwProcessId) >= 0
            && *(_DWORD *)(v5 + 164) != dwProcessId )
          {
            *(_DWORD *)(v5 + 164) = dwProcessId;
            v50 = *(_QWORD *)(v5 + 32);
            if ( v50 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v50, 2, L"UpgradeDesktop: Updating process id [0x%X].");
            v51 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 16) + 112LL))(*(_QWORD *)(v5 + 16));
            v10 = v51;
            if ( v51 < 0 )
            {
              v30 = 0;
              if ( !*(_QWORD *)(v5 + 32) )
                goto LABEL_51;
              v60 = v51;
              v59 = 1223;
              goto LABEL_62;
            }
          }
        }
      }
LABEL_100:
      if ( v40 != 258 )
        goto LABEL_103;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4F5,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlUpgradeDesktopImpl.h",
                           v56);
  }
  return result;
}

```

## disassembly

```asm
0x1800753f8  push    rbx
0x1800753fa  push    rsi
0x1800753fb  push    rdi
0x1800753fc  push    r12
0x1800753fe  push    r13
0x180075400  push    r14
0x180075402  push    r15
0x180075404  sub     rsp, 90h
0x18007540b  mov     [rsp+0C8h+var_60], 0FFFFFFFFFFFFFFFEh
0x180075414  mov     rax, cs:__security_cookie
0x18007541b  xor     rax, rsp
0x18007541e  mov     [rsp+0C8h+var_48], rax
0x180075426  mov     rax, r9
0x180075429  mov     [rsp+0C8h+var_68], rax
0x18007542e  mov     [rsp+0C8h+var_7C], r8d
0x180075433  mov     r15, rdx
0x180075436  mov     rsi, rcx
0x180075439  xor     r13d, r13d
0x18007543c  mov     [rsp+0C8h+lpCommandLine], r13
0x180075441  xor     ebx, ebx
0x180075443  mov     [rsp+0C8h+hObject], rbx
0x180075448  xor     r14d, r14d
0x18007544b  mov     [rsp+0C8h+Process], r14
0x180075450  mov     [rsp+0C8h+var_98], r14d
0x180075455  mov     [rsp+0C8h+dwProcessId], r14d
0x18007545a  mov     [rsp+0C8h+var_80], r14d
0x18007545f  mov     [rsp+0C8h+ExitCode], r14d
0x180075464  test    rdx, rdx
0x180075467  jnz     short loc_1800754B1
0x180075469  xor     ecx, ecx
0x18007546b  mov     edi, 80070057h
0x180075470  cmp     [rsi+20h], rcx
0x180075474  jz      short loc_1800754A7
0x180075476  mov     [rsp+0C8h+var_A0], edi
0x18007547a  mov     [rsp+0C8h+var_A8], 442h
0x180075482  lea     r9, aCscenarioctrlu_6; "CScenarioCtrlUpgradeDesktop::LaunchSetu"...
0x180075489  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180075490  lea     edx, [rbx+4]
0x180075493  mov     rcx, [rsi+20h]
0x180075497  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007549c  mov     ecx, eax
0x18007549e  test    ecx, ecx
0x1800754a0  jns     short loc_1800754A7
0x1800754a2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800754a7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800754ac  jmp     loc_180075B2B
0x1800754b1  test    rax, rax
0x1800754b4  jnz     short loc_1800754ED
0x1800754b6  xor     ecx, ecx
0x1800754b8  mov     edi, 80070057h
0x1800754bd  cmp     [rsi+20h], rcx
0x1800754c1  jz      short loc_1800754A7
0x1800754c3  mov     [rsp+0C8h+var_A0], edi
0x1800754c7  mov     [rsp+0C8h+var_A8], 443h
0x1800754cf  lea     r9, aCscenarioctrlu_6; "CScenarioCtrlUpgradeDesktop::LaunchSetu"...
0x1800754d6  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800754dd  lea     edx, [rax+4]
0x1800754e0  mov     rcx, [rsi+20h]
0x1800754e4  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800754e9  mov     ecx, eax
0x1800754eb  jmp     short loc_18007549E
0x1800754ed  xor     r13d, r13d
0x1800754f0  xor     ebx, ebx
0x1800754f2  mov     [rsp+0C8h+var_84], ebx
0x1800754f6  mov     [rsp+0C8h+var_78], ebx
0x1800754fa  cmp     dword ptr [rcx+18h], 1Ch
0x1800754fe  jz      short loc_18007554D
0x180075500  mov     rcx, [rcx+10h]
0x180075504  mov     rax, [rcx]
0x180075507  mov     rax, [rax+40h]
0x18007550b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075510  mov     r13, rax
0x180075513  test    rax, rax
0x180075516  jz      short loc_18007554D
0x180075518  lea     rdx, aSystemSetupSer_0; "SYSTEM\\Setup\\Servicing\\Volatile"
0x18007551f  lea     r12, aSystemSetupMos_2; "SYSTEM\\Setup\\MoSetup\\Volatile"
0x180075526  cmp     dword ptr [rsi+18h], 1Ch
0x18007552a  cmovnz  rdx, r12
0x18007552e  lea     r9, [rsp+0C8h+var_78]
0x180075533  lea     r8, aSetupprogress; "SetupProgress"
0x18007553a  call    ?GetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAK@Z; CRegUtilT<ulong,CRegType,0,1>::GetValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *)
0x18007553f  lea     ecx, [rbx+1]
0x180075542  test    eax, eax
0x180075544  cmovns  ebx, ecx
0x180075547  mov     [rsp+0C8h+var_84], ebx
0x18007554b  jmp     short loc_180075554
0x18007554d  lea     r12, aSystemSetupMos_2; "SYSTEM\\Setup\\MoSetup\\Volatile"
0x180075554  lea     rbx, aSystemSetupSer_0; "SYSTEM\\Setup\\Servicing\\Volatile"
0x18007555b  lea     r9, [rsp+0C8h+var_98]
0x180075560  lea     r8, [rsp+0C8h+hObject]
0x180075565  call    ?CreateMutexWithAcl@?$CDlpHelpersT@VCEmptyType@@@@SAJPEB_WHPEAPEAXPEAH@Z; CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(wchar_t const *,int,void * *,int *)
0x18007556a  mov     edi, eax
0x18007556c  test    eax, eax
0x18007556e  jns     short loc_180075577
0x180075570  mov     ecx, eax
0x180075572  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180075577  mov     ecx, edi
0x180075579  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007557e  test    edi, edi
0x180075580  jns     short loc_1800755CA
0x180075582  xor     ecx, ecx
0x180075584  cmp     [rsi+20h], rcx
0x180075588  jz      short loc_1800755BB
0x18007558a  mov     [rsp+0C8h+var_A0], edi
0x18007558e  mov     [rsp+0C8h+var_A8], 462h
0x180075596  lea     r9, aCscenarioctrlu_6; "CScenarioCtrlUpgradeDesktop::LaunchSetu"...
0x18007559d  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800755a4  lea     edx, [rcx+4]
0x1800755a7  mov     rcx, [rsi+20h]
0x1800755ab  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800755b0  mov     ecx, eax
0x1800755b2  test    eax, eax
0x1800755b4  jns     short loc_1800755BB
0x1800755b6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800755bb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800755c0  mov     rbx, [rsp+0C8h+hObject]
0x1800755c5  jmp     loc_180075B26
0x1800755ca  cmp     [rsp+0C8h+var_98], 0
0x1800755cf  jz      loc_1800756AE
0x1800755d5  cmp     dword ptr [rsi+0A4h], 0
0x1800755dc  jz      loc_1800756AE
0x1800755e2  mov     rdx, r12
0x1800755e5  cmp     dword ptr [rsi+18h], 1Ch
0x1800755e9  cmovz   rdx, rbx
0x1800755ed  lea     r9, [rsp+0C8h+dwProcessId]
0x1800755f2  lea     r8, aProcessid; "ProcessId"
0x1800755f9  call    ?GetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAK@Z; CRegUtilT<ulong,CRegType,0,1>::GetValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *)
0x1800755fe  test    eax, eax
0x180075600  js      loc_1800756AE
0x180075606  mov     ebx, [rsp+0C8h+dwProcessId]
0x18007560a  cmp     [rsi+0A4h], ebx
0x180075610  jnz     loc_1800756AE
0x180075616  mov     rcx, [rsi+20h]
0x18007561a  mov     r12d, 2
0x180075620  test    rcx, rcx
0x180075623  jz      short loc_180075634
0x180075625  lea     r8, aUpgradedesktop_25; "UpgradeDesktop: Found running instance "...
0x18007562c  mov     edx, r12d
0x18007562f  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180075634  mov     r8d, ebx; dwProcessId
0x180075637  xor     edx, edx; bInheritHandle
0x180075639  mov     ecx, 100400h; dwDesiredAccess
0x18007563e  call    cs:__imp_OpenProcess
0x180075645  nop     dword ptr [rax+rax+00h]
0x18007564a  mov     r14, rax
0x18007564d  test    rax, rax
0x180075650  jnz     short loc_18007568F
0x180075652  mov     [rsp+0C8h+Process], rax
0x180075657  cmp     [rsi+20h], rax
0x18007565b  jz      short loc_1800756B4
0x18007565d  call    cs:__imp_GetLastError
0x180075664  nop     dword ptr [rax+rax+00h]
0x180075669  test    eax, eax
0x18007566b  jle     short loc_180075675
0x18007566d  movzx   eax, ax
0x180075670  or      eax, 80070000h
0x180075675  mov     r9d, eax
0x180075678  lea     r8, aUpgradedesktop_39; "UpgradeDesktop: Process reconnnect fail"...
0x18007567f  mov     edx, 3
0x180075684  mov     rcx, [rsi+20h]
0x180075688  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007568d  jmp     short loc_1800756B4
0x18007568f  mov     [rsp+0C8h+Process], rax
0x180075694  mov     rcx, [rsi+20h]
0x180075698  test    rcx, rcx
0x18007569b  jz      short loc_1800756B4
0x18007569d  lea     r8, aUpgradedesktop_27; "UpgradeDesktop: Process reconnnect succ"...
0x1800756a4  mov     edx, r12d
0x1800756a7  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800756ac  jmp     short loc_18007568D
0x1800756ae  mov     r12d, 2
0x1800756b4  mov     rbx, [rsp+0C8h+hObject]
0x1800756b9  test    rbx, rbx
0x1800756bc  jz      short loc_1800756D4
0x1800756be  mov     rcx, rbx; hObject
0x1800756c1  call    cs:__imp_CloseHandle
0x1800756c8  nop     dword ptr [rax+rax+00h]
0x1800756cd  xor     ebx, ebx
0x1800756cf  mov     [rsp+0C8h+hObject], rbx
0x1800756d4  test    r14, r14
0x1800756d7  jnz     loc_180075844
0x1800756dd  mov     [rsp+0C8h+var_98], r14d
0x1800756e2  lea     rdx, [rsp+0C8h+var_98]
0x1800756e7  mov     rcx, r15
0x1800756ea  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEB_WPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(wchar_t const *,ulong *,ulong)
0x1800756ef  mov     edi, eax
0x1800756f1  test    eax, eax
0x1800756f3  js      short loc_18007570C
0x1800756f5  lea     r8, [rsp+0C8h+lpCommandLine]
0x1800756fa  mov     edx, [rsp+0C8h+var_98]
0x1800756fe  mov     rcx, r15; Src
0x180075701  call    ?CreateInternal@?$CImmutableStringsT@_WVCImmutableStringsPolicyDefault@@@@KAJPEB_WKPEAPEA_W@Z; CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(wchar_t const *,ulong,wchar_t * *)
0x180075706  mov     edi, eax
0x180075708  test    eax, eax
0x18007570a  jns     short loc_180075713
0x18007570c  mov     ecx, eax
0x18007570e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180075713  mov     ecx, edi
0x180075715  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007571a  test    edi, edi
0x18007571c  jns     short loc_180075761
0x18007571e  xor     ecx, ecx
0x180075720  cmp     [rsi+20h], rcx
0x180075724  jz      short loc_180075757
0x180075726  mov     [rsp+0C8h+var_A0], edi
0x18007572a  mov     [rsp+0C8h+var_A8], 47Eh
0x180075732  lea     r9, aCscenarioctrlu_6; "CScenarioCtrlUpgradeDesktop::LaunchSetu"...
0x180075739  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180075740  lea     edx, [rcx+4]
0x180075743  mov     rcx, [rsi+20h]
0x180075747  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007574c  mov     ecx, eax
0x18007574e  test    ecx, ecx
0x180075750  jns     short loc_180075757
0x180075752  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180075757  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007575c  jmp     loc_180075B26
0x180075761  lea     rdx, [rsp+0C8h+Process]
0x180075766  mov     rcx, [rsp+0C8h+lpCommandLine]; lpCommandLine
0x18007576b  call    ?LaunchProcess@?$CMoUpdateHelpersT@VCEmptyType@@@@SAJPEA_WPEAPEAX@Z; CMoUpdateHelpersT<CEmptyType>::LaunchProcess(wchar_t *,void * *)
0x180075770  mov     edi, eax
0x180075772  test    eax, eax
0x180075774  jns     short loc_1800757BE
0x180075776  xor     ecx, ecx
0x180075778  cmp     [rsi+20h], rcx
0x18007577c  jz      short loc_1800757AF
0x18007577e  mov     [rsp+0C8h+var_A0], eax
0x180075782  mov     [rsp+0C8h+var_A8], 47Fh
0x18007578a  lea     r9, aCscenarioctrlu_6; "CScenarioCtrlUpgradeDesktop::LaunchSetu"...
0x180075791  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180075798  lea     edx, [rcx+4]
0x18007579b  mov     rcx, [rsi+20h]
0x18007579f  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800757a4  mov     ecx, eax
0x1800757a6  test    eax, eax
0x1800757a8  jns     short loc_1800757AF
0x1800757aa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800757af  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800757b4  mov     r14, [rsp+0C8h+Process]
0x1800757b9  jmp     loc_180075B26
0x1800757be  mov     r14, [rsp+0C8h+Process]
0x1800757c3  mov     rcx, r14; Process
0x1800757c6  call    cs:__imp_GetProcessId
0x1800757cd  nop     dword ptr [rax+rax+00h]
0x1800757d2  mov     [rsi+0A4h], eax
0x1800757d8  mov     rcx, [rsi+20h]
0x1800757dc  test    rcx, rcx
0x1800757df  jz      short loc_1800757F3
0x1800757e1  mov     r9d, eax
0x1800757e4  lea     r8, aUpgradedesktop_28; "UpgradeDesktop: Saving process id [0x%X"...
0x1800757eb  mov     edx, r12d
0x1800757ee  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800757f3  mov     rcx, [rsi+10h]
0x1800757f7  mov     rax, [rcx]
0x1800757fa  mov     rax, [rax+70h]
0x1800757fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075803  mov     edi, eax
0x180075805  test    eax, eax
0x180075807  jns     short loc_180075844
0x180075809  xor     ecx, ecx
0x18007580b  cmp     [rsi+20h], rcx
0x18007580f  jz      loc_180075757
0x180075815  mov     [rsp+0C8h+var_A0], eax
0x180075819  mov     [rsp+0C8h+var_A8], 485h
0x180075821  lea     r9, aCscenarioctrlu_6; "CScenarioCtrlUpgradeDesktop::LaunchSetu"...
0x180075828  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18007582f  mov     edx, 4
0x180075834  mov     rcx, [rsi+20h]
0x180075838  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007583d  mov     ecx, eax
0x18007583f  jmp     loc_18007574E
0x180075844  mov     rcx, r14; hHandle
0x180075847  test    r13, r13
0x18007584a  jz      loc_180075A3C
0x180075850  xor     edx, edx; dwMilliseconds
0x180075852  call    cs:__imp_WaitForSingleObject
0x180075859  nop     dword ptr [rax+rax+00h]
0x18007585e  lea     rdi, aSystemSetupSer_0; "SYSTEM\\Setup\\Servicing\\Volatile"
0x180075865  mov     r15d, eax
0x180075868  cmp     eax, 102h
0x18007586d  jz      short loc_180075877
0x18007586f  test    eax, eax
0x180075871  jnz     loc_180075A4B
0x180075877  mov     rcx, [rsi+10h]
0x18007587b  test    rcx, rcx
0x18007587e  jz      short loc_18007588C
0x180075880  mov     rax, [rcx]
0x180075883  mov     rax, [rax+78h]
0x180075887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007588c  test    r13, r13
0x18007588f  jz      loc_180075A1A
0x180075895  mov     rcx, [rsi+80h]; hHandle
0x18007589c  test    rcx, rcx
0x18007589f  jz      short loc_1800758C5
0x1800758a1  xor     edx, edx; dwMilliseconds
0x1800758a3  call    cs:__imp_WaitForSingleObject
0x1800758aa  nop     dword ptr [rax+rax+00h]
0x1800758af  test    eax, eax
0x1800758b1  jnz     short loc_1800758C5
0x1800758b3  mov     rcx, [rsi+20h]
  ... truncated ...
```
