# CPMPServerProxy::StartupPMPProcess(ushort const *,ulong,_GUID const &)

- ea: `0x180187f24`
- end: `0x18018879c`
- name: `?StartupPMPProcess@CPMPServerProxy@@IEAAJPEBGKAEBU_GUID@@@Z`
- size: `2168`
- prototype: `__int64 __fastcall(CPMPServerProxy *__hidden this, const unsigned __int16 *, unsigned int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180186e94`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x18006b388`
- `0x180093088`
- `0x1800ce134`
- `0x1800cf5c8`
- `0x1800ec0e0`
- `0x18012add8`
- `0x18015c3c8`
- `0x180187f24`
- `0x1801887a4`
- `0x1801887f4`
- `0x18018a3a0`
- `0x180258480`
- `0x1802592a0`
- `0x180285630`
- `0x18029aec0`
- `0x18029c618`
- `0x18029cfc0`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801884fe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801884fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180188513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018857a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801885d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180188676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180188513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018857a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801885d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180188676`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180188666`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180188666`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18018800c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180188556`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18018800c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180188556`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801882ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801882ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018872e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018872e`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180188025`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180188025`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18018871e`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18018871e`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x1801885bc`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x1801885bc`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18018856a`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18018856a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180188744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180188744`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1801881af`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1801881af`
- `MFPlat!MFGetPlatformVersion` at `0x180188316`
- `MFPlat!MFGetPlatformVersion` at `0x180188316`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801881d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180188380`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801881d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180188380`

## pseudocode

```c
__int64 __fastcall CPMPServerProxy::StartupPMPProcess(
        CPMPServerProxy *this,
        const unsigned __int16 *a2,
        char a3,
        const struct _GUID *a4)
{
  int v8; // r13d
  DWORD dwCreationFlags; // r15d
  HANDLE CurrentProcess; // rax
  int v11; // ebx
  CPMPServerProxy *v12; // rcx
  int appended; // ebx
  unsigned int v14; // esi
  unsigned __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned __int64 v20; // rcx
  __int64 v21; // r9
  int v22; // eax
  DWORD CurrentProcessId; // eax
  unsigned int v24; // eax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  unsigned __int64 v30; // rcx
  const WCHAR *v31; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v34; // rax
  signed int v35; // eax
  __int64 v36; // rdx
  signed int v37; // eax
  WCHAR *v38; // rax
  signed int v39; // eax
  DWORD dwProcessId; // ecx
  BOOL v42; // [rsp+50h] [rbp-B0h]
  int v43; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v44[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v45; // [rsp+64h] [rbp-9Ch] BYREF
  _WORD v46[2]; // [rsp+68h] [rbp-98h] BYREF
  WINBOOL Wow64Process; // [rsp+6Ch] [rbp-94h] BYREF
  LPOLESTR lpsz; // [rsp+70h] [rbp-90h] BYREF
  PVOID OldValue; // [rsp+78h] [rbp-88h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+110h] [rbp+10h] BYREF
  int v53; // [rsp+118h] [rbp+18h]
  int v54; // [rsp+11Ch] [rbp+1Ch]
  char *v55; // [rsp+120h] [rbp+20h]
  char v56; // [rsp+128h] [rbp+28h] BYREF
  __int64 v57; // [rsp+230h] [rbp+130h] BYREF
  int v58; // [rsp+238h] [rbp+138h]
  int v59; // [rsp+23Ch] [rbp+13Ch]
  char *v60; // [rsp+240h] [rbp+140h]
  char v61; // [rsp+248h] [rbp+148h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v44, "CPMPServerProxy::StartupPMPProcess", 1528);
  v8 = 0;
  v53 = 0;
  v52 = v52 & 0xFFFFFFF8 | 1;
  v54 = 128;
  v55 = &v56;
  memset_0(&StartupInfo, 0, (unsigned int)(HIDWORD(v52) + 104));
  v59 = 128;
  dwCreationFlags = 0;
  lpsz = 0;
  v58 = 0;
  v57 = v57 & 0xFFFFFFF8 | 1;
  v60 = &v61;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  OldValue = 0;
  Wow64Process = 0;
  v42 = 0;
  v45 = 0;
  v46[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !(unsigned int)IsWow64Process2(CurrentProcess, &v45, v46)
    || v45 != 332 && v45 != -31132
    || (v11 = 1, v46[0] != 0xAA64) )
  {
    v11 = 0;
  }
  if ( !(unsigned int)MFIsThirdPartyCodeSuppressed() && !v11 )
    v8 = 1;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( *((_DWORD *)this + 26) )
  {
    appended = 0;
    if ( (unsigned __int8)byte_1803CECE9 >= 4u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 97, &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids, this);
    goto LABEL_111;
  }
  if ( (a3 & 1) != 0 )
  {
    v14 = 0;
  }
  else
  {
    v14 = 0;
    if ( !(unsigned int)CPMPServerProxy::ProtectedProcessDisabledInRegistry(v12) )
      dwCreationFlags = 0x40000;
  }
  v43 = -1;
  if ( (int)UIntPtrToLong(0xAu, &v43) >= 0 )
  {
    CMFBaseStringT<unsigned short>::_Append(&v52, L"mfpmp.exe ", (unsigned int)v43);
    appended = HIDWORD(v52);
  }
  else
  {
    appended = -2147024785;
    HIDWORD(v52) = -2147024785;
  }
  v43 = -1;
  if ( a2 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    if ( (int)UIntPtrToLong(v15, &v43) < 0 )
    {
      appended = -2147024785;
      HIDWORD(v52) = -2147024785;
      goto LABEL_27;
    }
    CMFBaseStringT<unsigned short>::_Append(&v52, a2, (unsigned int)v43);
    appended = HIDWORD(v52);
  }
  if ( appended < 0 )
  {
LABEL_27:
    if ( g_wppLevels )
    {
      v16 = 98;
LABEL_29:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
        this,
        appended);
      goto LABEL_110;
    }
    goto LABEL_110;
  }
  appended = StringFromCLSID(a4, &lpsz);
  if ( appended < 0 )
  {
    v17 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != appended )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CPMPServerProxy::StartupPMPProcess", 1581, appended);
    }
    if ( !g_wppLevels )
      goto LABEL_110;
    v16 = 99;
    goto LABEL_29;
  }
  CMFBaseStringT<unsigned short>::AppendChar(&v52, 32);
  v43 = -1;
  if ( lpsz )
  {
    v20 = -1;
    do
      ++v20;
    while ( lpsz[v20] );
    if ( (int)UIntPtrToLong(v20, &v43) < 0 )
    {
      v22 = -2147024785;
      HIDWORD(v52) = -2147024785;
LABEL_48:
      appended = v22;
      if ( v22 < 0 && g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids, this, v22);
      goto LABEL_110;
    }
    CMFBaseStringT<unsigned short>::_Append(&v52, v21, (unsigned int)v43);
  }
  v22 = HIDWORD(v52);
  if ( v52 < 0 )
    goto LABEL_48;
  CMFBaseStringT<unsigned short>::AppendChar(&v52, 32);
  CurrentProcessId = GetCurrentProcessId();
  CMFBaseStringT<unsigned short>::AppendUInt(&v52, CurrentProcessId, 10);
  CMFBaseStringT<unsigned short>::AppendChar(&v52, 32);
  v24 = MFGetPlatformVersion();
  CMFBaseStringT<unsigned short>::AppendUInt(&v52, v24, 10);
  CMFBaseStringT<unsigned short>::AppendChar(&v52, 32);
  while ( v14 < 2 )
  {
    appended = CPMPServerProxy::AppendEnvironmentVariable(this, off_180357BA8[v14], &v52);
    if ( appended < 0 )
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v25 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
        if ( *((_DWORD *)v27 + 499) != appended )
          CallStackContext::TraceFailure(v27, "CPMPServerProxy::StartupPMPProcess", 1610, appended);
      }
      if ( g_wppLevels )
      {
        v28 = 101;
        goto LABEL_65;
      }
      goto LABEL_66;
    }
    ++v14;
  }
  if ( (unsigned __int8)byte_1803CECE9 >= 8u )
  {
    v29 = CMFBaseStringT<unsigned short>::PContents(&v52);
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      102,
      (unsigned int)&WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
      (_DWORD)this,
      v29);
  }
  v43 = -1;
  if ( a2 )
  {
    v30 = -1;
    do
      ++v30;
    while ( a2[v30] );
    if ( (int)UIntPtrToLong(v30, &v43) >= 0 )
      CMFBaseStringT<unsigned short>::_Append(&v57, a2, (unsigned int)v43);
    else
      HIDWORD(v57) = -2147024785;
  }
  v43 = -1;
  if ( (int)UIntPtrToLong(0xAu, &v43) >= 0 )
    CMFBaseStringT<unsigned short>::_Append(&v57, L"/TermEvent", (unsigned int)v43);
  else
    HIDWORD(v57) = -2147024785;
  v31 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(&v57);
  EventW = CreateEventW(0, 1, 0, v31);
  *((_QWORD *)this + 12) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    appended = LastError;
    if ( LastError > 0 )
      appended = (unsigned __int16)LastError | 0x80070000;
    if ( appended < 0 && g_wppLevels )
    {
      v28 = 103;
LABEL_65:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v28,
        &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
        this,
        appended);
    }
