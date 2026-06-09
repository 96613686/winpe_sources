# CDevice::DoDredWatson(_D3DKMT_DEVICEEXECUTION_STATE,long)

- ea: `0x1800f1b20`
- end: `0x1800f208e`
- name: `?DoDredWatson@CDevice@@QEAAJW4_D3DKMT_DEVICEEXECUTION_STATE@@J@Z`
- size: `1390`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a6754`

## callees

- `0x18000ac4c`
- `0x18000b010`
- `0x180014368`
- `0x180016c2c`
- `0x180016c90`
- `0x18005671c`
- `0x180061460`
- `0x1800bb480`
- `0x1800bc094`
- `0x1800e8380`
- `0x1800e83bc`
- `0x1800ea6b8`
- `0x1800ea6dc`
- `0x1800eb580`
- `0x1800f1b20`
- `0x1801035f0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800f205f`
- `msvcp_win!_Mtx_unlock` at `0x1800f205f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800f1bde`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800f1bde`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800f1df2`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800f1df2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800f1dd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800f1dd9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f2001`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f2001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1fe2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f1bb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f1f84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f1bb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f1f84`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800f1fcf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800f1fcf`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1800f1b69`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1800f1b69`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x1800f1c30`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x1800f1c30`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerUnregisterCustomMetadata` at `0x1800f2027`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerUnregisterCustomMetadata` at `0x1800f2027`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800f1e8b`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800f1e8b`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x1800f1fa9`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x1800f1fa9`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCloseHandle` at `0x1800f1c5c`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCloseHandle` at `0x1800f1c5c`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x1800f1c87`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x1800f1c87`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1d50`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1d74`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1d98`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1dbc`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1e1e`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1eeb`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1f35`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1f5a`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1d50`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1d74`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1d98`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1dbc`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1e1e`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1eeb`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1f35`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800f1f5a`

## string_xrefs

