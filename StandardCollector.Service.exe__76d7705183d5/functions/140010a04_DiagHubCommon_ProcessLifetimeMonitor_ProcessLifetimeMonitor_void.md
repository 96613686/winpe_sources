# DiagHubCommon::ProcessLifetimeMonitor::~ProcessLifetimeMonitor(void)

- ea: `0x140010a04`
- end: `0x140010a70`
- name: `??1ProcessLifetimeMonitor@DiagHubCommon@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(DiagHubCommon::ProcessLifetimeMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140005a10`

## callees

- `0x140001fac`
- `0x14000d7fc`
- `0x140010a04`
- `0x140010d8c`
- `0x1400112f4`
- `0x140014c70`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140010a4e`
- `KERNEL32!DeleteCriticalSection` at `0x140010a4e`

## pseudocode

```c
void __fastcall DiagHubCommon::ProcessLifetimeMonitor::~ProcessLifetimeMonitor(
        DiagHubCommon::ProcessLifetimeMonitor *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx

  DiagHubCommon::ProcessLifetimeMonitor::ResetMonitoring(this);
  DiagHubCommon::Logger::~Logger((DiagHubCommon::ProcessLifetimeMonitor *)((char *)this + 168));
  v3 = *((_QWORD *)this + 20);
  if ( v3 )
  {
    LOBYTE(v2) = v3 != (_QWORD)this + 104;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, v2);
    *((_QWORD *)this + 20) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>((char *)this + 24);
  std::list<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>::~list<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>((char *)this + 8);
}

```

## disassembly

```asm
0x140010a04  mov     [rsp+arg_0], rbx
0x140010a09  push    rdi
0x140010a0a  sub     rsp, 20h
0x140010a0e  mov     rbx, rcx
0x140010a11  call    ?ResetMonitoring@ProcessLifetimeMonitor@DiagHubCommon@@QEAAXXZ; DiagHubCommon::ProcessLifetimeMonitor::ResetMonitoring(void)
0x140010a16  lea     rcx, [rbx+0A8h]; this
0x140010a1d  call    ??1Logger@DiagHubCommon@@QEAA@XZ; DiagHubCommon::Logger::~Logger(void)
0x140010a22  lea     rdi, [rbx+68h]
0x140010a26  mov     rcx, [rdi+38h]
0x140010a2a  test    rcx, rcx
0x140010a2d  jz      short loc_140010A4A
0x140010a2f  cmp     rcx, rdi
0x140010a32  setnz   dl
0x140010a35  mov     rax, [rcx]
0x140010a38  mov     rax, [rax+20h]
0x140010a3c  call    cs:__guard_dispatch_icall_fptr
0x140010a42  mov     qword ptr [rdi+38h], 0
0x140010a4a  lea     rcx, [rbx+40h]; lpCriticalSection
0x140010a4e  call    cs:__imp_DeleteCriticalSection
0x140010a54  lea     rcx, [rbx+18h]
0x140010a58  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>(void)
0x140010a5d  lea     rcx, [rbx+8]
0x140010a61  mov     rbx, [rsp+28h+arg_0]
0x140010a66  add     rsp, 20h
0x140010a6a  pop     rdi
0x140010a6b  jmp     ??1?$list@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>::~list<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>(void)
```
