# wWinMain

- ea: `0x1400054fc`
- end: `0x14000598a`
- name: `wWinMain`
- size: `1166`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140001450`

## callees

- `0x140001010`
- `0x14000113c`
- `0x140001600`
- `0x14000415c`
- `0x140004a10`
- `0x140004a2c`
- `0x140004dcc`
- `0x140004e5c`
- `0x140004f48`
- `0x140005030`
- `0x1400050e4`
- `0x140005110`
- `0x140005484`
- `0x1400054fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140005655`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140005686`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140005702`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140005729`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140005655`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140005686`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140005702`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140005729`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x140005630`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1400056ab`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x140005743`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x14000586b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x140005886`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1400058a1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x140005630`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1400056ab`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x140005743`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x14000586b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x140005886`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1400058a1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1400056d7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1400056d7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000584c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000584c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400057b6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400057b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005859`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005859`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005799`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000554e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000554e`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1400055ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1400055ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000552e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000552e`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1400055fe`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1400055fe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400057d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400057d8`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1400058d3`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1400058d3`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140005781`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140005781`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x140005540`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x140005540`

## string_xrefs

- `0x140005912`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`
- `0x140005928`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`
- `0x140005941`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`
- `0x140005957`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`
- `0x1400057cb`: `browserbroker.dll`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int v5; // edi
  HANDLE CurrentProcess; // rax
  unsigned int v7; // ecx
  signed int LastError; // eax
  int v9; // esi
  char v10; // r14
  wchar_t *v11; // rbx
  wchar_t *v12; // rax
  int v13; // ecx
  unsigned int v14; // r8d
  const char *v15; // r9
  const char *v16; // r9
  HRESULT v17; // eax
  const char *v18; // r9
  int v19; // eax
  void *v20; // rcx
  unsigned __int16 *v21; // rbx
  unsigned int v22; // r8d
  const char *v23; // r9
  wchar_t *v24; // rdi
  unsigned int v25; // r8d
  const char *v26; // r9
  wchar_t *v27; // rax
  REGHANDLE v28; // rcx
  int v30; // [rsp+20h] [rbp-49h]
  char v31; // [rsp+30h] [rbp-39h] BYREF
  wchar_t *EndPtr; // [rsp+38h] [rbp-31h] BYREF
  wchar_t *Context[10]; // [rsp+40h] [rbp-29h] BYREF
  wchar_t Delimiter[8]; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v5 = 0;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(hInstance, hPrevInstance, lpCmdLine, nShowCmd);
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)SetProcessInformation(CurrentProcess, 3, 0, 0) )
  {
    v7 = 0;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( (unsigned int)dword_14000B000 > 5
    && (qword_14000B010 & 0x400000000000LL) != 0
    && (qword_14000B018 & 0x400000000000LL) == qword_14000B018 )
  {
    LODWORD(EndPtr) = v7;
    Context[8] = (wchar_t *)&EndPtr;
    v31 = 1;
    Context[6] = (wchar_t *)&v31;
    Context[9] = (wchar_t *)4;
    v30 = 4;
    Context[7] = (wchar_t *)1;
    tlgWriteTransfer_BrowserWriteTransfer(&dword_14000B000, byte_140008FF1, 0, 0);
  }
  SetErrorMode(1u);
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  v9 = 0;
  wcscpy(Delimiter, L" ,\t\n");
  v10 = 0;
  Context[0] = 0;
  v11 = wcstok_s(lpCmdLine, Delimiter, Context);
  if ( v11 )
  {
    while ( 1 )
    {
      if ( !(unsigned int)_o__wcsnicmp(v11, L"-Embedding", 11) )
      {
        v10 = 1;
        g_fMultiUse = 0;
        g_fMayExitProcess = 1;
        g_ShutdownWaitInMilleseconds = 30000;
      }
      if ( !(unsigned int)_o__wcsnicmp(v11, L"-Multiuse", 10) )
      {
        v10 = 1;
        g_fMultiUse = 1;
        g_fMayExitProcess = 1;
        v12 = wcstok_s(0, Delimiter, Context);
        v11 = v12;
        if ( v12 )
        {
          EndPtr = 0;
          v13 = 1000 * wcstol(v12, &EndPtr, 10);
          if ( EndPtr == v11 )
            v9 = 99;
          g_ShutdownWaitInMilleseconds = v13;
        }
        else
        {
          g_ShutdownWaitInMilleseconds = 300000;
        }
      }
      if ( !(unsigned int)_o__wcsnicmp(v11, L"-Infinite", 10) )
      {
        v10 = 1;
        g_fMayExitProcess = 0;
        g_fMultiUse = 1;
      }
      if ( !(unsigned int)_o__wcsnicmp(v11, L"-IOAVHost", 10) )
        break;
      ++v9;
      v11 = wcstok_s(0, Delimiter, Context);
      if ( !v11 )
      {
        v5 = 0;
        if ( v9 == 1 && v10 )
        {
          SetProcessCIPolicy();
          SetProcessACGPolicy();
          LODWORD(EndPtr) = 3;
          if ( !(unsigned int)SetProcessMitigationPolicy(3, &EndPtr, 4) )
            wil::details::in1diag3::_FailFast_Unexpected(retaddr, (void *)0x1EC, v14, v15);
          g_hQuitEvent = CreateEventW(0, 1, 0, 0);
          if ( !g_hQuitEvent )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0x270,
              (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
              v16);
          v17 = CoInitializeEx(0, 2u);
          if ( v17 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x272,
              (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
              (const char *)(unsigned int)v17,
              v30);
          InitializeCOMSecurity_ForBrokerProcess();
          if ( !LoadLibraryExW(L"browserbroker.dll", 0, 0x800u) )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0x27A,
              (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
              v18);
          v19 = ThunkCOMServerDllMain(
                  (g_fMultiUse ? 1281 : 1025) | (g_fMayExitProcess ? 0x200 : 0),
                  COMServerCallback,
                  IncrementServerRefCount,
                  DecrementServerRefCount);
          if ( v19 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x283,
              (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
              (const char *)(unsigned int)v19,
              v30);
          WaitToCheckForServerShutdown();
          ServerMessageLoop(v20);
          v5 = ThunkCOMServerDllMain(2, 0, 0, 0);
          CoUninitialize();
          CloseHandle(g_hQuitEvent);
        }
        goto LABEL_33;
      }
    }
    v21 = wcstok_s(0, L"|", Context);
    if ( !v21 )
      wil::details::in1diag3::_FailFast_Unexpected(retaddr, (void *)0x255, v22, v23);
    v24 = wcstok_s(0, L"|", Context);
    if ( !v24 )
      wil::details::in1diag3::_FailFast_Unexpected(retaddr, (void *)0x258, v25, v26);
    v27 = wcstok_s(0, L"|", Context);
    v5 = RunIOAVPlugin(v21, v24, v27);
  }
LABEL_33:
  v28 = RegHandle;
  dword_14000B000 = 0;
  RegHandle = 0;
  EventUnregister(v28);
  return v5;
}

```

