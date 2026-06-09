# StartDeviceInstallThreadAndWait

- ea: `0x140009050`
- end: `0x140009702`
- name: `StartDeviceInstallThreadAndWait`
- size: `1714`
- prototype: `__int64 __fastcall(ULONG (__stdcall *)(PVOID Parameter), _QWORD *, DWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140009820`

## callees

- `0x140001a38`
- `0x1400070bc`
- `0x1400088c8`
- `0x140008d7c`
- `0x140009050`
- `0x1400165ac`
- `0x140018dc0`
- `0x14002102c`
- `0x140045f30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1400092fb`
- `msvcrt!_wcsicmp` at `0x1400092fb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14000922d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14000922d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400091a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400094c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400094ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400091a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400094c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400094ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140009557`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140009557`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000918e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000918e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1400094b7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1400094b7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140009252`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140009252`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400096de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400096de`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400092bf`
- `DEVRTL!DevRtlWriteTextLog` at `0x140009355`
- `DEVRTL!DevRtlWriteTextLog` at `0x140009551`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400096ca`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400092bf`
- `DEVRTL!DevRtlWriteTextLog` at `0x140009355`
- `DEVRTL!DevRtlWriteTextLog` at `0x140009551`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400096ca`

## string_xrefs

- `0x1400092a4`: `Device install process waited for %llu ms between heartbeats, more than double the expected %llu ms.`
- `0x14000933a`: `Device install process timeout waiting for device '%ws'.`
- `0x140009536`: `Device install process timeout exceeded. Error = 0x%08X [%d]`
- `0x1400096af`: `Device install status committed.`

## pseudocode

