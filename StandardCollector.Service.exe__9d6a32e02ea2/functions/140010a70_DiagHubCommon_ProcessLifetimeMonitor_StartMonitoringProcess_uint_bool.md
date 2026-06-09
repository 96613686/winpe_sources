# DiagHubCommon::ProcessLifetimeMonitor::StartMonitoringProcess(uint,bool)

- ea: `0x140010a70`
- end: `0x140010d3a`
- name: `?StartMonitoringProcess@ProcessLifetimeMonitor@DiagHubCommon@@QEAAJI_N@Z`
- size: `714`
- prototype: `__int64 __fastcall(DiagHubCommon::ProcessLifetimeMonitor *this, DWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006620`

## callees

- `0x14000a278`
- `0x140010a70`
- `0x140011220`
- `0x140011368`
- `0x1400113e8`
- `0x1400137e0`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x140010b0f`
- `KERNEL32!OpenProcess` at `0x140010b0f`
- `KERNEL32!RegisterWaitForSingleObject` at `0x140010c0b`
- `KERNEL32!RegisterWaitForSingleObject` at `0x140010c0b`
- `KERNEL32!LeaveCriticalSection` at `0x140010c68`
- `KERNEL32!LeaveCriticalSection` at `0x140010ce7`
- `KERNEL32!LeaveCriticalSection` at `0x140010d07`
- `KERNEL32!LeaveCriticalSection` at `0x140010c68`
- `KERNEL32!LeaveCriticalSection` at `0x140010ce7`
- `KERNEL32!LeaveCriticalSection` at `0x140010d07`
- `KERNEL32!EnterCriticalSection` at `0x140010aae`
- `KERNEL32!EnterCriticalSection` at `0x140010aae`
- `KERNEL32!GetLastError` at `0x140010b22`
- `KERNEL32!GetLastError` at `0x140010c25`
- `KERNEL32!GetLastError` at `0x140010b22`
- `KERNEL32!GetLastError` at `0x140010c25`
- `KERNEL32!CloseHandle` at `0x140010bd6`
- `KERNEL32!CloseHandle` at `0x140010c5e`
- `KERNEL32!CloseHandle` at `0x140010ca3`
- `KERNEL32!CloseHandle` at `0x140010cdd`
- `KERNEL32!CloseHandle` at `0x140010cfb`
- `KERNEL32!CloseHandle` at `0x140010bd6`
- `KERNEL32!CloseHandle` at `0x140010c5e`
- `KERNEL32!CloseHandle` at `0x140010ca3`
- `KERNEL32!CloseHandle` at `0x140010cdd`
- `KERNEL32!CloseHandle` at `0x140010cfb`

## string_xrefs

- `0x140010ae8`: `StartMonitoringProcess was called for a process we are already monitoring.                                         Existing monitoring configuration for process ID %d will not be changed.`
- `0x140010aef`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`
- `0x140010b4b`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`
- `0x140010c4e`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`
- `0x140010cc8`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`
- `0x140010b44`: `Failed to open process (%d) for monitoring. HRESULT: %#08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DiagHubCommon::ProcessLifetimeMonitor::StartMonitoringProcess(
        DiagHubCommon::ProcessLifetimeMonitor *this,
        DWORD a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  unsigned int v5; // esi
  HANDLE v6; // rax
  void *v7; // rbx
  signed int LastError; // eax
  __int64 v9; // rsi
  __int64 v10; // r13
  BOOL v11; // eax
  signed int v12; // eax
  HANDLE *v14; // r13
  void *v15; // rax
  __int64 dwMilliseconds; // [rsp+20h] [rbp-C8h]
  HANDLE v17; // [rsp+30h] [rbp-B8h] BYREF
  _QWORD v18[2]; // [rsp+38h] [rbp-B0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-A0h]
  _DWORD v20[4]; // [rsp+50h] [rbp-98h] BYREF
  __int64 v21; // [rsp+60h] [rbp-88h]
  char v22; // [rsp+68h] [rbp-80h]
  HANDLE hObject; // [rsp+70h] [rbp-78h]
  DiagHubCommon::ProcessLifetimeMonitor *v24; // [rsp+78h] [rbp-70h]
  int v25; // [rsp+80h] [rbp-68h]
  __int64 v26; // [rsp+88h] [rbp-60h]
  char v27; // [rsp+90h] [rbp-58h]
  __int64 v28; // [rsp+98h] [rbp-50h]
  DiagHubCommon::ProcessLifetimeMonitor *v29; // [rsp+A0h] [rbp-48h]
  HANDLE phNewWaitObject; // [rsp+A8h] [rbp-40h] BYREF
  DWORD v31; // [rsp+B0h] [rbp-38h] BYREF

  v31 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v18[0] = 0;
  std::_Hash<std::_Umap_traits<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::find(
    this,
    v18,
    &v31);
  if ( v18[0] != *((_QWORD *)this + 1) )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::ProcessLifetimeMonitor *)((char *)this + 224),
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\ProcessLifetimeMonitor.cpp",
      L"StartMonitoringProcess was called for a process we are already monitoring.                                        "
       " Existing monitoring configuration for process ID %d will not be changed.",
      a2);
    v5 = 1;
