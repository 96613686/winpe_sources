# LaunchProcessInSession(ushort const *,ushort const *,ushort const *,ulong,ushort const *,ulong,int *)

- ea: `0x140012124`
- end: `0x140012f7b`
- name: `?LaunchProcessInSession@@YAJPEBG00K0KPEAH@Z`
- size: `3671`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, ULONG, const unsigned __int16 *, DWORD dwMilliseconds, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140013894`

## callees

- `0x140002116`
- `0x140002148`
- `0x1400050d0`
- `0x1400076c8`
- `0x140008434`
- `0x14000ac50`
- `0x14000f67c`
- `0x140011be4`
- `0x140012124`
- `0x1400135b8`
- `0x140016bb4`
- `0x14001d4ac`

## import_xrefs

- `ADVAPI32!DuplicateTokenEx` at `0x1400122a0`
- `ADVAPI32!DuplicateTokenEx` at `0x1400122a0`
- `ADVAPI32!OpenProcessToken` at `0x140012303`
- `ADVAPI32!OpenProcessToken` at `0x140012303`
- `KERNEL32!CloseHandle` at `0x1400122d9`
- `KERNEL32!CloseHandle` at `0x1400125a6`
- `KERNEL32!CloseHandle` at `0x140012d93`
- `KERNEL32!CloseHandle` at `0x140012daf`
- `KERNEL32!CloseHandle` at `0x140012e79`
- `KERNEL32!CloseHandle` at `0x140012ef8`
- `KERNEL32!CloseHandle` at `0x140012f0d`
- `KERNEL32!CloseHandle` at `0x140012f24`
- `KERNEL32!CloseHandle` at `0x140012f3e`
- `KERNEL32!CloseHandle` at `0x140012f57`
- `KERNEL32!CloseHandle` at `0x1400122d9`
- `KERNEL32!CloseHandle` at `0x1400125a6`
- `KERNEL32!CloseHandle` at `0x140012d93`
- `KERNEL32!CloseHandle` at `0x140012daf`
- `KERNEL32!CloseHandle` at `0x140012e79`
- `KERNEL32!CloseHandle` at `0x140012ef8`
- `KERNEL32!CloseHandle` at `0x140012f0d`
- `KERNEL32!CloseHandle` at `0x140012f24`
- `KERNEL32!CloseHandle` at `0x140012f3e`
- `KERNEL32!CloseHandle` at `0x140012f57`
- `KERNEL32!CreateProcessW` at `0x140012570`
- `KERNEL32!CreateProcessW` at `0x140012570`
- `KERNEL32!GetExitCodeProcess` at `0x140012791`
- `KERNEL32!GetExitCodeProcess` at `0x140012791`
- `KERNEL32!HeapFree` at `0x14001284f`
- `KERNEL32!HeapFree` at `0x140012888`
- `KERNEL32!HeapFree` at `0x140012de0`
- `KERNEL32!HeapFree` at `0x140012e09`
- `KERNEL32!HeapFree` at `0x140012e2f`
- `KERNEL32!HeapFree` at `0x140012e5d`
- `KERNEL32!HeapFree` at `0x140012ea7`
- `KERNEL32!HeapFree` at `0x140012edc`
- `KERNEL32!HeapFree` at `0x14001284f`
- `KERNEL32!HeapFree` at `0x140012888`
- `KERNEL32!HeapFree` at `0x140012de0`
- `KERNEL32!HeapFree` at `0x140012e09`
- `KERNEL32!HeapFree` at `0x140012e2f`
- `KERNEL32!HeapFree` at `0x140012e5d`
- `KERNEL32!HeapFree` at `0x140012ea7`
- `KERNEL32!HeapFree` at `0x140012edc`
- `KERNEL32!HeapAlloc` at `0x140012633`
- `KERNEL32!HeapAlloc` at `0x140012688`
- `KERNEL32!HeapAlloc` at `0x1400127bc`
- `KERNEL32!HeapAlloc` at `0x140012633`
- `KERNEL32!HeapAlloc` at `0x140012688`
- `KERNEL32!HeapAlloc` at `0x1400127bc`
- `KERNEL32!GetProcessHeap` at `0x14001261e`
- `KERNEL32!GetProcessHeap` at `0x140012672`
- `KERNEL32!GetProcessHeap` at `0x1400127a5`
- `KERNEL32!GetProcessHeap` at `0x14001283b`
- `KERNEL32!GetProcessHeap` at `0x140012874`
- `KERNEL32!GetProcessHeap` at `0x140012dcc`
- `KERNEL32!GetProcessHeap` at `0x140012df5`
- `KERNEL32!GetProcessHeap` at `0x140012e1b`
- `KERNEL32!GetProcessHeap` at `0x140012e49`
- `KERNEL32!GetProcessHeap` at `0x140012e93`
- `KERNEL32!GetProcessHeap` at `0x140012ec8`
- `KERNEL32!GetProcessHeap` at `0x14001261e`
- `KERNEL32!GetProcessHeap` at `0x140012672`
- `KERNEL32!GetProcessHeap` at `0x1400127a5`
- `KERNEL32!GetProcessHeap` at `0x14001283b`
- `KERNEL32!GetProcessHeap` at `0x140012874`
- `KERNEL32!GetProcessHeap` at `0x140012dcc`
- `KERNEL32!GetProcessHeap` at `0x140012df5`
- `KERNEL32!GetProcessHeap` at `0x140012e1b`
- `KERNEL32!GetProcessHeap` at `0x140012e49`
- `KERNEL32!GetProcessHeap` at `0x140012e93`
- `KERNEL32!GetProcessHeap` at `0x140012ec8`
- `KERNEL32!GetLastError` at `0x140012238`
- `KERNEL32!GetLastError` at `0x140012a37`
- `KERNEL32!GetLastError` at `0x140012b44`
- `KERNEL32!GetLastError` at `0x140012c7f`
- `KERNEL32!GetLastError` at `0x140012238`
- `KERNEL32!GetLastError` at `0x140012a37`
- `KERNEL32!GetLastError` at `0x140012b44`
- `KERNEL32!GetLastError` at `0x140012c7f`
- `KERNEL32!ReadFile` at `0x1400128b2`
- `KERNEL32!ReadFile` at `0x1400128b2`
- `KERNEL32!OpenEventW` at `0x1400125f4`
- `KERNEL32!OpenEventW` at `0x1400125f4`
- `KERNEL32!WaitForSingleObject` at `0x140012ae0`
- `KERNEL32!WaitForSingleObject` at `0x140012c1b`
- `KERNEL32!WaitForSingleObject` at `0x140012ae0`
- `KERNEL32!WaitForSingleObject` at `0x140012c1b`
- `KERNEL32!CreatePipe` at `0x140012474`
- `KERNEL32!CreatePipe` at `0x140012474`
- `KERNEL32!WaitForMultipleObjects` at `0x1400126ea`
- `KERNEL32!WaitForMultipleObjects` at `0x140012739`
- `KERNEL32!WaitForMultipleObjects` at `0x140012767`
- `KERNEL32!WaitForMultipleObjects` at `0x1400126ea`
- `KERNEL32!WaitForMultipleObjects` at `0x140012739`
- `KERNEL32!WaitForMultipleObjects` at `0x140012767`
- `KERNEL32!TerminateProcess` at `0x140012aca`
- `KERNEL32!TerminateProcess` at `0x140012c05`
- `KERNEL32!TerminateProcess` at `0x140012aca`
- `KERNEL32!TerminateProcess` at `0x140012c05`
- `KERNEL32!GetCurrentProcess` at `0x1400122ea`
- `KERNEL32!GetCurrentProcess` at `0x1400122ea`
- `WTSAPI32!WTSQueryUserToken` at `0x140012228`
- `WTSAPI32!WTSQueryUserToken` at `0x140012228`

## string_xrefs

- `0x1400123f6`: `CreateProcessWithTokenInSession failed!  Error = 0x%X`
- `0x140012a1f`: `Dynamic update detected!  Returning: [0x%X]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LaunchProcessInSession(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        ULONG a4,
        const unsigned __int16 *a5,
        DWORD dwMilliseconds,
        int *a7)
{
  HANDLE v9; // r13
  HANDLE hThread; // r14
  void *v11; // rsi
  HANDLE *v12; // rbx
  void *v13; // rdi
  signed int HighestAvailableToken; // r15d
  __int64 v15; // rcx
  DWORD v16; // r12d
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  const int *v19; // r9
  const int *v20; // rdx
  HANDLE v21; // rcx
  HANDLE v22; // rcx
  void *v23; // rax
  const int *v24; // rdx
  const int *v25; // r9
  HANDLE v26; // rcx
  HANDLE v27; // rax
  HANDLE ProcessHeap; // rax
  HANDLE *v29; // rax
  HANDLE v30; // rax
  HANDLE v31; // rcx
  DWORD v32; // r15d
  DWORD v33; // r9d
  unsigned int v34; // eax
  DWORD v35; // r12d
  HANDLE v36; // rax
  HANDLE v37; // r9
  HANDLE v38; // rcx
  void *v39; // r15
  HANDLE v40; // rax
  void *v41; // r15
  HANDLE v42; // rax
  __int64 v43; // r8
  _BYTE *v44; // rax
  HANDLE v45; // rcx
  HANDLE v46; // r9
  HANDLE v47; // rcx
  int v48; // r12d
  HANDLE v49; // rcx
  signed int v50; // eax
  HANDLE v51; // rcx
  char *v52; // rax
  HANDLE v53; // rcx
  DWORD v54; // eax
  HANDLE v55; // r9
  signed int v56; // eax
  __int64 v57; // r9
  HANDLE v58; // rcx
  HANDLE v59; // rcx
  HANDLE v60; // rcx
  DWORD v61; // eax
  HANDLE v62; // r9
  signed int v63; // eax
  __int64 v64; // r9
  HANDLE v65; // rcx
  HANDLE v66; // rcx
  HANDLE v67; // rcx
  HANDLE v68; // rcx
  void *v69; // r12
  HANDLE v70; // rax
  HANDLE v71; // rax
  HANDLE v72; // rax
  LPWSTR v73; // rbx
  HANDLE v74; // rax
  void *v75; // rbx
  HANDLE v76; // rax
  WCHAR *v77; // rbx
  HANDLE v78; // rax
  TOKEN_TYPE TokenType[2]; // [rsp+28h] [rbp-E0h]
  int phNewToken; // [rsp+30h] [rbp-D8h]
  HANDLE hExistingToken; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v83; // [rsp+60h] [rbp-A8h]
  void *hWritePipe; // [rsp+68h] [rbp-A0h] BYREF
  int v85; // [rsp+70h] [rbp-98h]
  DWORD nCount; // [rsp+74h] [rbp-94h]
  DWORD ExitCode[2]; // [rsp+78h] [rbp-90h] BYREF
  void *v88; // [rsp+80h] [rbp-88h]
  __int64 v89; // [rsp+88h] [rbp-80h]
  HANDLE hProcess; // [rsp+90h] [rbp-78h] BYREF
  void *hReadPipe; // [rsp+98h] [rbp-70h] BYREF
  HANDLE hObject; // [rsp+A0h] [rbp-68h] BYREF
  LPWSTR lpCommandLine; // [rsp+A8h] [rbp-60h] BYREF
  LPCWSTR lpName; // [rsp+B0h] [rbp-58h] BYREF
  void *phToken; // [rsp+B8h] [rbp-50h] BYREF
  HANDLE *v96; // [rsp+C0h] [rbp-48h]
  HANDLE v97; // [rsp+C8h] [rbp-40h]
  HANDLE v98; // [rsp+D0h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+D8h] [rbp-30h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v101; // [rsp+108h] [rbp+0h]
  __int64 v102; // [rsp+110h] [rbp+8h]
  struct _STARTUPINFOW StartupInfo; // [rsp+118h] [rbp+10h] BYREF

  v101 = -2;
  phToken = 0;
  hObject = 0;
  hExistingToken = 0;
  v9 = 0;
  hProcess = 0;
  hThread = 0;
  v97 = 0;
  lpName = 0;
  v89 = 0;
  v11 = 0;
  v98 = 0;
  lpCommandLine = 0;
  v12 = 0;
  v96 = 0;
  v13 = 0;
  v102 = 0;
  v88 = 0;
  ExitCode[0] = 0;
  ExitCode[1] = 0;
  v85 = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&PipeAttributes, 0, sizeof(PipeAttributes));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  hWritePipe = (void *)-1LL;
  hReadPipe = (void *)-1LL;
  if ( !a1 || !a7 )
  {
    HighestAvailableToken = -2147024809;
    v15 = 2147942487LL;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
    goto LABEL_150;
  }
  LODWORD(v83) = 0;
  v16 = 2;
  nCount = 2;
  if ( a4 - 1 > 0xFFFFFFFD )
  {
    HighestAvailableToken = STRAPI_Format(&lpCommandLine, L"\"%s\" %s", a1, a2);
    if ( HighestAvailableToken < 0 )
      goto LABEL_11;
    PipeAttributes.nLength = 24;
    PipeAttributes.bInheritHandle = 1;
    PipeAttributes.lpSecurityDescriptor = 0;
    if ( !CreatePipe(&hReadPipe, &hWritePipe, &PipeAttributes, 0) )
    {
      HighestAvailableToken = 230;
      goto LABEL_153;
    }
    StartupInfo.cb = 104;
    StartupInfo.wShowWindow = 5;
    StartupInfo.lpDesktop = 0;
    v23 = hWritePipe;
    if ( hWritePipe )
    {
      StartupInfo.hStdError = hWritePipe;
    }
    else
    {
      StartupInfo.hStdError = 0;
      v23 = 0;
    }
    StartupInfo.hStdOutput = v23;
    StartupInfo.dwFlags = 256;
    v24 = (const int *)a3;
    if ( !a3 )
      v24 = &dword_1400860C4;
    v25 = (const int *)a2;
    if ( !a2 )
      v25 = &dword_1400860C4;
    v26 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v26 = g_shLogFile;
    OutputMsg(v26, g_shLogEvent, L"Launching: [%s] [%s] from [%s]!", a1, v25, v24);
    if ( !CreateProcessW(a1, lpCommandLine, 0, 0, 1, 0x400u, 0, a3, &StartupInfo, &ProcessInformation) )
      goto LABEL_7;
    hThread = ProcessInformation.hThread;
    v97 = ProcessInformation.hThread;
    v9 = ProcessInformation.hProcess;
    hProcess = ProcessInformation.hProcess;
  }
  else
  {
    if ( !WTSQueryUserToken(a4, &phToken) )
      goto LABEL_7;
    HighestAvailableToken = GetHighestAvailableToken(phToken, &hExistingToken);
    if ( HighestAvailableToken < 0 )
      goto LABEL_11;
    if ( !DuplicateTokenEx(hExistingToken, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
      goto LABEL_7;
    HighestAvailableToken = CMiscHelpersT<CEmptyType>::IsAdmin(hObject);
    if ( HighestAvailableToken < 0 )
      goto LABEL_11;
    if ( !v85 )
    {
      if ( hExistingToken )
      {
        CloseHandle(hExistingToken);
        hExistingToken = 0;
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0x2000000u, &hExistingToken) )
        goto LABEL_7;
    }
    LODWORD(v19) = (_DWORD)a3;
    if ( !a3 )
      v19 = &dword_1400860C4;
    v20 = (const int *)a2;
    if ( !a2 )
      v20 = &dword_1400860C4;
    v21 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v21 = g_shLogFile;
    phNewToken = (int)v19;
    OutputMsg(v21, g_shLogEvent, L"Launching: [%s] [%s] from [%s] in session [%d]! (%s)", a1, v20);
    HighestAvailableToken = CProcessHelpersT<CEmptyType>::CreateProcessWithTokenInSession(
                              hExistingToken,
                              a3,
                              phNewToken,
                              a4,
                              (__int64)&hProcess);
    if ( HighestAvailableToken < 0 )
    {
      v22 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v22 = g_shLogFile;
      OutputMsg(
        v22,
        g_shLogEvent,
        L"CreateProcessWithTokenInSession failed!  Error = 0x%X",
        (unsigned int)HighestAvailableToken);
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)HighestAvailableToken);
      v9 = hProcess;
LABEL_149:
      if ( HighestAvailableToken >= 0 )
        goto LABEL_153;
      goto LABEL_150;
    }
    v9 = hProcess;
  }
  StartupInfo.hStdOutput = 0;
  StartupInfo.hStdError = 0;
  if ( hWritePipe )
  {
    CloseHandle(hWritePipe);
    hWritePipe = 0;
  }
  if ( a5 )
  {
    HighestAvailableToken = STRAPI_Format((unsigned __int16 **)&lpName, L"%s{%s}", L"Global\\MoSetup");
    if ( HighestAvailableToken >= 0 )
    {
      v27 = OpenEventW(0x100000u, 0, lpName);
      v11 = v27;
      if ( !v27 )
      {
        v11 = 0;
LABEL_7:
        LastError = GetLastError();
        HighestAvailableToken = LastError;
        if ( LastError )
        {
          if ( LastError > 0 )
            HighestAvailableToken = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          HighestAvailableToken = -2147467259;
        }
        goto LABEL_11;
      }
      v98 = v27;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      ProcessHeap = GetProcessHeap();
      v29 = (HANDLE *)HeapAlloc(ProcessHeap, 0, 0x10u);
      v12 = v29;
      if ( !v29 )
        goto LABEL_51;
      *v29 = v9;
      v29[1] = v11;
      goto LABEL_55;
    }
LABEL_11:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)HighestAvailableToken);
    goto LABEL_149;
  }
  v16 = 1;
  nCount = 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v30 = GetProcessHeap();
  v29 = (HANDLE *)HeapAlloc(v30, 0, 8u);
  v12 = v29;
  if ( !v29 )
  {
LABEL_51:
    v12 = 0;
    v15 = 2147942414LL;
    HighestAvailableToken = -2147024882;
    goto LABEL_3;
  }
  *v29 = v9;