```c
__int64 __fastcall StartDeviceInstallThreadAndWait(ULONG (__stdcall *a1)(PVOID Parameter), _QWORD *a2, DWORD a3)
{
  LPDWORD lpThreadId; // [rsp+28h] [rbp-420h]
  int v5; // [rsp+40h] [rbp-408h]
  DWORD ExitCode; // [rsp+44h] [rbp-404h] BYREF
  DWORD v7; // [rsp+48h] [rbp-400h]
  DWORD dwMilliseconds; // [rsp+4Ch] [rbp-3FCh]
  DWORD v9; // [rsp+50h] [rbp-3F8h]
  __int64 v10; // [rsp+58h] [rbp-3F0h]
  DWORD CurrentProcessId; // [rsp+60h] [rbp-3E8h]
  _QWORD *v12; // [rsp+68h] [rbp-3E0h]
  HANDLE hThread; // [rsp+70h] [rbp-3D8h]
  DWORD ThreadId; // [rsp+78h] [rbp-3D0h] BYREF
  BOOL v15; // [rsp+7Ch] [rbp-3CCh]
  DWORD v16; // [rsp+80h] [rbp-3C8h]
  unsigned __int64 v17; // [rsp+88h] [rbp-3C0h]
  __int64 v18; // [rsp+90h] [rbp-3B8h]
  __int64 v19; // [rsp+98h] [rbp-3B0h]
  __int64 CurrentTickCount; // [rsp+A0h] [rbp-3A8h]
  __int64 v21; // [rsp+A8h] [rbp-3A0h]
  _BYTE *v22; // [rsp+B0h] [rbp-398h]
  __int64 v23; // [rsp+B8h] [rbp-390h]
  HANDLE Handles[2]; // [rsp+C0h] [rbp-388h] BYREF
  _QWORD v25[6]; // [rsp+D0h] [rbp-378h] BYREF
  _BYTE v26[16]; // [rsp+100h] [rbp-348h] BYREF
  wchar_t String2[200]; // [rsp+110h] [rbp-338h] BYREF
  wchar_t String1[200]; // [rsp+2A0h] [rbp-1A8h] BYREF

  ExitCode = 0;
  CurrentProcessId = 0;
  ThreadId = 0;
  v7 = 0;
  dwMilliseconds = 20000;
  CurrentTickCount = 0;
  memset(Handles, 0, sizeof(Handles));
  v19 = 0;
  v17 = 0;
  v18 = 0;
  v21 = 0;
  v9 = 0;
  memset(v26, 0, sizeof(v26));
  v22 = 0;
  v5 = 0;
  memset(v25, 0, sizeof(v25));
  v10 = 0;
  v12 = a2;
  hThread = CreateThread(0, 0, a1, a2, 0, &ThreadId);
  if ( !hThread )
  {
    ExitCode = GetLastError();
    goto LABEL_40;
  }
  Handles[0] = g_hResetTimeoutEvent;
  Handles[1] = hThread;
  if ( a3 < dwMilliseconds )
    dwMilliseconds = a3;
  CurrentTickCount = GetCurrentTickCount();
  while ( 1 )
  {
    do
    {
      v19 = GetCurrentTickCount();
      v7 = WaitForMultipleObjectsEx(2u, Handles, 0, dwMilliseconds, 0);
      v17 = GetCurrentTickCount();
      if ( v7 != 258 )
        goto LABEL_21;
    }
    while ( IsDebuggerPresent() );
    if ( 2 * dwMilliseconds <= v17 - v19 )
    {
      LODWORD(lpThreadId) = dwMilliseconds;
      DevRtlWriteTextLog(
        v12[5],
        1,
        2,
        "Device install process waited for %llu ms between heartbeats, more than double the expected %llu ms.",
        v17 - v19,
        lpThreadId);
    }
    if ( !(unsigned int)GetActiveQueryRemoveDevice(String1, 0xC8u) )
    {
      v23 = 0;
      String2[0] = 0;
      v18 = 0;
      goto LABEL_20;
    }
    if ( !v18 || _wcsicmp(String1, String2) )
    {
      if ( StringCchCopyW(String2, 0xC8u, String1) >= 0 )
        v18 = GetCurrentTickCount();
      goto LABEL_20;
    }
    if ( v17 > v18 + 120000 )
      break;
LABEL_20:
    ++v21;
    if ( v17 > (unsigned __int64)a3 + CurrentTickCount )
    {
LABEL_21:
      if ( v7 )
        goto LABEL_23;
      CurrentTickCount = GetCurrentTickCount();
      v21 = 0;
    }
  }
  v7 = 258;
  v5 = 4;
  DevRtlWriteTextLog(v12[5], 1, 1, "Device install process timeout waiting for device '%ws'.", String2);
LABEL_23:
  if ( v7 == 258 )
  {
    v9 = DetectQueryRemoveDeviceHang(v12[2], v12[5]);
    if ( v9 )
    {
      ExitCode = v9;
      if ( v9 == 480 || v9 == 481 )
        v5 = 4;
      else
        v5 = 5;
    }
    else
    {
      ExitCode = 1460;
      v5 = 3;
    }
  }
  else if ( v7 == 1 )
  {
    if ( GetExitCodeThread(hThread, &ExitCode) )
    {
      if ( ExitCode )
        v5 = 2;
    }
    else
    {
      ExitCode = GetLastError();
      v5 = 2;
    }
  }
  else
  {
    if ( v7 == -1 )
      ExitCode = GetLastError();
    else
      ExitCode = 13;
    v5 = 1;
  }
LABEL_40:
  if ( v5 == 3 || v5 == 4 || v5 == 5 )
  {
    DevRtlWriteTextLog(v12[5], 1, 1114113, "Device install process timeout exceeded. Error = 0x%08X [%d]", ExitCode, v5);
    CurrentProcessId = GetCurrentProcessId();
  }
  if ( v5 && v5 != 2 )
  {
    DrvInstActionCallback(8, (unsigned int *)v25);
    v10 = v25[5];
    if ( v25[5] )
      *(_DWORD *)(v10 + 2964) = ExitCode;
    DrvInstActionCallback(19, (unsigned int *)v25);
    if ( v10 )
      *(_QWORD *)(v10 + 2984) = v25[5];
    DrvInstActionCallback(15, (unsigned int *)v25);
    if ( v25[5] )
      v22 = (_BYTE *)v25[5];
    else
      v22 = v26;
    v15 = v5 == 4 || v10 && *(_QWORD *)(v10 + 2984);
    if ( CurrentProcessId )
      v16 = ThreadId;
    else
      v16 = 0;
    CommitDeviceInstallStatus((_DWORD)v22, v10, CurrentProcessId, v16, v15, 0, v12[5]);
    DevRtlWriteTextLog(v12[5], 1, 5, "Device install status committed.");
  }
  if ( hThread )
    CloseHandle(hThread);
  return ExitCode;
}

```

## disassembly

