# DoqPoqExecuteInternal

- ea: `0x1800f7290`
- end: `0x1800f7b86`
- name: `DoqPoqExecuteInternal`
- size: `2294`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, int, AutoTx *)`
- caller_count: `1`
- callee_count: `41`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f7110`

## callees

- `0x180013250`
- `0x180028e24`
- `0x180043d50`
- `0x1800441fc`
- `0x1800442a0`
- `0x18004a920`
- `0x18005b180`
- `0x18005ec58`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800cf8c8`
- `0x1800eb920`
- `0x1800f1eb4`
- `0x1800f2f74`
- `0x1800f648c`
- `0x1800f6644`
- `0x1800f6748`
- `0x1800f7290`
- `0x1800f7ba4`
- `0x1800ff474`
- `0x1800ff654`
- `0x180112e00`
- `0x180113080`
- `0x18011804c`
- `0x180119828`
- `0x180121528`
- `0x180123c8c`
- `0x180124384`
- `0x180141170`
- `0x1801424e4`
- `0x180142658`
- `0x180145fd0`
- `0x180146c94`
- `0x180146cb8`
- `0x180146f28`
- `0x180148040`
- `0x1801481f4`
- `0x1801bd650`
- `0x1801c1498`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800f76db`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800f77a6`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800f76db`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800f77a6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800f7567`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800f7567`

## string_xrefs