LABEL_14:
    LeaveCriticalSection(v4);
    return v5;
  }
  v6 = OpenProcess(0x100000u, 0, a2);
  v7 = v6;
  v17 = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    v5 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v5 = LastError;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::ProcessLifetimeMonitor *)((char *)this + 336),
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\ProcessLifetimeMonitor.cpp",
      L"Failed to open process (%d) for monitoring. HRESULT: %#08x.",
      a2,
      v5);
    goto LABEL_14;
  }
  try
  {
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v29 = this;
    v20[0] = a2;
    v20[2] = 0;
    v21 = 0;
    v22 = 0;
    hObject = 0;
    v24 = this;
    std::_Hash<std::_Umap_traits<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::emplace<std::pair<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>(
      this,
      v18,
      v20);
    if ( hObject )
      CloseHandle(hObject);
    v9 = v18[0];
    v10 = v18[0] + 24LL;
    v11 = RegisterWaitForSingleObject(
            &phNewWaitObject,
            v7,
            DiagHubCommon::ProcessLifetimeMonitor::OnProcessExit,
            (PVOID)(v18[0] + 24LL),
            0xFFFFFFFF,
            8u);
  }
  catch ( std::bad_alloc )
  {
    if ( v17 )
      CloseHandle(v17);
    LeaveCriticalSection(lpCriticalSection);
    return 2147942414LL;
  }
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = this;
  v20[0] = a2;
  v20[2] = 0;
  v21 = 0;
  v22 = 0;
  hObject = 0;
}