LABEL_55:
  v96 = v29;
  v31 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v31 = g_shLogFile;
  OutputMsg(v31, g_shLogEvent, L"Waiting for process events...");
  if ( (unsigned int)ConX::Setup::Common::COSInfoHelper::IsHostOSWin8Plus()
    || (v32 = dwMilliseconds, dwMilliseconds - 1 > 0xFFFFFFFD) )
  {
    v35 = WaitForMultipleObjects(v16, v12, 0, dwMilliseconds);
  }
  else
  {
    do
    {
      v33 = v32;
      if ( v32 >= 0x927C0 )
        v33 = 600000;
      v34 = v32;
      v32 -= 600000;
      if ( v34 < 0x927C0 )
        v32 = 0;
      v35 = WaitForMultipleObjects(nCount, v12, 0, v33);
    }
    while ( v35 == 258 && v32 );
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v35 )
  {
    v52 = (char *)g_shLogFile - 1;
    if ( v35 == 1 )
    {
      v53 = 0;
      if ( (unsigned __int64)v52 <= 0xFFFFFFFFFFFFFFFDuLL )
        v53 = g_shLogFile;
      OutputMsg(v53, g_shLogEvent, L"Suspend! Terminating process...");
      if ( TerminateProcess(v9, 0) )
      {
        v54 = WaitForSingleObject(v9, 0xFFFFFFFF);
        v55 = 0;
        if ( v54 )
        {
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v55 = g_shLogFile;
          OutputMsg(v55, g_shLogEvent, L"Error waiting for terminated process to exit!");
        }
        else
        {
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v55 = g_shLogFile;
          OutputMsg(v55, g_shLogEvent, L"Process termination succeeded for Suspend!");
        }
      }
      else
      {
        v56 = GetLastError();
        v57 = (unsigned int)v56;
        if ( v56 > 0 )
          v57 = (unsigned __int16)v56 | 0x80070000;
        v58 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v58 = g_shLogFile;
        OutputMsg(v58, g_shLogEvent, L"Process termination failed!  Error = 0x%X", v57);
      }
      HighestAvailableToken = -1047526943;
      v59 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v59 = g_shLogFile;
      OutputMsg(v59, g_shLogEvent, L"Process termination due to Suspend! Returning: [0x%X]", 3247440353LL);
      goto LABEL_150;
    }
    if ( v35 == 258 )
    {
      v60 = 0;
      if ( (unsigned __int64)v52 <= 0xFFFFFFFFFFFFFFFDuLL )
        v60 = g_shLogFile;
      OutputMsg(v60, g_shLogEvent, L"Process timed out!  Terminating process...");
      if ( TerminateProcess(v9, 0xC1900104) )
      {
        v61 = WaitForSingleObject(v9, 0xFFFFFFFF);
        v62 = 0;
        if ( v61 )
        {
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v62 = g_shLogFile;
          OutputMsg(v62, g_shLogEvent, L"Error waiting for terminated process to exit!");
        }
        else
        {
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v62 = g_shLogFile;
          OutputMsg(v62, g_shLogEvent, L"Process termination succeeded!");
        }
      }
      else
      {
        v63 = GetLastError();
        v64 = (unsigned int)v63;
        if ( v63 > 0 )
          v64 = (unsigned __int16)v63 | 0x80070000;
        v65 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v65 = g_shLogFile;
        OutputMsg(v65, g_shLogEvent, L"Process termination failed!  Error = 0x%X", v64);
      }
      HighestAvailableToken = -1047527164;
      v66 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v66 = g_shLogFile;
      OutputMsg(v66, g_shLogEvent, L"Process timed out!  Returning: [0x%X]", 3247440132LL);
      goto LABEL_150;
    }
    HighestAvailableToken = -2147418113;
    v67 = 0;
    if ( (unsigned __int64)v52 <= 0xFFFFFFFFFFFFFFFDuLL )
      v67 = g_shLogFile;
    TokenType[0] = -2147418113;
    OutputMsg(
      v67,
      g_shLogEvent,
      L"Unexpected return code from WaitForMultipleObjects: [0x%X]!  Error = 0x%X",
      v35,
      *(_QWORD *)TokenType);
    goto LABEL_146;
  }
  if ( !GetExitCodeProcess(v9, &ExitCode[1]) )
  {
    v50 = GetLastError();
    HighestAvailableToken = v50;
    if ( v50 > 0 )
      HighestAvailableToken = (unsigned __int16)v50 | 0x80070000;
    v51 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v51 = g_shLogFile;
    OutputMsg(
      v51,
      g_shLogEvent,
      L"Error retrieving process exit code!  Error = 0x%X",
      (unsigned int)HighestAvailableToken);
LABEL_146:
    v48 = v83;
    goto LABEL_147;
  }
  v36 = GetProcessHeap();
  v13 = HeapAlloc(v36, 0, 0x1000u);
  if ( v13 )
  {
    v38 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v38 = g_shLogFile;
    OutputMsg(v38, g_shLogEvent, L"*******SetupHost Logging Begin*******\n");
    while ( 1 )
    {
      if ( v89 )
      {
        v39 = (void *)(v89 - 4);
        v40 = GetProcessHeap();
        HeapFree(v40, 0, v39);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v89 = 0;
      }
      v41 = v88;
      if ( v88 )
      {
        v42 = GetProcessHeap();
        HeapFree(v42, 0, v41);
        v88 = 0;
      }
      if ( !ReadFile(hReadPipe, v13, 0xFFFu, ExitCode, 0) || !ExitCode[0] )
        break;
      *((_BYTE *)v13 + ExitCode[0]) = 0;
      v43 = 0x7FFFFFFF;
      v44 = v13;
      do
      {
        if ( !*v44 )
          break;
        ++v44;
        --v43;
      }
      while ( v43 );
      HighestAvailableToken = v43 == 0 ? 0x80070057 : 0;
      if ( !v43 )
        goto LABEL_11;
      HighestAvailableToken = CStringConvertT<unsigned long>::A2W((LPCCH)v13);
      if ( HighestAvailableToken < 0 )
        goto LABEL_11;
      HighestAvailableToken = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(v88);
      if ( HighestAvailableToken < 0 )
        goto LABEL_11;
      v45 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v45 = g_shLogFile;
      OutputMsg(v45, g_shLogEvent, L"%s", v89);
    }
    v46 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v46 = g_shLogFile;
    OutputMsg(v46, g_shLogEvent, L"*******SetupHost Logging End*******");
  }
  else
  {
    v13 = 0;
    v37 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v37 = g_shLogFile;
    OutputMsg(v37, g_shLogEvent, L"Continue without SetupHost logging.");
  }
  HighestAvailableToken = ExitCode[1];
  v47 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v47 = g_shLogFile;
  OutputMsg(v47, g_shLogEvent, L"Process exit code: [0x%X]", ExitCode[1]);
  if ( HighestAvailableToken != -2147023429 )
    goto LABEL_146;
  HighestAvailableToken = 0;
  v48 = 1;
  v49 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v49 = g_shLogFile;
  OutputMsg(v49, g_shLogEvent, L"Dynamic update detected!  Returning: [0x%X]", 0);
