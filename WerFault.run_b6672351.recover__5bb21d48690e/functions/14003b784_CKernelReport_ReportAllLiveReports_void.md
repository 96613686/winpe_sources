# CKernelReport::ReportAllLiveReports(void)

- ea: `0x14003b784`
- end: `0x14003bbcd`
- name: `?ReportAllLiveReports@CKernelReport@@QEAAJXZ`
- size: `1097`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140036e5c`
- `0x140038274`

## callees

- `0x140002490`
- `0x14000551c`
- `0x1400372dc`
- `0x140037ec4`
- `0x14003b56c`
- `0x14003b784`
- `0x14003c2bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003b942`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003ba69`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003b942`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003ba69`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14003b9c9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14003baeb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14003b9c9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14003baeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003bb6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003bb8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003bba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003bb6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003bb8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003bba2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003b8ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003b8f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003ba03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003b8ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003b8f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003ba03`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14003b817`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14003b817`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003b801`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003b801`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14003b7db`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14003b7db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b845`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b826`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b826`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14003bb55`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14003bb55`

## string_xrefs

- `0x14003b85a`: `Access denied for the event %ws`
- `0x14003ba1c`: `Failed to open the sub key %ws while reporting for all kernel reports`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKernelReport::ReportAllLiveReports(CKernelReport *this)
{
  HANDLE v2; // rax
  void *v3; // rbx
  HKEY *v4; // rax
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  bool v7; // cc
  HKEY *v8; // rax
  LSTATUS v9; // eax
  DWORD v10; // edi
  HKEY *v11; // rax
  LSTATUS v12; // eax
  __int64 v13; // rdx
  DWORD v14; // ebx
  LSTATUS v15; // eax
  HKEY v16; // rcx
  wil::details *phkResult; // [rsp+20h] [rbp-E0h]
  wil::details *phkResulta; // [rsp+20h] [rbp-E0h]
  wil::details *phkResultb; // [rsp+20h] [rbp-E0h]
  wil::details *phkResultc; // [rsp+20h] [rbp-E0h]
  const char *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  const char *lpcbMaxClassLen; // [rsp+30h] [rbp-D0h]
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v25; // [rsp+68h] [rbp-98h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-90h] BYREF
  DWORD v27; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY v28; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[20]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR SubKey[40]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+148h] [rbp+48h]

  v25 = 0;
  hKey = 0;
  cSubKeys = 0;
  v27 = 0;
  cchName = 0;
  CKernelReport::CheckForFullLiveReports(this);
  v2 = OpenMutexW(0x100001u, 0, L"Global\\WerKernelVerticalConvertingLiveDump");
  v3 = v2;
  if ( (unsigned __int64)v2 + 1 <= 1 )
  {
    if ( GetLastError() == 5 )
    {
      LODWORD(phkResult) = GetLastError();
      wil::details::in1diag4::Log_Win32Msg(
        retaddr,
        (void *)0x392,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
        "CKernelReport::WaitForLiveDumpConversion",
        phkResult,
        (unsigned int)"Access denied for the event %ws",
        (const char *)L"Global\\WerKernelVerticalConvertingLiveDump");
    }
  }
  else
  {
    if ( (WaitForSingleObject(v2, 0xFFFFFFFF) & 0xFFFFFF7F) == 0 )
      ReleaseMutex(v3);
    CloseHandle(v3);
  }
  Name[0] = 0;
  SubKey[0] = 0;
  v4 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_wszLiveKernelReportsQueueRoot, 0, 0xF003Fu, v4);
  v6 = v5;
  v7 = v5 <= 0;
  if ( !v5 )
  {
    v8 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v25);
    v5 = RegOpenKeyExW(hKey, L"LiveKernelReports", 0, 0xF003Fu, v8);
    v6 = v5;
    v7 = v5 <= 0;
    if ( !v5 )
    {
      v9 = RegQueryInfoKeyW(v25, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      v6 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v6 = (unsigned __int16)v9 | 0x80070000;
        LODWORD(phkResulta) = v6;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0xB33,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::ReportAllLiveReports",
          phkResulta,
          (int)"Failed to enumerate the report types",
          lpcbMaxClassLen);
        goto LABEL_33;
      }
      v10 = cSubKeys;
      while ( 1 )
      {
        do
        {
          if ( !v10 )
          {
            v6 = 0;
            goto LABEL_33;
          }
          cchName = 16;
          Name[0] = 0;
          --v10;
        }
        while ( RegEnumKeyExW(v25, v10, Name, &cchName, 0, 0, 0, 0) );
        v28 = 0;
        v11 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v28);
        v12 = RegOpenKeyExW(v25, Name, 0, 0xF003Fu, v11);
        if ( v12 )
          break;
        v12 = RegQueryInfoKeyW(v28, 0, 0, 0, &v27, 0, 0, 0, 0, 0, 0, 0);
        if ( v12 )
        {
          lpcbMaxSubKeyLen = "Failed to query the report id count for %ws.";
          v13 = 2934;
          goto LABEL_21;
        }
        v14 = v27;
        while ( v14 )
        {
          cchName = 40;
          SubKey[0] = 0;
          v15 = RegEnumKeyExW(v28, --v14, SubKey, &cchName, 0, 0, 0, 0);
          if ( v15 )
          {
            LODWORD(phkResultc) = v15;
            wil::details::in1diag4::Log_Win32Msg(
              retaddr,
              (void *)0xB8B,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
              "CKernelReport::ReportAllLiveReports",
              phkResultc,
              (unsigned int)"Failed to enum the keys for live kernel event %ws",
              (const char *)Name);
          }
          else
          {
            CKernelReport::ReportLiveReport(this, Name, SubKey);
          }
        }
LABEL_27:
        v16 = v28;
        if ( v28 )
        {
          RegDeleteKeyW(v25, Name);
          v16 = v28;
        }
        if ( v16 )
          RegCloseKey(v16);
      }
      lpcbMaxSubKeyLen = "Failed to open the sub key %ws while reporting for all kernel reports";
      v13 = 2911;
LABEL_21:
      LODWORD(phkResultb) = v12;
      wil::details::in1diag4::Log_Win32Msg(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
        "CKernelReport::ReportAllLiveReports",
        phkResultb,
        (unsigned int)lpcbMaxSubKeyLen,
        (const char *)Name);
      goto LABEL_27;
    }
  }
  if ( !v7 )
    v6 = (unsigned __int16)v5 | 0x80070000;
LABEL_33:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v25 )
    RegCloseKey(v25);
  return v6;
}

```