```

## disassembly

```asm
0x140010a70  mov     r11, rsp
0x140010a73  mov     [r11+18h], rbx
0x140010a77  push    rsi
0x140010a78  push    rdi
0x140010a79  push    r12
0x140010a7b  push    r13
0x140010a7d  push    r15
0x140010a7f  sub     rsp, 0C0h
0x140010a86  mov     rax, cs:__security_cookie
0x140010a8d  xor     rax, rsp
0x140010a90  mov     [rsp+0E8h+var_30], rax
0x140010a98  mov     r12d, edx
0x140010a9b  mov     r15, rcx
0x140010a9e  mov     [r11-38h], edx
0x140010aa2  lea     rdi, [rcx+40h]
0x140010aa6  mov     [rsp+0E8h+lpCriticalSection], rdi
0x140010aab  mov     rcx, rdi; lpCriticalSection
0x140010aae  call    cs:__imp_EnterCriticalSection
0x140010ab4  nop
0x140010ab5  mov     [rsp+0E8h+var_B0], 0
0x140010abe  lea     r8, [rsp+0E8h+var_38]
0x140010ac6  lea     rdx, [rsp+0E8h+var_B0]
0x140010acb  mov     rcx, r15
0x140010ace  call    ?find@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@std@@@std@@@2@AEBI@Z; std::_Hash<std::_Umap_traits<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::find(uint const &)
0x140010ad3  mov     r8, [r15+8]
0x140010ad7  cmp     [rsp+0E8h+var_B0], r8
0x140010adc  jz      short loc_140010B05
0x140010ade  lea     rcx, [r15+0E0h]; this
0x140010ae5  mov     r9d, r12d
0x140010ae8  lea     r8, aStartmonitorin; "StartMonitoringProcess was called for a"...
0x140010aef  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x140010af6  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x140010afb  mov     esi, 1
0x140010b00  jmp     loc_140010C65
0x140010b05  mov     r8d, r12d; dwProcessId
0x140010b08  xor     edx, edx; bInheritHandle
0x140010b0a  mov     ecx, 100000h; dwDesiredAccess
0x140010b0f  call    cs:__imp_OpenProcess
0x140010b15  mov     rbx, rax
0x140010b18  mov     [rsp+0E8h+var_B8], rax
0x140010b1d  test    rax, rax
0x140010b20  jnz     short loc_140010B5D
0x140010b22  call    cs:__imp_GetLastError
0x140010b28  movzx   esi, ax
0x140010b2b  or      esi, 80070000h
0x140010b31  test    eax, eax
0x140010b33  cmovle  esi, eax
0x140010b36  lea     rcx, [r15+150h]; this
0x140010b3d  mov     dword ptr [rsp+0E8h+dwMilliseconds], esi
0x140010b41  mov     r9d, r12d
0x140010b44  lea     r8, aFailedToOpenPr_0; "Failed to open process (%d) for monitor"...
0x140010b4b  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x140010b52  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x140010b57  nop
0x140010b58  jmp     loc_140010C65
0x140010b5d  mov     [rsp+0E8h+var_68], 0
0x140010b68  mov     [rsp+0E8h+var_60], 0
0x140010b74  mov     [rsp+0E8h+var_58], 0
0x140010b7c  mov     [rsp+0E8h+var_50], 0
0x140010b88  mov     [rsp+0E8h+var_48], r15
0x140010b90  mov     [rsp+0E8h+var_98], r12d
0x140010b95  mov     [rsp+0E8h+var_90], 0
0x140010b9d  mov     [rsp+0E8h+var_88], 0
0x140010ba6  mov     [rsp+0E8h+var_80], 0
0x140010bab  mov     [rsp+0E8h+hObject], 0
0x140010bb4  mov     [rsp+0E8h+var_70], r15
0x140010bb9  lea     r8, [rsp+0E8h+var_98]
0x140010bbe  lea     rdx, [rsp+0E8h+var_B0]
0x140010bc3  mov     rcx, r15
0x140010bc6  call    ??$emplace@U?$pair@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@1@@Z; std::_Hash<std::_Umap_traits<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::emplace<std::pair<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>(std::pair<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess> &&)
0x140010bcb  nop
0x140010bcc  mov     rcx, [rsp+0E8h+hObject]; hObject
0x140010bd1  test    rcx, rcx
0x140010bd4  jz      short loc_140010BDD
0x140010bd6  call    cs:__imp_CloseHandle
0x140010bdc  nop
0x140010bdd  mov     rsi, [rsp+0E8h+var_B0]
0x140010be2  lea     r13, [rsi+18h]
0x140010be6  mov     [rsp+0E8h+dwFlags], 8; dwFlags
0x140010bee  mov     dword ptr [rsp+0E8h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x140010bf6  mov     r9, r13; Context
0x140010bf9  lea     r8, ?OnProcessExit@ProcessLifetimeMonitor@DiagHubCommon@@CAXPEAXE@Z; Callback
0x140010c00  mov     rdx, rbx; hObject
0x140010c03  lea     rcx, [rsp+0E8h+phNewWaitObject]; phNewWaitObject
0x140010c0b  call    cs:__imp_RegisterWaitForSingleObject
0x140010c11  test    eax, eax
0x140010c13  jnz     short loc_140010C75
0x140010c15  mov     r8, rsi
0x140010c18  lea     rdx, [rsp+0E8h+var_B0]
0x140010c1d  mov     rcx, r15
0x140010c20  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@std@@@std@@@1@V21@@Z; std::_Hash<std::_Umap_traits<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>>>)
0x140010c25  call    cs:__imp_GetLastError
0x140010c2b  movzx   esi, ax
0x140010c2e  or      esi, 80070000h
0x140010c34  test    eax, eax
0x140010c36  cmovle  esi, eax
0x140010c39  lea     rcx, [r15+150h]; this
0x140010c40  mov     dword ptr [rsp+0E8h+dwMilliseconds], esi
0x140010c44  mov     r9d, r12d
0x140010c47  lea     r8, aFailedToRegist; "Failed to register process exit handler"...
0x140010c4e  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x140010c55  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x140010c5a  nop
0x140010c5b  mov     rcx, rbx; hObject
0x140010c5e  call    cs:__imp_CloseHandle
0x140010c64  nop
0x140010c65  mov     rcx, rdi; lpCriticalSection
0x140010c68  call    cs:__imp_LeaveCriticalSection
0x140010c6e  mov     eax, esi
0x140010c70  jmp     loc_140010D12
0x140010c75  mov     [r13+0], r12d
0x140010c79  mov     byte ptr [r13+10h], 0
0x140010c7e  mov     rax, [rsp+0E8h+phNewWaitObject]
0x140010c86  mov     [r13+8], rax
0x140010c8a  add     r13, 18h
0x140010c8e  lea     rax, [rsp+0E8h+var_B8]
0x140010c93  cmp     r13, rax
0x140010c96  jz      short loc_140010CB7
0x140010c98  cmp     qword ptr [r13+0], 0
0x140010c9d  jz      short loc_140010CA9
0x140010c9f  mov     rcx, [r13+0]; hObject
0x140010ca3  call    cs:__imp_CloseHandle
0x140010ca9  mov     rax, rbx
0x140010cac  xor     ebx, ebx
0x140010cae  mov     [rsp+0E8h+var_B8], rbx
0x140010cb3  mov     [r13+0], rax
0x140010cb7  lea     rcx, [r15+0E0h]; this
0x140010cbe  mov     r9d, r12d
0x140010cc1  lea     r8, aRegisteredProc; "Registered process exit handler for pro"...
0x140010cc8  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x140010ccf  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x140010cd4  nop
0x140010cd5  test    rbx, rbx
0x140010cd8  jz      short loc_140010CE4
0x140010cda  mov     rcx, rbx; hObject
0x140010cdd  call    cs:__imp_CloseHandle
0x140010ce3  nop
0x140010ce4  mov     rcx, rdi; lpCriticalSection
0x140010ce7  call    cs:__imp_LeaveCriticalSection
0x140010ced  xor     eax, eax
0x140010cef  jmp     short loc_140010D12
0x140010cf1  mov     rcx, [rsp+0E8h+var_B8]; hObject
0x140010cf6  test    rcx, rcx
0x140010cf9  jz      short loc_140010D02
0x140010cfb  call    cs:__imp_CloseHandle
0x140010d01  nop
0x140010d02  mov     rcx, [rsp+0E8h+lpCriticalSection]; lpCriticalSection
0x140010d07  call    cs:__imp_LeaveCriticalSection
0x140010d0d  mov     eax, 8007000Eh
0x140010d12  mov     rcx, [rsp+0E8h+var_30]
0x140010d1a  xor     rcx, rsp; StackCookie
0x140010d1d  call    __security_check_cookie
0x140010d22  mov     rbx, [rsp+0E8h+arg_10]
0x140010d2a  add     rsp, 0C0h
0x140010d31  pop     r15
0x140010d33  pop     r13
0x140010d35  pop     r12
0x140010d37  pop     rdi
0x140010d38  pop     rsi
0x140010d39  retn
```