- `0x1800f72e1`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing`
- `0x1800f733b`: `Max transactions retries set by registry to {}`
- `0x1800f7504`: `Failed opening driver update context`
- `0x1800f74ae`: `Unable to close driver update context`
- `0x1800f75e6`: `Failed to get offline Windows directory`
- `0x1800f7b01`: `Failed to get online Windows directory`
- `0x1800f7652`: `Unable to create transaction.  Continuing without transaction support.`
- `0x1800f77bd`: `Shtd: Driver operations completed successfully.`
- `0x1800f7790`: `{}: Driver operations completed successfully.`
- `0x1800f7800`: `Unable to open Drivers hive key`
- `0x1800f7a72`: `{}: Primitive operations completed successfully.`

## pseudocode

```c
__int64 __fastcall DoqPoqExecuteInternal(
        int a1,
        unsigned int a2,
        unsigned int a3,
        _DWORD *a4,
        int *a5,
        _DWORD *a6,
        __int64 a7,
        int a8,
        AutoTx *a9)
{
  int WindowsDirectory; // ebx
  unsigned int v14; // r14d
  __int64 v15; // rdx
  const char *v16; // rax
  const char **v17; // rsi
  unsigned int v18; // r13d
  int v19; // edx
  int v20; // r8d
  int v21; // r9d
  wchar_t *v22; // rdx
  wchar_t *v23; // rcx
  int v24; // edx
  unsigned int v25; // eax
  struct HDRIVERUPDATECONTEXT__ **v26; // r15
  unsigned int v27; // eax
  char *v28; // r13
  int v29; // eax
  _DWORD *v30; // rax
  CCbsSession *ActiveSession; // rcx
  CCbsSession *v32; // rcx
  int OfflineWindowsDirectory; // eax
  bool v34; // r8
  __int64 v35; // rdx
  unsigned int v36; // eax
  unsigned int v37; // eax
  int v38; // edx
  int v39; // r8d
  int v40; // r9d
  __int64 v41; // rcx
  int v42; // edx
  unsigned int v43; // ecx
  struct LogAdapter::Logger *v44; // rcx
  HKEY *v45; // rax
  unsigned int v46; // eax
  unsigned int v47; // ecx
  unsigned int v48; // eax
  unsigned int v49; // eax
  int v50; // edx
  int v51; // edx
  unsigned int v52; // ecx
  struct LogAdapter::Logger *v53; // rcx
  struct LogAdapter::Logger *v54; // rcx
  PHKEY v56; // [rsp+20h] [rbp-79h]
  int *v57; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v58; // [rsp+48h] [rbp-51h]
  wchar_t *v59; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v60; // [rsp+58h] [rbp-41h]
  BOOL v61; // [rsp+5Ch] [rbp-3Dh]
  _DWORD *v62; // [rsp+60h] [rbp-39h]
  __int128 v63; // [rsp+70h] [rbp-29h] BYREF
  int v64; // [rsp+80h] [rbp-19h] BYREF
  unsigned int v65; // [rsp+84h] [rbp-15h] BYREF
  unsigned int v66; // [rsp+88h] [rbp-11h] BYREF
  int v67; // [rsp+8Ch] [rbp-Dh] BYREF
  __int64 v68; // [rsp+90h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+3Fh]

  v57 = a5;
  v62 = a6;
  v60 = a3;
  WindowsDirectory = 0;
  v68 = 0;
  v65 = 0;
  v67 = 0;
  v66 = 2;
  v14 = 0xFFFF;
  if ( CbsRegQueryDWORDValue(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing",
         1u,
         L"MaxTransactionRetries",
         &v66) >= 0 )
    LogAdapter::TraceAtLevel<unsigned long>(1, "Max transactions retries set by registry to {}", &v66);
  else
    v66 = 2;
  if ( !a3 )
  {
    if ( a1 )
      v14 = (((unsigned __int8)vdwCbsCoreMode >> 1) & 1) != 0 ? 65539 : 2;
    else
      v14 = 0;
    SetPrimitiveExecutionContext(0, v14);
  }
  v15 = v60;
  v16 = "Startup";
  v17 = (const char **)((char *)a9 + 48);
  if ( !a1 )
    v16 = "Shtd";
  *v17 = v16;
  v61 = DoqCountDriverOperations(&v68, v15) != 0;
  while ( 1 )
  {
    v18 = a2 & 0xFFFF3FFF;
    v58 = v18;
    SetExecuteState(v18);
    if ( (unsigned __int64)(*((_QWORD *)a9 + 1) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      break;
    v28 = (char *)a9 + 40;
    v26 = (struct HDRIVERUPDATECONTEXT__ **)((char *)a9 + 32);
LABEL_28:
    v30 = v62;
    *a4 = 0;
    v59 = 0;
    *v30 = 1;
    ActiveSession = SafeGetActiveSession();
    if ( ActiveSession && (unsigned int)CCbsSession::IsOffline(ActiveSession) )
    {
      OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(v32, &v59);
      WindowsDirectory = OfflineWindowsDirectory;
      if ( OfflineWindowsDirectory < 0 )
      {
        v64 = OfflineWindowsDirectory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get offline Windows directory");
          v57 = &v64;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v57);
        }
        v35 = 203;
        goto LABEL_87;
      }
    }
    else
    {
      WindowsDirectory = PathGetWindowsDirectory(&v59, 0);
      if ( WindowsDirectory < 0 )
      {
        v64 = WindowsDirectory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get online Windows directory");
          v57 = &v64;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v57);
        }
        v35 = 209;
        goto LABEL_87;
      }
    }
    v36 = AutoCbsTransaction::Create(a9, L"CbsDriversAndPrimitives", v34, v59);
    LogAdapter::TraceAtLevelIfFailed<long,>(
      1,
      v36,
      "Unable to create transaction.  Continuing without transaction support.");
    v37 = CbsSetCurrentTransaction(0);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v37, "Unable to set the current transaction");
    if ( v61 )
    {
      InitializeDoqProgress(3 * v68);
      SetProgressMessage(0xFFFFFFFFLL, v58);
      if ( !v68 )
        goto LABEL_52;
      if ( LogAdapter::g_Logger )
        LogAdapter::Logger::LogNumObjects<char const *,unsigned __int64>(
          (_DWORD)LogAdapter::g_Logger,
          v38,
          v39,
          v40,
          (__int64)a9 + 48,
          (__int64)&v68);
      if ( !(unsigned int)_o__stricmp(*v17, "Shtd") )
      {
        v63 = CbsNonCriticalDoqStartEvent;
        CbsGenericEventReport(&v63, L"Shtd: Processing driver operations queue, Count %d.", (unsigned int)v68);
      }
      v56 = (PHKEY)*((_QWORD *)a9 + 1);
      WindowsDirectory = DoqExecute(v41, v60, v57, *((_QWORD *)a9 + 4));
      if ( (unsigned int)(WindowsDirectory + 2147018196) > 1
        && WindowsDirectory != -2147018096
        && WindowsDirectory != -2147018192
        || (unsigned __int64)(*((_QWORD *)a9 + 1) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL
        || (v43 = v65, ++v65, v43 >= v66) )
      {
        v44 = LogAdapter::g_Logger;
        if ( WindowsDirectory < 0 )
        {
          *a4 = 1;
          v64 = WindowsDirectory;
          if ( v44 )
          {
            LogAdapter::Logger::LogNumObjects<char const *>(
              (_DWORD)v44,
              0,
              3,
              (unsigned int)"{}: Failed while processing driver operations queue.",
              (__int64)v17);
            v57 = &v64;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v57);
          }
          v35 = 255;
          goto LABEL_87;
        }
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v42) = 1;
          LogAdapter::Logger::LogNumObjects<char const *>(
            (_DWORD)LogAdapter::g_Logger,
            v42,
            1,
            (unsigned int)"{}: Driver operations completed successfully.",
            (__int64)a9 + 48);
        }
        if ( !(unsigned int)_o__stricmp(*v17, "Shtd") )
        {
          v63 = CbsNonCriticalDoqEndEvent;
          CbsGenericEventReport(&v63, L"Shtd: Driver operations completed successfully.");
        }
        FlushHivesAndSystemVolume();