## disassembly

```asm
0x14003b784  push    rbp
0x14003b786  push    rbx
0x14003b787  push    rsi
0x14003b788  push    rdi
0x14003b789  push    r14
0x14003b78b  push    r15
0x14003b78d  lea     rbp, [rsp-18h]
0x14003b792  sub     rsp, 118h
0x14003b799  mov     rax, cs:__security_cookie
0x14003b7a0  xor     rax, rsp
0x14003b7a3  mov     [rbp+40h+var_40], rax
0x14003b7a7  mov     rsi, rcx
0x14003b7aa  xor     r14d, r14d
0x14003b7ad  mov     [rsp+140h+var_D8], r14
0x14003b7b2  mov     [rbp+40h+hKey], r14
0x14003b7b6  mov     [rsp+140h+cSubKeys], r14d
0x14003b7bb  mov     [rsp+140h+var_CC], r14d
0x14003b7c0  mov     [rsp+140h+cchName], r14d
0x14003b7c5  call    ?CheckForFullLiveReports@CKernelReport@@AEAAJXZ; CKernelReport::CheckForFullLiveReports(void)
0x14003b7ca  lea     rdi, aGlobalWerkerne; "Global\\WerKernelVerticalConvertingLive"...
0x14003b7d1  mov     r8, rdi; lpName
0x14003b7d4  xor     edx, edx; bInheritHandle
0x14003b7d6  mov     ecx, 100001h; dwDesiredAccess
0x14003b7db  call    cs:__imp_OpenMutexW
0x14003b7e2  nop     dword ptr [rax+rax+00h]
0x14003b7e7  mov     rbx, rax
0x14003b7ea  lea     rcx, [rax+1]
0x14003b7ee  lea     r15, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003b7f5  cmp     rcx, 1
0x14003b7f9  jbe     short loc_14003B834
0x14003b7fb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14003b7fe  mov     rcx, rax; hHandle
0x14003b801  call    cs:__imp_WaitForSingleObject
0x14003b808  nop     dword ptr [rax+rax+00h]
0x14003b80d  test    eax, 0FFFFFF7Fh
0x14003b812  jnz     short loc_14003B823
0x14003b814  mov     rcx, rbx; hMutex
0x14003b817  call    cs:__imp_ReleaseMutex
0x14003b81e  nop     dword ptr [rax+rax+00h]
0x14003b823  mov     rcx, rbx; hObject
0x14003b826  call    cs:__imp_CloseHandle
0x14003b82d  nop     dword ptr [rax+rax+00h]
0x14003b832  jmp     short loc_14003B87E
0x14003b834  call    cs:__imp_GetLastError
0x14003b83b  nop     dword ptr [rax+rax+00h]
0x14003b840  cmp     eax, 5
0x14003b843  jnz     short loc_14003B87E
0x14003b845  call    cs:__imp_GetLastError
0x14003b84c  nop     dword ptr [rax+rax+00h]
0x14003b851  mov     rcx, [rbp+48h]; this
0x14003b855  mov     [rsp+140h+lpcbMaxClassLen], rdi; char *
0x14003b85a  lea     rdx, aAccessDeniedFo; "Access denied for the event %ws"
0x14003b861  mov     [rsp+140h+lpcbMaxSubKeyLen], rdx; unsigned int
0x14003b866  mov     dword ptr [rsp+140h+phkResult], eax; wil::details *
0x14003b86a  lea     r9, aCkernelreportW_0; "CKernelReport::WaitForLiveDumpConversio"...
0x14003b871  mov     r8, r15; unsigned int
0x14003b874  mov     edx, 392h; void *
0x14003b879  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003b87e  mov     [rbp+40h+Name], r14w
0x14003b883  mov     [rbp+40h+SubKey], r14w
0x14003b888  lea     rcx, [rbp+40h+hKey]
0x14003b88c  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003b891  mov     [rsp+140h+phkResult], rax; phkResult
0x14003b896  mov     r9d, 0F003Fh; samDesired
0x14003b89c  xor     r8d, r8d; ulOptions
0x14003b89f  lea     rdx, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x14003b8a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003b8ad  call    cs:__imp_RegOpenKeyExW
0x14003b8b4  nop     dword ptr [rax+rax+00h]
0x14003b8b9  mov     ebx, eax
0x14003b8bb  test    eax, eax
0x14003b8bd  jz      short loc_14003B8D3
0x14003b8bf  jle     loc_14003BB82
0x14003b8c5  movzx   ebx, ax
0x14003b8c8  or      ebx, 80070000h
0x14003b8ce  jmp     loc_14003BB82
0x14003b8d3  lea     rcx, [rsp+140h+var_D8]
0x14003b8d8  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003b8dd  mov     [rsp+140h+phkResult], rax; phkResult
0x14003b8e2  mov     r9d, 0F003Fh; samDesired
0x14003b8e8  xor     r8d, r8d; ulOptions
0x14003b8eb  lea     rdx, aLivekernelrepo_0; "LiveKernelReports"
0x14003b8f2  mov     rcx, [rbp+40h+hKey]; hKey
0x14003b8f6  call    cs:__imp_RegOpenKeyExW
0x14003b8fd  nop     dword ptr [rax+rax+00h]
0x14003b902  mov     ebx, eax
0x14003b904  test    eax, eax
0x14003b906  jnz     short loc_14003B8BF
0x14003b908  mov     [rsp+140h+lpftLastWriteTime], r14; lpftLastWriteTime
0x14003b90d  mov     [rsp+140h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x14003b912  mov     [rsp+140h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x14003b917  mov     [rsp+140h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x14003b91c  mov     [rsp+140h+lpcValues], r14; lpcValues
0x14003b921  mov     [rsp+140h+lpcbMaxClassLen], r14; char *
0x14003b926  mov     [rsp+140h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x14003b92b  lea     rax, [rsp+140h+cSubKeys]
0x14003b930  mov     [rsp+140h+phkResult], rax; lpcSubKeys
0x14003b935  xor     r9d, r9d; lpReserved
0x14003b938  xor     r8d, r8d; lpcchClass
0x14003b93b  xor     edx, edx; lpClass
0x14003b93d  mov     rcx, [rsp+140h+var_D8]; hKey
0x14003b942  call    cs:__imp_RegQueryInfoKeyW
0x14003b949  nop     dword ptr [rax+rax+00h]
0x14003b94e  mov     ebx, eax
0x14003b950  test    eax, eax
0x14003b952  jz      short loc_14003B98C
0x14003b954  jle     short loc_14003B95F
0x14003b956  movzx   ebx, ax
0x14003b959  or      ebx, 80070000h
0x14003b95f  mov     rcx, [rbp+48h]; this
0x14003b963  lea     rax, aFailedToEnumer; "Failed to enumerate the report types"
0x14003b96a  mov     [rsp+140h+lpcbMaxSubKeyLen], rax; int
0x14003b96f  mov     dword ptr [rsp+140h+phkResult], ebx; wil::details *
0x14003b973  lea     r9, aCkernelreportR_2; "CKernelReport::ReportAllLiveReports"
0x14003b97a  mov     r8, r15; unsigned int
0x14003b97d  mov     edx, 0B33h; void *
0x14003b982  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003b987  jmp     loc_14003BB82
0x14003b98c  mov     edi, [rsp+140h+cSubKeys]
0x14003b990  jmp     loc_14003BB77
0x14003b995  mov     [rsp+140h+cchName], 10h
0x14003b99d  mov     [rbp+40h+Name], r14w
0x14003b9a2  lea     edx, [rdi-1]; dwIndex
0x14003b9a5  mov     edi, edx
0x14003b9a7  mov     [rsp+140h+lpcValues], r14; lpftLastWriteTime
0x14003b9ac  mov     [rsp+140h+lpcbMaxClassLen], r14; lpcchClass
0x14003b9b1  mov     [rsp+140h+lpcbMaxSubKeyLen], r14; lpClass
0x14003b9b6  mov     [rsp+140h+phkResult], r14; lpReserved
0x14003b9bb  lea     r9, [rsp+140h+cchName]; lpcchName
0x14003b9c0  lea     r8, [rbp+40h+Name]; lpName
0x14003b9c4  mov     rcx, [rsp+140h+var_D8]; hKey
0x14003b9c9  call    cs:__imp_RegEnumKeyExW
0x14003b9d0  nop     dword ptr [rax+rax+00h]
0x14003b9d5  test    eax, eax
0x14003b9d7  jnz     loc_14003BB77
0x14003b9dd  mov     [rsp+140h+var_C8], r14
0x14003b9e2  lea     rcx, [rsp+140h+var_C8]
0x14003b9e7  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003b9ec  mov     [rsp+140h+phkResult], rax; phkResult
0x14003b9f1  mov     r9d, 0F003Fh; samDesired
0x14003b9f7  xor     r8d, r8d; ulOptions
0x14003b9fa  lea     rdx, [rbp+40h+Name]; lpSubKey
0x14003b9fe  mov     rcx, [rsp+140h+var_D8]; hKey
0x14003ba03  call    cs:__imp_RegOpenKeyExW
0x14003ba0a  nop     dword ptr [rax+rax+00h]
0x14003ba0f  test    eax, eax
0x14003ba11  jz      short loc_14003BA2F
0x14003ba13  lea     rdx, [rbp+40h+Name]
0x14003ba17  mov     [rsp+140h+lpcbMaxClassLen], rdx
0x14003ba1c  lea     rdx, aFailedToOpenTh; "Failed to open the sub key %ws while re"...
0x14003ba23  mov     [rsp+140h+lpcbMaxSubKeyLen], rdx
0x14003ba28  mov     edx, 0B5Fh
0x14003ba2d  jmp     short loc_14003BA93
0x14003ba2f  mov     [rsp+140h+lpftLastWriteTime], r14; lpftLastWriteTime
0x14003ba34  mov     [rsp+140h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x14003ba39  mov     [rsp+140h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x14003ba3e  mov     [rsp+140h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x14003ba43  mov     [rsp+140h+lpcValues], r14; lpcValues
0x14003ba48  mov     [rsp+140h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x14003ba4d  mov     [rsp+140h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x14003ba52  lea     rax, [rsp+140h+var_CC]
0x14003ba57  mov     [rsp+140h+phkResult], rax; lpcSubKeys
0x14003ba5c  xor     r9d, r9d; lpReserved
0x14003ba5f  xor     r8d, r8d; lpcchClass
0x14003ba62  xor     edx, edx; lpClass
0x14003ba64  mov     rcx, [rsp+140h+var_C8]; hKey
0x14003ba69  call    cs:__imp_RegQueryInfoKeyW
0x14003ba70  nop     dword ptr [rax+rax+00h]
0x14003ba75  test    eax, eax
0x14003ba77  jz      short loc_14003BAAF
0x14003ba79  lea     rdx, [rbp+40h+Name]
0x14003ba7d  mov     [rsp+140h+lpcbMaxClassLen], rdx; char *
0x14003ba82  lea     rdx, aFailedToQueryT; "Failed to query the report id count for"...
0x14003ba89  mov     [rsp+140h+lpcbMaxSubKeyLen], rdx; unsigned int
0x14003ba8e  mov     edx, 0B76h; void *
0x14003ba93  mov     r8, r15; unsigned int
0x14003ba96  lea     r9, aCkernelreportR_2; "CKernelReport::ReportAllLiveReports"
0x14003ba9d  mov     dword ptr [rsp+140h+phkResult], eax; wil::details *
0x14003baa1  mov     rcx, [rbp+48h]; this
0x14003baa5  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003baaa  jmp     loc_14003BB42
0x14003baaf  mov     ebx, [rsp+140h+var_CC]
0x14003bab3  jmp     loc_14003BB3A
0x14003bab8  mov     [rsp+140h+cchName], 28h ; '('
0x14003bac0  mov     [rbp+40h+SubKey], r14w
0x14003bac5  dec     ebx
0x14003bac7  mov     [rsp+140h+lpcValues], r14; lpftLastWriteTime
0x14003bacc  mov     [rsp+140h+lpcbMaxClassLen], r14; lpcchClass
0x14003bad1  mov     [rsp+140h+lpcbMaxSubKeyLen], r14; lpClass
0x14003bad6  mov     [rsp+140h+phkResult], r14; lpReserved
0x14003badb  lea     r9, [rsp+140h+cchName]; lpcchName
0x14003bae0  lea     r8, [rbp+40h+SubKey]; lpName
0x14003bae4  mov     edx, ebx; dwIndex
0x14003bae6  mov     rcx, [rsp+140h+var_C8]; hKey
0x14003baeb  call    cs:__imp_RegEnumKeyExW
0x14003baf2  nop     dword ptr [rax+rax+00h]
0x14003baf7  lea     rdx, [rbp+40h+Name]; wchar_t *
0x14003bafb  test    eax, eax
0x14003bafd  jz      short loc_14003BB2E
0x14003baff  mov     rcx, [rbp+48h]; this
0x14003bb03  mov     [rsp+140h+lpcbMaxClassLen], rdx; char *
0x14003bb08  lea     rdx, aFailedToEnumTh; "Failed to enum the keys for live kernel"...
0x14003bb0f  mov     [rsp+140h+lpcbMaxSubKeyLen], rdx; unsigned int
0x14003bb14  mov     dword ptr [rsp+140h+phkResult], eax; wil::details *
0x14003bb18  lea     r9, aCkernelreportR_2; "CKernelReport::ReportAllLiveReports"
0x14003bb1f  mov     r8, r15; unsigned int
0x14003bb22  mov     edx, 0B8Bh; void *
0x14003bb27  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003bb2c  jmp     short loc_14003BB3A
0x14003bb2e  lea     r8, [rbp+40h+SubKey]; lpSubKey
0x14003bb32  mov     rcx, rsi; this
0x14003bb35  call    ?ReportLiveReport@CKernelReport@@QEAAJPEB_W0@Z; CKernelReport::ReportLiveReport(wchar_t const *,wchar_t const *)
0x14003bb3a  test    ebx, ebx
0x14003bb3c  jnz     loc_14003BAB8
0x14003bb42  mov     rcx, [rsp+140h+var_C8]
0x14003bb47  test    rcx, rcx
0x14003bb4a  jz      short loc_14003BB66
0x14003bb4c  lea     rdx, [rbp+40h+Name]; lpSubKey
0x14003bb50  mov     rcx, [rsp+140h+var_D8]; hKey
0x14003bb55  call    cs:__imp_RegDeleteKeyW
0x14003bb5c  nop     dword ptr [rax+rax+00h]
0x14003bb61  mov     rcx, [rsp+140h+var_C8]; hKey
0x14003bb66  test    rcx, rcx
0x14003bb69  jz      short loc_14003BB77
0x14003bb6b  call    cs:__imp_RegCloseKey
0x14003bb72  nop     dword ptr [rax+rax+00h]
0x14003bb77  test    edi, edi
0x14003bb79  jnz     loc_14003B995
0x14003bb7f  mov     ebx, r14d
0x14003bb82  mov     rcx, [rbp+40h+hKey]; hKey
0x14003bb86  test    rcx, rcx
0x14003bb89  jz      short loc_14003BB98
0x14003bb8b  call    cs:__imp_RegCloseKey
0x14003bb92  nop     dword ptr [rax+rax+00h]
0x14003bb97  nop
0x14003bb98  mov     rcx, [rsp+140h+var_D8]; hKey
0x14003bb9d  test    rcx, rcx
0x14003bba0  jz      short loc_14003BBAE
0x14003bba2  call    cs:__imp_RegCloseKey
0x14003bba9  nop     dword ptr [rax+rax+00h]
0x14003bbae  mov     eax, ebx
0x14003bbb0  mov     rcx, [rbp+40h+var_40]
0x14003bbb4  xor     rcx, rsp; StackCookie
0x14003bbb7  call    __security_check_cookie
0x14003bbbc  add     rsp, 118h
0x14003bbc3  pop     r15
0x14003bbc5  pop     r14
0x14003bbc7  pop     rdi
0x14003bbc8  pop     rsi
0x14003bbc9  pop     rbx
0x14003bbca  pop     rbp
0x14003bbcb  retn
```
