# WaasMedic::WaasDownloaderHelper::DoEdgeUpdateRepair(ushort const *)

- ea: `0x18002ceac`
- end: `0x18002d390`
- name: `?DoEdgeUpdateRepair@WaasDownloaderHelper@WaasMedic@@QEAAJPEBG@Z`
- size: `1252`
- prototype: `int(WaasMedic::WaasDownloaderHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180016af0`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180009a34`
- `0x180009a54`
- `0x18000ab48`
- `0x180026920`
- `0x18002c9bc`
- `0x18002ceac`
- `0x18002dc1c`
- `0x180030fbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d148`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d148`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002d0bb`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002d0bb`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002d20d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002d20d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d10d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d131`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d15f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d177`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d19b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d1d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d1f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d264`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d281`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d299`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d2b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d10d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d131`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d15f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d177`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d19b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d1d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d1f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d264`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d281`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d299`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d2b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d05c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d18d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d2ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d05c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d18d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d2ab`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002cf82`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002cf82`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002cefc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002cefc`

## string_xrefs

- `0x18002cfb7`: `/silent /install "needsadmin=true&brand=WAAS&runtime=persist"`
- `0x18002d0cc`: `Unable to invoke MicrosoftEdgeUpdateSetup: %ws`

## pseudocode

```c
__int64 __fastcall WaasMedic::WaasDownloaderHelper::DoEdgeUpdateRepair(
        WaasMedic::WaasDownloaderHelper *this,
        const unsigned __int16 *a2)
{
  WaasMedic *v3; // rcx
  HANDLE FileW; // rbx
  const char *v5; // r9
  bool IsTestSigningEnabled; // al
  int v8; // edi
  __int64 v9; // rdx
  int v10; // eax
  char *v11; // rdi
  unsigned int LastErrorMsg; // esi
  unsigned int v13; // r8d
  const char *v14; // r9
  unsigned int v15; // r8d
  const char *v16; // r9
  DWORD v17; // eax
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
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v41[6]; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v42[2]; // [rsp+150h] [rbp+50h]
  WCHAR Dst[264]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 4u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xB0,
             (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
             v5);
  IsTestSigningEnabled = WaasMedic::IsTestSigningEnabled(v3);
  v8 = WaasMedic::WaasDownloaderHelper::VerifyMicrosoftSignature(a2, IsTestSigningEnabled);
  if ( v8 < 0 )
  {
    v9 = 178;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
      (const char *)(unsigned int)v8,
      dwCreationDisposition);
LABEL_6:
    if ( FileW )
      CloseHandle(FileW);
    return (unsigned int)v8;
  }
  ExitCode = 1;
  if ( ExpandEnvironmentStringsW(a2, Dst, 0x104u) - 1 > 0x103 )
  {
    v8 = -2147024774;
    v9 = 189;
    goto LABEL_5;
  }
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  v41[1] = *(_OWORD *)L"/install \"needsadmin=true&brand=WAAS&runtime=persist\"";
  v41[0] = *(_OWORD *)L"/silent /install \"needsadmin=true&brand=WAAS&runtime=persist\"";
  v41[3] = *(_OWORD *)L"dmin=true&brand=WAAS&runtime=persist\"";
  v41[2] = *(_OWORD *)L" \"needsadmin=true&brand=WAAS&runtime=persist\"";
  v41[5] = *(_OWORD *)L"WAAS&runtime=persist\"";
  StartupInfo.cb = 104;
  v41[4] = *(_OWORD *)L"e&brand=WAAS&runtime=persist\"";
  v42[0] = *(_OWORD *)L"time=persist\"";
  *(_OWORD *)((char *)v42 + 12) = *(_OWORD *)L"ersist\"";
  pv[0] = 0;
  v10 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          pv,
          L"\"%ws\" %ws",
          Dst,
          v41);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
      (const char *)(unsigned int)v10,
      dwCreationDisposition);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    goto LABEL_6;
  }
  v11 = (char *)pv[0];
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessW(0, (LPWSTR)pv[0], 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0xD5,
                     (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
                     "Unable to invoke MicrosoftEdgeUpdateSetup: %ws",
                     v11);
    if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
LABEL_19:
    if ( v11 )
      CoTaskMemFree(v11);
    if ( FileW )
      CloseHandle(FileW);
    return LastErrorMsg;
  }
  v17 = WaitForSingleObject(ProcessInformation.hProcess, 0x927C0u);
  if ( v17 == 258 )
  {
    if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
    if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
    if ( v11 )
      CoTaskMemFree(v11);
    if ( FileW )
      CloseHandle(FileW);
    return 2147942658LL;
  }
  else
  {
    if ( v17 == -1 )
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0xE0,
                       (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
                       v18);
      if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
      if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
      goto LABEL_19;
    }
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) && ExitCode )
    {
      LastErrorMsg = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
        (const char *)0x80004005LL,
        dwCreationDispositiona);
      if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
      if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      goto LABEL_19;
    }
    if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    if ( v11 )
      CoTaskMemFree(v11);
    if ( FileW )
      CloseHandle(FileW);
    return 0;
  }
}

```