LABEL_52:
        v45 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(v28);
        v46 = CbsRegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Drivers", 0, 0x20019u, v45);
        LogAdapter::TraceAtLevelIfWin32Error<unsigned long,>(1, v46, "Unable to open Drivers hive key");
        goto LABEL_53;
      }
LABEL_58:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v59);
      a2 = v58;
    }
    else
    {
LABEL_53:
      *v62 = 0;
      WindowsDirectory = DoqNotifyVersionChange(0, *((void **)a9 + 1), v26, 0, 0);
      if ( ((unsigned int)(WindowsDirectory + 2147018196) <= 1
         || WindowsDirectory == -2147018096
         || WindowsDirectory == -2147018192)
        && (unsigned __int64)(*((_QWORD *)a9 + 1) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v47 = v65++;
        if ( v47 < v66 )
          goto LABEL_58;
      }
      if ( WindowsDirectory < 0 )
      {
        v54 = LogAdapter::g_Logger;
        *a4 = 1;
        v64 = WindowsDirectory;
        if ( v54 )
        {
          LogAdapter::Logger::LogNumObjects<char const *>(
            (_DWORD)v54,
            0,
            3,
            (unsigned int)"{}: Failed to notify PNP of possible OS version change.",
            (__int64)v17);
          v57 = &v64;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v57);
        }
        v35 = 290;
LABEL_87:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v35,
          (unsigned int)"onecore\\base\\cbs\\core\\cbscoreoperations.cpp",
          (const char *)(unsigned int)WindowsDirectory,
          (int)v56);
        goto LABEL_88;
      }
      v48 = CbsSetCurrentTransaction(*((void **)a9 + 1));
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v48, "Unable to set the current transaction");
      DeleteBootToPSRLRequest(0);
      v49 = CbsSetCurrentTransaction(0);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v49, "Unable to set the current transaction");
      a2 = v58 | 0x4000;
      SetExecuteState(v58 | 0x4000);
      SetProgressMessage(0xFFFFFFFFLL, v58 | 0x4000);
      UpdatePerfFromExecuteState(v58 | 0x4000);
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v50) = 1;
        LogAdapter::Logger::LogNumObjects<char const *>(
          (_DWORD)LogAdapter::g_Logger,
          v50,
          1,
          (unsigned int)"{}: Processing primitive operations queue.",
          (__int64)a9 + 48);
      }
      v67 = 0;
      WindowsDirectory = RunPoqExec(&v67, v57, (void **)a9);
      v64 = WindowsDirectory;
      if ( (unsigned int)(WindowsDirectory + 2147018196) > 1
        && WindowsDirectory != -2147018096
        && WindowsDirectory != -2147018192
        || (unsigned __int64)(*((_QWORD *)a9 + 1) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL
        || (v52 = v65, ++v65, v52 >= v66) )
      {
        if ( (vdwCbsCoreMode & 2) == 0 && !v60 && v67 )
          ReportPoqExecStatus(&v64, v14);
        v53 = LogAdapter::g_Logger;
        if ( WindowsDirectory < 0 )
        {
          *a4 = 1;
          v64 = WindowsDirectory;
          if ( v53 )
          {
            LogAdapter::Logger::LogNumObjects<char const *>(
              (_DWORD)v53,
              0,
              3,
              (unsigned int)"{}: Failed while processing primitive operations queue.",
              (__int64)v17);
            v57 = &v64;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v57);
          }
          v35 = 336;
          goto LABEL_87;
        }
        *a4 = 0;
        if ( v53 )
        {
          LOBYTE(v51) = 1;
          LogAdapter::Logger::LogNumObjects<char const *>(
            (_DWORD)v53,
            v51,
            1,
            (unsigned int)"{}: Primitive operations completed successfully.",
            (__int64)a9 + 48);
        }
LABEL_88:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v59);
        return (unsigned int)WindowsDirectory;
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v59);
    }
  }
  v64 = WindowsDirectory;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<char const *,unsigned long,unsigned long>(
      (_DWORD)LogAdapter::g_Logger,
      v19,
      v20,
      v21,
      (__int64)a9 + 48,
      (__int64)&v65,
      (__int64)&v66);
    v59 = (wchar_t *)&v64;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      1,
      (__int64)": {0}",
      (__int64)&v59);
  }
  SetProgressMessage(4, v18);
  if ( (int)FlushNtfsETWLog(v23, v22) >= 0 && LogAdapter::g_Logger )
  {
    LOBYTE(v24) = 1;
    LogAdapter::Logger::LogNumObjects<char const *>(
      (_DWORD)LogAdapter::g_Logger,
      v24,
      1,
      (unsigned int)"{}: Succesfully flushed NtfsLog.etl",
      (__int64)a9 + 48);
  }
  v25 = CbsSetCurrentTransaction(0);
  LogAdapter::TraceAtLevelIfFailed<long,>(1, v25, "Unable to set the current transaction");
  AutoTx::Rollback(a9);
  AutoTx::Close(a9);
  DoqReloadStates(0);
  v26 = (struct HDRIVERUPDATECONTEXT__ **)((char *)a9 + 32);
  if ( *((_QWORD *)a9 + 4) != a7 )
  {
    v27 = DoqCloseContext(*v26);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v27, "Unable to close driver update context");
    *v26 = 0;
  }
  v28 = (char *)a9 + 40;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    (char *)a9 + 40,
    0);
  if ( !vhDrupDll )
  {
    v61 = 0;
    goto LABEL_26;
  }
  v29 = DirectDriverOpenContext(0, (char *)a9 + 32);
  WindowsDirectory = v29;
  if ( v29 >= 0 )
  {
LABEL_26:
    Sleep(0x1388u);
    SetProgressMessage(0xFFFFFFFFLL, v58);
    UpdatePerfFromExecuteState(v58);
    goto LABEL_28;
  }
  v64 = v29;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed opening driver update context");
    v57 = &v64;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)&v57);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAF,
    (unsigned int)"onecore\\base\\cbs\\core\\cbscoreoperations.cpp",
    (const char *)(unsigned int)WindowsDirectory,
    (int)v56);
  return (unsigned int)WindowsDirectory;
}