LABEL_66:
    dwCreationFlags = 0;
    goto LABEL_111;
  }
  if ( !v8 )
    goto LABEL_99;
  v34 = GetCurrentProcess();
  if ( !IsWow64Process(v34, &Wow64Process) )
  {
    v35 = GetLastError();
    appended = v35;
    if ( v35 > 0 )
      appended = (unsigned __int16)v35 | 0x80070000;
    if ( appended < 0 && g_wppLevels )
    {
      v36 = 104;
LABEL_98:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v36,
        &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
        this,
        appended);
      goto LABEL_114;
    }
    goto LABEL_114;
  }
  if ( !Wow64Process || (v42 = Wow64DisableWow64FsRedirection(&OldValue)) )
  {
LABEL_99:
    StartupInfo.dwFlags |= 0x80u;
    v38 = (WCHAR *)CMFBaseStringT<unsigned short>::PContents(&v52);
    if ( CreateProcessW(0, v38, 0, 0, 0, dwCreationFlags, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      dwProcessId = ProcessInformation.dwProcessId;
      *((_QWORD *)this + 10) = ProcessInformation.hProcess;
      *((_DWORD *)this + 19) = dwProcessId;
      if ( (unsigned __int8)byte_1803CECE9 >= 8u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          107,
          &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
          this,
          dwProcessId);
      if ( (Microsoft_Windows_MFEnableBits & 0x10) != 0 )
        McTemplateU0q_EventWriteTransfer(
          &Microsoft_Windows_MF_Context,
          &PMPServerProxy_LaunchedProcess,
          *((unsigned int *)this + 19));
      CPMPServerProxy::TryLaunchPEDbg(this);
      goto LABEL_110;
    }
    v39 = GetLastError();
    appended = v39;
    if ( v39 > 0 )
      appended = (unsigned __int16)v39 | 0x80070000;
    if ( appended < 0 && g_wppLevels )
    {
      v16 = 106;
      goto LABEL_29;
    }
LABEL_110:
    dwCreationFlags = v42;
LABEL_111:
    if ( v8 && dwCreationFlags )
      Wow64RevertWow64FsRedirection(OldValue);
    goto LABEL_114;
  }
  v37 = GetLastError();
  appended = v37;
  if ( v37 > 0 )
    appended = (unsigned __int16)v37 | 0x80070000;
  if ( appended < 0 && g_wppLevels )
  {
    v36 = 105;
    goto LABEL_98;
  }
LABEL_114:
  CloseHandle(ProcessInformation.hThread);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  CMFBaseStringT<char>::~CMFBaseStringT<char>(&v57);
  CMFBaseStringT<char>::~CMFBaseStringT<char>(&v52);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180187f24  mov     [rsp-8+arg_10], rbx
0x180187f29  push    rbp
0x180187f2a  push    rsi
0x180187f2b  push    rdi
0x180187f2c  push    r12
0x180187f2e  push    r13
0x180187f30  push    r14
0x180187f32  push    r15
0x180187f34  lea     rbp, [rsp-260h]
0x180187f3c  sub     rsp, 360h
0x180187f43  mov     rax, cs:__security_cookie
0x180187f4a  xor     rax, rsp
0x180187f4d  mov     [rbp+290h+var_40], rax
0x180187f54  mov     esi, r8d
0x180187f57  mov     r14, rdx
0x180187f5a  mov     rdi, rcx
0x180187f5d  lea     rdx, aCpmpserverprox_8; "CPMPServerProxy::StartupPMPProcess"
0x180187f64  mov     r8d, 5F8h; int
0x180187f6a  lea     rcx, [rsp+390h+var_330]; this
0x180187f6f  mov     r12, r9
0x180187f72  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180187f77  mov     eax, [rbp+290h+var_280]
0x180187f7a  lea     rcx, [rbp+290h+StartupInfo]; void *
0x180187f7e  xor     r13d, r13d
0x180187f81  mov     ebx, 0FFFFFFF9h
0x180187f86  and     eax, ebx
0x180187f88  mov     [rbp+290h+var_27C], r13
0x180187f8c  or      eax, 1
0x180187f8f  mov     r15d, 80h
0x180187f95  mov     [rbp+290h+var_280], eax
0x180187f98  xor     edx, edx; Val
0x180187f9a  lea     rax, [rbp+290h+var_268]
0x180187f9e  mov     [rbp+290h+var_274], r15d
0x180187fa2  lea     r8d, [r13+68h]; Size
0x180187fa6  mov     [rbp+290h+var_270], rax
0x180187faa  call    memset_0
0x180187faf  xor     eax, eax
0x180187fb1  mov     [rbp+290h+var_154], r15d
0x180187fb8  mov     qword ptr [rbp+290h+ProcessInformation.dwProcessId], rax
0x180187fbc  xorps   xmm0, xmm0
0x180187fbf  mov     eax, [rbp+290h+var_160]
0x180187fc5  mov     r15d, r13d
0x180187fc8  and     eax, ebx
0x180187fca  mov     [rsp+390h+lpsz], r13
0x180187fcf  or      eax, 1
0x180187fd2  mov     [rbp+290h+var_15C], r13
0x180187fd9  mov     [rbp+290h+var_160], eax
0x180187fdf  lea     rax, [rbp+290h+var_148]
0x180187fe6  mov     [rbp+290h+var_150], rax
0x180187fed  movups  xmmword ptr [rbp+290h+ProcessInformation.hProcess], xmm0
0x180187ff1  mov     [rsp+390h+OldValue], r13
0x180187ff6  mov     [rsp+390h+Wow64Process], r13d
0x180187ffb  mov     [rsp+390h+var_340], r13d
0x180188000  mov     [rsp+390h+var_32C], r13w
0x180188006  mov     [rsp+390h+var_328], r13w
0x18018800c  call    cs:__imp_GetCurrentProcess
0x180188013  nop     dword ptr [rax+rax+00h]
0x180188018  mov     rcx, rax
0x18018801b  lea     r8, [rsp+390h+var_328]
0x180188020  lea     rdx, [rsp+390h+var_32C]
0x180188025  call    cs:__imp_IsWow64Process2
0x18018802c  nop     dword ptr [rax+rax+00h]
0x180188031  test    eax, eax
0x180188033  jz      short loc_18018805E
0x180188035  mov     eax, 14Ch
0x18018803a  cmp     [rsp+390h+var_32C], ax
0x18018803f  jz      short loc_18018804D
0x180188041  mov     eax, 8664h
0x180188046  cmp     [rsp+390h+var_32C], ax
0x18018804b  jnz     short loc_18018805E
0x18018804d  mov     eax, 0AA64h
0x180188052  mov     ebx, 1
0x180188057  cmp     [rsp+390h+var_328], ax
0x18018805c  jz      short loc_180188061
0x18018805e  mov     ebx, r13d
0x180188061  call    ?MFIsThirdPartyCodeSuppressed@@YAHXZ; MFIsThirdPartyCodeSuppressed(void)
0x180188066  test    eax, eax
0x180188068  jnz     short loc_180188072
0x18018806a  test    ebx, ebx
0x18018806c  jnz     short loc_180188072
0x18018806e  lea     r13d, [rax+1]
0x180188072  xor     edx, edx; Val
0x180188074  lea     rcx, [rbp+290h+StartupInfo]; void *
0x180188078  lea     r8d, [rdx+68h]; Size
0x18018807c  call    memset_0
0x180188081  xor     eax, eax
0x180188083  xorps   xmm0, xmm0
0x180188086  movups  xmmword ptr [rbp+290h+ProcessInformation.hProcess], xmm0
0x18018808a  mov     qword ptr [rbp+290h+ProcessInformation.dwProcessId], rax
0x18018808e  cmp     [rdi+68h], eax
0x180188091  jz      short loc_1801880C6
0x180188093  xor     esi, esi
0x180188095  mov     ebx, esi
0x180188097  cmp     cs:byte_1803CECE9, 4
0x18018809e  jb      loc_18018870F
0x1801880a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801880ab  lea     edx, [rax+61h]
0x1801880ae  mov     r9, rdi
0x1801880b1  lea     r8, WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids
0x1801880b8  mov     rcx, [rcx+38h]
0x1801880bc  call    WPP_SF_q
0x1801880c1  jmp     loc_18018870F
0x1801880c6  test    sil, 1
0x1801880ca  jnz     short loc_1801880E0
0x1801880cc  call    ?ProtectedProcessDisabledInRegistry@CPMPServerProxy@@IEAAHXZ; CPMPServerProxy::ProtectedProcessDisabledInRegistry(void)
0x1801880d1  xor     esi, esi
0x1801880d3  mov     ecx, 40000h
0x1801880d8  test    eax, eax
0x1801880da  cmovz   r15d, ecx
0x1801880de  jmp     short loc_1801880E2
0x1801880e0  xor     esi, esi
0x1801880e2  lea     rdx, [rsp+390h+var_338]; int *
0x1801880e7  mov     [rsp+390h+var_338], 0FFFFFFFFh
0x1801880ef  mov     ecx, 0Ah; unsigned __int64
0x1801880f4  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x1801880f9  test    eax, eax
0x1801880fb  jns     short loc_180188107
0x1801880fd  mov     ebx, 8007006Fh
0x180188102  mov     dword ptr [rbp+290h+var_27C], ebx
0x180188105  jmp     short loc_18018811F
0x180188107  mov     r8d, [rsp+390h+var_338]
0x18018810c  lea     rdx, aMfpmpExe; "mfpmp.exe "
0x180188113  lea     rcx, [rbp+290h+var_280]
0x180188117  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x18018811c  mov     ebx, dword ptr [rbp+290h+var_27C]
0x18018811f  mov     [rsp+390h+var_338], 0FFFFFFFFh
0x180188127  test    r14, r14
0x18018812a  jz      short loc_180188166
0x18018812c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180188130  inc     rcx; unsigned __int64
0x180188133  cmp     [r14+rcx*2], si
0x180188138  jnz     short loc_180188130
0x18018813a  lea     rdx, [rsp+390h+var_338]; int *
0x18018813f  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x180188144  test    eax, eax
0x180188146  jns     short loc_180188152
0x180188148  mov     ebx, 8007006Fh
0x18018814d  mov     dword ptr [rbp+290h+var_27C], ebx
0x180188150  jmp     short loc_18018816A
0x180188152  mov     r8d, [rsp+390h+var_338]
0x180188157  lea     rcx, [rbp+290h+var_280]
0x18018815b  mov     rdx, r14
0x18018815e  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x180188163  mov     ebx, dword ptr [rbp+290h+var_27C]
0x180188166  test    ebx, ebx
0x180188168  jns     short loc_1801881A7
0x18018816a  test    ebx, ebx
0x18018816c  jns     loc_18018870A
0x180188172  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180188179  jb      loc_18018870A
0x18018817f  mov     edx, 62h ; 'b'
0x180188184  mov     [rsp+390h+bInheritHandles], ebx
0x180188188  mov     rcx, cs:WPP_GLOBAL_Control
0x18018818f  lea     r8, WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids
0x180188196  mov     r9, rdi
0x180188199  mov     rcx, [rcx+10h]
0x18018819d  call    WPP_SF_qD
0x1801881a2  jmp     loc_18018870A
0x1801881a7  lea     rdx, [rsp+390h+lpsz]; lplpsz
0x1801881ac  mov     rcx, r12; rclsid
0x1801881af  call    cs:__imp_StringFromCLSID
0x1801881b6  nop     dword ptr [rax+rax+00h]
0x1801881bb  mov     ebx, eax
0x1801881bd  test    eax, eax
0x1801881bf  jns     loc_18018825B
0x1801881c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801881cc  test    rcx, rcx
0x1801881cf  jnz     short loc_180188219
0x1801881d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801881d8  nop     dword ptr [rax+rax+00h]
0x1801881dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801881e4  mov     rcx, rax
0x1801881e7  test    rax, rax
0x1801881ea  jz      short loc_18018820B
0x1801881ec  mov     rax, [rax]
0x1801881ef  mov     edx, 7F0h
0x1801881f4  mov     rax, [rax+8]
0x1801881f8  call    cs:__guard_dispatch_icall_fptr
0x1801881fe  test    eax, eax
0x180188200  jz      short loc_18018820B
0x180188202  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180188209  jmp     short loc_180188219
0x18018820b  lea     rcx, qword_1803CE250; this
0x180188212  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180188219  cmp     [rcx+8], sil
0x18018821d  jz      short loc_180188244
0x18018821f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180188224  cmp     [rax+7CCh], ebx
0x18018822a  jz      short loc_180188244
0x18018822c  mov     r9d, ebx; int
0x18018822f  lea     rdx, aCpmpserverprox_8; "CPMPServerProxy::StartupPMPProcess"
0x180188236  mov     r8d, 62Dh; int
0x18018823c  mov     rcx, rax; this
0x18018823f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180188244  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18018824b  jb      loc_18018870A
0x180188251  mov     edx, 63h ; 'c'
0x180188256  jmp     loc_180188184
0x18018825b  mov     r12d, 20h ; ' '
0x180188261  lea     rcx, [rbp+290h+var_280]
0x180188265  mov     edx, r12d
0x180188268  call    ?AppendChar@?$CMFBaseStringT@G@@QEAAJG@Z; CMFBaseStringT<ushort>::AppendChar(ushort)
0x18018826d  mov     r9, [rsp+390h+lpsz]
0x180188272  or      rax, 0FFFFFFFFFFFFFFFFh
0x180188276  mov     [rsp+390h+var_338], eax
0x18018827a  test    r9, r9
0x18018827d  jz      short loc_1801882B5
0x18018827f  mov     rcx, rax
0x180188282  inc     rcx; unsigned __int64
0x180188285  cmp     [r9+rcx*2], si
0x18018828a  jnz     short loc_180188282
0x18018828c  lea     rdx, [rsp+390h+var_338]; int *
0x180188291  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x180188296  test    eax, eax
0x180188298  jns     short loc_1801882A4
0x18018829a  mov     eax, 8007006Fh
0x18018829f  mov     dword ptr [rbp+290h+var_27C], eax
0x1801882a2  jmp     short loc_1801882BC
0x1801882a4  mov     r8d, [rsp+390h+var_338]
0x1801882a9  lea     rcx, [rbp+290h+var_280]
0x1801882ad  mov     rdx, r9
0x1801882b0  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x1801882b5  mov     eax, dword ptr [rbp+290h+var_27C]
0x1801882b8  test    eax, eax
0x1801882ba  jns     short loc_1801882E1
0x1801882bc  mov     ebx, eax
0x1801882be  test    eax, eax
0x1801882c0  jns     loc_18018870A
0x1801882c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801882cd  jb      loc_18018870A
0x1801882d3  mov     edx, 64h ; 'd'
0x1801882d8  mov     [rsp+390h+bInheritHandles], eax
0x1801882dc  jmp     loc_180188188
0x1801882e1  mov     edx, r12d
0x1801882e4  lea     rcx, [rbp+290h+var_280]
0x1801882e8  call    ?AppendChar@?$CMFBaseStringT@G@@QEAAJG@Z; CMFBaseStringT<ushort>::AppendChar(ushort)
0x1801882ed  call    cs:__imp_GetCurrentProcessId
0x1801882f4  nop     dword ptr [rax+rax+00h]
0x1801882f9  mov     r8d, 0Ah
0x1801882ff  lea     rcx, [rbp+290h+var_280]
0x180188303  mov     edx, eax
0x180188305  call    ?AppendUInt@?$CMFBaseStringT@G@@QEAAJIH@Z; CMFBaseStringT<ushort>::AppendUInt(uint,int)
0x18018830a  mov     edx, r12d
0x18018830d  lea     rcx, [rbp+290h+var_280]
0x180188311  call    ?AppendChar@?$CMFBaseStringT@G@@QEAAJG@Z; CMFBaseStringT<ushort>::AppendChar(ushort)
0x180188316  call    cs:__imp_?MFGetPlatformVersion@@YAKXZ; MFGetPlatformVersion(void)
0x18018831d  nop     dword ptr [rax+rax+00h]
0x180188322  mov     r8d, 0Ah
0x180188328  lea     rcx, [rbp+290h+var_280]
0x18018832c  mov     edx, eax
0x18018832e  call    ?AppendUInt@?$CMFBaseStringT@G@@QEAAJIH@Z; CMFBaseStringT<ushort>::AppendUInt(uint,int)
0x180188333  mov     edx, r12d
0x180188336  lea     rcx, [rbp+290h+var_280]
0x18018833a  call    ?AppendChar@?$CMFBaseStringT@G@@QEAAJG@Z; CMFBaseStringT<ushort>::AppendChar(ushort)
0x18018833f  mov     r12d, 1
0x180188345  cmp     esi, 2
0x180188348  jnb     loc_180188427
0x18018834e  lea     rax, off_180357BA8; "TEMP"
0x180188355  mov     edx, esi
0x180188357  lea     r8, [rbp+290h+var_280]
0x18018835b  mov     rcx, rdi
0x18018835e  mov     rdx, [rax+rdx*8]
0x180188362  call    ?AppendEnvironmentVariable@CPMPServerProxy@@IEAAJPEBGAEAV?$CMFStackStringT@G$0IA@@@@Z; CPMPServerProxy::AppendEnvironmentVariable(ushort const *,CMFStackStringT<ushort,128> &)
0x180188367  mov     ebx, eax
0x180188369  test    eax, eax
0x18018836b  js      short loc_180188372
0x18018836d  add     esi, r12d
0x180188370  jmp     short loc_180188345
0x180188372  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180188379  xor     esi, esi
0x18018837b  test    rcx, rcx
0x18018837e  jnz     short loc_1801883C8
0x180188380  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180188387  nop     dword ptr [rax+rax+00h]
0x18018838c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180188393  mov     rcx, rax
0x180188396  test    rax, rax
0x180188399  jz      short loc_1801883BA
0x18018839b  mov     rax, [rax]
0x18018839e  mov     edx, 7F0h
0x1801883a3  mov     rax, [rax+8]
0x1801883a7  call    cs:__guard_dispatch_icall_fptr
0x1801883ad  test    eax, eax
0x1801883af  jz      short loc_1801883BA
0x1801883b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801883b8  jmp     short loc_1801883C8
0x1801883ba  lea     rcx, qword_1803CE250; this
0x1801883c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801883c8  cmp     [rcx+8], sil
0x1801883cc  jz      short loc_1801883F3
0x1801883ce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801883d3  cmp     [rax+7CCh], ebx
0x1801883d9  jz      short loc_1801883F3
0x1801883db  mov     r9d, ebx; int
0x1801883de  lea     rdx, aCpmpserverprox_8; "CPMPServerProxy::StartupPMPProcess"
0x1801883e5  mov     r8d, 64Ah; int
0x1801883eb  mov     rcx, rax; this
0x1801883ee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801883f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1801883fa  jb      short loc_18018841F
  ... truncated ...
```