## disassembly

```asm
0x18002ceac  push    rbp
0x18002ceae  push    rbx
0x18002ceaf  push    rsi
0x18002ceb0  push    rdi
0x18002ceb1  lea     rbp, [rsp-298h]
0x18002ceb9  sub     rsp, 398h
0x18002cec0  mov     rax, cs:__security_cookie
0x18002cec7  xor     rax, rsp
0x18002ceca  mov     [rbp+2B0h+var_30], rax
0x18002ced1  mov     rsi, rdx
0x18002ced4  mov     [rsp+3B0h+hTemplateFile], 0; hTemplateFile
0x18002cedd  xor     r9d, r9d; lpSecurityAttributes
0x18002cee0  mov     [rsp+3B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002cee8  mov     edx, 80000000h; dwDesiredAccess
0x18002ceed  mov     [rsp+3B0h+dwCreationDisposition], 4; int
0x18002cef5  mov     rcx, rsi; lpFileName
0x18002cef8  lea     r8d, [r9+1]; dwShareMode
0x18002cefc  call    cs:__imp_CreateFileW
0x18002cf02  mov     rbx, rax
0x18002cf05  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002cf09  jnz     short loc_18002CF28
0x18002cf0b  mov     rcx, [rbp+2B8h]; this
0x18002cf12  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002cf19  mov     edx, 0B0h; void *
0x18002cf1e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002cf23  jmp     loc_18002D2C1
0x18002cf28  call    ?IsTestSigningEnabled@WaasMedic@@YA_NXZ; WaasMedic::IsTestSigningEnabled(void)
0x18002cf2d  mov     dl, al; bool
0x18002cf2f  mov     rcx, rsi; unsigned __int16 *
0x18002cf32  call    ?VerifyMicrosoftSignature@WaasDownloaderHelper@WaasMedic@@CAJPEBG_N@Z; WaasMedic::WaasDownloaderHelper::VerifyMicrosoftSignature(ushort const *,bool)
0x18002cf37  mov     edi, eax
0x18002cf39  test    eax, eax
0x18002cf3b  jns     short loc_18002CF6D
0x18002cf3d  mov     edx, 0B2h; void *
0x18002cf42  mov     rcx, [rbp+2B8h]; this
0x18002cf49  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002cf50  mov     r9d, edi; char *
0x18002cf53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cf58  test    rbx, rbx
0x18002cf5b  jz      short loc_18002CF66
0x18002cf5d  mov     rcx, rbx; hObject
0x18002cf60  call    cs:__imp_CloseHandle
0x18002cf66  mov     eax, edi
0x18002cf68  jmp     loc_18002D2C1
0x18002cf6d  mov     r8d, 104h; nSize
0x18002cf73  mov     [rsp+3B0h+ExitCode], 1
0x18002cf7b  lea     rdx, [rbp+2B0h+Dst]; lpDst
0x18002cf7f  mov     rcx, rsi; lpSrc
0x18002cf82  call    cs:__imp_ExpandEnvironmentStringsW
0x18002cf88  dec     eax
0x18002cf8a  cmp     eax, 103h
0x18002cf8f  jbe     short loc_18002CF9D
0x18002cf91  mov     edi, 8007007Ah
0x18002cf96  mov     edx, 0BDh
0x18002cf9b  jmp     short loc_18002CF42
0x18002cf9d  xor     edx, edx; Val
0x18002cf9f  lea     rcx, [rbp+2B0h+StartupInfo+4]; void *
0x18002cfa3  lea     r8d, [rdx+64h]; Size
0x18002cfa7  call    memset_0
0x18002cfac  movaps  xmm1, xmmword ptr cs:aSilentInstallN+10h; "/install \"needsadmin=true&brand=WAAS&r"...
0x18002cfb3  lea     r9, [rbp+2B0h+var_2C0]
0x18002cfb7  movaps  xmm0, xmmword ptr cs:aSilentInstallN; "/silent /install \"needsadmin=true&bran"...
0x18002cfbe  lea     r8, [rbp+2B0h+Dst]
0x18002cfc2  movaps  [rbp+2B0h+var_2B0], xmm1
0x18002cfc6  lea     rdx, aWsWs; "\"%ws\" %ws"
0x18002cfcd  movaps  xmm1, xmmword ptr cs:aSilentInstallN+30h; "dmin=true&brand=WAAS&runtime=persist\""
0x18002cfd4  lea     rcx, [rsp+3B0h+pv]
0x18002cfd9  movaps  [rbp+2B0h+var_2C0], xmm0
0x18002cfdd  movaps  xmm0, xmmword ptr cs:aSilentInstallN+20h; " \"needsadmin=true&brand=WAAS&runtime=p"...
0x18002cfe4  movaps  [rbp+2B0h+var_290], xmm1
0x18002cfe8  movaps  xmm1, xmmword ptr cs:aSilentInstallN+50h; "WAAS&runtime=persist\""
0x18002cfef  movaps  [rbp+2B0h+var_2A0], xmm0
0x18002cff3  movaps  xmm0, xmmword ptr cs:aSilentInstallN+40h; "e&brand=WAAS&runtime=persist\""
0x18002cffa  movaps  [rbp+2B0h+var_270], xmm1
0x18002cffe  movups  xmm1, xmmword ptr cs:aSilentInstallN+6Ch; "ersist\""
0x18002d005  mov     [rbp+2B0h+StartupInfo.cb], 68h ; 'h'
0x18002d00c  movaps  [rbp+2B0h+var_280], xmm0
0x18002d010  movaps  xmm0, xmmword ptr cs:aSilentInstallN+60h; "time=persist\""
0x18002d017  movaps  xmmword ptr [rbp+2B0h+var_260], xmm0
0x18002d01b  movups  xmmword ptr [rbp+2B0h+var_260+0Ch], xmm1
0x18002d01f  mov     [rsp+3B0h+pv], 0
0x18002d028  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18002d02d  mov     edi, eax
0x18002d02f  test    eax, eax
0x18002d031  jns     short loc_18002D067
0x18002d033  mov     rcx, [rbp+2B8h]; this
0x18002d03a  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d041  mov     r9d, eax; char *
0x18002d044  mov     edx, 0C7h; void *
0x18002d049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d04e  mov     rcx, [rsp+3B0h+pv]; pv
0x18002d053  test    rcx, rcx
0x18002d056  jz      loc_18002CF58
0x18002d05c  call    cs:__imp_CoTaskMemFree
0x18002d062  jmp     loc_18002CF58
0x18002d067  mov     rdi, [rsp+3B0h+pv]
0x18002d06c  xor     eax, eax
0x18002d06e  mov     qword ptr [rsp+3B0h+ProcessInformation.dwProcessId], rax
0x18002d073  xorps   xmm0, xmm0
0x18002d076  lea     rax, [rsp+3B0h+ProcessInformation]
0x18002d07b  xor     r9d, r9d; lpThreadAttributes
0x18002d07e  mov     [rsp+3B0h+lpProcessInformation], rax; lpProcessInformation
0x18002d083  xor     r8d, r8d; lpProcessAttributes
0x18002d086  lea     rax, [rbp+2B0h+StartupInfo]
0x18002d08a  mov     rdx, rdi; lpCommandLine
0x18002d08d  mov     [rsp+3B0h+lpStartupInfo], rax; lpStartupInfo
0x18002d092  xor     ecx, ecx; lpApplicationName
0x18002d094  mov     [rsp+3B0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18002d09d  mov     [rsp+3B0h+hTemplateFile], 0; lpEnvironment
0x18002d0a6  mov     [rsp+3B0h+dwFlagsAndAttributes], 0; dwCreationFlags
0x18002d0ae  mov     [rsp+3B0h+dwCreationDisposition], 0; int
0x18002d0b6  movups  xmmword ptr [rsp+3B0h+ProcessInformation.hProcess], xmm0
0x18002d0bb  call    cs:__imp_CreateProcessW
0x18002d0c1  test    eax, eax
0x18002d0c3  jnz     short loc_18002D13E
0x18002d0c5  mov     rcx, [rbp+2B8h]; this
0x18002d0cc  lea     r9, aUnableToInvoke; "Unable to invoke MicrosoftEdgeUpdateSet"...
0x18002d0d3  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d0da  mov     qword ptr [rsp+3B0h+dwCreationDisposition], rdi; char *
0x18002d0df  mov     edx, 0D5h; void *
0x18002d0e4  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18002d0e9  mov     rcx, [rsp+3B0h+ProcessInformation.hProcess]; hObject
0x18002d0ee  mov     esi, eax
0x18002d0f0  test    rcx, rcx
0x18002d0f3  jz      short loc_18002D103
0x18002d0f5  call    cs:__imp_CloseHandle
0x18002d0fb  test    eax, eax
0x18002d0fd  jz      loc_18002D312
0x18002d103  mov     rcx, [rsp+3B0h+ProcessInformation.hThread]; hObject
0x18002d108  test    rcx, rcx
0x18002d10b  jz      short loc_18002D11B
0x18002d10d  call    cs:__imp_CloseHandle
0x18002d113  test    eax, eax
0x18002d115  jz      loc_18002D324
0x18002d11b  test    rdi, rdi
0x18002d11e  jz      short loc_18002D129
0x18002d120  mov     rcx, rdi; pv
0x18002d123  call    cs:__imp_CoTaskMemFree
0x18002d129  test    rbx, rbx
0x18002d12c  jz      short loc_18002D137
0x18002d12e  mov     rcx, rbx; hObject
0x18002d131  call    cs:__imp_CloseHandle
0x18002d137  mov     eax, esi
0x18002d139  jmp     loc_18002D2C1
0x18002d13e  mov     rcx, [rsp+3B0h+ProcessInformation.hProcess]; hHandle
0x18002d143  mov     edx, 927C0h; dwMilliseconds
0x18002d148  call    cs:__imp_WaitForSingleObject
0x18002d14e  cmp     eax, 102h
0x18002d153  jnz     short loc_18002D1AB
0x18002d155  mov     rcx, [rsp+3B0h+ProcessInformation.hProcess]; hObject
0x18002d15a  test    rcx, rcx
0x18002d15d  jz      short loc_18002D16D
0x18002d15f  call    cs:__imp_CloseHandle
0x18002d165  test    eax, eax
0x18002d167  jz      loc_18002D336
0x18002d16d  mov     rcx, [rsp+3B0h+ProcessInformation.hThread]; hObject
0x18002d172  test    rcx, rcx
0x18002d175  jz      short loc_18002D185
0x18002d177  call    cs:__imp_CloseHandle
0x18002d17d  test    eax, eax
0x18002d17f  jz      loc_18002D348
0x18002d185  test    rdi, rdi
0x18002d188  jz      short loc_18002D193
0x18002d18a  mov     rcx, rdi; pv
0x18002d18d  call    cs:__imp_CoTaskMemFree
0x18002d193  test    rbx, rbx
0x18002d196  jz      short loc_18002D1A1
0x18002d198  mov     rcx, rbx; hObject
0x18002d19b  call    cs:__imp_CloseHandle
0x18002d1a1  mov     eax, 80070102h
0x18002d1a6  jmp     loc_18002D2C1
0x18002d1ab  cmp     eax, 0FFFFFFFFh
0x18002d1ae  jnz     short loc_18002D203
0x18002d1b0  mov     rcx, [rbp+2B8h]; this
0x18002d1b7  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d1be  mov     edx, 0E0h; void *
0x18002d1c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d1c8  mov     rcx, [rsp+3B0h+ProcessInformation.hProcess]; hObject
0x18002d1cd  mov     esi, eax
0x18002d1cf  test    rcx, rcx
0x18002d1d2  jz      short loc_18002D1E2
0x18002d1d4  call    cs:__imp_CloseHandle
0x18002d1da  test    eax, eax
0x18002d1dc  jz      loc_18002D35A
0x18002d1e2  mov     rcx, [rsp+3B0h+ProcessInformation.hThread]; hObject
0x18002d1e7  test    rcx, rcx
0x18002d1ea  jz      loc_18002D11B
0x18002d1f0  call    cs:__imp_CloseHandle
0x18002d1f6  test    eax, eax
0x18002d1f8  jz      loc_18002D2EE
0x18002d1fe  jmp     loc_18002D11B
0x18002d203  mov     rcx, [rsp+3B0h+ProcessInformation.hProcess]; hProcess
0x18002d208  lea     rdx, [rsp+3B0h+ExitCode]; lpExitCode
0x18002d20d  call    cs:__imp_GetExitCodeProcess
0x18002d213  test    eax, eax
0x18002d215  jz      short loc_18002D277
0x18002d217  cmp     [rsp+3B0h+ExitCode], 0
0x18002d21c  jz      short loc_18002D277
0x18002d21e  mov     rcx, [rbp+2B8h]; this
0x18002d225  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d22c  mov     esi, 80004005h
0x18002d231  mov     edx, 0E5h; void *
0x18002d236  mov     r9d, esi; char *
0x18002d239  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d23e  mov     rcx, [rsp+3B0h+ProcessInformation.hProcess]; hObject
0x18002d243  test    rcx, rcx
0x18002d246  jz      short loc_18002D256
0x18002d248  call    cs:__imp_CloseHandle
0x18002d24e  test    eax, eax
0x18002d250  jz      loc_18002D36C
0x18002d256  mov     rcx, [rsp+3B0h+ProcessInformation.hThread]; hObject
0x18002d25b  test    rcx, rcx
0x18002d25e  jz      loc_18002D11B
0x18002d264  call    cs:__imp_CloseHandle
0x18002d26a  test    eax, eax
0x18002d26c  jz      loc_18002D300
0x18002d272  jmp     loc_18002D11B
0x18002d277  mov     rcx, [rsp+3B0h+ProcessInformation.hProcess]; hObject
0x18002d27c  test    rcx, rcx
0x18002d27f  jz      short loc_18002D28F
0x18002d281  call    cs:__imp_CloseHandle
0x18002d287  test    eax, eax
0x18002d289  jz      loc_18002D37E
0x18002d28f  mov     rcx, [rsp+3B0h+ProcessInformation.hThread]; hObject
0x18002d294  test    rcx, rcx
0x18002d297  jz      short loc_18002D2A3
0x18002d299  call    cs:__imp_CloseHandle
0x18002d29f  test    eax, eax
0x18002d2a1  jz      short loc_18002D2DC
0x18002d2a3  test    rdi, rdi
0x18002d2a6  jz      short loc_18002D2B1
0x18002d2a8  mov     rcx, rdi; pv
0x18002d2ab  call    cs:__imp_CoTaskMemFree
0x18002d2b1  test    rbx, rbx
0x18002d2b4  jz      short loc_18002D2BF
0x18002d2b6  mov     rcx, rbx; hObject
0x18002d2b9  call    cs:__imp_CloseHandle
0x18002d2bf  xor     eax, eax
0x18002d2c1  mov     rcx, [rbp+2B0h+var_30]
0x18002d2c8  xor     rcx, rsp; StackCookie
0x18002d2cb  call    __security_check_cookie
0x18002d2d0  add     rsp, 398h
0x18002d2d7  pop     rdi
0x18002d2d8  pop     rsi
0x18002d2d9  pop     rbx
0x18002d2da  pop     rbp
0x18002d2db  retn
0x18002d2dc  mov     rcx, [rbp+2B8h]; this
0x18002d2e3  mov     edx, 0A0Bh; void *
0x18002d2e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002d2ee  mov     rcx, [rbp+2B8h]; this
0x18002d2f5  mov     edx, 0A0Bh; void *
0x18002d2fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002d300  mov     rcx, [rbp+2B8h]; this
0x18002d307  mov     edx, 0A0Bh; void *
0x18002d30c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002d312  mov     rcx, [rbp+2B8h]; this
0x18002d319  mov     edx, 0A0Bh; void *
0x18002d31e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002d324  mov     rcx, [rbp+2B8h]; this
0x18002d32b  mov     edx, 0A0Bh; void *
0x18002d330  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002d336  mov     rcx, [rbp+2B8h]; this
0x18002d33d  mov     edx, 0A0Bh; void *
0x18002d342  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002d348  mov     rcx, [rbp+2B8h]; this
0x18002d34f  mov     edx, 0A0Bh; void *
0x18002d354  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002d35a  mov     rcx, [rbp+2B8h]; this
0x18002d361  mov     edx, 0A0Bh; void *
0x18002d366  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002d36c  mov     rcx, [rbp+2B8h]; this
0x18002d373  mov     edx, 0A0Bh; void *
0x18002d378  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002d37e  mov     rcx, [rbp+2B8h]; this
0x18002d385  mov     edx, 0A0Bh; void *
0x18002d38a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
