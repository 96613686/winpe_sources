# WaasMedic::UsoCleanupPlugin::PerformAction(void)

- ea: `0x18003f550`
- end: `0x18003f964`
- name: `?PerformAction@UsoCleanupPlugin@WaasMedic@@UEAAJXZ`
- size: `1044`
- prototype: `__int64 __fastcall(WaasMedic::UsoCleanupPlugin *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180009a34`
- `0x180009a54`
- `0x18000ab48`
- `0x180026920`
- `0x18002c9bc`
- `0x18003f550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f727`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f59f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f59f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003f6a8`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003f6a8`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18003f7e6`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18003f7e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f6e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f6fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f73e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f756`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f7a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f7c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f83d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f85a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f872`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f6e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f6fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f73e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f756`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f7a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f7c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f83d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f85a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f636`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f710`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f76c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f884`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f636`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f710`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f76c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f884`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003f595`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003f595`

## string_xrefs

- `0x18003f5bf`: `onecore\enduser\waasmedic\lib\plugins\usocleanupplugin.cpp`
- `0x18003f618`: `onecore\enduser\waasmedic\lib\plugins\usocleanupplugin.cpp`
- `0x18003f6c0`: `onecore\enduser\waasmedic\lib\plugins\usocleanupplugin.cpp`
- `0x18003f788`: `onecore\enduser\waasmedic\lib\plugins\usocleanupplugin.cpp`
- `0x18003f7fe`: `onecore\enduser\waasmedic\lib\plugins\usocleanupplugin.cpp`
- `0x18003f58e`: `%windir%\System32\usoclient.exe`

## pseudocode

```c
__int64 __fastcall WaasMedic::UsoCleanupPlugin::PerformAction(WaasMedic::UsoCleanupPlugin *this)
{
  signed int LastError; // eax
  unsigned int v2; // ebx
  int v4; // eax
  char *v5; // rbx
  unsigned int LastErrorMsg; // edi
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int v9; // r8d
  const char *v10; // r9
  DWORD v11; // eax
  const char *v12; // r9
  unsigned int v13; // r8d
  const char *v14; // r9
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int v19; // r8d
  const char *v20; // r9
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  int bInheritHandles; // [rsp+20h] [rbp-E0h]
  int bInheritHandlesa; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v35[2]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Dst[264]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  pv[0] = 0;
  if ( !ExpandEnvironmentStringsW(L"%windir%\\System32\\usoclient.exe", Dst, 0x104u) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (v2 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\usocleanupplugin.cpp",
        (const char *)v2,
        bInheritHandles);
    return v2;
  }
  v35[0] = *(_OWORD *)L"UsoCleanup";
  *(_QWORD *)((char *)v35 + 14) = *(_QWORD *)L"nup";
  v4 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         pv,
         L"\"%ws\" %ws",
         Dst,
         v35);
  v2 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\usocleanupplugin.cpp",
      (const char *)(unsigned int)v4,
      bInheritHandles);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    return v2;
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  v5 = (char *)pv[0];
  StartupInfo.cb = 104;
  if ( !CreateProcessW(0, (LPWSTR)pv[0], 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x8F,
                     (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\usocleanupplugin.cpp",
                     "Unable to invoke: %ws",
                     v5);
    if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v7, v8);
    if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
LABEL_15:
    if ( v5 )
      CoTaskMemFree(v5);
    return LastErrorMsg;
  }
  v11 = WaitForSingleObject(ProcessInformation.hProcess, 0xEA60u);
  if ( v11 == 258 )
  {
    if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    if ( v5 )
      CoTaskMemFree(v5);
    return 2147942658LL;
  }
  else
  {
    if ( v11 == -1 )
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0x9A,
                       (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\usocleanupplugin.cpp",
                       v12);
      if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
      if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
      goto LABEL_15;
    }
    ExitCode = 1;
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) && ExitCode )
    {
      LastErrorMsg = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\usocleanupplugin.cpp",
        (const char *)0x80004005LL,
        bInheritHandlesa);
      if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
      if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
      goto LABEL_15;
    }
    if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( v5 )
      CoTaskMemFree(v5);
    return 0;
  }
}

```

## disassembly