LABEL_147:
  if ( HighestAvailableToken >= 0 )
  {
    *a7 = v48;
    goto LABEL_149;
  }
LABEL_150:
  v68 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v68 = g_shLogFile;
  TokenType[0] = HighestAvailableToken;
  OutputMsg(v68, g_shLogEvent, L"%s: Error = 0x%X", L"LaunchProcessInSession", *(_QWORD *)TokenType);
LABEL_153:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)HighestAvailableToken);
  if ( hReadPipe )
  {
    CloseHandle(hReadPipe);
    hReadPipe = 0;
  }
  if ( hWritePipe )
  {
    CloseHandle(hWritePipe);
    hWritePipe = 0;
  }
  v69 = v88;
  if ( v88 )
  {
    v70 = GetProcessHeap();
    HeapFree(v70, 0, v69);
  }
  if ( v13 )
  {
    v71 = GetProcessHeap();
    HeapFree(v71, 0, v13);
  }
  if ( v12 )
  {
    v72 = GetProcessHeap();
    HeapFree(v72, 0, v12);
  }
  if ( lpCommandLine )
  {
    v73 = lpCommandLine - 2;
    v74 = GetProcessHeap();
    HeapFree(v74, 0, v73);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v11 )
    CloseHandle(v11);
  if ( v89 )
  {
    v75 = (void *)(v89 - 4);
    v76 = GetProcessHeap();
    HeapFree(v76, 0, v75);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( lpName )
  {
    v77 = (WCHAR *)(lpName - 2);
    v78 = GetProcessHeap();
    HeapFree(v78, 0, v77);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( hThread )
    CloseHandle(hThread);
  if ( v9 )
    CloseHandle(v9);
  if ( hExistingToken )
  {
    CloseHandle(hExistingToken);
    hExistingToken = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( phToken )
    CloseHandle(phToken);
  return (unsigned int)HighestAvailableToken;
}

```

## disassembly

```asm
0x140012124  mov     rax, rsp
0x140012127  mov     [rax+20h], r9d
0x14001212b  mov     [rax+18h], r8
0x14001212f  mov     [rax+10h], rdx
0x140012133  mov     [rax+8], rcx
0x140012137  push    rbp
0x140012138  push    rbx
0x140012139  push    rsi
0x14001213a  push    rdi
0x14001213b  push    r12
0x14001213d  push    r13
0x14001213f  push    r14
0x140012141  push    r15
0x140012143  lea     rbp, [rax-0C8h]
0x14001214a  sub     rsp, 188h
0x140012151  mov     [rbp+0C0h+var_C0], 0FFFFFFFFFFFFFFFEh
0x140012159  mov     r15d, r9d
0x14001215c  mov     r12, rcx
0x14001215f  xor     eax, eax
0x140012161  mov     [rbp+0C0h+phToken], rax
0x140012165  mov     [rbp+0C0h+hObject], rax
0x140012169  mov     [rsp+1C0h+hExistingToken], rax
0x14001216e  mov     r13d, eax
0x140012171  mov     [rbp+0C0h+hProcess], rax
0x140012175  mov     r14d, eax
0x140012178  mov     [rbp+0C0h+var_100], rax
0x14001217c  mov     [rbp+0C0h+lpName], rax
0x140012180  mov     [rbp+0C0h+var_140], rax
0x140012184  mov     esi, eax
0x140012186  mov     [rbp+0C0h+var_F8], rax
0x14001218a  mov     [rbp+0C0h+lpCommandLine], rax
0x14001218e  mov     ebx, eax
0x140012190  mov     [rbp+0C0h+var_108], rax
0x140012194  mov     edi, eax
0x140012196  mov     [rbp+0C0h+var_B8], rax
0x14001219a  mov     [rsp+1C0h+var_148], rax
0x14001219f  mov     [rsp+1C0h+ExitCode], eax
0x1400121a3  mov     [rsp+1C0h+ExitCode+4], eax
0x1400121a7  mov     [rsp+1C0h+var_158], eax
0x1400121ab  xor     edx, edx; Val
0x1400121ad  lea     r8d, [rax+68h]; Size
0x1400121b1  lea     rcx, [rbp+0C0h+StartupInfo]; void *
0x1400121b5  call    memset_0
0x1400121ba  xorps   xmm0, xmm0
0x1400121bd  xor     eax, eax
0x1400121bf  movups  xmmword ptr [rbp+0C0h+PipeAttributes.nLength], xmm0
0x1400121c3  mov     qword ptr [rbp+0C0h+PipeAttributes.bInheritHandle], rax
0x1400121c7  xorps   xmm1, xmm1
0x1400121ca  movups  xmmword ptr [rbp+0C0h+ProcessInformation.hProcess], xmm1
0x1400121ce  mov     qword ptr [rbp+0C0h+ProcessInformation.dwProcessId], rax
0x1400121d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400121d6  mov     [rsp+1C0h+hWritePipe], rax
0x1400121db  mov     [rbp+0C0h+hReadPipe], rax
0x1400121df  xor     eax, eax
0x1400121e1  test    r12, r12
0x1400121e4  jnz     short loc_1400121FC
0x1400121e6  mov     r12d, 80070057h
0x1400121ec  mov     r15d, r12d
0x1400121ef  mov     ecx, r12d
0x1400121f2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400121f7  jmp     loc_140012D44
0x1400121fc  cmp     [rbp+0C0h+arg_30], rax
0x140012203  jz      short loc_1400121E6
0x140012205  mov     dword ptr [rsp+1C0h+var_168], eax
0x140012209  lea     eax, [r15-1]
0x14001220d  mov     r12d, 2
0x140012213  mov     [rsp+1C0h+nCount], r12d
0x140012218  cmp     eax, 0FFFFFFFDh
0x14001221b  ja      loc_140012426
0x140012221  lea     rdx, [rbp+0C0h+phToken]; phToken
0x140012225  mov     ecx, r15d; SessionId
0x140012228  call    cs:__imp_WTSQueryUserToken
0x14001222f  nop     dword ptr [rax+rax+00h]
0x140012234  test    eax, eax
0x140012236  jnz     short loc_14001226D
0x140012238  call    cs:__imp_GetLastError
0x14001223f  nop     dword ptr [rax+rax+00h]
0x140012244  mov     r15d, eax
0x140012247  test    eax, eax
0x140012249  jnz     short loc_140012253
0x14001224b  mov     r15d, 80004005h
0x140012251  jmp     short loc_140012260
0x140012253  jle     short loc_140012260
0x140012255  movzx   r15d, r15w
0x140012259  or      r15d, 80070000h
0x140012260  mov     ecx, r15d
0x140012263  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140012268  jmp     loc_140012D3F
0x14001226d  lea     rdx, [rsp+1C0h+hExistingToken]; void **
0x140012272  mov     rcx, [rbp+0C0h+phToken]; void *
0x140012276  call    ?GetHighestAvailableToken@@YAJPEAXPEAPEAX@Z; GetHighestAvailableToken(void *,void * *)
0x14001227b  mov     r15d, eax
0x14001227e  test    eax, eax
0x140012280  js      short loc_140012260
0x140012282  lea     rax, [rbp+0C0h+hObject]
0x140012286  mov     [rsp+1C0h+phNewToken], rax; phNewToken
0x14001228b  mov     [rsp+1C0h+TokenType], r12d; TokenType
0x140012290  mov     r9d, r12d; ImpersonationLevel
0x140012293  xor     r8d, r8d; lpTokenAttributes
0x140012296  mov     edx, 2000000h; dwDesiredAccess
0x14001229b  mov     rcx, [rsp+1C0h+hExistingToken]; hExistingToken
0x1400122a0  call    cs:__imp_DuplicateTokenEx
0x1400122a7  nop     dword ptr [rax+rax+00h]
0x1400122ac  test    eax, eax
0x1400122ae  jz      short loc_140012238
0x1400122b0  lea     rdx, [rsp+1C0h+var_158]
0x1400122b5  mov     rcx, [rbp+0C0h+hObject]; TokenHandle
0x1400122b9  call    ?IsAdmin@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAXPEAH@Z; CMiscHelpersT<CEmptyType>::IsAdmin(void *,int *)
0x1400122be  mov     r15d, eax
0x1400122c1  test    eax, eax
0x1400122c3  js      short loc_140012260
0x1400122c5  xor     r15d, r15d
0x1400122c8  cmp     [rsp+1C0h+var_158], r15d
0x1400122cd  jnz     short loc_140012320
0x1400122cf  mov     rcx, [rsp+1C0h+hExistingToken]; hObject
0x1400122d4  test    rcx, rcx
0x1400122d7  jz      short loc_1400122EA
0x1400122d9  call    cs:__imp_CloseHandle
0x1400122e0  nop     dword ptr [rax+rax+00h]
0x1400122e5  mov     [rsp+1C0h+hExistingToken], r15
0x1400122ea  call    cs:__imp_GetCurrentProcess
0x1400122f1  nop     dword ptr [rax+rax+00h]
0x1400122f6  lea     r8, [rsp+1C0h+hExistingToken]; TokenHandle
0x1400122fb  mov     edx, 2000000h; DesiredAccess
0x140012300  mov     rcx, rax; ProcessHandle
0x140012303  call    cs:__imp_OpenProcessToken
0x14001230a  nop     dword ptr [rax+rax+00h]
0x14001230f  test    eax, eax
0x140012311  jz      loc_140012238
0x140012317  lea     r10, aNonAdmin; "non-admin"
0x14001231e  jmp     short loc_140012327
0x140012320  lea     r10, aAdmin; "admin"
0x140012327  lea     rcx, dword_1400860C4
0x14001232e  mov     rax, [rbp+0C0h+arg_10]
0x140012335  mov     r9, rax
0x140012338  test    rax, rax
0x14001233b  cmovz   r9, rcx
0x14001233f  mov     rax, [rbp+0C0h+arg_8]
0x140012346  mov     rdx, rax
0x140012349  test    rax, rax
0x14001234c  cmovz   rdx, rcx
0x140012350  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140012357  lea     rax, [r8-1]
0x14001235b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001235f  setnbe  al
0x140012362  mov     rcx, r15
0x140012365  test    al, al
0x140012367  cmovz   rcx, r8; hFile
0x14001236b  mov     [rsp+1C0h+lpCurrentDirectory], r10
0x140012370  mov     r15d, [rbp+0C0h+arg_18]
0x140012377  mov     dword ptr [rsp+1C0h+lpEnvironment], r15d; int
0x14001237c  mov     [rsp+1C0h+phNewToken], r9; int
0x140012381  mov     qword ptr [rsp+1C0h+TokenType], rdx
0x140012386  mov     r9, [rbp+0C0h+lpApplicationName]
0x14001238d  lea     r8, aLaunchingSSFro_0; "Launching: [%s] [%s] from [%s] in sessi"...
0x140012394  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001239b  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x1400123a0  lea     rax, [rbp+0C0h+hProcess]
0x1400123a4  mov     [rsp+1C0h+lpCurrentDirectory], rax; __int64
0x1400123a9  mov     r8, [rbp+0C0h+arg_10]
0x1400123b0  mov     qword ptr [rsp+1C0h+TokenType], r8; LPCWSTR
0x1400123b5  mov     r9, [rbp+0C0h+arg_8]
0x1400123bc  mov     r8, [rbp+0C0h+lpApplicationName]
0x1400123c3  mov     edx, r15d
0x1400123c6  mov     rcx, [rsp+1C0h+hExistingToken]; hExistingToken
0x1400123cb  call    ?CreateProcessWithTokenInSession@?$CProcessHelpersT@VCEmptyType@@@@SAJPEAXKPEBG11HHPEAPEAX2H@Z; CProcessHelpersT<CEmptyType>::CreateProcessWithTokenInSession(void *,ulong,ushort const *,ushort const *,ushort const *,int,int,void * *,void * *,int)
0x1400123d0  mov     r15d, eax
0x1400123d3  xor     edx, edx
0x1400123d5  test    eax, eax
0x1400123d7  jns     short loc_14001241A
0x1400123d9  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x1400123e0  lea     rax, [r8-1]
0x1400123e4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400123e8  setnbe  al
0x1400123eb  mov     ecx, edx
0x1400123ed  test    al, al
0x1400123ef  cmovz   rcx, r8; hFile
0x1400123f3  mov     r9d, r15d
0x1400123f6  lea     r8, aCreateprocessw; "CreateProcessWithTokenInSession failed!"...
0x1400123fd  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140012404  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140012409  mov     ecx, r15d
0x14001240c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140012411  mov     r13, [rbp+0C0h+hProcess]
0x140012415  jmp     loc_140012D3F
0x14001241a  mov     r13, [rbp+0C0h+hProcess]
0x14001241e  xor     r15d, r15d
0x140012421  jmp     loc_140012594
0x140012426  mov     r9, [rbp+0C0h+arg_8]
0x14001242d  mov     r8, [rbp+0C0h+lpApplicationName]
0x140012434  lea     rdx, aSS_6; "\"%s\" %s"
0x14001243b  lea     rcx, [rbp+0C0h+lpCommandLine]; unsigned __int16 **
0x14001243f  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x140012444  mov     r15d, eax
0x140012447  test    eax, eax
0x140012449  js      loc_140012260
0x14001244f  mov     [rbp+0C0h+PipeAttributes.nLength], 18h
0x140012456  mov     [rbp+0C0h+PipeAttributes.bInheritHandle], 1
0x14001245d  xor     r15d, r15d
0x140012460  mov     [rbp+0C0h+PipeAttributes.lpSecurityDescriptor], r15
0x140012464  xor     r9d, r9d; nSize
0x140012467  lea     r8, [rbp+0C0h+PipeAttributes]; lpPipeAttributes
0x14001246b  lea     rdx, [rsp+1C0h+hWritePipe]; hWritePipe
0x140012470  lea     rcx, [rbp+0C0h+hReadPipe]; hReadPipe
0x140012474  call    cs:__imp_CreatePipe
0x14001247b  nop     dword ptr [rax+rax+00h]
0x140012480  test    eax, eax
0x140012482  jnz     short loc_14001248F
0x140012484  mov     r15d, 0E6h
0x14001248a  jmp     loc_140012D81
0x14001248f  mov     [rbp+0C0h+StartupInfo.cb], 68h ; 'h'
0x140012496  mov     eax, 5
0x14001249b  mov     [rbp+0C0h+StartupInfo.wShowWindow], ax
0x14001249f  mov     [rbp+0C0h+StartupInfo.lpDesktop], r15
0x1400124a3  mov     rax, [rsp+1C0h+hWritePipe]
0x1400124a8  test    rax, rax
0x1400124ab  jnz     short loc_1400124B6
0x1400124ad  mov     [rbp+0C0h+StartupInfo.hStdError], r15
0x1400124b1  mov     rax, r15
0x1400124b4  jmp     short loc_1400124BA
0x1400124b6  mov     [rbp+0C0h+StartupInfo.hStdError], rax
0x1400124ba  mov     [rbp+0C0h+StartupInfo.hStdOutput], rax
0x1400124be  mov     [rbp+0C0h+StartupInfo.dwFlags], 100h
0x1400124c5  lea     rcx, dword_1400860C4
0x1400124cc  mov     rax, [rbp+0C0h+arg_10]
0x1400124d3  mov     rdx, rax
0x1400124d6  test    rax, rax
0x1400124d9  cmovz   rdx, rcx
0x1400124dd  mov     r9, [rbp+0C0h+arg_8]
0x1400124e4  test    r9, r9
0x1400124e7  cmovz   r9, rcx
0x1400124eb  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x1400124f2  lea     rax, [r8-1]
0x1400124f6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400124fa  setnbe  al
0x1400124fd  mov     rcx, r15
0x140012500  test    al, al
0x140012502  cmovz   rcx, r8; hFile
0x140012506  mov     [rsp+1C0h+phNewToken], rdx
0x14001250b  mov     qword ptr [rsp+1C0h+TokenType], r9
0x140012510  mov     r9, [rbp+0C0h+lpApplicationName]
0x140012517  lea     r8, aLaunchingSSFro; "Launching: [%s] [%s] from [%s]!"
0x14001251e  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140012525  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001252a  lea     rax, [rbp+0C0h+ProcessInformation]
0x14001252e  mov     [rsp+1C0h+lpProcessInformation], rax; lpProcessInformation
0x140012533  lea     rax, [rbp+0C0h+StartupInfo]
0x140012537  mov     [rsp+1C0h+lpStartupInfo], rax; lpStartupInfo
0x14001253c  mov     r8, [rbp+0C0h+arg_10]
0x140012543  mov     [rsp+1C0h+lpCurrentDirectory], r8; lpCurrentDirectory
0x140012548  xor     eax, eax
0x14001254a  mov     [rsp+1C0h+lpEnvironment], rax; lpEnvironment
0x14001254f  mov     dword ptr [rsp+1C0h+phNewToken], 400h; dwCreationFlags
0x140012557  mov     [rsp+1C0h+TokenType], 1; bInheritHandles
0x14001255f  xor     r9d, r9d; lpThreadAttributes
0x140012562  xor     r8d, r8d; lpProcessAttributes
0x140012565  mov     rdx, [rbp+0C0h+lpCommandLine]; lpCommandLine
0x140012569  mov     rcx, [rbp+0C0h+lpApplicationName]; lpApplicationName
0x140012570  call    cs:__imp_CreateProcessW
0x140012577  nop     dword ptr [rax+rax+00h]
0x14001257c  test    eax, eax
0x14001257e  jz      loc_140012238
0x140012584  mov     r14, [rbp+0C0h+ProcessInformation.hThread]
0x140012588  mov     [rbp+0C0h+var_100], r14
0x14001258c  mov     r13, [rbp+0C0h+ProcessInformation.hProcess]
0x140012590  mov     [rbp+0C0h+hProcess], r13
0x140012594  mov     [rbp+0C0h+StartupInfo.hStdOutput], r15
0x140012598  mov     [rbp+0C0h+StartupInfo.hStdError], r15
0x14001259c  mov     rcx, [rsp+1C0h+hWritePipe]; hObject
0x1400125a1  test    rcx, rcx
0x1400125a4  jz      short loc_1400125B7
0x1400125a6  call    cs:__imp_CloseHandle
0x1400125ad  nop     dword ptr [rax+rax+00h]
0x1400125b2  mov     [rsp+1C0h+hWritePipe], r15
0x1400125b7  mov     r9, [rbp+0C0h+arg_20]
0x1400125be  test    r9, r9
0x1400125c1  jz      loc_140012660
0x1400125c7  lea     r8, aGlobalMosetup; "Global\\MoSetup"
0x1400125ce  lea     rdx, aSS; "%s{%s}"
0x1400125d5  lea     rcx, [rbp+0C0h+lpName]; unsigned __int16 **
0x1400125d9  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x1400125de  mov     r15d, eax
0x1400125e1  test    eax, eax
0x1400125e3  js      loc_140012260
0x1400125e9  mov     r8, [rbp+0C0h+lpName]; lpName
0x1400125ed  xor     edx, edx; bInheritHandle
0x1400125ef  mov     ecx, 100000h; dwDesiredAccess
0x1400125f4  call    cs:__imp_OpenEventW
0x1400125fb  nop     dword ptr [rax+rax+00h]
0x140012600  mov     rsi, rax
0x140012603  xor     r15d, r15d
0x140012606  test    rax, rax
0x140012609  jnz     short loc_140012613
0x14001260b  mov     esi, r15d
0x14001260e  jmp     loc_140012238
0x140012613  mov     [rbp+0C0h+var_F8], rsi
0x140012617  xor     ecx, ecx
0x140012619  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001261e  call    cs:__imp_GetProcessHeap
0x140012625  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