```asm
0x140009050  mov     [rsp+arg_10], r8d
0x140009055  mov     [rsp+lpParameter], rdx
0x14000905a  mov     [rsp+lpStartAddress], rcx
0x14000905f  push    rdi
0x140009060  sub     rsp, 440h
0x140009067  mov     rax, cs:__security_cookie
0x14000906e  xor     rax, rsp
0x140009071  mov     [rsp+448h+var_18], rax
0x140009079  mov     [rsp+448h+ExitCode], 0
0x140009081  mov     [rsp+448h+hThread], 0
0x14000908a  mov     [rsp+448h+var_3E8], 0
0x140009092  mov     [rsp+448h+ThreadId], 0
0x14000909a  mov     [rsp+448h+var_400], 0
0x1400090a2  mov     [rsp+448h+dwMilliseconds], 4E20h
0x1400090aa  mov     [rsp+448h+var_3A8], 0
0x1400090b6  lea     rax, [rsp+448h+Handles]
0x1400090be  mov     rdi, rax
0x1400090c1  xor     eax, eax
0x1400090c3  mov     ecx, 10h
0x1400090c8  rep stosb
0x1400090ca  mov     [rsp+448h+var_3B0], 0
0x1400090d6  mov     [rsp+448h+var_3C0], 0
0x1400090e2  mov     [rsp+448h+var_3B8], 0
0x1400090ee  mov     [rsp+448h+var_3A0], 0
0x1400090fa  mov     [rsp+448h+var_3F8], 0
0x140009102  lea     rax, [rsp+448h+var_348]
0x14000910a  mov     rdi, rax
0x14000910d  xor     eax, eax
0x14000910f  mov     ecx, 10h
0x140009114  rep stosb
0x140009116  mov     [rsp+448h+var_398], 0
0x140009122  mov     [rsp+448h+var_408], 0
0x14000912a  lea     rax, [rsp+448h+var_374]
0x140009132  mov     rdi, rax
0x140009135  xor     eax, eax
0x140009137  mov     ecx, 4
0x14000913c  rep stosb
0x14000913e  lea     rax, [rsp+448h+var_378]
0x140009146  mov     rdi, rax
0x140009149  xor     eax, eax
0x14000914b  mov     ecx, 30h ; '0'
0x140009150  rep stosb
0x140009152  mov     [rsp+448h+var_3F0], 0
0x14000915b  mov     rax, [rsp+448h+lpParameter]
0x140009163  mov     [rsp+448h+var_3E0], rax
0x140009168  lea     rax, [rsp+448h+ThreadId]
0x14000916d  mov     [rsp+448h+lpThreadId], rax; lpThreadId
0x140009172  mov     [rsp+448h+dwCreationFlags], 0; dwCreationFlags
0x14000917a  mov     r9, [rsp+448h+lpParameter]; lpParameter
0x140009182  mov     r8, [rsp+448h+lpStartAddress]; lpStartAddress
0x14000918a  xor     edx, edx; dwStackSize
0x14000918c  xor     ecx, ecx; lpThreadAttributes
0x14000918e  call    cs:__imp_CreateThread
0x140009194  mov     [rsp+448h+hThread], rax
0x140009199  cmp     [rsp+448h+hThread], 0
0x14000919f  jnz     short loc_1400091B0
0x1400091a1  call    cs:__imp_GetLastError
0x1400091a7  mov     [rsp+448h+ExitCode], eax
0x1400091ab  jmp     loc_140009511
0x1400091b0  mov     eax, 8
0x1400091b5  imul    rax, 0
0x1400091b9  mov     rcx, cs:g_hResetTimeoutEvent
0x1400091c0  mov     [rsp+rax+448h+Handles], rcx
0x1400091c8  mov     eax, 8
0x1400091cd  imul    rax, 1
0x1400091d1  mov     rcx, [rsp+448h+hThread]
0x1400091d6  mov     [rsp+rax+448h+Handles], rcx
0x1400091de  mov     eax, [rsp+448h+dwMilliseconds]
0x1400091e2  cmp     [rsp+448h+arg_10], eax
0x1400091e9  jnb     short loc_1400091F6
0x1400091eb  mov     eax, [rsp+448h+arg_10]
0x1400091f2  mov     [rsp+448h+dwMilliseconds], eax
0x1400091f6  call    GetCurrentTickCount
0x1400091fb  mov     [rsp+448h+var_3A8], rax
0x140009203  call    GetCurrentTickCount
0x140009208  mov     [rsp+448h+var_3B0], rax
0x140009210  mov     [rsp+448h+dwCreationFlags], 0; bAlertable
0x140009218  mov     r9d, [rsp+448h+dwMilliseconds]; dwMilliseconds
0x14000921d  xor     r8d, r8d; bWaitAll
0x140009220  lea     rdx, [rsp+448h+Handles]; lpHandles
0x140009228  mov     ecx, 2; nCount
0x14000922d  call    cs:__imp_WaitForMultipleObjectsEx
0x140009233  mov     [rsp+448h+var_400], eax
0x140009237  call    GetCurrentTickCount
0x14000923c  mov     [rsp+448h+var_3C0], rax
0x140009244  cmp     [rsp+448h+var_400], 102h
0x14000924c  jnz     loc_14000940C
0x140009252  call    cs:__imp_IsDebuggerPresent
0x140009258  test    eax, eax
0x14000925a  jz      short loc_14000925E
0x14000925c  jmp     short loc_140009203
0x14000925e  mov     eax, [rsp+448h+dwMilliseconds]
0x140009262  shl     eax, 1
0x140009264  mov     eax, eax
0x140009266  mov     rcx, [rsp+448h+var_3B0]
0x14000926e  mov     rdx, [rsp+448h+var_3C0]
0x140009276  sub     rdx, rcx
0x140009279  mov     rcx, rdx
0x14000927c  cmp     rax, rcx
0x14000927f  ja      short loc_1400092C6
0x140009281  mov     rax, [rsp+448h+var_3B0]
0x140009289  mov     rcx, [rsp+448h+var_3C0]
0x140009291  sub     rcx, rax
0x140009294  mov     rax, rcx
0x140009297  mov     ecx, [rsp+448h+dwMilliseconds]
0x14000929b  mov     dword ptr [rsp+448h+lpThreadId], ecx
0x14000929f  mov     qword ptr [rsp+448h+dwCreationFlags], rax
0x1400092a4  lea     r9, aDeviceInstallP_2; "Device install process waited for %llu "...
0x1400092ab  mov     r8d, 2
0x1400092b1  mov     edx, 1
0x1400092b6  mov     rax, [rsp+448h+var_3E0]
0x1400092bb  mov     rcx, [rax+28h]
0x1400092bf  call    cs:__imp_DevRtlWriteTextLog
0x1400092c5  nop
0x1400092c6  mov     edx, 0C8h; unsigned __int64
0x1400092cb  lea     rcx, [rsp+448h+String1]; unsigned __int16 *
0x1400092d3  call    GetActiveQueryRemoveDevice
0x1400092d8  test    eax, eax
0x1400092da  jz      loc_140009390
0x1400092e0  cmp     [rsp+448h+var_3B8], 0
0x1400092e9  jz      short loc_140009363
0x1400092eb  lea     rdx, [rsp+448h+String2]; String2
0x1400092f3  lea     rcx, [rsp+448h+String1]; String1
0x1400092fb  call    cs:__imp__wcsicmp
0x140009301  test    eax, eax
0x140009303  jnz     short loc_140009363
0x140009305  mov     rax, [rsp+448h+var_3B8]
0x14000930d  add     rax, 1D4C0h
0x140009313  cmp     [rsp+448h+var_3C0], rax
0x14000931b  jbe     short loc_140009361
0x14000931d  mov     [rsp+448h+var_400], 102h
0x140009325  mov     [rsp+448h+var_408], 4
0x14000932d  lea     rax, [rsp+448h+String2]
0x140009335  mov     qword ptr [rsp+448h+dwCreationFlags], rax
0x14000933a  lea     r9, aDeviceInstallP_1; "Device install process timeout waiting "...
0x140009341  mov     r8d, 1
0x140009347  mov     edx, 1
0x14000934c  mov     rax, [rsp+448h+var_3E0]
0x140009351  mov     rcx, [rax+28h]
0x140009355  call    cs:__imp_DevRtlWriteTextLog
0x14000935b  nop
0x14000935c  jmp     loc_140009438
0x140009361  jmp     short loc_14000938E
0x140009363  lea     r8, [rsp+448h+String1]; unsigned __int16 *
0x14000936b  mov     edx, 0C8h; unsigned __int64
0x140009370  lea     rcx, [rsp+448h+String2]; unsigned __int16 *
0x140009378  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000937d  test    eax, eax
0x14000937f  jl      short loc_14000938E
0x140009381  call    GetCurrentTickCount
0x140009386  mov     [rsp+448h+var_3B8], rax
0x14000938e  jmp     short loc_1400093D5
0x140009390  mov     eax, 2
0x140009395  imul    rax, 0
0x140009399  mov     [rsp+448h+var_390], rax
0x1400093a1  cmp     [rsp+448h+var_390], 190h
0x1400093ad  jnb     short loc_1400093B1
0x1400093af  jmp     short loc_1400093B7
0x1400093b1  call    __report_rangecheckfailure
0x1400093b7  xor     eax, eax
0x1400093b9  mov     rcx, [rsp+448h+var_390]
0x1400093c1  mov     [rsp+rcx+448h+String2], ax
0x1400093c9  mov     [rsp+448h+var_3B8], 0
0x1400093d5  mov     rax, [rsp+448h+var_3A0]
0x1400093dd  inc     rax
0x1400093e0  mov     [rsp+448h+var_3A0], rax
0x1400093e8  mov     eax, [rsp+448h+arg_10]
0x1400093ef  mov     rcx, [rsp+448h+var_3A8]
0x1400093f7  add     rcx, rax
0x1400093fa  mov     rax, rcx
0x1400093fd  cmp     [rsp+448h+var_3C0], rax
0x140009405  ja      short loc_14000940C
0x140009407  jmp     loc_140009203
0x14000940c  cmp     [rsp+448h+var_400], 0
0x140009411  jnz     short loc_140009431
0x140009413  call    GetCurrentTickCount
0x140009418  mov     [rsp+448h+var_3A8], rax
0x140009420  mov     [rsp+448h+var_3A0], 0
0x14000942c  jmp     loc_140009203
0x140009431  jmp     short loc_140009438
0x140009433  jmp     loc_140009203
0x140009438  cmp     [rsp+448h+var_400], 102h
0x140009440  jnz     short loc_1400094A6
0x140009442  mov     rax, [rsp+448h+var_3E0]
0x140009447  mov     rdx, [rax+28h]
0x14000944b  mov     rax, [rsp+448h+var_3E0]
0x140009450  mov     rcx, [rax+10h]
0x140009454  call    DetectQueryRemoveDeviceHang
0x140009459  mov     [rsp+448h+var_3F8], eax
0x14000945d  cmp     [rsp+448h+var_3F8], 0
0x140009462  jz      short loc_140009494
0x140009464  mov     eax, [rsp+448h+var_3F8]
0x140009468  mov     [rsp+448h+ExitCode], eax
0x14000946c  cmp     [rsp+448h+var_3F8], 1E0h
0x140009474  jz      short loc_140009480
0x140009476  cmp     [rsp+448h+var_3F8], 1E1h
0x14000947e  jnz     short loc_14000948A
0x140009480  mov     [rsp+448h+var_408], 4
0x140009488  jmp     short loc_140009492
0x14000948a  mov     [rsp+448h+var_408], 5
0x140009492  jmp     short loc_1400094A4
0x140009494  mov     [rsp+448h+ExitCode], 5B4h
0x14000949c  mov     [rsp+448h+var_408], 3
0x1400094a4  jmp     short loc_140009511
0x1400094a6  cmp     [rsp+448h+var_400], 1
0x1400094ab  jnz     short loc_1400094E6
0x1400094ad  lea     rdx, [rsp+448h+ExitCode]; lpExitCode
0x1400094b2  mov     rcx, [rsp+448h+hThread]; hThread
0x1400094b7  call    cs:__imp_GetExitCodeThread
0x1400094bd  test    eax, eax
0x1400094bf  jnz     short loc_1400094D5
0x1400094c1  call    cs:__imp_GetLastError
0x1400094c7  mov     [rsp+448h+ExitCode], eax
0x1400094cb  mov     [rsp+448h+var_408], 2
0x1400094d3  jmp     short loc_1400094E4
0x1400094d5  cmp     [rsp+448h+ExitCode], 0
0x1400094da  jz      short loc_1400094E4
0x1400094dc  mov     [rsp+448h+var_408], 2
0x1400094e4  jmp     short loc_140009511
0x1400094e6  cmp     [rsp+448h+var_400], 0FFFFFFFFh
0x1400094eb  jnz     short loc_140009501
0x1400094ed  call    cs:__imp_GetLastError
0x1400094f3  mov     [rsp+448h+ExitCode], eax
0x1400094f7  mov     [rsp+448h+var_408], 1
0x1400094ff  jmp     short loc_140009511
0x140009501  mov     [rsp+448h+ExitCode], 0Dh
0x140009509  mov     [rsp+448h+var_408], 1
0x140009511  cmp     [rsp+448h+var_408], 3
0x140009516  jz      short loc_140009526
0x140009518  cmp     [rsp+448h+var_408], 4
0x14000951d  jz      short loc_140009526
0x14000951f  cmp     [rsp+448h+var_408], 5
0x140009524  jnz     short loc_140009561
0x140009526  mov     eax, [rsp+448h+var_408]
0x14000952a  mov     dword ptr [rsp+448h+lpThreadId], eax
0x14000952e  mov     eax, [rsp+448h+ExitCode]
0x140009532  mov     [rsp+448h+dwCreationFlags], eax
0x140009536  lea     r9, aDeviceInstallP_0; "Device install process timeout exceeded"...
0x14000953d  mov     r8d, 110001h
0x140009543  mov     edx, 1
0x140009548  mov     rax, [rsp+448h+var_3E0]
0x14000954d  mov     rcx, [rax+28h]
0x140009551  call    cs:__imp_DevRtlWriteTextLog
0x140009557  call    cs:__imp_GetCurrentProcessId
0x14000955d  mov     [rsp+448h+var_3E8], eax
0x140009561  cmp     [rsp+448h+var_408], 0
0x140009566  jz      loc_1400096D1
0x14000956c  cmp     [rsp+448h+var_408], 2
0x140009571  jz      loc_1400096D1
0x140009577  xor     r8d, r8d
0x14000957a  lea     rdx, [rsp+448h+var_378]
0x140009582  mov     ecx, 8
0x140009587  call    DrvInstActionCallback
0x14000958c  mov     rax, [rsp+448h+var_350]
0x140009594  mov     [rsp+448h+var_3F0], rax
0x140009599  cmp     [rsp+448h+var_3F0], 0
0x14000959f  jz      short loc_1400095B0
0x1400095a1  mov     rax, [rsp+448h+var_3F0]
0x1400095a6  mov     ecx, [rsp+448h+ExitCode]
0x1400095aa  mov     [rax+0B94h], ecx
0x1400095b0  xor     r8d, r8d
0x1400095b3  lea     rdx, [rsp+448h+var_378]
0x1400095bb  mov     ecx, 13h
0x1400095c0  call    DrvInstActionCallback
0x1400095c5  cmp     [rsp+448h+var_3F0], 0
0x1400095cb  jz      short loc_1400095E1
0x1400095cd  mov     rax, [rsp+448h+var_3F0]
0x1400095d2  mov     rcx, [rsp+448h+var_350]
0x1400095da  mov     [rax+0BA8h], rcx
0x1400095e1  xor     r8d, r8d
0x1400095e4  lea     rdx, [rsp+448h+var_378]
0x1400095ec  mov     ecx, 0Fh
0x1400095f1  call    DrvInstActionCallback
0x1400095f6  cmp     [rsp+448h+var_350], 0
0x1400095ff  jz      short loc_140009613
0x140009601  mov     rax, [rsp+448h+var_350]
0x140009609  mov     [rsp+448h+var_398], rax
0x140009611  jmp     short loc_140009623
0x140009613  lea     rax, [rsp+448h+var_348]
0x14000961b  mov     [rsp+448h+var_398], rax
0x140009623  cmp     [rsp+448h+var_408], 4
0x140009628  jz      short loc_14000964B
0x14000962a  cmp     [rsp+448h+var_3F0], 0
0x140009630  jz      short loc_140009641
0x140009632  mov     rax, [rsp+448h+var_3F0]
0x140009637  cmp     qword ptr [rax+0BA8h], 0
0x14000963f  jnz     short loc_14000964B
0x140009641  mov     [rsp+448h+var_3CC], 0
0x140009649  jmp     short loc_140009653
0x14000964b  mov     [rsp+448h+var_3CC], 1
0x140009653  cmp     [rsp+448h+var_3E8], 0
0x140009658  jz      short loc_140009667
0x14000965a  mov     eax, [rsp+448h+ThreadId]
0x14000965e  mov     [rsp+448h+var_3C8], eax
0x140009665  jmp     short loc_140009672
0x140009667  mov     [rsp+448h+var_3C8], 0
0x140009672  mov     rax, [rsp+448h+var_3E0]
0x140009677  mov     rax, [rax+28h]
0x14000967b  mov     [rsp+448h+var_418], rax
0x140009680  mov     dword ptr [rsp+448h+lpThreadId], 0
  ... truncated ...
```
