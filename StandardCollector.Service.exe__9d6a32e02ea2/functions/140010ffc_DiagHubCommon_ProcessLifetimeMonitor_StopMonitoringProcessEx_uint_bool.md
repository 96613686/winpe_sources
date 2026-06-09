# DiagHubCommon::ProcessLifetimeMonitor::StopMonitoringProcessEx(uint,bool)

- ea: `0x140010ffc`
- end: `0x1400111aa`
- name: `?StopMonitoringProcessEx@ProcessLifetimeMonitor@DiagHubCommon@@AEAAJI_N@Z`
- size: `430`
- prototype: `__int64 __fastcall(DiagHubCommon::ProcessLifetimeMonitor *this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140010fc0`

## callees

- `0x14000a278`
- `0x140010ffc`
- `0x140011220`
- `0x140011368`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `KERNEL32!UnregisterWaitEx` at `0x1400110b7`
- `KERNEL32!UnregisterWaitEx` at `0x1400110b7`
- `KERNEL32!LeaveCriticalSection` at `0x140011180`
- `KERNEL32!LeaveCriticalSection` at `0x140011180`
- `KERNEL32!EnterCriticalSection` at `0x14001105d`
- `KERNEL32!EnterCriticalSection` at `0x14001105d`
- `KERNEL32!GetLastError` at `0x1400110c1`
- `KERNEL32!GetLastError` at `0x1400110c1`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x140011038`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x140011162`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x140011038`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x140011162`

## string_xrefs

- `0x14001109b`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`
- `0x1400110e5`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`
- `0x140011112`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`
- `0x14001113f`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`
- `0x140011094`: `StopMonitoringProcessEx was called for a process (PID: %d) we are not monitoring.                                         Existing monitoring configuration will not be changed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiagHubCommon::ProcessLifetimeMonitor::StopMonitoringProcessEx(
        DiagHubCommon::ProcessLifetimeMonitor *this,
        unsigned int a2)
{
  __int64 v4; // rcx
  _QWORD *v5; // rbx
  unsigned int v6; // ebx
  DWORD LastError; // eax
  int v8; // ebp
  __int64 v9; // rcx
  DWORD v11; // [rsp+20h] [rbp-48h]
  __int64 v12; // [rsp+38h] [rbp-30h] BYREF
  __int64 v13; // [rsp+40h] [rbp-28h] BYREF

  LODWORD(v13) = a2;
  LODWORD(v12) = a2;
  v4 = *((_QWORD *)this + 20);
  if ( !v4 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 16LL))(v4, &v12);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v12 = 0;
  std::_Hash<std::_Umap_traits<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::find(
    this,
    &v12,
    &v13);
  v5 = (_QWORD *)v12;
  if ( v12 == *((_QWORD *)this + 1) )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::ProcessLifetimeMonitor *)((char *)this + 224),
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\ProcessLifetimeMonitor.cpp",
      L"StopMonitoringProcessEx was called for a process (PID: %d) we are not monitoring.                                 "
       "        Existing monitoring configuration will not be changed.",
      a2);
    v6 = 1;
  }
  else if ( UnregisterWaitEx(*(HANDLE *)(v12 + 32), 0) || (LastError = GetLastError(), v8 = LastError, LastError == 997) )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::ProcessLifetimeMonitor *)((char *)this + 224),
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\ProcessLifetimeMonitor.cpp",
      L"Unregistered process exit handler for process ID: %d",
      a2);
    std::_Hash<std::_Umap_traits<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>>>,0>(
      this,
      &v13,
      v5);
    if ( !*((_QWORD *)this + 2) )
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::ProcessLifetimeMonitor *)((char *)this + 224),
        L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\ProcessLifetimeMonitor.cpp",
        L"Session has no remaining target processes");
      LODWORD(v13) = -1;
      v9 = *((_QWORD *)this + 20);
      if ( !v9 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 16LL))(v9, &v13);
    }
    v6 = 0;
  }
  else
  {
    v11 = LastError;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::ProcessLifetimeMonitor *)((char *)this + 224),
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\ProcessLifetimeMonitor.cpp",
      L"Failed to unregister process exit handler for process ID: %d. Error code: %#08x",
      a2,
      v11);
    v6 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v6 = v8;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return v6;
}

```

## disassembly

