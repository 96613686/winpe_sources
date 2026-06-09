# CUpdateManager::RunScript(ushort const *,ulong)

- ea: `0x1400380cc`
- end: `0x140038514`
- name: `?RunScript@CUpdateManager@@IEAAJPEBGK@Z`
- size: `1096`
- prototype: `__int64 __fastcall(CUpdateManager *this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140035ec0`

## callees

- `0x14002c8e8`
- `0x14002c950`
- `0x1400380cc`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140067ed0`
- `0x1400680d0`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400384a9`
- `KERNEL32!CloseHandle` at `0x1400384a9`
- `KERNEL32!WaitForSingleObject` at `0x140038277`
- `KERNEL32!WaitForSingleObject` at `0x140038277`
- `KERNEL32!GetFileAttributesW` at `0x140038140`
- `KERNEL32!GetFileAttributesW` at `0x140038140`
- `KERNEL32!GetExitCodeProcess` at `0x1400383dd`
- `KERNEL32!GetExitCodeProcess` at `0x1400383dd`
- `KERNEL32!GetLastError` at `0x14003819e`
- `KERNEL32!GetLastError` at `0x14003831c`
- `KERNEL32!GetLastError` at `0x1400383e7`
- `KERNEL32!GetLastError` at `0x14003819e`
- `KERNEL32!GetLastError` at `0x14003831c`
- `KERNEL32!GetLastError` at `0x1400383e7`
- `KERNEL32!IsDebuggerPresent` at `0x1400381f7`
- `KERNEL32!IsDebuggerPresent` at `0x1400382d7`
- `KERNEL32!IsDebuggerPresent` at `0x140038375`
- `KERNEL32!IsDebuggerPresent` at `0x140038440`
- `KERNEL32!IsDebuggerPresent` at `0x1400381f7`
- `KERNEL32!IsDebuggerPresent` at `0x1400382d7`
- `KERNEL32!IsDebuggerPresent` at `0x140038375`
- `KERNEL32!IsDebuggerPresent` at `0x140038440`
- `SHELL32!ShellExecuteExW` at `0x140038190`
- `SHELL32!ShellExecuteExW` at `0x140038190`

## string_xrefs

