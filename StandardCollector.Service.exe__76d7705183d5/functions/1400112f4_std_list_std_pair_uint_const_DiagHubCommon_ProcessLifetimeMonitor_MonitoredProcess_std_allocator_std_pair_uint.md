# std::list<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>>::~list<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>>(void)

- ea: `0x1400112f4`
- end: `0x140011367`
- name: `??1?$list@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@2@@std@@QEAA@XZ`
- size: `115`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400109e4`
- `0x140010a04`
- `0x140010d8c`
- `0x140014f4e`
- `0x140015a18`

## callees

- `0x1400112f4`
- `0x14001382c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140011328`
- `KERNEL32!CloseHandle` at `0x140011328`

## pseudocode

```c
void __fastcall std::list<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>::~list<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>(
        void **a1)
{
  _QWORD **v1; // rdx
  _QWORD *v3; // rbx
  void *v4; // rcx
  _QWORD *v5; // rsi

  v1 = (_QWORD **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = *v1;
  if ( *v1 )
  {
    do
    {
      v4 = (void *)v3[6];
      v5 = (_QWORD *)*v3;
      if ( v4 )
      {
        CloseHandle(v4);
        v3[6] = 0;
      }
      operator delete(v3);
      v3 = v5;
    }
    while ( v5 );
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x1400112f4  mov     [rsp+arg_8], rbx
0x1400112f9  mov     [rsp+arg_10], rsi
0x1400112fe  push    rdi
0x1400112ff  sub     rsp, 20h
0x140011303  mov     rdx, [rcx]
0x140011306  mov     rdi, rcx
0x140011309  mov     rax, [rdx+8]
0x14001130d  mov     qword ptr [rax], 0
0x140011314  mov     rbx, [rdx]
0x140011317  test    rbx, rbx
0x14001131a  jz      short loc_14001134B
0x14001131c  mov     rcx, [rbx+30h]; hObject
0x140011320  mov     rsi, [rbx]
0x140011323  test    rcx, rcx
0x140011326  jz      short loc_140011336
0x140011328  call    cs:__imp_CloseHandle
0x14001132e  mov     qword ptr [rbx+30h], 0
0x140011336  mov     edx, 40h ; '@'
0x14001133b  mov     rcx, rbx; Block
0x14001133e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011343  mov     rbx, rsi
0x140011346  test    rsi, rsi
0x140011349  jnz     short loc_14001131C
0x14001134b  mov     rcx, [rdi]; Block
0x14001134e  mov     edx, 40h ; '@'
0x140011353  mov     rbx, [rsp+28h+arg_8]
0x140011358  mov     rsi, [rsp+28h+arg_10]
0x14001135d  add     rsp, 20h
0x140011361  pop     rdi
0x140011362  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