```asm
0x140010ffc  mov     r11, rsp
0x140010fff  mov     [r11+18h], rbx
0x140011003  mov     [r11+20h], rbp
0x140011007  push    rsi
0x140011008  push    rdi
0x140011009  push    r14
0x14001100b  sub     rsp, 50h
0x14001100f  mov     rax, cs:__security_cookie
0x140011016  xor     rax, rsp
0x140011019  mov     [rsp+68h+var_20], rax
0x14001101e  mov     r14d, edx
0x140011021  mov     rsi, rcx
0x140011024  mov     [r11-28h], edx
0x140011028  mov     [r11-30h], edx
0x14001102c  mov     rcx, [rcx+0A0h]
0x140011033  test    rcx, rcx
0x140011036  jnz     short loc_14001103F
0x140011038  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ
0x14001103e  int     3; Trap to Debugger
0x14001103f  mov     rax, [rcx]
0x140011042  lea     rdx, [rsp+68h+var_30]
0x140011047  mov     rax, [rax+10h]
0x14001104b  call    cs:__guard_dispatch_icall_fptr
0x140011051  lea     rdi, [rsi+40h]
0x140011055  mov     [rsp+68h+var_38], rdi
0x14001105a  mov     rcx, rdi; lpCriticalSection
0x14001105d  call    cs:__imp_EnterCriticalSection
0x140011063  nop
0x140011064  mov     [rsp+68h+var_30], 0
0x14001106d  lea     r8, [rsp+68h+var_28]
0x140011072  lea     rdx, [rsp+68h+var_30]
0x140011077  mov     rcx, rsi
0x14001107a  call    ?find@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@std@@@std@@@2@AEBI@Z
0x14001107f  mov     rbx, [rsp+68h+var_30]
0x140011084  cmp     rbx, [rsi+8]
0x140011088  jnz     short loc_1400110B1
0x14001108a  lea     rcx, [rsi+0E0h]; this
0x140011091  mov     r9d, r14d
0x140011094  lea     r8, aStopmonitoring
0x14001109b  lea     rdx, aDAWork1SSource_1
0x1400110a2  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ
0x1400110a7  mov     ebx, 1
0x1400110ac  jmp     loc_14001117D
0x1400110b1  xor     edx, edx; CompletionEvent
0x1400110b3  mov     rcx, [rbx+20h]; WaitHandle
0x1400110b7  call    cs:__imp_UnregisterWaitEx
0x1400110bd  test    eax, eax
0x1400110bf  jnz     short loc_140011101
0x1400110c1  call    cs:__imp_GetLastError
0x1400110c7  mov     ebp, eax
0x1400110c9  cmp     eax, 3E5h
0x1400110ce  jz      short loc_140011101
0x1400110d0  lea     rcx, [rsi+0E0h]; this
0x1400110d7  mov     [rsp+68h+var_48], eax
0x1400110db  mov     r9d, r14d
0x1400110de  lea     r8, aFailedToUnregi
0x1400110e5  lea     rdx, aDAWork1SSource_1
0x1400110ec  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ
0x1400110f1  movzx   ebx, bp
0x1400110f4  or      ebx, 80070000h
0x1400110fa  test    ebp, ebp
0x1400110fc  cmovle  ebx, ebp
0x1400110ff  jmp     short loc_14001117D
0x140011101  lea     rbp, [rsi+0E0h]
0x140011108  mov     r9d, r14d
0x14001110b  lea     r8, aUnregisteredPr
0x140011112  lea     rdx, aDAWork1SSource_1
0x140011119  mov     rcx, rbp; this
0x14001111c  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ
0x140011121  mov     r8, rbx
0x140011124  lea     rdx, [rsp+68h+var_28]
0x140011129  mov     rcx, rsi
0x14001112c  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@std@@@std@@@1@V21@@Z
0x140011131  cmp     qword ptr [rsi+10h], 0
0x140011136  jnz     short loc_14001117B
0x140011138  lea     r8, aSessionHasNoRe
0x14001113f  lea     rdx, aDAWork1SSource_1
0x140011146  mov     rcx, rbp; this
0x140011149  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ
0x14001114e  mov     dword ptr [rsp+68h+var_28], 0FFFFFFFFh
0x140011156  mov     rcx, [rsi+0A0h]
0x14001115d  test    rcx, rcx
0x140011160  jnz     short loc_140011169
0x140011162  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ
0x140011168  int     3; Trap to Debugger
0x140011169  mov     rax, [rcx]
0x14001116c  lea     rdx, [rsp+68h+var_28]
0x140011171  mov     rax, [rax+10h]
0x140011175  call    cs:__guard_dispatch_icall_fptr
0x14001117b  xor     ebx, ebx
0x14001117d  mov     rcx, rdi; lpCriticalSection
0x140011180  call    cs:__imp_LeaveCriticalSection
0x140011186  mov     eax, ebx
0x140011188  mov     rcx, [rsp+68h+var_20]
0x14001118d  xor     rcx, rsp; StackCookie
0x140011190  call    __security_check_cookie
0x140011195  lea     r11, [rsp+68h+var_18]
0x14001119a  mov     rbx, [r11+30h]
0x14001119e  mov     rbp, [r11+38h]
0x1400111a2  mov     rsp, r11
0x1400111a5  pop     r14
0x1400111a7  pop     rdi
0x1400111a8  pop     rsi
0x1400111a9  retn
```