```

## disassembly

```asm
0x1800f7290  mov     [rsp-8+arg_0], rbx
0x1800f7295  push    rbp
0x1800f7296  push    rsi
0x1800f7297  push    rdi
0x1800f7298  push    r12
0x1800f729a  push    r13
0x1800f729c  push    r14
0x1800f729e  push    r15
0x1800f72a0  lea     rbp, [rsp-7]
0x1800f72a5  sub     rsp, 0A0h
0x1800f72ac  mov     rax, cs:__security_cookie
0x1800f72b3  xor     rax, rsp
0x1800f72b6  mov     [rbp+37h+var_38], rax
0x1800f72ba  mov     rax, [rbp+37h+arg_20]
0x1800f72be  mov     r12, r9
0x1800f72c1  mov     rdi, [rbp+37h+arg_40]
0x1800f72c8  lea     r9, aMaxtransaction; "MaxTransactionRetries"
0x1800f72cf  mov     [rbp+37h+var_90], rax
0x1800f72d3  mov     esi, r8d
0x1800f72d6  mov     rax, [rbp+37h+arg_28]
0x1800f72da  mov     r13d, edx
0x1800f72dd  mov     [rbp+37h+var_70], rax
0x1800f72e1  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800f72e8  xor     eax, eax
0x1800f72ea  mov     [rbp+37h+var_78], r8d
0x1800f72ee  mov     ebx, eax
0x1800f72f0  mov     [rbp+37h+var_40], rax
0x1800f72f4  mov     [rbp+37h+var_4C], eax
0x1800f72f7  mov     r15d, ecx
0x1800f72fa  mov     [rbp+37h+var_44], eax
0x1800f72fd  mov     r8d, 1; unsigned int
0x1800f7303  lea     rax, [rbp+37h+var_48]
0x1800f7307  mov     [rbp+37h+var_48], 2
0x1800f730e  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800f7315  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x1800f731a  mov     r14d, 0FFFFh
0x1800f7320  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x1800f7325  test    eax, eax
0x1800f7327  jns     short loc_1800F7332
0x1800f7329  mov     [rbp+37h+var_48], 2
0x1800f7330  jmp     short loc_1800F7347
0x1800f7332  lea     r8, [rbp+37h+var_48]
0x1800f7336  mov     ecx, 1
0x1800f733b  lea     rdx, aMaxTransaction; "Max transactions retries set by registr"...
0x1800f7342  call    ??$TraceAtLevel@K@LogAdapter@@YAXW4LogLevel@0@QEBDAEBK@Z; LogAdapter::TraceAtLevel<ulong>(LogAdapter::LogLevel,char const * const,ulong const &)
0x1800f7347  test    esi, esi
0x1800f7349  jnz     short loc_1800F737B
0x1800f734b  test    r15d, r15d
0x1800f734e  jz      short loc_1800F736E
0x1800f7350  movzx   eax, byte ptr cs:?vdwCbsCoreMode@@3KA; ulong vdwCbsCoreMode
0x1800f7357  shr     eax, 1
0x1800f7359  and     eax, 1
0x1800f735c  neg     eax
0x1800f735e  sbb     r14d, r14d
0x1800f7361  and     r14d, 10001h
0x1800f7368  add     r14d, 2
0x1800f736c  jmp     short loc_1800F7371
0x1800f736e  xor     r14d, r14d
0x1800f7371  mov     edx, r14d
0x1800f7374  xor     ecx, ecx
0x1800f7376  call    SetPrimitiveExecutionContext
0x1800f737b  mov     edx, [rbp+37h+var_78]
0x1800f737e  lea     rcx, aShtd; "Shtd"
0x1800f7385  test    r15d, r15d
0x1800f7388  lea     rax, aStartup_0; "Startup"
0x1800f738f  lea     rsi, [rdi+30h]
0x1800f7393  cmovz   rax, rcx
0x1800f7397  lea     rcx, [rbp+37h+var_40]
0x1800f739b  mov     [rsi], rax
0x1800f739e  call    ?DoqCountDriverOperations@@YA_KPEA_KW4_CbsDoqDirection@@@Z; DoqCountDriverOperations(unsigned __int64 *,_CbsDoqDirection)
0x1800f73a3  xor     ecx, ecx
0x1800f73a5  test    rax, rax
0x1800f73a8  setnz   cl
0x1800f73ab  mov     [rbp+37h+var_74], ecx
0x1800f73ae  mov     r15d, 1
0x1800f73b4  and     r13d, 0FFFF3FFFh
0x1800f73bb  xor     edx, edx
0x1800f73bd  mov     ecx, r13d; unsigned int
0x1800f73c0  mov     [rbp+37h+var_88], r13d
0x1800f73c4  call    SetExecuteState
0x1800f73c9  mov     rax, [rdi+8]
0x1800f73cd  sub     rax, r15
0x1800f73d0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f73d4  ja      loc_1800F758B
0x1800f73da  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f73e1  mov     [rbp+37h+var_50], ebx
0x1800f73e4  test    rcx, rcx
0x1800f73e7  jz      short loc_1800F742F
0x1800f73e9  lea     rax, [rbp+37h+var_48]
0x1800f73ed  mov     [rsp+0D0h+var_A0], rax
0x1800f73f2  lea     rax, [rbp+37h+var_4C]
0x1800f73f6  mov     [rsp+0D0h+var_A8], rax
0x1800f73fb  mov     [rsp+0D0h+var_B0], rsi
0x1800f7400  call    ??$LogNumObjects@PEBDKK@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEBDAEBK4@Z; LogAdapter::Logger::LogNumObjects<char const *,ulong,ulong>(bool,LogAdapter::LogLevel,char const * const,char const * const &,ulong const &,ulong const &)
0x1800f7405  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f740c  lea     rax, [rbp+37h+var_50]
0x1800f7410  mov     [rbp+37h+var_80], rax
0x1800f7414  lea     r9, a0; ": {0}"
0x1800f741b  lea     rax, [rbp+37h+var_80]
0x1800f741f  mov     r8d, r15d
0x1800f7422  mov     dl, r15b
0x1800f7425  mov     [rsp+0D0h+var_B0], rax
0x1800f742a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f742f  xor     r8d, r8d
0x1800f7432  mov     edx, r13d
0x1800f7435  lea     ecx, [r8+4]
0x1800f7439  call    ?SetProgressMessage@@YAXW4CbsProgressMessageStage@@KK@Z; SetProgressMessage(CbsProgressMessageStage,ulong,ulong)
0x1800f743e  call    ?FlushNtfsETWLog@@YAJPEA_W0@Z; FlushNtfsETWLog(wchar_t *,wchar_t *)
0x1800f7443  test    eax, eax
0x1800f7445  js      short loc_1800F746A
0x1800f7447  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f744e  test    rcx, rcx
0x1800f7451  jz      short loc_1800F746A
0x1800f7453  lea     r9, aSuccesfullyFlu; "{}: Succesfully flushed NtfsLog.etl"
0x1800f745a  mov     [rsp+0D0h+var_B0], rsi
0x1800f745f  mov     r8d, r15d
0x1800f7462  mov     dl, r15b
0x1800f7465  call    ??$LogNumObjects@PEBD@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEBD@Z; LogAdapter::Logger::LogNumObjects<char const *>(bool,LogAdapter::LogLevel,char const * const,char const * const &)
0x1800f746a  xor     ecx, ecx; lpTlsValue
0x1800f746c  call    ?CbsSetCurrentTransaction@@YAJPEAX@Z; CbsSetCurrentTransaction(void *)
0x1800f7471  lea     r8, aUnableToSetThe; "Unable to set the current transaction"
0x1800f7478  mov     edx, eax
0x1800f747a  mov     ecx, r15d
0x1800f747d  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800f7482  mov     rcx, rdi; this
0x1800f7485  call    ?Rollback@AutoTx@@QEAAJXZ; AutoTx::Rollback(void)
0x1800f748a  mov     rcx, rdi; this
0x1800f748d  call    ?Close@AutoTx@@QEAAXXZ; AutoTx::Close(void)
0x1800f7492  xor     ecx, ecx; struct CCbsSession *
0x1800f7494  call    ?DoqReloadStates@@YAJPEAVCCbsSession@@@Z; DoqReloadStates(CCbsSession *)
0x1800f7499  mov     rax, [rbp+37h+arg_30]
0x1800f749d  lea     r15, [rdi+20h]
0x1800f74a1  cmp     [r15], rax
0x1800f74a4  jz      short loc_1800F74C8
0x1800f74a6  mov     rcx, [r15]; struct HDRIVERUPDATECONTEXT__ *
0x1800f74a9  call    ?DoqCloseContext@@YAJPEAUHDRIVERUPDATECONTEXT__@@@Z; DoqCloseContext(HDRIVERUPDATECONTEXT__ *)
0x1800f74ae  lea     r8, aUnableToCloseD; "Unable to close driver update context"
0x1800f74b5  mov     edx, eax
0x1800f74b7  mov     ecx, 1
0x1800f74bc  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800f74c1  mov     qword ptr [r15], 0
0x1800f74c8  lea     r13, [rdi+28h]
0x1800f74cc  xor     edx, edx
0x1800f74ce  mov     rcx, r13
0x1800f74d1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800f74d6  cmp     cs:?vhDrupDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * vhDrupDll
0x1800f74de  jz      short loc_1800F755B
0x1800f74e0  mov     rdx, r15
0x1800f74e3  xor     ecx, ecx
0x1800f74e5  call    DirectDriverOpenContext
0x1800f74ea  mov     ebx, eax
0x1800f74ec  test    eax, eax
0x1800f74ee  jns     short loc_1800F7562
0x1800f74f0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f74f7  mov     [rbp+37h+var_50], eax
0x1800f74fa  test    rcx, rcx
0x1800f74fd  jz      short loc_1800F753E
0x1800f74ff  mov     edi, 3
0x1800f7504  lea     r9, aFailedOpeningD_1; "Failed opening driver update context"
0x1800f750b  mov     r8d, edi
0x1800f750e  xor     edx, edx
0x1800f7510  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f7515  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f751c  lea     rax, [rbp+37h+var_50]
0x1800f7520  mov     [rbp+37h+var_90], rax
0x1800f7524  lea     r9, asc_1802EE7AC; ": {}"
0x1800f752b  lea     rax, [rbp+37h+var_90]
0x1800f752f  mov     r8d, edi
0x1800f7532  mov     dl, 1
0x1800f7534  mov     [rsp+0D0h+var_B0], rax; int
0x1800f7539  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f753e  mov     rcx, [rbp+3Fh]; this
0x1800f7542  lea     r8, aOnecoreBaseCbs_117; "onecore\\base\\cbs\\core\\cbscoreoperat"...
0x1800f7549  mov     r9d, ebx; char *
0x1800f754c  mov     edx, 0AFh; void *
0x1800f7551  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f7556  jmp     loc_1800F7B5C
0x1800f755b  mov     [rbp+37h+var_74], 0
0x1800f7562  mov     ecx, 1388h; dwMilliseconds
0x1800f7567  call    cs:__imp_Sleep
0x1800f756e  nop     dword ptr [rax+rax+00h]
0x1800f7573  mov     edx, [rbp+37h+var_88]
0x1800f7576  xor     r8d, r8d
0x1800f7579  or      ecx, 0FFFFFFFFh
0x1800f757c  call    ?SetProgressMessage@@YAXW4CbsProgressMessageStage@@KK@Z; SetProgressMessage(CbsProgressMessageStage,ulong,ulong)
0x1800f7581  mov     ecx, [rbp+37h+var_88]; unsigned int
0x1800f7584  call    ?UpdatePerfFromExecuteState@@YAXK@Z; UpdatePerfFromExecuteState(ulong)
0x1800f7589  jmp     short loc_1800F7593
0x1800f758b  lea     r13, [rdi+28h]
0x1800f758f  lea     r15, [rdi+20h]
0x1800f7593  mov     rax, [rbp+37h+var_70]
0x1800f7597  mov     dword ptr [r12], 0
0x1800f759f  mov     [rbp+37h+var_80], 0
0x1800f75a7  mov     dword ptr [rax], 1
0x1800f75ad  call    ?SafeGetActiveSession@@YAPEAVCCbsSession@@XZ; SafeGetActiveSession(void)
0x1800f75b2  mov     rcx, rax; this
0x1800f75b5  test    rax, rax
0x1800f75b8  jz      short loc_1800F762A
0x1800f75ba  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x1800f75bf  test    eax, eax
0x1800f75c1  jz      short loc_1800F762A
0x1800f75c3  lea     rdx, [rbp+37h+var_80]; wchar_t **
0x1800f75c7  call    ?GetOfflineWindowsDirectory@CCbsSession@@QEBAJPEAPEA_W@Z; CCbsSession::GetOfflineWindowsDirectory(wchar_t * *)
0x1800f75cc  mov     ebx, eax
0x1800f75ce  test    eax, eax
0x1800f75d0  jns     short loc_1800F763F
0x1800f75d2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f75d9  mov     [rbp+37h+var_50], eax
0x1800f75dc  test    rcx, rcx
0x1800f75df  jz      short loc_1800F7620
0x1800f75e1  mov     edi, 3
0x1800f75e6  lea     r9, aFailedToGetOff_3; "Failed to get offline Windows directory"
0x1800f75ed  mov     r8d, edi
0x1800f75f0  xor     edx, edx
0x1800f75f2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f75f7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f75fe  lea     rax, [rbp+37h+var_50]
0x1800f7602  mov     [rbp+37h+var_90], rax
0x1800f7606  lea     r9, asc_1802EE7AC; ": {}"
0x1800f760d  lea     rax, [rbp+37h+var_90]
0x1800f7611  mov     r8d, edi
0x1800f7614  mov     dl, 1
0x1800f7616  mov     [rsp+0D0h+var_B0], rax
0x1800f761b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f7620  mov     edx, 0CBh
0x1800f7625  jmp     loc_1800F7B40
0x1800f762a  xor     edx, edx
0x1800f762c  lea     rcx, [rbp+37h+var_80]
0x1800f7630  call    PathGetWindowsDirectory
0x1800f7635  mov     ebx, eax
0x1800f7637  test    eax, eax
0x1800f7639  js      loc_1800F7AED
0x1800f763f  mov     r9, [rbp+37h+var_80]; wchar_t *
0x1800f7643  lea     rdx, aCbsdriversandp; "CbsDriversAndPrimitives"
0x1800f764a  mov     rcx, rdi; this
0x1800f764d  call    ?Create@AutoCbsTransaction@@QEAAJQEB_W_NPEB_W@Z; AutoCbsTransaction::Create(wchar_t const * const,bool,wchar_t const *)
0x1800f7652  lea     r8, aUnableToCreate_1; "Unable to create transaction.  Continui"...
0x1800f7659  mov     edx, eax
0x1800f765b  mov     ecx, 1
0x1800f7660  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800f7665  xor     ecx, ecx; lpTlsValue
0x1800f7667  call    ?CbsSetCurrentTransaction@@YAJPEAX@Z; CbsSetCurrentTransaction(void *)
0x1800f766c  lea     r8, aUnableToSetThe; "Unable to set the current transaction"
0x1800f7673  mov     edx, eax
0x1800f7675  mov     ecx, 1
0x1800f767a  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800f767f  cmp     [rbp+37h+var_74], 0
0x1800f7683  jz      loc_1800F7813
0x1800f7689  mov     rax, [rbp+37h+var_40]
0x1800f768d  lea     rcx, [rax+rax*2]; unsigned __int64
0x1800f7691  call    ?InitializeDoqProgress@@YAX_K@Z; InitializeDoqProgress(unsigned __int64)
0x1800f7696  mov     edx, [rbp+37h+var_88]
0x1800f7699  mov     r8d, 2
0x1800f769f  or      ecx, 0FFFFFFFFh
0x1800f76a2  call    ?SetProgressMessage@@YAXW4CbsProgressMessageStage@@KK@Z; SetProgressMessage(CbsProgressMessageStage,ulong,ulong)
0x1800f76a7  cmp     [rbp+37h+var_40], 0
0x1800f76ac  jz      loc_1800F77D7
0x1800f76b2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f76b9  test    rcx, rcx
0x1800f76bc  jz      short loc_1800F76D1
0x1800f76be  lea     rax, [rbp+37h+var_40]
0x1800f76c2  mov     [rsp+0D0h+var_A8], rax
0x1800f76c7  mov     [rsp+0D0h+var_B0], rsi
0x1800f76cc  call    ??$LogNumObjects@PEBD_K@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEBDAEB_K@Z; LogAdapter::Logger::LogNumObjects<char const *,unsigned __int64>(bool,LogAdapter::LogLevel,char const * const,char const * const &,unsigned __int64 const &)
0x1800f76d1  mov     rcx, [rsi]
0x1800f76d4  lea     rdx, aShtd; "Shtd"
0x1800f76db  call    cs:__imp__o__stricmp
0x1800f76e2  nop     dword ptr [rax+rax+00h]
0x1800f76e7  test    eax, eax
0x1800f76e9  jnz     short loc_1800F770B
0x1800f76eb  movups  xmm0, cs:CbsNonCriticalDoqStartEvent
0x1800f76f2  mov     r8d, dword ptr [rbp+37h+var_40]
0x1800f76f6  lea     rdx, aShtdProcessing; "Shtd: Processing driver operations queu"...
0x1800f76fd  lea     rcx, [rbp+37h+var_60]
0x1800f7701  movdqu  [rbp+37h+var_60], xmm0
0x1800f7706  call    CbsGenericEventReport
0x1800f770b  mov     rax, [rdi+8]
0x1800f770f  mov     r9, [rdi+20h]
0x1800f7713  mov     r8, [rbp+37h+var_90]
0x1800f7717  mov     edx, [rbp+37h+var_78]
0x1800f771a  mov     [rsp+0D0h+var_B0], rax
0x1800f771f  call    ?DoqExecute@@YAJPEAVCCbsSession@@W4_CbsDoqDirection@@PEAHPEAUHDRIVERUPDATECONTEXT__@@PEAX@Z; DoqExecute(CCbsSession *,_CbsDoqDirection,int *,HDRIVERUPDATECONTEXT__ *,void *)
0x1800f7724  mov     ebx, eax
0x1800f7726  add     eax, 7FF8E5D4h
0x1800f772b  cmp     eax, 1
0x1800f772e  jbe     short loc_1800F7740
0x1800f7730  cmp     ebx, 80071A90h
0x1800f7736  jz      short loc_1800F7740
0x1800f7738  cmp     ebx, 80071A30h
0x1800f773e  jnz     short loc_1800F776E
0x1800f7740  mov     rax, [rdi+8]
0x1800f7744  dec     rax
0x1800f7747  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f774b  ja      short loc_1800F776E
0x1800f774d  mov     eax, [rbp+37h+var_4C]
0x1800f7750  mov     ecx, eax
0x1800f7752  inc     eax
0x1800f7754  mov     [rbp+37h+var_4C], eax
0x1800f7757  cmp     ecx, [rbp+37h+var_48]
0x1800f775a  jnb     short loc_1800F776E
  ... truncated ...
```