## disassembly

```asm
0x1400054fc  mov     [rsp-8+arg_0], rbx
0x140005501  mov     [rsp-8+arg_8], rsi
0x140005506  push    rbp
0x140005507  push    rdi
0x140005508  push    r14
0x14000550a  lea     rbp, [rsp-47h]
0x14000550f  sub     rsp, 0B0h
0x140005516  mov     rax, cs:__security_cookie
0x14000551d  xor     rax, rsp
0x140005520  mov     [rbp+57h+var_20], rax
0x140005524  mov     rbx, r8
0x140005527  xor     edi, edi
0x140005529  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000552e  call    cs:__imp_GetCurrentProcess
0x140005534  xor     r9d, r9d
0x140005537  lea     edx, [rdi+3]
0x14000553a  mov     rcx, rax
0x14000553d  xor     r8d, r8d
0x140005540  call    cs:__imp_SetProcessInformation
0x140005546  test    eax, eax
0x140005548  jz      short loc_14000554E
0x14000554a  xor     ecx, ecx
0x14000554c  jmp     short loc_140005563
0x14000554e  call    cs:__imp_GetLastError
0x140005554  mov     ecx, eax
0x140005556  test    eax, eax
0x140005558  jle     short loc_140005563
0x14000555a  movzx   ecx, ax
0x14000555d  or      ecx, 80070000h
0x140005563  mov     eax, cs:dword_14000B000
0x140005569  cmp     eax, 5
0x14000556c  jbe     short loc_1400055E7
0x14000556e  mov     rdx, cs:qword_14000B018
0x140005575  mov     r8, 400000000000h
0x14000557f  mov     rax, cs:qword_14000B010
0x140005586  test    r8, rax
0x140005589  jz      short loc_1400055E7
0x14000558b  mov     rax, rdx
0x14000558e  and     rax, r8
0x140005591  cmp     rax, rdx
0x140005594  jnz     short loc_1400055E7
0x140005596  lea     rax, [rbp+57h+EndPtr]
0x14000559a  mov     dword ptr [rbp+57h+EndPtr], ecx
0x14000559d  mov     [rbp+57h+var_40], rax
0x1400055a1  lea     rdx, byte_140008FF1
0x1400055a8  lea     rax, [rbp+57h+var_90]
0x1400055ac  mov     [rbp+57h+var_90], 1
0x1400055b0  mov     [rbp+57h+var_50], rax
0x1400055b4  lea     rcx, dword_14000B000
0x1400055bb  lea     rax, [rbp+57h+var_70]
0x1400055bf  mov     [rbp+57h+var_38], 4
0x1400055c7  mov     [rsp+0C0h+var_98], rax
0x1400055cc  xor     r9d, r9d
0x1400055cf  xor     r8d, r8d
0x1400055d2  mov     [rsp+0C0h+var_A0], 4; int
0x1400055da  mov     [rbp+57h+var_48], 1
0x1400055e2  call    _tlgWriteTransfer_BrowserWriteTransfer
0x1400055e7  mov     ecx, 1; uMode
0x1400055ec  call    cs:__imp_SetErrorMode
0x1400055f2  xor     r9d, r9d; HeapInformationLength
0x1400055f5  xor     r8d, r8d; HeapInformation
0x1400055f8  xor     ecx, ecx; HeapHandle
0x1400055fa  lea     edx, [r9+1]; HeapInformationClass
0x1400055fe  call    cs:__imp_HeapSetInformation
0x140005604  movsd   xmm0, qword ptr cs:asc_140008A48; " ,\t\n"
0x14000560c  lea     r8, [rbp+57h+Context]; Context
0x140005610  movzx   eax, word ptr cs:asc_140008A48+8; ""
0x140005617  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x14000561b  xor     esi, esi
0x14000561d  movsd   qword ptr [rbp+57h+Delimiter], xmm0
0x140005622  mov     rcx, rbx; String
0x140005625  mov     [rbp+57h+var_28], ax
0x140005629  xor     r14b, r14b
0x14000562c  mov     [rbp+57h+Context], rsi
0x140005630  call    cs:__imp_wcstok_s
0x140005636  mov     rbx, rax
0x140005639  test    rax, rax
0x14000563c  jz      loc_1400058B7
0x140005642  lea     edi, [rsi+0Ah]
0x140005645  mov     r8d, 0Bh
0x14000564b  lea     rdx, aEmbedding; "-Embedding"
0x140005652  mov     rcx, rbx
0x140005655  call    cs:__imp__o__wcsnicmp
0x14000565b  test    eax, eax
0x14000565d  jnz     short loc_140005679
0x14000565f  mov     r14b, 1
0x140005662  mov     cs:?g_fMultiUse@@3_NA, al; bool g_fMultiUse
0x140005668  mov     cs:?g_fMayExitProcess@@3_NA, r14b; bool g_fMayExitProcess
0x14000566f  mov     cs:?g_ShutdownWaitInMilleseconds@@3KA, 7530h; ulong g_ShutdownWaitInMilleseconds
0x140005679  mov     r8, rdi
0x14000567c  lea     rdx, aMultiuse; "-Multiuse"
0x140005683  mov     rcx, rbx
0x140005686  call    cs:__imp__o__wcsnicmp
0x14000568c  test    eax, eax
0x14000568e  jnz     short loc_1400056F5
0x140005690  mov     r14b, 1
0x140005693  lea     r8, [rbp+57h+Context]; Context
0x140005697  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x14000569b  mov     cs:?g_fMultiUse@@3_NA, r14b; bool g_fMultiUse
0x1400056a2  xor     ecx, ecx; String
0x1400056a4  mov     cs:?g_fMayExitProcess@@3_NA, r14b; bool g_fMayExitProcess
0x1400056ab  call    cs:__imp_wcstok_s
0x1400056b1  mov     rbx, rax
0x1400056b4  test    rax, rax
0x1400056b7  jnz     short loc_1400056C5
0x1400056b9  mov     cs:?g_ShutdownWaitInMilleseconds@@3KA, 493E0h; ulong g_ShutdownWaitInMilleseconds
0x1400056c3  jmp     short loc_1400056F5
0x1400056c5  mov     r8d, edi; Radix
0x1400056c8  mov     [rbp+57h+EndPtr], 0
0x1400056d0  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x1400056d4  mov     rcx, rbx; String
0x1400056d7  call    cs:__imp_wcstol
0x1400056dd  imul    ecx, eax, 3E8h
0x1400056e3  mov     eax, 63h ; 'c'
0x1400056e8  cmp     [rbp+57h+EndPtr], rbx
0x1400056ec  cmovz   esi, eax
0x1400056ef  mov     cs:?g_ShutdownWaitInMilleseconds@@3KA, ecx; ulong g_ShutdownWaitInMilleseconds
0x1400056f5  mov     r8, rdi
0x1400056f8  lea     rdx, aInfinite; "-Infinite"
0x1400056ff  mov     rcx, rbx
0x140005702  call    cs:__imp__o__wcsnicmp
0x140005708  test    eax, eax
0x14000570a  jnz     short loc_14000571C
0x14000570c  mov     r14b, 1
0x14000570f  mov     cs:?g_fMayExitProcess@@3_NA, al; bool g_fMayExitProcess
0x140005715  mov     cs:?g_fMultiUse@@3_NA, r14b; bool g_fMultiUse
0x14000571c  mov     r8, rdi
0x14000571f  lea     rdx, aIoavhost; "-IOAVHost"
0x140005726  mov     rcx, rbx
0x140005729  call    cs:__imp__o__wcsnicmp
0x14000572f  xor     ecx, ecx; String
0x140005731  lea     r8, [rbp+57h+Context]; Context
0x140005735  test    eax, eax
0x140005737  jz      loc_140005861
0x14000573d  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x140005741  inc     esi
0x140005743  call    cs:__imp_wcstok_s
0x140005749  mov     rbx, rax
0x14000574c  test    rax, rax
0x14000574f  jnz     loc_140005645
0x140005755  xor     edi, edi
0x140005757  cmp     esi, 1
0x14000575a  jnz     loc_1400058B7
0x140005760  test    r14b, r14b
0x140005763  jz      loc_1400058B7
0x140005769  call    ?SetProcessCIPolicy@@YAXXZ; SetProcessCIPolicy(void)
0x14000576e  call    ?SetProcessACGPolicy@@YAXXZ; SetProcessACGPolicy(void)
0x140005773  lea     ecx, [rbx+3]
0x140005776  lea     r8d, [rbx+4]
0x14000577a  mov     dword ptr [rbp+57h+EndPtr], ecx
0x14000577d  lea     rdx, [rbp+57h+EndPtr]
0x140005781  call    cs:__imp_SetProcessMitigationPolicy
0x140005787  test    eax, eax
0x140005789  jz      loc_1400058FF
0x14000578f  xor     r9d, r9d; lpName
0x140005792  xor     r8d, r8d; bInitialState
0x140005795  mov     edx, esi; bManualReset
0x140005797  xor     ecx, ecx; lpEventAttributes
0x140005799  call    cs:__imp_CreateEventW
0x14000579f  mov     cs:?g_hQuitEvent@@3PEAXEA, rax; void * g_hQuitEvent
0x1400057a6  test    rax, rax
0x1400057a9  jz      loc_14000590E
0x1400057af  lea     ebx, [rdi+2]
0x1400057b2  xor     ecx, ecx; pvReserved
0x1400057b4  mov     edx, ebx; dwCoInit
0x1400057b6  call    cs:__imp_CoInitializeEx
0x1400057bc  test    eax, eax
0x1400057be  js      loc_140005924
0x1400057c4  call    _InitializeCOMSecurity_ForBrokerProcess
0x1400057c9  xor     edx, edx; hFile
0x1400057cb  lea     rcx, LibFileName; "browserbroker.dll"
0x1400057d2  mov     r8d, 800h; dwFlags
0x1400057d8  call    cs:__imp_LoadLibraryExW
0x1400057de  test    rax, rax
0x1400057e1  jz      loc_14000593D
0x1400057e7  mov     al, cs:?g_fMultiUse@@3_NA; bool g_fMultiUse
0x1400057ed  lea     r9, ?DecrementServerRefCount@@YAJXZ; DecrementServerRefCount(void)
0x1400057f4  neg     al
0x1400057f6  lea     r8, ?IncrementServerRefCount@@YAJXZ; IncrementServerRefCount(void)
0x1400057fd  mov     al, cs:?g_fMayExitProcess@@3_NA; bool g_fMayExitProcess
0x140005803  sbb     edx, edx
0x140005805  and     edx, 100h
0x14000580b  add     edx, 401h
0x140005811  neg     al
0x140005813  sbb     ecx, ecx
0x140005815  and     ecx, 200h
0x14000581b  or      ecx, edx
0x14000581d  lea     rdx, ?COMServerCallback@@YAJK@Z; COMServerCallback(ulong)
0x140005824  call    _ThunkCOMServerDllMain
0x140005829  test    eax, eax
0x14000582b  js      loc_140005953
0x140005831  call    ?WaitToCheckForServerShutdown@@YAHXZ; WaitToCheckForServerShutdown(void)
0x140005836  call    ?ServerMessageLoop@@YAXPEAX@Z; ServerMessageLoop(void *)
0x14000583b  xor     r9d, r9d
0x14000583e  xor     r8d, r8d
0x140005841  xor     edx, edx
0x140005843  mov     ecx, ebx
0x140005845  call    _ThunkCOMServerDllMain
0x14000584a  mov     edi, eax
0x14000584c  call    cs:__imp_CoUninitialize
0x140005852  mov     rcx, cs:?g_hQuitEvent@@3PEAXEA; hObject
0x140005859  call    cs:__imp_CloseHandle
0x14000585f  jmp     short loc_1400058B7
0x140005861  lea     rsi, Delimiter; "|"
0x140005868  mov     rdx, rsi; Delimiter
0x14000586b  call    cs:__imp_wcstok_s
0x140005871  mov     rbx, rax
0x140005874  test    rax, rax
0x140005877  jz      loc_14000596C
0x14000587d  lea     r8, [rbp+57h+Context]; Context
0x140005881  mov     rdx, rsi; Delimiter
0x140005884  xor     ecx, ecx; String
0x140005886  call    cs:__imp_wcstok_s
0x14000588c  mov     rdi, rax
0x14000588f  test    rax, rax
0x140005892  jz      loc_14000597B
0x140005898  lea     r8, [rbp+57h+Context]; Context
0x14000589c  mov     rdx, rsi; Delimiter
0x14000589f  xor     ecx, ecx; String
0x1400058a1  call    cs:__imp_wcstok_s
0x1400058a7  mov     rdx, rdi; unsigned __int16 *
0x1400058aa  mov     rcx, rbx; StringUuid
0x1400058ad  mov     r8, rax; unsigned __int16 *
0x1400058b0  call    ?RunIOAVPlugin@@YAJPEBG00@Z; RunIOAVPlugin(ushort const *,ushort const *,ushort const *)
0x1400058b5  mov     edi, eax
0x1400058b7  mov     rcx, cs:RegHandle; RegHandle
0x1400058be  mov     cs:dword_14000B000, 0
0x1400058c8  mov     cs:RegHandle, 0
0x1400058d3  call    cs:__imp_EventUnregister
0x1400058d9  mov     eax, edi
0x1400058db  mov     rcx, [rbp+57h+var_20]
0x1400058df  xor     rcx, rsp; StackCookie
0x1400058e2  call    __security_check_cookie
0x1400058e7  lea     r11, [rsp+0C0h+var_10]
0x1400058ef  mov     rbx, [r11+20h]
0x1400058f3  mov     rsi, [r11+28h]
0x1400058f7  mov     rsp, r11
0x1400058fa  pop     r14
0x1400058fc  pop     rdi
0x1400058fd  pop     rbp
0x1400058fe  retn
0x1400058ff  mov     rcx, [rbp+5Fh]; this
0x140005903  mov     edx, 1ECh; void *
0x140005908  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000590e  mov     rcx, [rbp+5Fh]; this
0x140005912  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x140005919  mov     edx, 270h; void *
0x14000591e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005924  mov     rcx, [rbp+5Fh]; this
0x140005928  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x14000592f  mov     r9d, eax; char *
0x140005932  mov     edx, 272h; void *
0x140005937  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x14000593d  mov     rcx, [rbp+5Fh]; this
0x140005941  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x140005948  mov     edx, 27Ah; void *
0x14000594d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005953  mov     rcx, [rbp+5Fh]; this
0x140005957  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x14000595e  mov     r9d, eax; char *
0x140005961  mov     edx, 283h; void *
0x140005966  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x14000596c  mov     rcx, [rbp+5Fh]; this
0x140005970  mov     edx, 255h; void *
0x140005975  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000597b  mov     rcx, [rbp+5Fh]; this
0x14000597f  mov     edx, 258h; void *
0x140005984  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