```asm
0x18003f550  mov     [rsp-8+arg_0], rbx
0x18003f555  mov     [rsp-8+arg_8], rdi
0x18003f55a  push    rbp
0x18003f55b  lea     rbp, [rsp-230h]
0x18003f563  sub     rsp, 330h
0x18003f56a  mov     rax, cs:__security_cookie
0x18003f571  xor     rax, rsp
0x18003f574  mov     [rbp+230h+var_10], rax
0x18003f57b  mov     r8d, 104h; nSize
0x18003f581  mov     [rsp+330h+pv], 0
0x18003f58a  lea     rdx, [rbp+230h+Dst]; lpDst
0x18003f58e  lea     rcx, Src; "%windir%\\System32\\usoclient.exe"
0x18003f595  call    cs:__imp_ExpandEnvironmentStringsW
0x18003f59b  test    eax, eax
0x18003f59d  jnz     short loc_18003F5DA
0x18003f59f  call    cs:__imp_GetLastError
0x18003f5a5  mov     ebx, eax
0x18003f5a7  test    eax, eax
0x18003f5a9  jle     short loc_18003F5B4
0x18003f5ab  movzx   ebx, ax
0x18003f5ae  or      ebx, 80070000h
0x18003f5b4  test    ebx, ebx
0x18003f5b6  jns     short loc_18003F5D3
0x18003f5b8  mov     rcx, [rbp+238h]; this
0x18003f5bf  lea     r8, aOnecoreEnduser_19; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003f5c6  mov     r9d, ebx; char *
0x18003f5c9  mov     edx, 7Bh ; '{'; void *
0x18003f5ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f5d3  mov     eax, ebx
0x18003f5d5  jmp     loc_18003F88C
0x18003f5da  movups  xmm0, xmmword ptr cs:aUsocleanup; "UsoCleanup"
0x18003f5e1  lea     r9, [rbp+230h+var_240]
0x18003f5e5  movsd   xmm1, qword ptr cs:aUsocleanup+0Eh; "nup"
0x18003f5ed  lea     r8, [rbp+230h+Dst]
0x18003f5f1  movups  xmmword ptr [rbp+230h+var_240], xmm0
0x18003f5f5  lea     rdx, aWsWs; "\"%ws\" %ws"
0x18003f5fc  lea     rcx, [rsp+330h+pv]
0x18003f601  movsd   qword ptr [rbp+230h+var_240+0Eh], xmm1
0x18003f606  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003f60b  mov     ebx, eax
0x18003f60d  test    eax, eax
0x18003f60f  jns     short loc_18003F63E
0x18003f611  mov     rcx, [rbp+238h]; this
0x18003f618  lea     r8, aOnecoreEnduser_19; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003f61f  mov     r9d, eax; char *
0x18003f622  mov     edx, 7Eh ; '~'; void *
0x18003f627  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f62c  mov     rcx, [rsp+330h+pv]; pv
0x18003f631  test    rcx, rcx
0x18003f634  jz      short loc_18003F5D3
0x18003f636  call    cs:__imp_CoTaskMemFree
0x18003f63c  jmp     short loc_18003F5D3
0x18003f63e  xor     eax, eax
0x18003f640  lea     rcx, [rbp+230h+StartupInfo+4]; void *
0x18003f644  xorps   xmm0, xmm0
0x18003f647  mov     qword ptr [rsp+330h+ProcessInformation.dwProcessId], rax
0x18003f64c  xor     edx, edx; Val
0x18003f64e  movups  xmmword ptr [rsp+330h+ProcessInformation.hProcess], xmm0
0x18003f653  lea     r8d, [rax+64h]; Size
0x18003f657  call    memset_0
0x18003f65c  mov     rbx, [rsp+330h+pv]
0x18003f661  lea     rax, [rsp+330h+ProcessInformation]
0x18003f666  mov     [rsp+330h+lpProcessInformation], rax; lpProcessInformation
0x18003f66b  xor     r9d, r9d; lpThreadAttributes
0x18003f66e  lea     rax, [rbp+230h+StartupInfo]
0x18003f672  mov     [rbp+230h+StartupInfo.cb], 68h ; 'h'
0x18003f679  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x18003f67e  xor     r8d, r8d; lpProcessAttributes
0x18003f681  mov     [rsp+330h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18003f68a  mov     rdx, rbx; lpCommandLine
0x18003f68d  mov     [rsp+330h+lpEnvironment], 0; lpEnvironment
0x18003f696  xor     ecx, ecx; lpApplicationName
0x18003f698  mov     [rsp+330h+dwCreationFlags], 0; dwCreationFlags
0x18003f6a0  mov     [rsp+330h+bInheritHandles], 0; int
0x18003f6a8  call    cs:__imp_CreateProcessW
0x18003f6ae  test    eax, eax
0x18003f6b0  jnz     short loc_18003F71D
0x18003f6b2  mov     rcx, [rbp+238h]; this
0x18003f6b9  lea     r9, aUnableToInvoke_0; "Unable to invoke: %ws"
0x18003f6c0  lea     r8, aOnecoreEnduser_19; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003f6c7  mov     qword ptr [rsp+330h+bInheritHandles], rbx; char *
0x18003f6cc  mov     edx, 8Fh; void *
0x18003f6d1  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003f6d6  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hObject
0x18003f6db  mov     edi, eax
0x18003f6dd  test    rcx, rcx
0x18003f6e0  jz      short loc_18003F6F0
0x18003f6e2  call    cs:__imp_CloseHandle
0x18003f6e8  test    eax, eax
0x18003f6ea  jz      loc_18003F8E6
0x18003f6f0  mov     rcx, [rsp+330h+ProcessInformation.hThread]; hObject
0x18003f6f5  test    rcx, rcx
0x18003f6f8  jz      short loc_18003F708
0x18003f6fa  call    cs:__imp_CloseHandle
0x18003f700  test    eax, eax
0x18003f702  jz      loc_18003F8F8
0x18003f708  test    rbx, rbx
0x18003f70b  jz      short loc_18003F716
0x18003f70d  mov     rcx, rbx; pv
0x18003f710  call    cs:__imp_CoTaskMemFree
0x18003f716  mov     eax, edi
0x18003f718  jmp     loc_18003F88C
0x18003f71d  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hHandle
0x18003f722  mov     edx, 0EA60h; dwMilliseconds
0x18003f727  call    cs:__imp_WaitForSingleObject
0x18003f72d  cmp     eax, 102h
0x18003f732  jnz     short loc_18003F77C
0x18003f734  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hObject
0x18003f739  test    rcx, rcx
0x18003f73c  jz      short loc_18003F74C
0x18003f73e  call    cs:__imp_CloseHandle
0x18003f744  test    eax, eax
0x18003f746  jz      loc_18003F90A
0x18003f74c  mov     rcx, [rsp+330h+ProcessInformation.hThread]; hObject
0x18003f751  test    rcx, rcx
0x18003f754  jz      short loc_18003F764
0x18003f756  call    cs:__imp_CloseHandle
0x18003f75c  test    eax, eax
0x18003f75e  jz      loc_18003F91C
0x18003f764  test    rbx, rbx
0x18003f767  jz      short loc_18003F772
0x18003f769  mov     rcx, rbx; pv
0x18003f76c  call    cs:__imp_CoTaskMemFree
0x18003f772  mov     eax, 80070102h
0x18003f777  jmp     loc_18003F88C
0x18003f77c  cmp     eax, 0FFFFFFFFh
0x18003f77f  jnz     short loc_18003F7D4
0x18003f781  mov     rcx, [rbp+238h]; this
0x18003f788  lea     r8, aOnecoreEnduser_19; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003f78f  mov     edx, 9Ah; void *
0x18003f794  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003f799  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hObject
0x18003f79e  mov     edi, eax
0x18003f7a0  test    rcx, rcx
0x18003f7a3  jz      short loc_18003F7B3
0x18003f7a5  call    cs:__imp_CloseHandle
0x18003f7ab  test    eax, eax
0x18003f7ad  jz      loc_18003F92E
0x18003f7b3  mov     rcx, [rsp+330h+ProcessInformation.hThread]; hObject
0x18003f7b8  test    rcx, rcx
0x18003f7bb  jz      loc_18003F708
0x18003f7c1  call    cs:__imp_CloseHandle
0x18003f7c7  test    eax, eax
0x18003f7c9  jz      loc_18003F8C2
0x18003f7cf  jmp     loc_18003F708
0x18003f7d4  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hProcess
0x18003f7d9  lea     rdx, [rsp+330h+ExitCode]; lpExitCode
0x18003f7de  mov     [rsp+330h+ExitCode], 1
0x18003f7e6  call    cs:__imp_GetExitCodeProcess
0x18003f7ec  test    eax, eax
0x18003f7ee  jz      short loc_18003F850
0x18003f7f0  cmp     [rsp+330h+ExitCode], 0
0x18003f7f5  jz      short loc_18003F850
0x18003f7f7  mov     rcx, [rbp+238h]; this
0x18003f7fe  lea     r8, aOnecoreEnduser_19; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003f805  mov     edi, 80004005h
0x18003f80a  mov     edx, 0A0h; void *
0x18003f80f  mov     r9d, edi; char *
0x18003f812  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f817  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hObject
0x18003f81c  test    rcx, rcx
0x18003f81f  jz      short loc_18003F82F
0x18003f821  call    cs:__imp_CloseHandle
0x18003f827  test    eax, eax
0x18003f829  jz      loc_18003F940
0x18003f82f  mov     rcx, [rsp+330h+ProcessInformation.hThread]; hObject
0x18003f834  test    rcx, rcx
0x18003f837  jz      loc_18003F708
0x18003f83d  call    cs:__imp_CloseHandle
0x18003f843  test    eax, eax
0x18003f845  jz      loc_18003F8D4
0x18003f84b  jmp     loc_18003F708
0x18003f850  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hObject
0x18003f855  test    rcx, rcx
0x18003f858  jz      short loc_18003F868
0x18003f85a  call    cs:__imp_CloseHandle
0x18003f860  test    eax, eax
0x18003f862  jz      loc_18003F952
0x18003f868  mov     rcx, [rsp+330h+ProcessInformation.hThread]; hObject
0x18003f86d  test    rcx, rcx
0x18003f870  jz      short loc_18003F87C
0x18003f872  call    cs:__imp_CloseHandle
0x18003f878  test    eax, eax
0x18003f87a  jz      short loc_18003F8B0
0x18003f87c  test    rbx, rbx
0x18003f87f  jz      short loc_18003F88A
0x18003f881  mov     rcx, rbx; pv
0x18003f884  call    cs:__imp_CoTaskMemFree
0x18003f88a  xor     eax, eax
0x18003f88c  mov     rcx, [rbp+230h+var_10]
0x18003f893  xor     rcx, rsp; StackCookie
0x18003f896  call    __security_check_cookie
0x18003f89b  lea     r11, [rsp+330h+var_s0]
0x18003f8a3  mov     rbx, [r11+10h]
0x18003f8a7  mov     rdi, [r11+18h]
0x18003f8ab  mov     rsp, r11
0x18003f8ae  pop     rbp
0x18003f8af  retn
0x18003f8b0  mov     rcx, [rbp+238h]; this
0x18003f8b7  mov     edx, 0A0Bh; void *
0x18003f8bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003f8c2  mov     rcx, [rbp+238h]; this
0x18003f8c9  mov     edx, 0A0Bh; void *
0x18003f8ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003f8d4  mov     rcx, [rbp+238h]; this
0x18003f8db  mov     edx, 0A0Bh; void *
0x18003f8e0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003f8e6  mov     rcx, [rbp+238h]; this
0x18003f8ed  mov     edx, 0A0Bh; void *
0x18003f8f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003f8f8  mov     rcx, [rbp+238h]; this
0x18003f8ff  mov     edx, 0A0Bh; void *
0x18003f904  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003f90a  mov     rcx, [rbp+238h]; this
0x18003f911  mov     edx, 0A0Bh; void *
0x18003f916  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003f91c  mov     rcx, [rbp+238h]; this
0x18003f923  mov     edx, 0A0Bh; void *
0x18003f928  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003f92e  mov     rcx, [rbp+238h]; this
0x18003f935  mov     edx, 0A0Bh; void *
0x18003f93a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003f940  mov     rcx, [rbp+238h]; this
0x18003f947  mov     edx, 0A0Bh; void *
0x18003f94c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003f952  mov     rcx, [rbp+238h]; this
0x18003f959  mov     edx, 0A0Bh; void *
0x18003f95e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