- `0x1400381c2`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x1400382a5`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140038340`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x1400383ae`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x14003840b`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x14003811f`: `CUpdateManager::RunScript Running script "%s" with timeout of %i minutes\n`
- `0x1400381b9`: `CUpdateManager::RunScript`
- `0x14003829e`: `CUpdateManager::RunScript`
- `0x140038337`: `CUpdateManager::RunScript`
- `0x1400383a7`: `CUpdateManager::RunScript`
- `0x140038402`: `CUpdateManager::RunScript`
- `0x140038473`: `CUpdateManager::RunScript - Script "%s" returned code %d (0x%08X)`
- `0x1400384d2`: `CUpdateManager::RunScript - Script "%s" failed\n`
- `0x1400384db`: `CUpdateManager::RunScript - Script "%s" completed succesfully\n`

## pseudocode

```c
__int64 __fastcall CUpdateManager::RunScript(CUpdateManager *this, unsigned __int16 *a2, unsigned int a3)
{
  const unsigned __int16 *v5; // rdx
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  signed int v7; // ebx
  DWORD FileAttributesW; // eax
  const unsigned __int16 *v9; // rdx
  unsigned __int64 v10; // rcx
  signed int LastError; // eax
  const unsigned __int16 *v12; // r12
  __int64 v13; // r9
  __int64 v14; // r8
  DWORD v15; // eax
  signed int v16; // eax
  unsigned __int64 v17; // rcx
  signed int v18; // eax
  HANDLE hProcess; // rcx
  signed int v21; // [rsp+30h] [rbp-79h]
  int v22; // [rsp+30h] [rbp-79h]
  signed int v23; // [rsp+38h] [rbp-71h]
  int v24; // [rsp+38h] [rbp-71h]
  DWORD ExitCode[4]; // [rsp+40h] [rbp-69h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+50h] [rbp-59h] BYREF
  __int128 v27; // [rsp+C0h] [rbp+17h]
  int v28; // [rsp+D0h] [rbp+27h]

  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  ExitCode[0] = 0;
  DEBUGMSG(L"CUpdateManager::RunScript Running script \"%s\" with timeout of %i minutes\n", a2, a3);
  v7 = ScriptUtils::CheckExtension((ScriptUtils *)a2, v5);
  if ( v7 >= 0 )
  {
    FileAttributesW = GetFileAttributesW(a2);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) != 0 )
    {
      DEBUGMSG(L"ScriptUtils::CheckExistence - File \"%s\" does not exist!", a2);
      v7 = -2147024894;
      goto LABEL_41;
    }
    v7 = ScriptUtils::CheckUsersGrpReadOnly(a2, v9);
    if ( v7 < 0 )
      goto LABEL_41;
    pExecInfo.cbSize = 112;
    pExecInfo.lpVerb = L"open";
    pExecInfo.fMask = 1088;
    pExecInfo.lpFile = a2;
    pExecInfo.nShow = 0;
    if ( !ShellExecuteExW(&pExecInfo) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v12 = L"fSuccess";
      if ( v7 >= 0 )
        v7 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        0x784u,
        L"CUpdateManager::RunScript",
        L"CBRAEx",
        L"fSuccess",
        v7);
      if ( IsDebuggerPresent() )
      {
        v13 = 1924;
LABEL_12:
        v23 = v7;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
          v13,
          L"CUpdateManager::RunScript",
          L"CBRAEx",
          v12,
          v23);
        goto LABEL_41;
      }
      v14 = 1924;
      goto LABEL_15;
    }
    LogEventMessage1(v10, &WmsSvc_CustomScriptStart, a2);
    v15 = WaitForSingleObject(pExecInfo.hProcess, 60000 * a3);
    switch ( v15 )
    {
      case 0u:
        if ( GetExitCodeProcess(pExecInfo.hProcess, ExitCode) )
        {
          LogEventMessage1(v17, &WmsSvc_CustomScriptEnd, a2);
          DEBUGMSG(L"CUpdateManager::RunScript - Script \"%s\" returned code %d (0x%08X)", a2, ExitCode[0], ExitCode[0]);
          goto LABEL_41;
        }
        v18 = GetLastError();
        v7 = v18;
        if ( v18 > 0 )
          v7 = (unsigned __int16)v18 | 0x80070000;
        v12 = L"fSuccess";
        if ( v7 >= 0 )
          v7 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
          0x7A5u,
          L"CUpdateManager::RunScript",
          L"CBRAEx",
          L"fSuccess",
          v7);
        if ( IsDebuggerPresent() )
        {
          v13 = 1957;
          goto LABEL_12;
        }
        v14 = 1957;
LABEL_15:
        v21 = v7;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
          v14,
          L"CUpdateManager::RunScript",
          L"CBRAEx",
          v12,
          v21);
        goto LABEL_41;
      case 0x102u:
        v7 = -2147024638;
        DEBUGMSGLEVEL(
          4u,
          L"%s(%d) - %s - Test failed:  %s\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
          1939,
          L"CUpdateManager::RunScript",
          L"Script timed out");
        goto LABEL_41;
      case 0xFFFFFFFF:
        v16 = GetLastError();
        v7 = v16;
        if ( v16 > 0 )
          v7 = (unsigned __int16)v16 | 0x80070000;
        v12 = L"0";
        if ( v7 >= 0 )
          v7 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
          0x797u,
          L"CUpdateManager::RunScript",
          L"CBRAEx",
          L"0",
          v7);
        if ( IsDebuggerPresent() )
        {
          v13 = 1943;
          goto LABEL_12;
        }
        v14 = 1943;
        goto LABEL_15;
    }
    v7 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      0x79Bu,
      L"CUpdateManager::RunScript",
      L"CBRA",
      L"0",
      -2147467259);
    if ( IsDebuggerPresent() )
    {
      v24 = -2147467259;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        1947,
        L"CUpdateManager::RunScript",
        L"CBRA",
        L"0",
        v24);
    }
    else
    {
      v22 = -2147467259;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        1947,
        L"CUpdateManager::RunScript",
        L"CBRA",
        L"0",
        v22);
    }
  }