- `0x1800f1bca`: `D3D12 Device Removed Extended Data`
- `0x1800f1d89`: `DeviceRemovedReason`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDevice::DoDredWatson(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v5; // rsi
  unsigned int v6; // edi
  const WCHAR *v7; // rdx
  HRESULT v8; // eax
  HRESULT v9; // ecx
  HRESULT v10; // eax
  HRESULT v11; // eax
  HRESULT v12; // eax
  HRESULT v13; // eax
  wchar_t *v14; // rax
  const WCHAR *v15; // rax
  HRESULT v16; // eax
  __int64 v17; // rcx
  HRESULT v18; // eax
  HRESULT v19; // ecx
  HRESULT v20; // eax
  HANDLE CurrentProcess; // rax
  HRESULT v22; // eax
  HANDLE Thread; // rbx
  signed int LastError; // eax
  CD3D12TelemetryHelper *v25; // rcx
  HRESULT v27; // eax
  PWER_EXCEPTION_INFORMATION pExceptionParam; // [rsp+20h] [rbp-FE8h]
  bool pExceptionParama; // [rsp+20h] [rbp-FE8h]
  PWER_DUMP_CUSTOM_OPTIONS pDumpCustomOptions; // [rsp+28h] [rbp-FE0h]
  unsigned int pDumpCustomOptionsa; // [rsp+28h] [rbp-FE0h]
  __int64 dwFlags; // [rsp+30h] [rbp-FD8h]
  DWORD dwFlagsa; // [rsp+30h] [rbp-FD8h]
  HREPORT hReportHandle; // [rsp+40h] [rbp-FC8h] BYREF
  unsigned int v35; // [rsp+48h] [rbp-FC0h] BYREF
  unsigned int puLen; // [rsp+4Ch] [rbp-FBCh] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp-FB8h] BYREF
  __int64 v38; // [rsp+58h] [rbp-FB0h]
  _QWORD Parameter[3]; // [rsp+60h] [rbp-FA8h] BYREF
  LPCVOID pBlock[5]; // [rsp+78h] [rbp-F90h] BYREF
  const _com_error *v41; // [rsp+A0h] [rbp-F68h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+B0h] [rbp-F58h] BYREF
  _BYTE v43[20]; // [rsp+950h] [rbp-6B8h] BYREF
  unsigned int v44; // [rsp+964h] [rbp-6A4h]
  WCHAR v45[16]; // [rsp+C70h] [rbp-398h] BYREF
  WCHAR pwzValue[16]; // [rsp+C90h] [rbp-378h] BYREF
  WCHAR v47[32]; // [rsp+CB0h] [rbp-358h] BYREF
  WCHAR v48[32]; // [rsp+CF0h] [rbp-318h] BYREF
  WCHAR v49[8]; // [rsp+D30h] [rbp-2D8h] BYREF
  _BYTE v50[112]; // [rsp+D40h] [rbp-2C8h] BYREF
  WCHAR Filename[264]; // [rsp+DB0h] [rbp-258h] BYREF

  v5 = a1;
  v38 = a1;
  v6 = 0;
  if ( !*(_BYTE *)(a1 + 8091) || !IsApiSetImplemented("ext-ms-win-wer-reporting-l1-1-0") )
    return 0;
  pBlock[3] = &g_Module;
  std::_Mutex_base::lock((std::_Mutex_base *)&g_Module);
  v35 = 13;
  memset_0(&pReportInformation.dwSize + 1, 0, 0x89Cu);
  pReportInformation.dwSize = 2208;
  pReportInformation.hProcess = GetCurrentProcess();
  hReportHandle = 0;
  _o_wcscpy_s(pReportInformation.wzDescription, 512, L"D3D12 Device Removed Extended Data");
  memset_0(v43, 0, 0x320u);
  CShaderCacheAdapter::GetFileUniqueness((CShaderCacheAdapter *)(v5 + 5648), (struct FileUniqueness *)v43);
  v7 = L"1";
  if ( !*(_BYTE *)(v5 + 8091) )
    v7 = L"0";
  v8 = WerRegisterCustomMetadata(L"d3ddredDataPresent", v7);
  try
  {
    ThrowFailure(v8);
    pBlock[4] = L"d3ddredDataPresent";
    hReportHandle = 0;
    v9 = WerReportCreate(L"D3DDRED2", WerReportNonCritical, &pReportInformation, &hReportHandle);
    ThrowFailure(v9);
    _snwprintf_s<16>(pwzValue, 32, L"VEN_%04X", v44);
    _snwprintf_s<32>(
      v48,
      64,
      L"%d.%d.%d.%d",
      (unsigned int)(*(int *)(v5 + 6740) >> 16),
      (unsigned __int16)*(_DWORD *)(v5 + 6740),
      HIWORD(*(_DWORD *)(v5 + 6736)),
      (unsigned __int16)*(_DWORD *)(v5 + 6736));
    v45[0] = 0;
    _snwprintf_s<16>(v45, 32, L"0x%08X", a3);
    v47[0] = 0;
    _snwprintf_s<32>(v47, 64, L"%d", a2);
    v10 = WerReportSetParameter(hReportHandle, 0, L"GpuManufacturer", pwzValue);
    ThrowFailure(v10);
    v11 = WerReportSetParameter(hReportHandle, 1u, L"GpuDriverVersion", v48);
    ThrowFailure(v11);
    v12 = WerReportSetParameter(hReportHandle, 2u, L"DeviceRemovedReason", v45);
    ThrowFailure(v12);
    v13 = WerReportSetParameter(hReportHandle, 3u, L"DeviceExecutionState", v47);
    ThrowFailure(v13);
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      v14 = wcsrchr(Filename, 0x5Cu);
      if ( v14 )
        v15 = v14 + 1;
      else
        v15 = (const WCHAR *)&qword_1802A0AD0;
      v16 = WerReportSetParameter(hReportHandle, 4u, L"AppName", v15);
      ThrowFailure(v16);
      wcscpy(v49, L"Unknown");
      memset_0(v50, 0, sizeof(v50));
      try
      {
        lambda_a7426270190b2e5238aaa609ac6ae87b_::operator()(v17, pBlock, Filename);
        if ( pBlock[1] != pBlock[0] )
        {
          lpBuffer = 0;
          puLen = 0;
          if ( VerQueryValueW(pBlock[0], L"\\", &lpBuffer, &puLen) )
          {
            LODWORD(dwFlags) = *((unsigned __int16 *)lpBuffer + 10);
            LODWORD(pDumpCustomOptions) = *((unsigned __int16 *)lpBuffer + 11);
            LODWORD(pExceptionParam) = *((unsigned __int16 *)lpBuffer + 8);
            StringCchPrintfW(
              v49,
              0x40u,
              L"%u.%u.%u.%u",
              *((unsigned __int16 *)lpBuffer + 9),
              pExceptionParam,
              pDumpCustomOptions,
              dwFlags);
          }
        }
        v18 = WerReportSetParameter(hReportHandle, 5u, L"AppVer", v49);
        ThrowFailure(v18);
        std::vector<char>::_Tidy(pBlock);
      }
      catch ( std::bad_alloc )
      {
        v27 = WerReportSetParameter(hReportHandle, 5u, L"AppVer", L"Unknown");
        ThrowFailure(v27);
        v6 = 0;
        v5 = v38;
      }
    }
    else
    {
      v19 = WerReportSetParameter(hReportHandle, 4u, L"AppName", L"Unknown");
      ThrowFailure(v19);
      v20 = WerReportSetParameter(hReportHandle, 5u, L"AppVer", L"Unknown");
      ThrowFailure(v20);
    }
    Parameter[0] = hReportHandle;
    Parameter[1] = &v35;
    Parameter[2] = 32;
    CurrentProcess = GetCurrentProcess();
    v22 = WerReportAddDump(hReportHandle, CurrentProcess, 0, WerDumpTypeHeapDump, 0, 0, 0);
    ThrowFailure(v22);
    Thread = CreateThread(0, 0, lambda_dab77ad03f29ba3a9ddc9b4d6ea11f93_::_lambda_invoker_cdecl_, Parameter, 0, 0);
    lpBuffer = Thread;
    if ( !Thread )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      ThrowFailure(LastError);
    }
    WaitForSingleObject(Thread, 0xFFFFFFFF);
    if ( v35 == 4 )
      ThrowFailure(-2147467259);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&lpBuffer);
    WerUnregisterCustomMetadata(L"d3ddredDataPresent");
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hReportHandle);
  }
  catch ( const _com_error *v41 )
  {
    v25 = (CD3D12TelemetryHelper *)*((unsigned int *)v41 + 2);
    puLen = *((_DWORD *)v41 + 2);
    v6 = puLen;
    v5 = v38;
  }
  CD3D12TelemetryHelper::LogDredWatsonReport(v25, (void *)v5, v6, v35, pExceptionParama, pDumpCustomOptionsa, dwFlagsa);
  _Mtx_unlock((_Mtx_t)&g_Module);
  return v6;
}

