# CKernelReport::ReportAllLiveReports(void)

- ea: `0x140039230`
- end: `0x14003960b`
- name: `?ReportAllLiveReports@CKernelReport@@QEAAJXZ`
- size: `987`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14003494c`
- `0x140035d20`

## callees

- `0x140002470`
- `0x140005468`
- `0x140034d9c`
- `0x1400359ac`
- `0x14003902c`
- `0x140039230`
- `0x140039c40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400393be`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400394d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400393be`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400394d3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14003943f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14003954c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14003943f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14003954c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400395bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400395d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400395e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400395bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400395d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400395e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039335`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039378`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039473`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039335`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039378`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039473`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400392b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400392b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400392a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400392a7`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140039287`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140039287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400392c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400392d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400392c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400392d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400392c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400392c0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1400395ac`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1400395ac`

## string_xrefs

- `0x1400392e2`: `Access denied for the event %ws`
- `0x140039486`: `Failed to open the sub key %ws while reporting for all kernel reports`

## pseudocode

```c
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
        (void *)0x39C,
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
          (void *)0xABD,
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
          v13 = 2816;
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
              (void *)0xB15,
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
      v13 = 2793;
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
0x140039230  push    rbp
0x140039232  push    rbx
0x140039233  push    rsi
0x140039234  push    rdi
0x140039235  push    r14
0x140039237  push    r15
0x140039239  lea     rbp, [rsp-18h]
0x14003923e  sub     rsp, 118h
0x140039245  mov     rax, cs:__security_cookie
0x14003924c  xor     rax, rsp
0x14003924f  mov     [rbp+40h+var_40], rax
0x140039253  mov     rsi, rcx
0x140039256  xor     r14d, r14d
0x140039259  mov     [rsp+140h+var_D8], r14
0x14003925e  mov     [rbp+40h+hKey], r14
0x140039262  mov     [rsp+140h+cSubKeys], r14d
0x140039267  mov     [rsp+140h+var_CC], r14d
0x14003926c  mov     [rsp+140h+cchName], r14d
0x140039271  call    ?CheckForFullLiveReports@CKernelReport@@AEAAJXZ; CKernelReport::CheckForFullLiveReports(void)
0x140039276  lea     rdi, aGlobalWerkerne; "Global\\WerKernelVerticalConvertingLive"...
0x14003927d  mov     r8, rdi; lpName
0x140039280  xor     edx, edx; bInheritHandle
0x140039282  mov     ecx, 100001h; dwDesiredAccess
0x140039287  call    cs:__imp_OpenMutexW
0x14003928d  mov     rbx, rax
0x140039290  lea     rcx, [rax+1]
0x140039294  lea     r15, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003929b  cmp     rcx, 1
0x14003929f  jbe     short loc_1400392C8
0x1400392a1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400392a4  mov     rcx, rax; hHandle
0x1400392a7  call    cs:__imp_WaitForSingleObject
0x1400392ad  test    eax, 0FFFFFF7Fh
0x1400392b2  jnz     short loc_1400392BD
0x1400392b4  mov     rcx, rbx; hMutex
0x1400392b7  call    cs:__imp_ReleaseMutex
0x1400392bd  mov     rcx, rbx; hObject
0x1400392c0  call    cs:__imp_CloseHandle
0x1400392c6  jmp     short loc_140039306
0x1400392c8  call    cs:__imp_GetLastError
0x1400392ce  cmp     eax, 5
0x1400392d1  jnz     short loc_140039306
0x1400392d3  call    cs:__imp_GetLastError
0x1400392d9  mov     rcx, [rbp+48h]; this
0x1400392dd  mov     [rsp+140h+lpcbMaxClassLen], rdi; char *
0x1400392e2  lea     rdx, aAccessDeniedFo; "Access denied for the event %ws"
0x1400392e9  mov     [rsp+140h+lpcbMaxSubKeyLen], rdx; unsigned int
0x1400392ee  mov     dword ptr [rsp+140h+phkResult], eax; wil::details *
0x1400392f2  lea     r9, aCkernelreportW_0; "CKernelReport::WaitForLiveDumpConversio"...
0x1400392f9  mov     r8, r15; unsigned int
0x1400392fc  mov     edx, 39Ch; void *
0x140039301  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x140039306  mov     [rbp+40h+Name], r14w
0x14003930b  mov     [rbp+40h+SubKey], r14w
0x140039310  lea     rcx, [rbp+40h+hKey]
0x140039314  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140039319  mov     [rsp+140h+phkResult], rax; phkResult
0x14003931e  mov     r9d, 0F003Fh; samDesired
0x140039324  xor     r8d, r8d; ulOptions
0x140039327  lea     rdx, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x14003932e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140039335  call    cs:__imp_RegOpenKeyExW
0x14003933b  mov     ebx, eax
0x14003933d  test    eax, eax
0x14003933f  jz      short loc_140039355
0x140039341  jle     loc_1400395CD
0x140039347  movzx   ebx, ax
0x14003934a  or      ebx, 80070000h
0x140039350  jmp     loc_1400395CD
0x140039355  lea     rcx, [rsp+140h+var_D8]
0x14003935a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003935f  mov     [rsp+140h+phkResult], rax; phkResult
0x140039364  mov     r9d, 0F003Fh; samDesired
0x14003936a  xor     r8d, r8d; ulOptions
0x14003936d  lea     rdx, aLivekernelrepo_0; "LiveKernelReports"
0x140039374  mov     rcx, [rbp+40h+hKey]; hKey
0x140039378  call    cs:__imp_RegOpenKeyExW
0x14003937e  mov     ebx, eax
0x140039380  test    eax, eax
0x140039382  jnz     short loc_140039341
0x140039384  mov     [rsp+140h+lpftLastWriteTime], r14; lpftLastWriteTime
0x140039389  mov     [rsp+140h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x14003938e  mov     [rsp+140h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x140039393  mov     [rsp+140h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x140039398  mov     [rsp+140h+lpcValues], r14; lpcValues
0x14003939d  mov     [rsp+140h+lpcbMaxClassLen], r14; char *
0x1400393a2  mov     [rsp+140h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1400393a7  lea     rax, [rsp+140h+cSubKeys]
0x1400393ac  mov     [rsp+140h+phkResult], rax; lpcSubKeys
0x1400393b1  xor     r9d, r9d; lpReserved
0x1400393b4  xor     r8d, r8d; lpcchClass
0x1400393b7  xor     edx, edx; lpClass
0x1400393b9  mov     rcx, [rsp+140h+var_D8]; hKey
0x1400393be  call    cs:__imp_RegQueryInfoKeyW
0x1400393c4  mov     ebx, eax
0x1400393c6  test    eax, eax
0x1400393c8  jz      short loc_140039402
0x1400393ca  jle     short loc_1400393D5
0x1400393cc  movzx   ebx, ax
0x1400393cf  or      ebx, 80070000h
0x1400393d5  mov     rcx, [rbp+48h]; this
0x1400393d9  lea     rax, aFailedToEnumer; "Failed to enumerate the report types"
0x1400393e0  mov     [rsp+140h+lpcbMaxSubKeyLen], rax; int
0x1400393e5  mov     dword ptr [rsp+140h+phkResult], ebx; wil::details *
0x1400393e9  lea     r9, aCkernelreportR_2; "CKernelReport::ReportAllLiveReports"
0x1400393f0  mov     r8, r15; unsigned int
0x1400393f3  mov     edx, 0ABDh; void *
0x1400393f8  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400393fd  jmp     loc_1400395CD
0x140039402  mov     edi, [rsp+140h+cSubKeys]
0x140039406  jmp     loc_1400395C2
0x14003940b  mov     [rsp+140h+cchName], 10h
0x140039413  mov     [rbp+40h+Name], r14w
0x140039418  lea     edx, [rdi-1]; dwIndex
0x14003941b  mov     edi, edx
0x14003941d  mov     [rsp+140h+lpcValues], r14; lpftLastWriteTime
0x140039422  mov     [rsp+140h+lpcbMaxClassLen], r14; lpcchClass
0x140039427  mov     [rsp+140h+lpcbMaxSubKeyLen], r14; lpClass
0x14003942c  mov     [rsp+140h+phkResult], r14; lpReserved
0x140039431  lea     r9, [rsp+140h+cchName]; lpcchName
0x140039436  lea     r8, [rbp+40h+Name]; lpName
0x14003943a  mov     rcx, [rsp+140h+var_D8]; hKey
0x14003943f  call    cs:__imp_RegEnumKeyExW
0x140039445  test    eax, eax
0x140039447  jnz     loc_1400395C2
0x14003944d  mov     [rsp+140h+var_C8], r14
0x140039452  lea     rcx, [rsp+140h+var_C8]
0x140039457  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003945c  mov     [rsp+140h+phkResult], rax; phkResult
0x140039461  mov     r9d, 0F003Fh; samDesired
0x140039467  xor     r8d, r8d; ulOptions
0x14003946a  lea     rdx, [rbp+40h+Name]; lpSubKey
0x14003946e  mov     rcx, [rsp+140h+var_D8]; hKey
0x140039473  call    cs:__imp_RegOpenKeyExW
0x140039479  test    eax, eax
0x14003947b  jz      short loc_140039499
0x14003947d  lea     rdx, [rbp+40h+Name]
0x140039481  mov     [rsp+140h+lpcbMaxClassLen], rdx
0x140039486  lea     rdx, aFailedToOpenTh; "Failed to open the sub key %ws while re"...
0x14003948d  mov     [rsp+140h+lpcbMaxSubKeyLen], rdx
0x140039492  mov     edx, 0AE9h
0x140039497  jmp     short loc_1400394F7
0x140039499  mov     [rsp+140h+lpftLastWriteTime], r14; lpftLastWriteTime
0x14003949e  mov     [rsp+140h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1400394a3  mov     [rsp+140h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1400394a8  mov     [rsp+140h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1400394ad  mov     [rsp+140h+lpcValues], r14; lpcValues
0x1400394b2  mov     [rsp+140h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1400394b7  mov     [rsp+140h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1400394bc  lea     rax, [rsp+140h+var_CC]
0x1400394c1  mov     [rsp+140h+phkResult], rax; lpcSubKeys
0x1400394c6  xor     r9d, r9d; lpReserved
0x1400394c9  xor     r8d, r8d; lpcchClass
0x1400394cc  xor     edx, edx; lpClass
0x1400394ce  mov     rcx, [rsp+140h+var_C8]; hKey
0x1400394d3  call    cs:__imp_RegQueryInfoKeyW
0x1400394d9  test    eax, eax
0x1400394db  jz      short loc_140039513
0x1400394dd  lea     rdx, [rbp+40h+Name]
0x1400394e1  mov     [rsp+140h+lpcbMaxClassLen], rdx; char *
0x1400394e6  lea     rdx, aFailedToQueryT; "Failed to query the report id count for"...
0x1400394ed  mov     [rsp+140h+lpcbMaxSubKeyLen], rdx; unsigned int
0x1400394f2  mov     edx, 0B00h; void *
0x1400394f7  mov     r8, r15; unsigned int
0x1400394fa  lea     r9, aCkernelreportR_2; "CKernelReport::ReportAllLiveReports"
0x140039501  mov     dword ptr [rsp+140h+phkResult], eax; wil::details *
0x140039505  mov     rcx, [rbp+48h]; this
0x140039509  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003950e  jmp     loc_140039599
0x140039513  mov     ebx, [rsp+140h+var_CC]
0x140039517  jmp     short loc_140039595
0x140039519  mov     [rsp+140h+cchName], 28h ; '('
0x140039521  mov     [rbp+40h+SubKey], r14w
0x140039526  dec     ebx
0x140039528  mov     [rsp+140h+lpcValues], r14; lpftLastWriteTime
0x14003952d  mov     [rsp+140h+lpcbMaxClassLen], r14; lpcchClass
0x140039532  mov     [rsp+140h+lpcbMaxSubKeyLen], r14; lpClass
0x140039537  mov     [rsp+140h+phkResult], r14; lpReserved
0x14003953c  lea     r9, [rsp+140h+cchName]; lpcchName
0x140039541  lea     r8, [rbp+40h+SubKey]; lpName
0x140039545  mov     edx, ebx; dwIndex
0x140039547  mov     rcx, [rsp+140h+var_C8]; hKey
0x14003954c  call    cs:__imp_RegEnumKeyExW
0x140039552  lea     rdx, [rbp+40h+Name]; wchar_t *
0x140039556  test    eax, eax
0x140039558  jz      short loc_140039589
0x14003955a  mov     rcx, [rbp+48h]; this
0x14003955e  mov     [rsp+140h+lpcbMaxClassLen], rdx; char *
0x140039563  lea     rdx, aFailedToEnumTh; "Failed to enum the keys for live kernel"...
0x14003956a  mov     [rsp+140h+lpcbMaxSubKeyLen], rdx; unsigned int
0x14003956f  mov     dword ptr [rsp+140h+phkResult], eax; wil::details *
0x140039573  lea     r9, aCkernelreportR_2; "CKernelReport::ReportAllLiveReports"
0x14003957a  mov     r8, r15; unsigned int
0x14003957d  mov     edx, 0B15h; void *
0x140039582  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x140039587  jmp     short loc_140039595
0x140039589  lea     r8, [rbp+40h+SubKey]; lpSubKey
0x14003958d  mov     rcx, rsi; this
0x140039590  call    ?ReportLiveReport@CKernelReport@@QEAAJPEB_W0@Z; CKernelReport::ReportLiveReport(wchar_t const *,wchar_t const *)
0x140039595  test    ebx, ebx
0x140039597  jnz     short loc_140039519
0x140039599  mov     rcx, [rsp+140h+var_C8]
0x14003959e  test    rcx, rcx
0x1400395a1  jz      short loc_1400395B7
0x1400395a3  lea     rdx, [rbp+40h+Name]; lpSubKey
0x1400395a7  mov     rcx, [rsp+140h+var_D8]; hKey
0x1400395ac  call    cs:__imp_RegDeleteKeyW
0x1400395b2  mov     rcx, [rsp+140h+var_C8]; hKey
0x1400395b7  test    rcx, rcx
0x1400395ba  jz      short loc_1400395C2
0x1400395bc  call    cs:__imp_RegCloseKey
0x1400395c2  test    edi, edi
0x1400395c4  jnz     loc_14003940B
0x1400395ca  mov     ebx, r14d
0x1400395cd  mov     rcx, [rbp+40h+hKey]; hKey
0x1400395d1  test    rcx, rcx
0x1400395d4  jz      short loc_1400395DD
0x1400395d6  call    cs:__imp_RegCloseKey
0x1400395dc  nop
0x1400395dd  mov     rcx, [rsp+140h+var_D8]; hKey
0x1400395e2  test    rcx, rcx
0x1400395e5  jz      short loc_1400395ED
0x1400395e7  call    cs:__imp_RegCloseKey
0x1400395ed  mov     eax, ebx
0x1400395ef  mov     rcx, [rbp+40h+var_40]
0x1400395f3  xor     rcx, rsp; StackCookie
0x1400395f6  call    __security_check_cookie
0x1400395fb  add     rsp, 118h
0x140039602  pop     r15
0x140039604  pop     r14
0x140039606  pop     rdi
0x140039607  pop     rsi
0x140039608  pop     rbx
0x140039609  pop     rbp
0x14003960a  retn
```