LABEL_41:
  hProcess = pExecInfo.hProcess;
  if ( (unsigned __int64)pExecInfo.hProcess - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(pExecInfo.hProcess);
    pExecInfo.hProcess = 0;
  }
  if ( v7 >= 0 )
  {
    DEBUGMSG(L"CUpdateManager::RunScript - Script \"%s\" completed succesfully\n", a2);
  }
  else
  {
    v28 = 0;
    v27 = 0;
    LogEventMessageHr((unsigned __int64)hProcess, v6, v7, a2);
    DEBUGMSG(L"CUpdateManager::RunScript - Script \"%s\" failed\n", a2);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400380cc  mov     [rsp-8+arg_0], rbx
0x1400380d1  mov     [rsp-8+arg_18], rsi
0x1400380d6  push    rbp
0x1400380d7  push    rdi
0x1400380d8  push    r12
0x1400380da  push    r14
0x1400380dc  push    r15
0x1400380de  lea     rbp, [rsp-37h]
0x1400380e3  sub     rsp, 0E0h
0x1400380ea  mov     rax, cs:__security_cookie
0x1400380f1  xor     rax, rsp
0x1400380f4  mov     [rbp+57h+var_28], rax
0x1400380f8  mov     edi, r8d
0x1400380fb  lea     rcx, [rbp+57h+pExecInfo]; void *
0x1400380ff  mov     r14, rdx
0x140038102  mov     r15d, 70h ; 'p'
0x140038108  mov     r8d, r15d; Size
0x14003810b  xor     edx, edx; Val
0x14003810d  call    memset_0
0x140038112  mov     r8d, edi
0x140038115  mov     [rbp+57h+ExitCode], 0
0x14003811c  mov     rdx, r14
0x14003811f  lea     rcx, aCupdatemanager_3; "CUpdateManager::RunScript Running scrip"...
0x140038126  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14003812b  mov     rcx, r14; this
0x14003812e  call    ?CheckExtension@ScriptUtils@@YAJPEBG@Z; ScriptUtils::CheckExtension(ushort const *)
0x140038133  mov     ebx, eax
0x140038135  test    eax, eax
0x140038137  js      loc_14003849B
0x14003813d  mov     rcx, r14; lpFileName
0x140038140  call    cs:__imp_GetFileAttributesW
0x140038146  or      esi, 0FFFFFFFFh
0x140038149  cmp     eax, esi
0x14003814b  jz      loc_140038487
0x140038151  test    al, 10h
0x140038153  jnz     loc_140038487
0x140038159  mov     rcx, r14; pObjectName
0x14003815c  call    ?CheckUsersGrpReadOnly@ScriptUtils@@YAJPEBG@Z; ScriptUtils::CheckUsersGrpReadOnly(ushort const *)
0x140038161  mov     ebx, eax
0x140038163  test    eax, eax
0x140038165  js      loc_14003849B
0x14003816b  lea     rax, aOpen; "open"
0x140038172  mov     [rbp+57h+pExecInfo.cbSize], r15d
0x140038176  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x14003817a  mov     [rbp+57h+pExecInfo.lpVerb], rax
0x14003817e  mov     [rbp+57h+pExecInfo.fMask], 440h
0x140038185  mov     [rbp+57h+pExecInfo.lpFile], r14
0x140038189  mov     [rbp+57h+pExecInfo.nShow], 0
0x140038190  call    cs:__imp_ShellExecuteExW
0x140038196  test    eax, eax
0x140038198  jnz     loc_14003825E
0x14003819e  call    cs:__imp_GetLastError
0x1400381a4  mov     ebx, eax
0x1400381a6  test    eax, eax
0x1400381a8  jle     short loc_1400381B3
0x1400381aa  movzx   ebx, ax
0x1400381ad  or      ebx, 80070000h
0x1400381b3  mov     r15d, 80004005h
0x1400381b9  lea     rsi, aCupdatemanager_50; "CUpdateManager::RunScript"
0x1400381c0  test    ebx, ebx
0x1400381c2  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x1400381c9  lea     r12, aFsuccess; "fSuccess"
0x1400381d0  mov     r8, rsi; unsigned __int16 *
0x1400381d3  cmovns  ebx, r15d
0x1400381d7  mov     edx, 784h; unsigned int
0x1400381dc  lea     r15, aCbraex; "CBRAEx"
0x1400381e3  mov     [rsp+100h+var_D8], ebx; int
0x1400381e7  mov     r9, r15; unsigned __int16 *
0x1400381ea  mov     [rsp+100h+var_E0], r12; unsigned __int16 *
0x1400381ef  mov     rcx, rdi; unsigned __int16 *
0x1400381f2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400381f7  call    cs:__imp_IsDebuggerPresent
0x1400381fd  test    eax, eax
0x1400381ff  jz      short loc_140038233
0x140038201  mov     r9d, 784h
0x140038207  mov     [rsp+100h+var_C8], ebx
0x14003820b  mov     [rsp+100h+var_D0], r12
0x140038210  mov     qword ptr [rsp+100h+var_D8], r15
0x140038215  mov     r8, rdi
0x140038218  mov     [rsp+100h+var_E0], rsi
0x14003821d  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140038224  mov     ecx, 2; unsigned __int8
0x140038229  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14003822e  jmp     loc_14003849B
0x140038233  mov     r8d, 784h
0x140038239  mov     dword ptr [rsp+100h+var_D0], ebx
0x14003823d  mov     qword ptr [rsp+100h+var_D8], r12
0x140038242  mov     [rsp+100h+var_E0], r15
0x140038247  mov     r9, rsi
0x14003824a  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140038251  mov     rdx, rdi
0x140038254  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140038259  jmp     loc_14003849B
0x14003825e  mov     r8, r14; unsigned __int16 *
0x140038261  lea     rdx, WmsSvc_CustomScriptStart; struct _EVENT_DESCRIPTOR *
0x140038268  call    ?LogEventMessage1@@YAJ_KPEBU_EVENT_DESCRIPTOR@@PEBG@Z; LogEventMessage1(unsigned __int64,_EVENT_DESCRIPTOR const *,ushort const *)
0x14003826d  mov     rcx, [rbp+57h+pExecInfo.hProcess]; hHandle
0x140038271  imul    edx, edi, 0EA60h; dwMilliseconds
0x140038277  call    cs:__imp_WaitForSingleObject
0x14003827d  test    eax, eax
0x14003827f  jz      loc_1400383D5
0x140038285  cmp     eax, 102h
0x14003828a  jz      loc_140038395
0x140038290  cmp     eax, esi
0x140038292  jz      loc_14003831C
0x140038298  mov     r15d, 80004005h
0x14003829e  lea     rsi, aCupdatemanager_50; "CUpdateManager::RunScript"
0x1400382a5  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x1400382ac  mov     [rsp+100h+var_D8], r15d; int
0x1400382b1  lea     r12, a0; "0"
0x1400382b8  mov     r8, rsi; unsigned __int16 *
0x1400382bb  mov     rcx, rdi; unsigned __int16 *
0x1400382be  mov     [rsp+100h+var_E0], r12; unsigned __int16 *
0x1400382c3  lea     r9, aCbra; "CBRA"
0x1400382ca  mov     edx, 79Bh; unsigned int
0x1400382cf  mov     ebx, r15d
0x1400382d2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400382d7  call    cs:__imp_IsDebuggerPresent
0x1400382dd  test    eax, eax
0x1400382df  lea     rax, aCbra; "CBRA"
0x1400382e6  jz      short loc_140038302
0x1400382e8  mov     [rsp+100h+var_C8], r15d
0x1400382ed  mov     r9d, 79Bh
0x1400382f3  mov     [rsp+100h+var_D0], r12
0x1400382f8  mov     qword ptr [rsp+100h+var_D8], rax
0x1400382fd  jmp     loc_140038215
0x140038302  mov     dword ptr [rsp+100h+var_D0], r15d
0x140038307  mov     r8d, 79Bh
0x14003830d  mov     qword ptr [rsp+100h+var_D8], r12
0x140038312  mov     [rsp+100h+var_E0], rax
0x140038317  jmp     loc_140038247
0x14003831c  call    cs:__imp_GetLastError
0x140038322  mov     ebx, eax
0x140038324  test    eax, eax
0x140038326  jle     short loc_140038331
0x140038328  movzx   ebx, ax
0x14003832b  or      ebx, 80070000h
0x140038331  mov     r15d, 80004005h
0x140038337  lea     rsi, aCupdatemanager_50; "CUpdateManager::RunScript"
0x14003833e  test    ebx, ebx
0x140038340  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140038347  lea     r12, a0; "0"
0x14003834e  mov     r8, rsi; unsigned __int16 *
0x140038351  cmovns  ebx, r15d
0x140038355  mov     edx, 797h; unsigned int
0x14003835a  lea     r15, aCbraex; "CBRAEx"
0x140038361  mov     [rsp+100h+var_D8], ebx; int
0x140038365  mov     r9, r15; unsigned __int16 *
0x140038368  mov     [rsp+100h+var_E0], r12; unsigned __int16 *
0x14003836d  mov     rcx, rdi; unsigned __int16 *
0x140038370  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140038375  call    cs:__imp_IsDebuggerPresent
0x14003837b  test    eax, eax
0x14003837d  jz      short loc_14003838A
0x14003837f  mov     r9d, 797h
0x140038385  jmp     loc_140038207
0x14003838a  mov     r8d, 797h
0x140038390  jmp     loc_140038239
0x140038395  lea     rax, aScriptTimedOut; "Script timed out"
0x14003839c  mov     r9d, 793h
0x1400383a2  mov     qword ptr [rsp+100h+var_D8], rax
0x1400383a7  lea     rsi, aCupdatemanager_50; "CUpdateManager::RunScript"
0x1400383ae  lea     r8, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x1400383b5  mov     [rsp+100h+var_E0], rsi
0x1400383ba  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x1400383c1  mov     ecx, 4; unsigned __int8
0x1400383c6  mov     ebx, 80070102h
0x1400383cb  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400383d0  jmp     loc_14003849B
0x1400383d5  mov     rcx, [rbp+57h+pExecInfo.hProcess]; hProcess
0x1400383d9  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x1400383dd  call    cs:__imp_GetExitCodeProcess
0x1400383e3  test    eax, eax
0x1400383e5  jnz     short loc_140038460
0x1400383e7  call    cs:__imp_GetLastError
0x1400383ed  mov     ebx, eax
0x1400383ef  test    eax, eax
0x1400383f1  jle     short loc_1400383FC
0x1400383f3  movzx   ebx, ax
0x1400383f6  or      ebx, 80070000h
0x1400383fc  mov     r15d, 80004005h
0x140038402  lea     rsi, aCupdatemanager_50; "CUpdateManager::RunScript"
0x140038409  test    ebx, ebx
0x14003840b  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140038412  lea     r12, aFsuccess; "fSuccess"
0x140038419  mov     r8, rsi; unsigned __int16 *
0x14003841c  cmovns  ebx, r15d
0x140038420  mov     edx, 7A5h; unsigned int
0x140038425  lea     r15, aCbraex; "CBRAEx"
0x14003842c  mov     [rsp+100h+var_D8], ebx; int
0x140038430  mov     r9, r15; unsigned __int16 *
0x140038433  mov     [rsp+100h+var_E0], r12; unsigned __int16 *
0x140038438  mov     rcx, rdi; unsigned __int16 *
0x14003843b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140038440  call    cs:__imp_IsDebuggerPresent
0x140038446  test    eax, eax
0x140038448  jz      short loc_140038455
0x14003844a  mov     r9d, 7A5h
0x140038450  jmp     loc_140038207
0x140038455  mov     r8d, 7A5h
0x14003845b  jmp     loc_140038239
0x140038460  mov     r8, r14; unsigned __int16 *
0x140038463  lea     rdx, WmsSvc_CustomScriptEnd; struct _EVENT_DESCRIPTOR *
0x14003846a  call    ?LogEventMessage1@@YAJ_KPEBU_EVENT_DESCRIPTOR@@PEBG@Z; LogEventMessage1(unsigned __int64,_EVENT_DESCRIPTOR const *,ushort const *)
0x14003846f  mov     r8d, [rbp+57h+ExitCode]
0x140038473  lea     rcx, aCupdatemanager_37; "CUpdateManager::RunScript - Script \"%s"...
0x14003847a  mov     r9d, r8d
0x14003847d  mov     rdx, r14
0x140038480  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140038485  jmp     short loc_14003849B
0x140038487  mov     rdx, r14
0x14003848a  lea     rcx, aScriptutilsChe; "ScriptUtils::CheckExistence - File \"%s"...
0x140038491  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140038496  mov     ebx, 80070002h
0x14003849b  mov     rcx, [rbp+57h+pExecInfo.hProcess]; hObject
0x14003849f  lea     rax, [rcx-1]
0x1400384a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400384a7  ja      short loc_1400384B7
0x1400384a9  call    cs:__imp_CloseHandle
0x1400384af  mov     [rbp+57h+pExecInfo.hProcess], 0
0x1400384b7  test    ebx, ebx
0x1400384b9  jns     short loc_1400384DB
0x1400384bb  xorps   xmm0, xmm0
0x1400384be  xor     eax, eax
0x1400384c0  mov     r9, r14; unsigned __int16 *
0x1400384c3  mov     [rbp+57h+var_30], eax
0x1400384c6  mov     r8d, ebx; int
0x1400384c9  movups  [rbp+57h+var_40], xmm0
0x1400384cd  call    ?LogEventMessageHr@@YAJ_KPEBU_EVENT_DESCRIPTOR@@JPEBG@Z; LogEventMessageHr(unsigned __int64,_EVENT_DESCRIPTOR const *,long,ushort const *)
0x1400384d2  lea     rcx, aCupdatemanager_13; "CUpdateManager::RunScript - Script \"%s"...
0x1400384d9  jmp     short loc_1400384E2
0x1400384db  lea     rcx, aCupdatemanager_8; "CUpdateManager::RunScript - Script \"%s"...
0x1400384e2  mov     rdx, r14
0x1400384e5  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400384ea  mov     eax, ebx
0x1400384ec  mov     rcx, [rbp+57h+var_28]
0x1400384f0  xor     rcx, rsp; StackCookie
0x1400384f3  call    __security_check_cookie
0x1400384f8  lea     r11, [rsp+100h+var_20]
0x140038500  mov     rbx, [r11+30h]
0x140038504  mov     rsi, [r11+48h]
0x140038508  mov     rsp, r11
0x14003850b  pop     r15
0x14003850d  pop     r14
0x14003850f  pop     r12
0x140038511  pop     rdi
0x140038512  pop     rbp
0x140038513  retn
```