```

## disassembly

```asm
0x1800f1b20  push    rbx
0x1800f1b22  push    rsi
0x1800f1b23  push    rdi
0x1800f1b24  push    r12
0x1800f1b26  push    r13
0x1800f1b28  push    r14
0x1800f1b2a  push    r15
0x1800f1b2c  sub     rsp, 0FD0h
0x1800f1b33  mov     rax, cs:__security_cookie
0x1800f1b3a  xor     rax, rsp
0x1800f1b3d  mov     [rsp+1008h+var_48], rax
0x1800f1b45  mov     r13d, r8d
0x1800f1b48  mov     r12d, edx
0x1800f1b4b  mov     rsi, rcx
0x1800f1b4e  mov     [rsp+1008h+var_FB0], rcx
0x1800f1b53  xor     edi, edi
0x1800f1b55  cmp     [rcx+1F9Bh], dil
0x1800f1b5c  jz      loc_1800F2069
0x1800f1b62  lea     rcx, aExtMsWinWerRep_0; "ext-ms-win-wer-reporting-l1-1-0"
0x1800f1b69  call    cs:__imp_IsApiSetImplemented
0x1800f1b6f  test    eax, eax
0x1800f1b71  jz      loc_1800F2069
0x1800f1b77  lea     r14, ?g_Module@@3VCModule@@A; CModule g_Module
0x1800f1b7e  mov     [rsp+1008h+var_F78], r14
0x1800f1b86  mov     rcx, r14; this
0x1800f1b89  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800f1b8e  nop
0x1800f1b8f  mov     [rsp+1008h+var_FC0], 0Dh
0x1800f1b97  xor     edx, edx; Val
0x1800f1b99  mov     r8d, 89Ch; Size
0x1800f1b9f  lea     rcx, [rsp+1008h+pReportInformation+4]; void *
0x1800f1ba7  call    memset_0
0x1800f1bac  mov     [rsp+1008h+pReportInformation.dwSize], 8A0h
0x1800f1bb7  call    cs:__imp_GetCurrentProcess
0x1800f1bbd  mov     [rsp+1008h+pReportInformation.hProcess], rax
0x1800f1bc5  mov     [rsp+1008h+hReportHandle], rdi
0x1800f1bca  lea     r8, aD3d12DeviceRem; "D3D12 Device Removed Extended Data"
0x1800f1bd1  mov     edx, 200h
0x1800f1bd6  lea     rcx, [rsp+1008h+pReportInformation.wzDescription]
0x1800f1bde  call    cs:__imp__o_wcscpy_s
0x1800f1be4  xor     edx, edx; Val
0x1800f1be6  mov     r8d, 320h; Size
0x1800f1bec  lea     rcx, [rsp+1008h+var_6B8]; void *
0x1800f1bf4  call    memset_0
0x1800f1bf9  lea     rcx, [rsi+1610h]; this
0x1800f1c00  lea     rdx, [rsp+1008h+var_6B8]; struct FileUniqueness *
0x1800f1c08  call    ?GetFileUniqueness@CShaderCacheAdapter@@QEAAJPEAUFileUniqueness@@@Z; CShaderCacheAdapter::GetFileUniqueness(FileUniqueness *)
0x1800f1c0d  lea     rax, value; "0"
0x1800f1c14  lea     rdx, a1; "1"
0x1800f1c1b  cmp     [rsi+1F9Bh], dil
0x1800f1c22  cmovz   rdx, rax; value
0x1800f1c26  lea     r15, key; "d3ddredDataPresent"
0x1800f1c2d  mov     rcx, r15; key
0x1800f1c30  call    cs:__imp_WerRegisterCustomMetadata
0x1800f1c36  mov     ecx, eax; int
0x1800f1c38  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f1c3d  mov     [rsp+1008h+var_F70], r15
0x1800f1c45  mov     rbx, [rsp+1008h+hReportHandle]
0x1800f1c4a  test    rbx, rbx
0x1800f1c4d  jz      short loc_1800F1C6C
0x1800f1c4f  lea     rcx, [rsp+1008h+lpBuffer]; this
0x1800f1c54  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800f1c59  mov     rcx, rbx; hReportHandle
0x1800f1c5c  call    cs:__imp_WerReportCloseHandle
0x1800f1c62  lea     rcx, [rsp+1008h+lpBuffer]; this
0x1800f1c67  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800f1c6c  mov     [rsp+1008h+hReportHandle], rdi
0x1800f1c71  lea     r9, [rsp+1008h+hReportHandle]; phReportHandle
0x1800f1c76  lea     r8, [rsp+1008h+pReportInformation]; pReportInformation
0x1800f1c7e  xor     edx, edx; repType
0x1800f1c80  lea     rcx, pwzEventType; "D3DDRED2"
0x1800f1c87  call    cs:__imp_WerReportCreate
0x1800f1c8d  mov     ecx, eax; int
0x1800f1c8f  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f1c94  mov     r9d, [rsp+1008h+var_6A4]
0x1800f1c9c  lea     r8, aVen04x; "VEN_%04X"
0x1800f1ca3  mov     edx, 20h ; ' '
0x1800f1ca8  lea     rcx, [rsp+1008h+pwzValue]
0x1800f1cb0  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1800f1cb5  mov     edx, [rsi+1A50h]
0x1800f1cbb  mov     r9d, [rsi+1A54h]
0x1800f1cc2  movzx   ecx, dx
0x1800f1cc5  shr     edx, 10h
0x1800f1cc8  movzx   eax, r9w
0x1800f1ccc  sar     r9d, 10h
0x1800f1cd0  mov     [rsp+1008h+dwFlags], ecx
0x1800f1cd4  mov     dword ptr [rsp+1008h+pDumpCustomOptions], edx
0x1800f1cd8  mov     dword ptr [rsp+1008h+pExceptionParam], eax
0x1800f1cdc  lea     r8, aDDDD; "%d.%d.%d.%d"
0x1800f1ce3  mov     ebx, 40h ; '@'
0x1800f1ce8  mov     edx, ebx
0x1800f1cea  lea     rcx, [rsp+1008h+var_318]
0x1800f1cf2  call    ??$_snwprintf_s@$0CA@@@YAHAEAY0CA@G_KPEBGZZ; _snwprintf_s<32>(ushort (&)[32],unsigned __int64,ushort const *,...)
0x1800f1cf7  mov     [rsp+1008h+var_398], di
0x1800f1cff  mov     r9d, r13d
0x1800f1d02  lea     r8, a0x08x; "0x%08X"
0x1800f1d09  lea     edx, [rbx-20h]
0x1800f1d0c  lea     rcx, [rsp+1008h+var_398]
0x1800f1d14  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1800f1d19  mov     [rsp+1008h+var_358], di
0x1800f1d21  mov     r9d, r12d
0x1800f1d24  lea     r8, aD; "%d"
0x1800f1d2b  mov     edx, ebx
0x1800f1d2d  lea     rcx, [rsp+1008h+var_358]
0x1800f1d35  call    ??$_snwprintf_s@$0CA@@@YAHAEAY0CA@G_KPEBGZZ; _snwprintf_s<32>(ushort (&)[32],unsigned __int64,ushort const *,...)
0x1800f1d3a  lea     r9, [rsp+1008h+pwzValue]; pwzValue
0x1800f1d42  lea     r8, pwzName; "GpuManufacturer"
0x1800f1d49  xor     edx, edx; dwparamID
0x1800f1d4b  mov     rcx, [rsp+1008h+hReportHandle]; hReportHandle
0x1800f1d50  call    cs:__imp_WerReportSetParameter
0x1800f1d56  mov     ecx, eax; int
0x1800f1d58  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f1d5d  lea     r9, [rsp+1008h+var_318]; pwzValue
0x1800f1d65  lea     r8, aGpudriverversi; "GpuDriverVersion"
0x1800f1d6c  lea     edx, [rbx-3Fh]; dwparamID
0x1800f1d6f  mov     rcx, [rsp+1008h+hReportHandle]; hReportHandle
0x1800f1d74  call    cs:__imp_WerReportSetParameter
0x1800f1d7a  mov     ecx, eax; int
0x1800f1d7c  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f1d81  lea     r9, [rsp+1008h+var_398]; pwzValue
0x1800f1d89  lea     r8, aDeviceremovedr; "DeviceRemovedReason"
0x1800f1d90  lea     edx, [rbx-3Eh]; dwparamID
0x1800f1d93  mov     rcx, [rsp+1008h+hReportHandle]; hReportHandle
0x1800f1d98  call    cs:__imp_WerReportSetParameter
0x1800f1d9e  mov     ecx, eax; int
0x1800f1da0  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f1da5  lea     r9, [rsp+1008h+var_358]; pwzValue
0x1800f1dad  lea     r8, aDeviceexecutio; "DeviceExecutionState"
0x1800f1db4  lea     edx, [rbx-3Dh]; dwparamID
0x1800f1db7  mov     rcx, [rsp+1008h+hReportHandle]; hReportHandle
0x1800f1dbc  call    cs:__imp_WerReportSetParameter
0x1800f1dc2  mov     ecx, eax; int
0x1800f1dc4  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f1dc9  mov     r8d, 104h; nSize
0x1800f1dcf  lea     rdx, [rsp+1008h+Filename]; lpFilename
0x1800f1dd7  xor     ecx, ecx; hModule
0x1800f1dd9  call    cs:__imp_GetModuleFileNameW
0x1800f1ddf  test    eax, eax
0x1800f1de1  jz      loc_1800F1F1D
0x1800f1de7  lea     edx, [rbx+1Ch]; Ch
0x1800f1dea  lea     rcx, [rsp+1008h+Filename]; Str
0x1800f1df2  call    cs:__imp_wcsrchr
0x1800f1df8  test    rax, rax
0x1800f1dfb  jz      short loc_1800F1E03
0x1800f1dfd  add     rax, 2
0x1800f1e01  jmp     short loc_1800F1E0A
0x1800f1e03  lea     rax, qword_1802A0AD0
0x1800f1e0a  mov     r9, rax; pwzValue
0x1800f1e0d  lea     r8, aAppname; "AppName"
0x1800f1e14  mov     edx, 4; dwparamID
0x1800f1e19  mov     rcx, [rsp+1008h+hReportHandle]; hReportHandle
0x1800f1e1e  call    cs:__imp_WerReportSetParameter
0x1800f1e24  mov     ecx, eax; int
0x1800f1e26  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f1e2b  movups  xmm0, xmmword ptr cs:aUnknown_0; "Unknown"
0x1800f1e32  movdqu  xmmword ptr [rsp+1008h+var_2D8], xmm0
0x1800f1e3b  xor     edx, edx; Val
0x1800f1e3d  lea     r8d, [rdx+70h]; Size
0x1800f1e41  lea     rcx, [rsp+1008h+var_2C8]; void *
0x1800f1e49  call    memset_0
0x1800f1e4e  nop
0x1800f1e4f  lea     r8, [rsp+1008h+Filename]
0x1800f1e57  lea     rdx, [rsp+1008h+pBlock]
0x1800f1e5c  call    _lambda_a7426270190b2e5238aaa609ac6ae87b___operator__
0x1800f1e61  nop
0x1800f1e62  mov     rcx, [rsp+1008h+pBlock]; pBlock
0x1800f1e67  cmp     [rsp+1008h+var_F88], rcx
0x1800f1e6f  jz      short loc_1800F1ED2
0x1800f1e71  mov     [rsp+1008h+lpBuffer], rdi
0x1800f1e76  mov     [rsp+1008h+puLen], edi
0x1800f1e7a  lea     r9, [rsp+1008h+puLen]; puLen
0x1800f1e7f  lea     r8, [rsp+1008h+lpBuffer]; lplpBuffer
0x1800f1e84  lea     rdx, SubBlock; "\\"
0x1800f1e8b  call    cs:__imp_VerQueryValueW
0x1800f1e91  test    eax, eax
0x1800f1e93  jz      short loc_1800F1ED2
0x1800f1e95  mov     r9, [rsp+1008h+lpBuffer]
0x1800f1e9a  movzx   ecx, word ptr [r9+14h]
0x1800f1e9f  movzx   r8d, word ptr [r9+16h]
0x1800f1ea4  movzx   eax, word ptr [r9+10h]
0x1800f1ea9  movzx   r9d, word ptr [r9+12h]
0x1800f1eae  mov     [rsp+1008h+dwFlags], ecx
0x1800f1eb2  mov     dword ptr [rsp+1008h+pDumpCustomOptions], r8d
0x1800f1eb7  mov     dword ptr [rsp+1008h+pExceptionParam], eax
0x1800f1ebb  lea     r8, aUUUU; "%u.%u.%u.%u"
0x1800f1ec2  mov     rdx, rbx; unsigned __int64
0x1800f1ec5  lea     rcx, [rsp+1008h+var_2D8]; unsigned __int16 *
0x1800f1ecd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f1ed2  lea     r9, [rsp+1008h+var_2D8]; pwzValue
0x1800f1eda  lea     r8, aAppver; "AppVer"
0x1800f1ee1  mov     edx, 5; dwparamID
0x1800f1ee6  mov     rcx, [rsp+1008h+hReportHandle]; hReportHandle
0x1800f1eeb  call    cs:__imp_WerReportSetParameter
0x1800f1ef1  mov     ecx, eax; int
0x1800f1ef3  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f1ef8  nop
0x1800f1ef9  lea     rcx, [rsp+1008h+pBlock]
0x1800f1efe  call    ?_Tidy@?$vector@DV?$allocator@D@std@@@std@@AEAAXXZ; std::vector<char>::_Tidy(void)
0x1800f1f03  nop
0x1800f1f04  jmp     short loc_1800F1F67
0x1800f1f06  xor     edi, edi
0x1800f1f08  lea     r14, ?g_Module@@3VCModule@@A; CModule g_Module
0x1800f1f0f  lea     r15, key; "d3ddredDataPresent"
0x1800f1f16  mov     rsi, [rsp+1008h+var_FB0]
0x1800f1f1b  jmp     short loc_1800F1F67
0x1800f1f1d  lea     r9, aUnknown_0; "Unknown"
0x1800f1f24  lea     r8, aAppname; "AppName"
0x1800f1f2b  mov     edx, 4; dwparamID
0x1800f1f30  mov     rcx, [rsp+1008h+hReportHandle]; hReportHandle
0x1800f1f35  call    cs:__imp_WerReportSetParameter
0x1800f1f3b  mov     ecx, eax; int
0x1800f1f3d  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f1f42  lea     r9, aUnknown_0; "Unknown"
0x1800f1f49  lea     r8, aAppver; "AppVer"
0x1800f1f50  mov     edx, 5; dwparamID
0x1800f1f55  mov     rcx, [rsp+1008h+hReportHandle]; hReportHandle
0x1800f1f5a  call    cs:__imp_WerReportSetParameter
0x1800f1f60  mov     ecx, eax; int
0x1800f1f62  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f1f67  mov     rax, [rsp+1008h+hReportHandle]
0x1800f1f6c  mov     [rsp+1008h+Parameter], rax
0x1800f1f71  lea     rax, [rsp+1008h+var_FC0]
0x1800f1f76  mov     [rsp+1008h+var_FA0], rax
0x1800f1f7b  mov     [rsp+1008h+var_F98], 20h ; ' '
0x1800f1f84  call    cs:__imp_GetCurrentProcess
0x1800f1f8a  mov     [rsp+1008h+dwFlags], edi; dwFlags
0x1800f1f8e  mov     [rsp+1008h+pDumpCustomOptions], rdi; pDumpCustomOptions
0x1800f1f93  mov     [rsp+1008h+pExceptionParam], rdi; pExceptionParam
0x1800f1f98  mov     r9d, 3; dumpType
0x1800f1f9e  xor     r8d, r8d; hThread
0x1800f1fa1  mov     rdx, rax; hProcess
0x1800f1fa4  mov     rcx, [rsp+1008h+hReportHandle]; hReportHandle
0x1800f1fa9  call    cs:__imp_WerReportAddDump
0x1800f1faf  mov     ecx, eax; int
0x1800f1fb1  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f1fb6  mov     [rsp+1008h+pDumpCustomOptions], rdi; lpThreadId
0x1800f1fbb  mov     dword ptr [rsp+1008h+pExceptionParam], edi; dwCreationFlags
0x1800f1fbf  lea     r9, [rsp+1008h+Parameter]; lpParameter
0x1800f1fc4  lea     r8, _lambda_dab77ad03f29ba3a9ddc9b4d6ea11f93____lambda_invoker_cdecl_; lpStartAddress
0x1800f1fcb  xor     edx, edx; dwStackSize
0x1800f1fcd  xor     ecx, ecx; lpThreadAttributes
0x1800f1fcf  call    cs:__imp_CreateThread
0x1800f1fd5  mov     rbx, rax
0x1800f1fd8  mov     [rsp+1008h+lpBuffer], rax
0x1800f1fdd  test    rax, rax
0x1800f1fe0  jnz     short loc_1800F1FFB
0x1800f1fe2  call    cs:__imp_GetLastError
0x1800f1fe8  test    eax, eax
0x1800f1fea  jle     short loc_1800F1FF4
0x1800f1fec  movzx   eax, ax
0x1800f1fef  or      eax, 80070000h
0x1800f1ff4  mov     ecx, eax; int
0x1800f1ff6  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f1ffb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800f1ffe  mov     rcx, rbx; hHandle
0x1800f2001  call    cs:__imp_WaitForSingleObject
0x1800f2007  cmp     [rsp+1008h+var_FC0], 4
0x1800f200c  jnz     short loc_1800F2019
0x1800f200e  mov     ecx, 80004005h; int
0x1800f2013  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f2018  nop
0x1800f2019  lea     rcx, [rsp+1008h+lpBuffer]
0x1800f201e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f2023  nop
0x1800f2024  mov     rcx, r15; key
0x1800f2027  call    cs:__imp_WerUnregisterCustomMetadata
0x1800f202d  nop
0x1800f202e  lea     rcx, [rsp+1008h+hReportHandle]
0x1800f2033  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f2038  nop
0x1800f2039  jmp     short loc_1800F204B
0x1800f203b  lea     r14, ?g_Module@@3VCModule@@A; CModule g_Module
0x1800f2042  mov     edi, [rsp+1008h+puLen]
0x1800f2046  mov     rsi, [rsp+1008h+var_FB0]
0x1800f204b  mov     r9d, [rsp+1008h+var_FC0]; unsigned int
0x1800f2050  mov     r8d, edi; int
0x1800f2053  mov     rdx, rsi; void *
0x1800f2056  call    ?LogDredWatsonReport@CD3D12TelemetryHelper@@QEAAXPEAXJI_NII@Z; CD3D12TelemetryHelper::LogDredWatsonReport(void *,long,uint,bool,uint,uint)
0x1800f205b  nop
0x1800f205c  mov     rcx, r14; _Mtx_t
0x1800f205f  call    cs:__imp__Mtx_unlock
0x1800f2065  mov     eax, edi
0x1800f2067  jmp     short loc_1800F206B
0x1800f2069  xor     eax, eax
0x1800f206b  mov     rcx, [rsp+1008h+var_48]
0x1800f2073  xor     rcx, rsp; StackCookie
0x1800f2076  call    __security_check_cookie
0x1800f207b  add     rsp, 0FD0h
0x1800f2082  pop     r15
0x1800f2084  pop     r14
0x1800f2086  pop     r13
0x1800f2088  pop     r12
0x1800f208a  pop     rdi
0x1800f208b  pop     rsi
0x1800f208c  pop     rbx
0x1800f208d  retn
```
